# Rluan’s Payment System

## 개요
**Rluan’s Payment System**은 결제 승인, 취소, 조회 흐름을 중심으로  
정확성, 정합성, 추적성, 운영 안정성을 핵심 가치로 설계한  
**결제 시스템 아키텍처 포트폴리오 프로젝트**입니다.

이 프로젝트는 새로운 기능을 많이 구현하는 것을 목표로 하지 않습니다.  
대신, **“더 나은 결제 시스템이란 무엇인가”**라는 질문에  
설계 관점에서 답하는 것을 목표로 합니다.

---

## 문제 인식
결제 시스템은 다음과 같은 구조적 위험을 항상 내포합니다.

- 외부 승인 결과와 내부 데이터 간의 불일치
- 중복 요청으로 인한 이중 승인
- 장애 발생 시 원인 추적의 어려움
- 외부 결제 시스템 장애가 내부 시스템 전체로 전파되는 문제

실무 경험을 통해 이러한 문제의 대부분은  
기술 부족이 아니라 **설계 단계에서의 경계 설정과 책임 분리가 부족하기 때문**임을 확인했습니다.

---

## 설계 목표
이 시스템은 다음 원칙을 기준으로 설계되었습니다.

1. **정확성과 정합성**
   - 결제 상태와 내부 원장은 항상 일관성을 유지해야 한다
   - 명시적인 상태 전이(State Machine) 기반 설계

2. **중복 요청에 안전한 구조**
   - 동일한 요청이 여러 번 전달되더라도 결과는 단 한 번만 반영

3. **추적 가능성**
   - 모든 거래는 시간 흐름에 따라 재구성 가능해야 한다
   - 요청–응답–상태 변경 이력의 명확한 기록

4. **외부 장애 격리**
   - VAN/카드사 장애가 내부 시스템 전체로 확산되지 않도록 설계

5. **확장 가능한 구조**
   - 결제 수단 및 외부 연동 시스템 추가 시 핵심 도메인에 영향을 최소화

---

## 범위 (MVP)
### 포함
- 결제 승인
- 결제 취소 (전체 취소)
- 거래 조회
- 정산을 위한 기초 데이터 제공

### 제외 (확장 예정)
- 부분 취소 / 부분 환불
- 부정 거래 탐지
- 멀티 PG 라우팅
- 포인트·쿠폰 복합 결제

---

## 이 프로젝트가 보여주는 것
이 포트폴리오는 단순한 예제 구현이 아니라 다음을 보여주기 위한 프로젝트입니다.

- 결제 도메인에 대한 구조적 이해
- 정상/예외 흐름을 함께 고려한 설계 능력
- 운영과 감사 관점까지 포함한 시스템 사고
- 설계 의사결정의 근거를 설명할 수 있는 역량

## ⚠️ 주의 사항

이 프로젝트는 **학습 및 설계 참고 목적**으로 제공됩니다.

본 저장소에 포함된 소스 코드, 다이어그램, 설계 패턴은
결제 시스템의 구조 및 설계 개념을 설명하기 위한 것이며,
실제 금융 거래를 처리하는 상용 결제 시스템으로 사용할 수 없습니다.

특히 다음 사항을 준수해야 합니다:

- 이 프로젝트는 실제 결제사(PG), 밴(VAN), 카드망 등과
  연동되지 않습니다.
- PCI DSS 및 실제 카드정보 처리와 관련된 법적/규제 기준을
  충족하지 않습니다.
- 이 코드를 사용하여 실제 카드정보를 처리, 저장, 전송해서는 안 됩니다.
- 이 코드를 실제 결제 환경에 배포하면 법적, 규제적,
  계약적 의무 위반이 될 수 있습니다.

본 프로젝트는 **학습 자료, 아키텍처 케이스 스터디,
개념 증명(Proof of Concept)** 용도로만 활용해 주시기 바랍니다.

## ⚠️ Disclaimer

This project is provided for **educational and architectural reference only**.

The source code, diagrams, and design patterns in this repository are
intended to illustrate concepts related to payment system design,
architecture, and best practices. This project is **not** a fully
compliant payment gateway and should **not** be used as a production
system for handling real financial transactions.

Specifically:

- This project does **not** integrate with any real payment processor,
  acquirer, or card network.
- It does **not** comply with PCI DSS, financial regulations, or
  industry certification standards required for handling cardholder data.
- No actual cardholder data should be processed, stored, or transmitted
  using this code.
- Using this code in a real payment environment may violate legal,
  regulatory, or contractual obligations.

Use this project as a learning resource, architectural case study,
or proof of concept, but **do not deploy it for live financial use.**