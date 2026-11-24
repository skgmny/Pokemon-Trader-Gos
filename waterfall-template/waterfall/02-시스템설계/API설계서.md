# API 설계서

| 항목 | 내용 |
| --- | --- |
| 프로젝트 | Pokemon-Trader-Gos |
| 문서 ID | API-Pokemon-Trader-Gos-v0.1 |
| 작성일 | 2026-11-24 |
| 상태 | Phase 2 초안 · G2 미승인 |

## 1. 공통 계약

HTTPS JSON API의 기본 경로는 설계안 기준 `/api/v1`이다. 아래 목록의 경로는 이 접두사를 생략했다. 사진 등록은 multipart 요청으로 처리한다. 금액 필드는 테스트 잔액 단위의 정수이며, 화면 표기에도 테스트 잔액임을 명시한다.

- 사용자별 정보는 식별된 요청 주체의 소유권으로 제한한다. `/ops` 경로에는 별도 운영 권한이 필요하다. 실제 계정·인증 방식은 DEC-006에서 결정한다.
- 조회 응답은 자원별 데이터다. 목록은 `items`와 다음 페이지가 있는 경우 `nextCursor`를 반환한다. 오류는 `code`, 사용자용 `message`, 필요한 경우 `details`를 반환한다.
- 잔액과 상품 가격은 서버 결과를 기준으로 한다. 구매·개봉 요청의 `expectedPrice`와 서버 가격이 다르면 새 가격 확인을 요청하고 거래를 확정하지 않는다. 최초 매입·재매입은 발행된 제안 ID에 금액을 고정한다.
- 아래 목록에서 **재시도 키**가 적힌 변경 요청에는 `Idempotency-Key`를 보낸다. 동일 계정의 같은 키와 같은 요청은 기존 결과를 재사용하며, 키를 다른 요청에 사용하면 거절한다. 사용자 화면은 결과가 불명확하면 같은 키를 유지한다.

## 2. 엔드포인트

| ID | 메서드·경로 | 입력 및 결과 | 요구사항 |
| --- | --- | --- | --- |
| API-01 | `GET /intake-policy`, `POST /media` | 현재 동봉 정책의 대상 레어도 코드, 동봉 레어도 코드와 최대 장수를 조회한다. 사진 등록 성공 시 연결할 `mediaId`를 받는다. | FR-001, NFR-001 |
| API-02 | `POST /intakes`, `GET /intakes`, `GET /intakes/{intakeId}` | 신청은 카드별 이름·세트·번호·희귀도와 앞뒷면 사진 ID를 받는다. 서버가 조건을 확인해 접수 번호를 발급한다. 목록·상세는 신청과 검수 상태, 제안 및 등록된 운송장을 반환한다. 신청 생성에 재시도 키를 사용한다. | FR-001, FR-002, FR-003 |
| API-03 | `PATCH /intakes/{intakeId}/tracking` | 본인 신청에 입고 운송장을 기록한다. 적용 가능한 물류 범위는 DEC-005에 따른다. | FR-001 |
| API-04 | `GET /listings`, `GET /listings/{inventoryId}` | `q`, `rarity`, `inspectionStatus`, `cursor`를 지원한다. 상세에 실물 사진 링크, 검수 판정·사유, 상태와 판매가를 보낸다. | FR-004 |
| API-05 | `POST /listings/{inventoryId}/purchase` | 예상 차감액과 재시도 키를 받는다. 성공 시 거래 번호, 재고 번호와 변경된 테스트 잔액을 반환한다. | FR-005, NFR-002 |
| API-06 | `GET /packs`, `GET /packs/{packId}`, `POST /packs/{packId}/open` | 조회에서 `packType`, `rarityCodes`, 팩별 테스트 코인 가격 `testPrice`, 장수와 개봉 가능 상태를 반환한다. 개봉 시 예상 차감액과 재시도 키를 받는다. 성공 시 거래 번호와 배정된 실물 한 장, 변경된 잔액을 반환한다. | FR-006, NFR-002 |
| API-07 | `GET /collection`, `GET /collection/{inventoryId}` | 본인 보유 카드, 재고 번호, 검수 및 보관·배송 상태, 가능한 행동을 반환한다. | FR-007, FR-008, NFR-001 |
| API-08 | `POST /collection/{inventoryId}/shipments`, `GET /shipments`, `GET /shipments/{shipmentId}` | 보관 중인 카드에 재시도 키로 배송을 접수한다. 조회에서 출고 상태·운송장을 반환한다. 실제 배송지 데이터는 DEC-005가 확정되면 계약에 추가한다. | FR-007, NFR-001, NFR-002 |
| API-09 | `GET /me/offers`, `POST /collection/{inventoryId}/repurchase-offer`, `POST /me/offers/{offerId}/accept` | 최초 매입·재매입 제안을 조회한다. 보관 카드의 재매입가를 요청한다. 제안 수락은 재시도 키를 받고 거래 번호, 적용 금액, 잔액을 반환한다. | FR-003, FR-008, NFR-002 |
| API-10 | `GET /me/test-balance`, `GET /me/transactions`, `GET /me/transactions/by-request` | 본인의 테스트 잔액·거래 유형·금액·상태를 조회한다. 결과 확인 엔드포인트는 요청 키 헤더로 같은 계정의 처리 결과를 조회한다. | FR-009, NFR-001, NFR-002 |
| API-11 | `GET /ops/intakes`, `GET /ops/intakes/{intakeId}`, `POST /ops/intakes/{intakeId}/inspection` | 운영자가 입고 자료를 조회하고 카드별 판정·사유·실물 상태, 확인 사진 ID와 가격 예외를 입력한다. 검수 후 조건과 제안·보류 결과를 반환한다. | FR-002, FR-003, FR-010, NFR-001 |
| API-12 | `GET /ops/inventory/{inventoryId}`, `PUT /ops/inventory/{inventoryId}/allocation` | 실물 이력을 조회하고 개별 판매가 또는 팩 ID로 판매처를 배정한다. 배정할 때 판매 가능한 상태를 재확인한다. | FR-010, NFR-001, NFR-002 |
| API-13 | `GET /ops/shipments`, `PATCH /ops/shipments/{shipmentId}/dispatch` | 출고 요청 목록을 확인하고 출고 상태·운송장을 기록한다. | FR-007, FR-010, NFR-001 |
| API-14 | `GET /ops/offers`, `PUT /ops/offers/{offerId}/exception-price` | 운영자가 입고 번호 또는 재고 번호로 대상 제안을 조회하고 수락 전 예외 금액과 사유를 등록한다. 변경 시 기존 제안을 대체하는 새 ID를 발행하고 변경 전 제안의 수락을 제한한다. 예외 기준은 DEC-002에 따른다. | FR-003, FR-008, NFR-001 |

## 3. 주요 입출력과 처리 경계

- **입고와 검수** · 신청의 카드 배열 항목은 `name`, `set`, `cardNumber`, `rarity`, `frontMediaId`, `backMediaId`로 구성한다. 동봉 조건이 부족하면 서버는 요구 레어도 코드와 필요·제출 수량을 반환한다. 인쇄 레어도가 무표기이거나 미확인이면 별도 확인 상태로 처리한다. 검수 후 미달은 오류 응답으로 되돌리는 대신 보류 상태로 기록한다.
- **개별 구매·팩 개봉** · 공통 요청에 `expectedPrice`를 전송한다. 성공 응답은 `tradeId`, `status`, `inventoryId`, `chargedAmount`, `testBalance`를 포함한다. `packType`은 `MIXED_RARITY` 또는 `SINGLE_RARITY`다. 단일형의 `rarityCodes`에는 정확히 한 코드가 있으며, 혼합형의 구성 코드와 현재 개봉 가능 상태는 별도 값이다. 허용 코드 밖의 카드를 배정하지 않는다.
- **최초 매입·재매입 수락** · 클라이언트는 `offerId`를 확정한다. 서버는 제안의 수신자와 상태, 관련 입고 또는 실물 보관 상태를 재검증한다. 확정 응답은 `tradeId`, `status`, `inventoryIds`, `creditedAmount`, `testBalance`를 포함한다. 수락한 제안은 다른 요청 키로 다시 보내도 중복 적립할 수 없다.
- **시간 초과** · 요청 결과 조회에서 현재 결과를 확인한다. 기록이 아직 없으면 같은 키로 재시도할 수 있다. 서버는 재고·잔액의 변경과 성공 결과를 함께 확정한다. 재전송 응답의 잔액은 당시 확정값일 수 있으므로 최신 잔액은 별도 조회한다.

## 4. 오류와 화면 대응

| HTTP | 예시 코드 | 클라이언트 대응 |
| --- | --- | --- |
| 401 / 403 / 404 | AUTH_REQUIRED, FORBIDDEN, NOT_FOUND | 계정 확인 또는 권한 안내. 다른 사용자의 자원은 존재 여부가 드러나지 않게 처리한다. |
| 422 | INVALID_INPUT, INTAKE_RULE_UNMET | 필드나 동봉 수량을 수정할 위치를 보여준다. |
| 409 | PRICE_CHANGED, OFFER_UNAVAILABLE | 최신 가격이나 제안 상태를 불러오고, 변경된 제안은 다시 확인받는다. |
| 409 | OUT_OF_STOCK, INSUFFICIENT_BALANCE | 품절 또는 잔액 부족을 안내한다. 미배정·미차감을 보장한다. |
| 409 | INVENTORY_STATE_CONFLICT, IDEMPOTENCY_CONFLICT | 최신 카드 상태를 표시한다. 키가 충돌하면 원래 요청의 결과를 확인한다. |
| 5xx 또는 응답 없음 | 처리 결과 미확인 | 요청 키로 조회하거나 같은 요청을 재시도한다. |

API 구현과 계약 테스트는 미실행이다. 사진 형식·크기, 응답 시간 목표, 인증 방식과 실제 배송 계약은 확인 후 확정한다. [SRS](../01-요구사항분석/요구사항명세서-SRS.md) · [데이터베이스설계서](데이터베이스설계서.md) · [시스템아키텍처설계서](시스템아키텍처설계서-SAD.md)
