# Rluan-s-Payment-system

결제 승인·취소·조회 흐름과 설계 결정을 정리한 결제 시스템 아키텍처 자료입니다. 현재 저장소는 Markdown 문서, ADR과 PlantUML 다이어그램으로 구성합니다.

## 읽는 순서

1. [프로젝트 개요](payment-system-portfolio/README.md)와 [범위](payment-system-portfolio/docs/01_scope.md)
2. [품질 속성](payment-system-portfolio/docs/03_quality_attributes.md)과 [아키텍처](payment-system-portfolio/docs/04_architecture.md)
3. [도메인 모델](payment-system-portfolio/docs/05_domain_model.md)과 [핵심 흐름](payment-system-portfolio/docs/06_core_flows.md)
4. [API 계약](payment-system-portfolio/docs/07_api_contracts.md)과 [데이터 모델](payment-system-portfolio/docs/08_data_model.md)
5. [설계 결정(ADR)](payment-system-portfolio/docs/12_adr/)

## 추가 자료

- [문제와 목표](payment-system-portfolio/docs/00_overview.md) · [이해관계자](payment-system-portfolio/docs/02_stakeholders.md)
- [보안·준수 설계](payment-system-portfolio/docs/09_security_compliance.md)
- [장애 대응](payment-system-portfolio/docs/10_reliability_resilience.md) · [관측·운영 설계](payment-system-portfolio/docs/11_observability_ops.md)
- [시스템 경계](payment-system-portfolio/assets/diagrams/context.puml)
- [승인 시퀀스](payment-system-portfolio/assets/diagrams/sequence_approve.puml)
- [결제 상태](payment-system-portfolio/assets/diagrams/state_payment.puml)

## 현재 범위

실행 애플리케이션이나 실제 결제망 연동을 제공하는 저장소가 아닙니다. 문서의 MVP 범위는 설계 대상이며 구현 완료 목록과 구분합니다. 원래 프로젝트 개요의 학습·설계 참고 목적과 사용 제한은 그대로 유지합니다.
