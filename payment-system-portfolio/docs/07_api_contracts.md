# API 설계 원칙

## 공통 규칙
- 모든 요청은 Idempotency-Key 헤더를 포함
- Correlation ID를 통한 요청 추적
- 에러 코드는 안정적으로 유지

---

## 주요 API

### 결제 승인
POST /v1/payments/authorize

### 결제 취소
POST /v1/payments/{paymentId}/cancel

### 거래 조회
GET /v1/payments/{paymentId}