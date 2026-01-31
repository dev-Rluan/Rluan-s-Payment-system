# 도메인 모델

## 핵심 애그리게이트: Payment

Payment는 하나의 결제 트랜잭션을 대표하는 애그리게이트입니다.

### 주요 속성
- paymentId (내부 식별자)
- merchantId
- merchantOrderId
- 결제 금액 (Money)
- 결제 상태 (Status)
- 외부 승인 참조 정보
- Idempotency Key

---

## 상태 모델
Payment는 명시적인 상태 머신을 따릅니다.

- PENDING
- APPROVED
- FAILED
- CANCELED
- CANCEL_FAILED

모든 상태 전이는 **명시적인 조건과 근거**를 가져야 하며,
암묵적인 상태 변경은 허용하지 않습니다.

---

## 값 객체
- Money (amount, currency)
- PaymentMethod (type, masked info)
- AcquirerReference (승인번호 등)