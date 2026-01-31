# 10. Reliability & Resilience
# 장애 대응 및 안정성

## 외부 시스템 장애 전략
- 타임아웃 명시
- 재시도 정책 분리
- Circuit Breaker 적용 가능 구조

---

## 정합성 보장
- 외부 승인 성공 + 내부 저장 실패 시 재처리 가능 구조
- 사후 정합성 검증(Reconciliation) 고려