# 데이터 모델

## 주요 테이블

### payments
- 결제의 현재 상태를 표현

### payment_events
- 결제 상태 변경 이력
- Append-only 구조

### idempotency_keys
- 중복 요청 방지용 키 저장

---

## 설계 의도
- 상태는 payments
- 히스토리는 payment_events
- 정산과 감사는 이벤트 기준