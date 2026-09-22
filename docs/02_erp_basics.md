# ERP Basics

## 목차

- [ERP 및 모듈 기초](#1-erp란)
- [SD 기본 개념](#8-sd---sales-and-distribution)
- [SD 조직구조 기초](#9-sd-조직구조)
- **[SD 심화 학습 — 수업자료와 머슬앤허슬 사례](#sd-deep-dive)**
- [FI·CO 및 다른 모듈](#10-fi---financial-accounting)
- [주요 ERP 용어](#24-주요-용어-빠르게-찾기)

ERP 캡스톤디자인 프로젝트를 진행하면서 필요한 기본 개념과 SAP 용어를 정리한다.

> 이 문서는 ERP 및 SAP를 처음 접하는 입장에서 이해하기 쉽게 정리한 개인 학습 노트이다.

---

## 1. ERP란?

**ERP (Enterprise Resource Planning)**  
= 전사적 자원관리

기업의 여러 부서에서 따로 관리하던 정보를 하나의 시스템에서 연결하여 관리하는 것을 의미한다.

예를 들어 제조기업에는 다음과 같은 업무가 있다.

- 제품 판매
- 원재료 구매
- 재고 관리
- 생산
- 배송
- 대금 청구
- 회계 처리
- 원가 분석

ERP가 없다면 각 부서가 Excel, 전화, 메모 등으로 정보를 따로 관리할 수 있다.

ERP를 사용하면 판매, 구매, 생산, 재고, 회계 정보가 하나의 시스템에서 연결된다.

### 쉽게 이해하면

ERP가 없는 경우

```text
영업팀 Excel
생산팀 Excel
창고 Excel
구매팀 Excel
회계팀 Excel
```

각 부서가 서로 전화나 메일로 정보를 전달해야 한다.

ERP가 있는 경우

```text
               SAP ERP
                  │
        ┌─────────┼─────────┐
        │         │         │
       MM        PP        SD
        │         │         │
        └──────── FI ───────┘
                  │
                  CO
```

즉, 각 부서가 서로 완전히 따로 일하는 것이 아니라 같은 시스템 안에서 데이터를 연결하여 사용하는 것이 ERP의 핵심이다.

---

## 2. 우리 프로젝트의 SAP 모듈

우리 팀은 다음 5개 모듈을 담당한다.

| Module | Full Name | 쉽게 말하면 | 담당자 |
|---|---|---|---|
| PP | Production Planning | 생산관리 | 정유진 |
| MM | Materials Management | 구매·자재·재고관리 | 정민혁 |
| SD | Sales and Distribution | 영업·판매·출고 | 홍지민 |
| FI | Financial Accounting | 재무회계 | 황인형 |
| CO | Controlling | 관리회계·원가관리 | 장성하 (PM) |

가장 간단하게 기억하면 다음과 같다.

> **MM이 재료를 사고 → PP가 제품을 만들고 → SD가 제품을 팔고 → FI가 돈을 기록하고 → CO가 원가와 수익성을 분석한다.**

---

## 3. MM - Materials Management

### 정의

**MM (Materials Management)**  
= 자재관리

회사가 제품 생산에 필요한 자재를 구매하고, 입고하고, 재고로 관리하는 영역이다.

쉽게 말하면 다음 질문을 담당한다.

> "우리 회사에 제품을 만들 재료가 충분한가?"  
> "부족하면 어디에서 얼마나 구매해야 하는가?"

### MM에서 하는 일

```text
원재료 필요
↓
구매 요청
↓
공급업체에 주문
↓
자재 입고
↓
재고 증가
↓
공급업체 인보이스 확인
↓
FI와 연계하여 대금 처리
```

### Vendor

**Vendor = 공급업체**

우리 회사에 원재료나 상품을 판매하는 회사이다.

예를 들어 키링 제조기업이라면 다음과 같이 설정할 수 있다.

```text
Vendor A → 키캡 공급
Vendor B → 스위치 공급
Vendor C → 금속 링 공급
Vendor D → 포장재 공급
```

### Purchase Requisition (PR)

**Purchase Requisition = 구매요청**

회사 내부에서 자재가 필요하다고 요청하는 단계이다.

쉽게 말하면

> "키캡이 부족하니까 100개 구매해야 합니다."

라고 구매 필요성을 등록하는 것이다.

### Purchase Order (PO)

**Purchase Order = 구매오더 / 구매주문**

실제로 Vendor에게 자재를 주문하는 문서이다.

예:

```text
Mechanical Switch 100 EA 주문
Metal Ring 100 EA 주문
```

### Goods Receipt (GR)

**Goods Receipt = 입고**

Vendor에게 구매한 자재가 실제 회사에 도착한 것을 SAP에 기록하는 것이다.

예:

```text
Mechanical Switch 100개 주문
↓
Vendor 배송
↓
창고 도착
↓
Goods Receipt
↓
SAP 재고 +100
```

---

## 4. PP - Production Planning

### 정의

**PP (Production Planning)**  
= 생산계획 / 생산관리

원재료를 이용하여 제품을 어떻게, 얼마나 생산할지를 관리하는 영역이다.

쉽게 말하면 다음 질문을 담당한다.

> "제품 100개를 만들려면 무엇이 얼마나 필요한가?"  
> "어떤 순서로 제품을 만들어야 하는가?"

### PP에서 하는 일

```text
생산할 제품 결정
↓
필요한 자재 확인
↓
생산 수량 결정
↓
생산 작업 수행
↓
완제품 생산
↓
완제품 재고 증가
```

PP에서는 BOM, Work Center, Routing 등의 개념이 중요하다.

---

## 5. BOM - Bill of Materials

### 정의

**BOM (Bill of Materials)**  
= 자재명세서

제품 하나를 만들기 위해 필요한 재료와 수량을 정리한 것이다.

쉽게 말하면

> **제품의 레시피**

라고 생각하면 된다.

### 예시

키캡 키링 1개를 만든다고 가정한다.

| Material | Quantity | Unit |
|---|---:|---|
| Keycap | 1 | EA |
| Mechanical Switch | 1 | EA |
| Keyring Base | 1 | EA |
| Metal Ring | 1 | EA |
| Brand Tag | 1 | EA |
| Package | 1 | EA |

즉,

```text
키캡 1개
+
스위치 1개
+
키링 베이스 1개
+
금속 링 1개
+
브랜드 태그 1개
+
포장재 1개
=
키캡 키링 완제품 1개
```

제품 종류가 여러 개더라도 공정을 단순하게 만들고 싶다면 공통 부품은 그대로 사용하고 일부 자재만 변경하는 방식이 좋다.

예:

```text
Lucky Cat Keyring
→ Cat Keycap 사용

Cherry Keyring
→ Cherry Keycap 사용

나머지 부품과 생산공정은 동일
```

---

## 6. RM / SFG / FG

제품 생산 과정에서 자재의 상태를 구분할 때 자주 사용하는 표현이다.

### RM - Raw Material

**RM = Raw Material**  
= 원재료

제품을 만들기 위해 투입되는 재료이다.

예:

```text
키캡
스위치
금속 링
원단
솜
포장 박스
```

### SFG - Semi-Finished Goods

**SFG = Semi-Finished Goods**  
= 반제품

제품이 완전히 완성되기 전 중간 단계의 제품이다.

예를 들어 봉제 백참을 만든다면 다음과 같다.

```text
원단
↓
재단
↓
봉제된 캐릭터 몸체
↓
솜 충전
↓
키링 부착
↓
완제품
```

여기서 `봉제된 캐릭터 몸체`를 반제품으로 관리할 수 있다.

단, 모든 제품에 반드시 반제품이 필요한 것은 아니다.

프로젝트를 단순하게 구성하려면 다음과 같이 설계할 수도 있다.

```text
원재료 → 생산 → 완제품
```

### FG - Finished Goods

**FG = Finished Goods**  
= 완제품

생산이 모두 끝나 고객에게 판매할 수 있는 상태의 제품이다.

예:

```text
Lucky Cat Keyring
Cherry Keyring
Happy Bag Charm
Sleepy Bag Charm
```

---

## 7. 자재 단위

ERP에서는 자재마다 수량 단위를 설정한다.

### EA

**EA = Each**

쉽게 말하면

> **개**

라는 뜻이다.

예:

```text
Keycap       1 EA
Metal Ring   1 EA
Keyring      1 EA
```

### 기타 단위

| Unit | 의미 | 예 |
|---|---|---|
| EA | 개 | 키링 1개 |
| SET | 세트 | 부품 세트 1개 |
| KG | 킬로그램 | 원재료 10kg |
| G | 그램 | 향료 30g |
| L | 리터 | 액체 원료 5L |
| M | 미터 | 원단 10m |

프로젝트 난이도를 낮추려면 가능하면 `EA` 중심의 제품이 편하다.

식품처럼 `g`, `kg`, `L` 등이 함께 사용되면 자재 단위와 BOM 관리가 상대적으로 복잡해질 수 있다.

---

## 8. SD - Sales and Distribution

### 정의

**SD (Sales and Distribution)**  
= 영업 및 판매관리

고객이 제품을 주문한 순간부터 제품을 출고하고 대금을 청구하기까지의 과정을 관리한다.

쉽게 말하면

> **고객에게 제품을 판매하는 과정**

을 담당한다.

### 기본 흐름

```text
Customer
↓
Sales Order
↓
재고 확인
↓
Delivery
↓
Picking
↓
Packing
↓
Goods Issue
↓
Billing
↓
FI 연계
```

### Sales Order

**Sales Order = 판매 주문 / 수주**

고객이 제품을 구매하겠다고 주문했을 때 생성하는 문서이다.

예:

```text
고객: 성수동 소품샵

Lucky Cat Keyring 100 EA
Cherry Keyring    100 EA
```

이 주문을 SAP에 등록한다.

### Availability Check

**Availability Check = 재고 가용성 확인**

고객이 주문한 수량만큼 실제 판매 가능한 재고가 있는지 확인하는 과정이다.

예:

```text
고객 주문
Cherry Keyring 100개

현재 재고
Cherry Keyring 40개

→ 60개 부족
```

이 경우 부족한 60개를 추가 생산해야 할 수 있다.

### Delivery

**Delivery = 납품 / 출하 준비**

판매 주문을 기반으로 고객에게 제품을 보내기 위한 배송 문서를 생성하는 단계이다.

### Picking

**Picking = 피킹**

창고에서 고객에게 보낼 제품을 실제로 꺼내는 작업이다.

예:

```text
Lucky Cat Keyring 재고 500개
↓
고객 주문 100개
↓
100개 Picking
```

### Packing

**Packing = 포장**

Picking한 제품을 배송할 수 있도록 포장하는 작업이다.

### Goods Issue

**Goods Issue = 출고**

제품이 실제 우리 회사의 재고에서 빠져나간 것을 시스템에 기록하는 것이다.

예:

```text
기존 재고 500개
↓
100개 출고
↓
남은 재고 400개
```

### Billing

**Billing = 청구**

제품을 판매한 뒤 고객에게 판매대금을 청구하는 과정이다.

Billing 이후에는 FI와 연결되어 회계 기록이 만들어질 수 있다.

---

## 9. SD 조직구조

SD에서는 판매활동을 조직 단위로 설정한다.

대표적으로 다음 개념이 중요하다.

```text
Sales Organization
Distribution Channel
Division
Sales Area
Shipping Point
```

### Sales Organization

**Sales Organization = 판매조직**

기업에서 판매 활동을 담당하는 조직 단위이다.

쉽게 말하면

> "어느 영업조직이 이 판매를 담당하는가?"

를 나타낸다.

예:

```text
KR01 = 국내 영업조직
```

### Distribution Channel

**Distribution Channel = 유통경로 / 판매채널**

제품이 어떤 경로를 통해 고객에게 판매되는지를 나타낸다.

예:

```text
Online
Wholesale
Offline Store
```

프로젝트에서는 너무 많은 채널을 만들기보다 2개 정도로 단순하게 구성하는 것이 좋다.

예:

```text
10 = Online
20 = Wholesale
```

### Division

**Division = 제품군**

판매하는 제품을 제품 그룹 또는 제품 라인별로 구분하는 조직 단위이다.

예:

```text
Keyring
Bag Charm
Stationery
```

또는

```text
Basic
Premium
```

등으로 구분할 수 있다.

### Sales Area

다음 세 가지의 조합을 **Sales Area**라고 한다.

```text
Sales Organization
+
Distribution Channel
+
Division
=
Sales Area
```

예:

```text
KR01
+
Online
+
Keyring
=
하나의 Sales Area
```

### Shipping Point

**Shipping Point = 출하 지점**

제품의 Delivery와 Goods Issue를 처리하는 조직 단위이다.

쉽게 말하면

> "제품을 어느 곳에서 고객에게 출고하는가?"

를 나타낸다.

---

## 10. FI - Financial Accounting

### 정의

**FI (Financial Accounting)**  
= 재무회계

기업에서 발생한 거래를 회계 관점에서 공식적으로 기록하는 영역이다.

쉽게 말하면

> **회사 돈이 들어오고 나가는 것을 장부에 기록하는 역할**

이다.

### 원재료를 구매했을 때

```text
MM에서 원재료 구매
↓
Vendor에게 지급해야 할 돈 발생
↓
FI에 회계 기록
```

### 제품을 판매했을 때

```text
SD에서 제품 판매
↓
Customer에게 받을 돈 발생
↓
FI에 회계 기록
```

### A/P - Accounts Payable

**A/P = Accounts Payable**  
= 매입채무

Vendor에게 지급해야 하는 돈이다.

쉽게 말하면

> **우리가 줄 돈**

이다.

### A/R - Accounts Receivable

**A/R = Accounts Receivable**  
= 매출채권

Customer에게 받아야 하는 돈이다.

쉽게 말하면

> **우리가 받을 돈**

이다.

### 쉽게 비교하면

| 구분 | 의미 |
|---|---|
| A/P | 공급업체에게 줄 돈 |
| A/R | 고객에게 받을 돈 |

---

## 11. CO - Controlling

### 정의

**CO (Controlling)**  
= 관리회계

기업 내부에서 원가와 수익성을 분석하기 위한 영역이다.

FI가

> "얼마가 들어오고 얼마가 나갔는가?"

를 기록한다면,

CO는

> "왜 이 비용이 발생했는가?"  
> "어떤 제품이 더 수익성이 좋은가?"

를 분석하는 역할에 가깝다.

### 예시

Lucky Cat Keyring 1개의 비용이 다음과 같다고 가정한다.

| 항목 | 비용 |
|---|---:|
| Keycap | 1,000원 |
| Switch | 1,000원 |
| Keyring Parts | 500원 |
| Package | 500원 |
| Production Cost | 1,000원 |
| **총원가** | **4,000원** |

판매가격이 12,000원이라면 CO에서는 제품의 원가와 수익성을 분석할 수 있다.

---

## 12. Plant

**Plant = 플랜트**

SAP에서 생산, 재고관리 등 물류 활동이 이루어지는 주요 조직 단위이다.

제조기업에서는 일반적으로

> **공장 또는 사업장**

과 비슷하게 이해하면 된다.

예:

```text
Company Code KR00
│
├── Seoul Plant
└── Busan Plant
```

---

## 13. Storage Location

**Storage Location = 저장 위치 / 창고**

Plant 내부에서 재고를 세부적으로 구분하여 보관하는 단위이다.

예:

```text
Seoul Plant
│
├── RM00 : Raw Material
├── SF00 : Semi-Finished Goods
├── FG00 : Finished Goods
└── MI00 : Miscellaneous
```

쉽게 기억하면 다음과 같다.

```text
Plant
= 큰 사업장 또는 공장

Storage Location
= 그 안에 있는 세부 창고
```

---

## 14. Customer

**Customer = 고객**

우리 회사의 제품을 구매하는 개인 또는 기업이다.

### B2C

**Business to Consumer**

기업이 개인 소비자에게 판매하는 방식이다.

예:

```text
자사 온라인몰에서
키링 1개를 구매하는 개인 소비자
```

### B2B

**Business to Business**

기업이 다른 기업에게 판매하는 방식이다.

예:

```text
소품샵에서
키링 200개를 대량 주문
```

ERP 프로젝트에서는 주문과 배송 프로세스를 명확하게 표현하기 위해 B2B 고객을 사용하는 것도 편리하다.

---

## 15. Material Master

**Material Master = 자재 마스터**

SAP에서 사용하는 원재료, 반제품, 완제품 등의 기본 정보를 등록한 데이터이다.

예:

```text
RM001 = Cat Keycap
RM002 = Cherry Keycap
RM003 = Mechanical Switch
RM004 = Metal Ring

FG001 = Lucky Cat Keyring
FG002 = Cherry Keyring
```

즉, SAP에서는 제품 이름만 사용하는 것이 아니라 각각의 자재를 고유한 코드와 정보로 관리한다.

---

## 16. Work Center

**Work Center = 작업장**

생산공정에서 실제 작업이 이루어지는 장소 또는 기능 단위이다.

예를 들어 키링 제조기업이라면 다음과 같이 구성할 수 있다.

```text
WC01 = Assembly
WC02 = Inspection
WC03 = Packaging
```

봉제 백참이라면 다음과 같이 구성할 수 있다.

```text
WC01 = Cutting
WC02 = Sewing
WC03 = Filling
WC04 = Inspection
WC05 = Packaging
```

---

## 17. Routing

**Routing = 생산공정 순서**

제품을 어떤 순서로 생산할지를 정의한 것이다.

키캡 키링의 예:

```text
1. 부품 준비
↓
2. Switch 조립
↓
3. Keycap 장착
↓
4. Metal Ring 결합
↓
5. 검사
↓
6. 포장
```

제품의 디자인이 달라져도 Routing을 동일하게 유지하면 생산공정을 단순하게 관리할 수 있다.

---

## 18. 모듈이 서로 연결되는 방식

ERP에서 가장 중요한 것은 각 모듈이 서로 독립적으로 존재하는 것이 아니라 연결되어 있다는 점이다.

예를 들어 고객이 제품 100개를 주문했다고 가정한다.

### Step 1. SD - 고객 주문

```text
Customer
↓
Sales Order 100 EA
```

### Step 2. SD - 재고 확인

```text
고객 주문 = 100 EA

현재 FG 재고 = 40 EA

→ 60 EA 부족
```

### Step 3. PP - 생산 필요 확인

```text
부족 수량 60 EA
↓
생산계획 수립
↓
BOM 확인
↓
필요 자재 계산
```

### Step 4. MM - 부족한 원재료 구매

원재료까지 부족하면 MM이 구매를 진행한다.

```text
Purchase Requisition
↓
Purchase Order
↓
Vendor
↓
Goods Receipt
```

### Step 5. PP - 생산

원재료가 준비되면 제품을 생산한다.

```text
RM
↓
Production
↓
FG
```

### Step 6. SD - 고객에게 출고

```text
Delivery
↓
Picking
↓
Packing
↓
Goods Issue
```

### Step 7. SD + FI - 청구 및 회계

```text
Billing
↓
FI
↓
Accounts Receivable
```

### Step 8. CO - 원가 및 수익성 분석

```text
Material Cost
+
Production Cost
+
기타 비용
↓
제품 원가 분석
↓
수익성 분석
```

---

## 19. 전체 프로세스 한 번에 보기

```text
                    [Customer]
                        │
                        │ 주문
                        ▼
                      [SD]
                Sales Order 생성
                        │
                        │ 재고 부족
                        ▼
                      [PP]
                 생산계획 수립
                        │
                        │ 자재 부족
                        ▼
                      [MM]
                  원재료 구매
                        │
                        ▼
                      [PP]
                   제품 생산
                        │
                    FG 생성
                        │
                        ▼
                      [SD]
               Delivery / 출고
                        │
                        ▼
                   [Customer]
                        │
                     Billing
                        ▼
                      [FI]
                   회계 처리
                        │
                        ▼
                      [CO]
                 원가·수익 분석
```

한 문장으로 요약하면 다음과 같다.

> **판매 수요가 발생하면 SD가 주문을 받고, PP가 생산하고, 필요한 원재료가 부족하면 MM이 구매하며, 완성된 제품을 SD가 출고·청구하고, FI와 CO가 관련 금액을 관리한다.**

---

## 20. AS-IS / TO-BE

ERP 프로젝트에서 매우 중요한 개념이다.

### AS-IS

**AS-IS = 현재 업무 방식**

ERP를 도입하기 전 기업이 현재 어떻게 업무를 처리하고 있는지를 의미한다.

예:

```text
주문을 Excel로 관리
재고를 수기로 관리
영업팀과 생산팀이 전화로 소통
구매오더를 메모로 전달
회계팀이 가격 정보를 전화로 확인
```

### TO-BE

**TO-BE = 개선된 미래 업무 방식**

ERP를 구축한 후 업무를 어떻게 개선할 것인지를 의미한다.

예:

```text
주문 정보를 SAP에서 통합 관리
재고를 실시간으로 확인
판매 수요를 생산계획과 연결
구매·입고 데이터를 회계와 연결
제품별 원가와 수익성을 분석
```

즉,

```text
AS-IS
현재 문제 있는 업무 방식

↓

ERP 구축

↓

TO-BE
개선된 업무 방식
```

이라고 생각하면 된다.

---

## 21. 현재 수업의 시나리오에서 파악한 AS-IS 문제

### 1. 구매·입고·반품 프로세스의 비통합 관리

전화, 메모, 개별 파일로 주문과 반품을 처리하고 있다.

문제:

- 구매오더 누락
- 반품 자재 추적 어려움
- 긴급 구매 발생
- 중복 입고 가능성

### 2. 생산계획·재고·판매 수요 간 연계 부족

판매 수요와 생산계획, 재고 데이터가 서로 제대로 연결되지 않는다.

문제:

- 자재 부족을 미리 확인하지 못함
- 추가 수요가 생산계획에 늦게 반영됨
- 생산 지연
- 고객 납기 지연

### 3. 수작업 정보 전달에 따른 오류

가격이나 수량 등의 정보를 전화와 메모로 전달한다.

문제:

- 잘못된 제품 가격 전달
- 데이터 입력 오류
- Human Error 증가

### 4. 회계 전표 관리 및 내부 통제 부족

인보이스 번호와 승인 절차가 시스템에서 충분히 관리되지 않는다.

문제:

- 특정 인보이스 조회의 어려움
- 중복 또는 잘못된 문서 처리 가능
- 관리자 승인 규정 미준수 가능

---

## 22. ERP 도입 후 기대하는 TO-BE

ERP를 구축하면 다음과 같은 개선이 가능하다.

### 구매 및 재고

```text
AS-IS
전화 / 메모 / Excel

↓

TO-BE
SAP를 통한 구매오더 및 재고 통합관리
```

### 생산

```text
AS-IS
실제 재고와 판매수요를 제대로 확인하지 못하고 생산계획 수립

↓

TO-BE
재고와 판매수요를 연결하여 생산계획 수립
```

### 판매

```text
AS-IS
주문 상태와 재고를 실시간으로 확인하기 어려움

↓

TO-BE
Sales Order부터 Delivery까지 SAP에서 통합관리
```

### 회계

```text
AS-IS
수기로 가격 및 인보이스 정보 확인

↓

TO-BE
구매 및 판매 데이터를 FI와 자동 연계
```

### 관리회계

```text
AS-IS
제품별 실제 원가 및 수익성 확인 어려움

↓

TO-BE
제품별 원가와 수익성 분석
```

---

## 23. 산업 선정 시 고려해야 할 사항

ERP 프로젝트에서 고객사 산업을 선정할 때 다음 조건을 고려한다.

### BOM이 너무 복잡하지 않을 것

제품 하나에 수십~수백 개의 자재가 들어가면 프로젝트 난이도가 높아질 수 있다.

### 제품이 달라져도 생산공정을 재사용할 수 있을 것

예:

```text
Happy Bag Charm
Sleepy Bag Charm
Grumpy Bag Charm

→ 디자인만 다름
→ 기본 생산공정은 동일
```

이런 구조가 프로젝트에 적합하다.

### 원재료 단위가 단순할 것

가능하면 다음과 같이 `EA` 중심이면 관리하기 쉽다.

```text
부품 1 EA
금속 링 1 EA
포장재 1 EA
```

### PP를 구성할 수 있을 것

단순히 완제품을 구매하여 재판매하는 회사보다는 어느 정도 생산공정이 존재하는 제조업이 적합하다.

### MM을 구성할 수 있을 것

제품을 생산하기 위한 원재료와 공급업체가 존재해야 한다.

### SD를 구성할 수 있을 것

고객, 판매채널, 주문, 배송 등의 판매 프로세스를 구성할 수 있어야 한다.

### FI를 연결할 수 있을 것

원재료 구매와 제품 판매에 따른 회계 거래가 발생해야 한다.

### CO를 구성할 수 있을 것

제품별 원가 또는 수익성을 비교할 수 있어야 한다.

---

## 24. 주요 용어 빠르게 찾기

| 용어 | Full Name | 쉽게 말하면 |
|---|---|---|
| ERP | Enterprise Resource Planning | 회사 전체 업무를 연결하는 시스템 |
| SAP S/4HANA | SAP S/4HANA | 이번 프로젝트에서 사용하는 ERP 시스템 |
| BOM | Bill of Materials | 제품의 재료 목록 |
| RM | Raw Material | 원재료 |
| SFG | Semi-Finished Goods | 반제품 |
| FG | Finished Goods | 완제품 |
| EA | Each | 개 |
| Vendor | Vendor | 공급업체 |
| Customer | Customer | 고객 |
| Plant | Plant | 공장 / 사업장 |
| Storage Location | Storage Location | Plant 내부의 세부 창고 |
| Material Master | Material Master | 자재 기본정보 |
| Work Center | Work Center | 생산 작업장 |
| Routing | Routing | 생산공정 순서 |
| PR | Purchase Requisition | 구매요청 |
| PO | Purchase Order | 구매주문 |
| GR | Goods Receipt | 입고 |
| GI | Goods Issue | 출고 |
| PP | Production Planning | 생산관리 |
| MM | Materials Management | 구매·자재·재고관리 |
| SD | Sales and Distribution | 판매·출고관리 |
| FI | Financial Accounting | 재무회계 |
| CO | Controlling | 관리회계 |
| Sales Order | Sales Order | 고객 주문 |
| Delivery | Delivery | 배송 / 출하 준비 |
| Picking | Picking | 창고에서 제품 꺼내기 |
| Packing | Packing | 제품 포장 |
| Billing | Billing | 고객에게 대금 청구 |
| A/P | Accounts Payable | 우리가 공급업체에게 줄 돈 |
| A/R | Accounts Receivable | 고객에게 받을 돈 |
| Sales Organization | Sales Organization | 판매 담당 조직 |
| Distribution Channel | Distribution Channel | 판매채널 |
| Division | Division | 제품군 |
| Sales Area | Sales Area | Sales Org + Distribution Channel + Division |
| Shipping Point | Shipping Point | 제품 출하 지점 |
| AS-IS | As-Is | 현재 업무 방식 |
| TO-BE | To-Be | ERP 도입 후 개선 업무 방식 |

---

## 25. 가장 중요하게 기억할 내용

### 각 모듈 역할

```text
MM
재료를 구매하고 재고를 관리한다.

↓

PP
재료를 사용하여 제품을 생산한다.

↓

SD
완제품을 고객에게 판매하고 출고한다.

↓

FI
구매와 판매에서 발생한 돈을 회계에 기록한다.

↓

CO
제품의 원가와 수익성을 분석한다.
```

### 핵심 문장

> **MM이 재료를 사고, PP가 제품을 만들고, SD가 고객에게 판매하고, FI가 거래를 회계에 기록하며, CO가 원가와 수익성을 분석한다.**

이 다섯 모듈이 하나의 업무 흐름으로 연결되는 것이 ERP 프로젝트의 핵심이다.

---

<a id="sd-deep-dive"></a>
## 26. SD 심화 학습 — 수업자료와 머슬앤허슬 사례

> 수업자료에 나온 **개념과 GBI 실습 사례**를 먼저 설명하고, 머슬앤허슬의 단백질바에 적용하는 내용은 **프로젝트 적용 예시**로 구분한다. 아래 조직코드·가격·고객은 아직 SAP에 등록된 확정값이 아니다.
>
> 참조: 「SD 강의노트_250508_173609.pdf」, 「L04_SD 모듈 컨피규레이션_260915_175509.pdf」(필기 포함), 「SD_Configuration_실습과제.pdf」. 각 소제목의 끝에는 해당 자료의 페이지를 적었다.

### 26-1. SD가 담당하는 범위

**SD(Sales and Distribution) = 영업·판매 및 출하 관리.** 고객이 주문한 제품이 무엇인지, 언제 얼마나 보낼 수 있는지, 어느 창고에서 출고하고 얼마를 청구할지 관리한다.

강의노트에서는 SD의 기능을 판매(Sales), 출하·운송(Shipping and Transportation), 청구(Billing), 신용관리(Credit Management), 해외무역(Foreign Trade)로 소개한다. 이번 프로젝트는 우선 **국내 도매 고객의 단백질바 수주·출고·청구**를 중심으로 설계한다.

**Order-to-Cash(O2C, 주문부터 수금까지)** 또는 **Fulfillment(고객 주문 이행)**은 고객의 주문을 실제 납품과 대금 수금까지 연결하는 업무다.

    문의(선택) → 견적(선택) → 고객 발주 → 판매오더
       → 납품·출고 → 청구 → 수금

**자료:** 「SD 강의노트」 p.2~4, 23; 「L04_SD 모듈 컨피규레이션_260915_175509」 p.2~3.

### 26-2. 주문에서 수금까지: 단계별로 정확히 구분하기

| 단계 | 영어 / 한국어 | 쉽게 설명하면 | 머슬앤허슬 예시 |
|---|---|---|---|
| 사전 영업 | Inquiry / 문의 | 고객이 재고·가격·납품일을 물어봄. 주문 확정은 아님 | 도매 고객이 카카오바 100개 가격 문의 |
| 사전 영업 | Quotation / 견적 | 정해진 조건으로 판매할 수 있다고 제안 | 가격·유효기간을 기재한 견적 전달 |
| 1 | Sales Order / 판매오더(수주) | 확정 주문을 SAP에 등록 | 카카오바 100 EA, 고객·납품일·가격 입력 |
| 2 | Availability Check / 가용성 점검 | 그 날짜에 약속한 수량을 공급할 수 있는지 확인 | 가용재고와 출고예정·입고예정 확인 |
| 3 | Outbound Delivery / 납품문서 | 물류팀이 출고를 준비할 문서 생성 | 카카오바 100개 납품 지시 |
| 4 | Picking / 피킹 | 창고에서 주문수량만큼 제품을 꺼냄 | 완제품 창고에서 카카오바 100개 집기 |
| 5 | Packing / 포장 | 배송에 맞게 묶고 포장 | 개별 포장된 바를 운송박스에 담기 |
| 6 | Post Goods Issue(PGI) / 출고전기 | 실제 출고를 SAP에 기록하여 재고·회계에 반영 | 완제품 재고에서 출고수량 차감 |
| 7 | Billing / 청구 | 고객에게 받을 판매대금을 청구 | 고객 송장 발행·FI 연계 |
| 8 | Payment / 수금 | 실제 대금 입금을 회계에서 처리 | FI가 입금과 매출채권 정리 |

**혼동하기 쉬운 부분:** 판매오더는 주문 문서이고, 납품문서는 출고 준비 문서다. **납품문서 생성만으로 실제 재고가 차감된다고 생각하지 않는다.** 출고전기(PGI)와 구분한다. 또한 **Billing은 받을 돈을 청구하는 것, Payment는 실제 돈을 받는 것**이다.

**생산 포장 vs 배송 포장:** PP가 맛별 인쇄필름으로 단백질바를 1개씩 포장하는 제조공정과, SD 출하 때 개별 포장된 완제품을 운송박스에 담는 작업은 다른 단계다.

**자료:** 「SD 강의노트」 p.23, 26~30, 39~53.

### 26-3. 판매오더 내부의 세 부분

| 구분 | 의미 | 예 |
|---|---|---|
| Header(헤더) | 주문서 전체에 공통인 정보 | 고객, 주문일, 판매영역 |
| Item(항목) | 주문서 안의 제품별 주문 내용 | 10번 카카오바 100 EA, 20번 모카바 50 EA |
| Schedule Line(일정 라인) | 한 항목을 언제 몇 개 납품하는지 | 카카오바 60개는 첫 날짜, 40개는 다음 날짜 |

따라서 같은 고객에게서 한 번에 주문을 받아도 **제품마다 수량과 납품일이 다를 수 있다.** 판매오더에는 고객·자재·수량·가격조건·납품일·출하 및 청구정보 등이 필요하다.

**자료:** 「SD 강의노트」 p.28~30.

### 26-4. SD 조직구조는 실제 회사의 무엇을 나타낼까?

SAP의 조직구조는 '누가, 어떤 방식으로, 어떤 제품군을 팔고, 어디에서 출고하는지'를 구분하는 설정이다. 비슷해 보이는 용어라도 서로 다르다.

| 용어 | 쉽게 말하면 | 우리 회사 적용 예시 |
|---|---|---|
| Client(클라이언트) | SAP의 독립적인 데이터 환경 | 수업에서 배정된 실습 환경 |
| Company Code(회사코드) | 회계장부를 관리하는 법인 단위 | 머슬앤허슬 국내 법인 |
| Sales Organization(영업조직) | 판매를 담당하고 책임지는 조직 | 국내영업 |
| Distribution Channel(유통경로) | 고객에게 판매하는 경로 | 도매, 온라인(추가 여부 논의) |
| Division(제품군) | 비슷한 상품·서비스를 묶는 단위 | 단백질바 |
| Sales Area(판매영역) | **영업조직 + 유통경로 + 제품군** | 국내영업 + 도매 + 단백질바 |
| Distribution Chain(유통체인) | **영업조직 + 유통경로** | 국내영업 + 도매 |
| Plant(플랜트) | 생산·재고·출고의 기준 사업장 | 단백질바 생산공장 |
| Storage Location(저장위치) | 플랜트 안의 세부 재고 관리 구분 | 완제품 저장위치 |
| Shipping Point(출하지점) | 납품문서·출하를 처리하는 출하 장소/조직 | 공장 출하장 |
| Credit Control Area(신용관리영역) | 고객 신용한도를 관리하는 조직 | FI 및 실습 환경에 맞춰 검토 |

**핵심 관계**

    머슬앤허슬 회사코드
      └─ 국내 영업조직
          ├─ 도매 유통경로
          │    └─ 단백질바 제품군 → 판매영역 1
          └─ 온라인 유통경로(선택)
               └─ 단백질바 제품군 → 판매영역 2

    국내영업 + 도매 = 유통체인
      → 단백질바 공장을 출고 플랜트로 연결

    단백질바 공장(Plant)
      → 완제품 저장위치 + 출하지점

**특히 중요:** Sales Area에는 세 요소, Distribution Chain에는 두 요소가 들어간다. **카카오·모카·솔티드 캐러멜은 서로 다른 완제품 자재코드**이며 꼭 서로 다른 Division으로 만들어야 하는 것은 아니다.

**코드 예시는 확정된 설정이 아님:** 회사코드 MH01 / 공장 MH10 / 영업조직 MH30 / 도매채널 10 / 제품군 01 / 출하지점 MH40. SAP 실습 시스템에서 기존 값·코드 길이·권한을 확인하고 팀이 최종 결정한다.

**자료:** 「SD 강의노트」 p.5~12; 「L04_SD 모듈 컨피규레이션_260915_175509」 p.5~18; 「SD_Configuration_실습과제」 p.9~36.

### 26-5. Configuration, Master Data, Transaction Data 구분

| 종류 | 뜻 | 실제 예 |
|---|---|---|
| **Configuration(설정)** | 회사의 조직과 업무 처리 규칙을 미리 정함 | 영업조직을 회사코드에 연결, 도매채널 구성 |
| **Master Data(마스터데이터)** | 매번 거래할 때 재사용하는 기본정보 | 고객 주소, 완제품 판매정보, 판매가격 조건 |
| **Transaction Data(거래데이터)** | 특정 시점에 실제 발생한 주문·출고·청구 기록 | A 유통사의 카카오바 100 EA 판매오더 |

**실습 순서:** 조직구조(Enterprise Structure) → 업무 규칙 설정(Process Configuration) → 기본정보 등록(Master Data) → 거래 실행 테스트(Process Execution).

실습서의 **SPRO / SAP Reference IMG**는 조직과 업무 규칙을 설정하는 메뉴다. **SAP Easy Access**는 마스터·거래 데이터 생성·조회에 쓰이는 메뉴로 설명된다. GBI 실습서의 숫자 표기 ##는 각 학생에게 배정된 식별번호이므로 **GBI용 코드·주소·통화·가격을 우리 팀 설정으로 그대로 복사하지 않는다.**

**자료:** 「SD_Configuration_실습과제」 p.2~8.

### 26-6. SD를 시작하기 전에 준비할 기본정보 세 가지

**① Customer Master(고객 마스터): 누가 주문하고, 어디로 받고, 누가 청구·지급하는가?**

고객 데이터는 일반 데이터(고객명·주소·연락처), 회사코드 데이터(회계 관련 정보), 판매영역 데이터(판매·납품·청구 조건)로 구분된다.

| Partner Function(고객 역할) | 무슨 뜻? | 도매거래 예시 |
|---|---|---|
| Sold-to Party | 제품을 주문하는 판매처 | 유통사 본사 |
| Ship-to Party | 실제 제품을 받는 납품처 | 유통사 물류센터 |
| Bill-to Party | 청구서를 받는 청구처 | 유통사 정산부서 |
| Payer | 실제 돈을 지급하는 지급처 | 유통사 본사 |

한 업체가 여러 역할을 동시에 가질 수도 있다. **판매영역이 바뀌면 그 영역의 고객 판매 데이터가 있는지**도 확인한다.

**② Material Master(자재 마스터): 무엇을 어떤 조건으로 팔 수 있는가?**

MM·PP가 카카오바를 완제품으로 등록하고 재고를 만들었다고 해서 **해당 영업조직·유통경로에 필요한 판매 데이터가 모두 자동으로 갖춰지는 것은 아니다.** SD는 제품의 판매영역, 단위, 출고 플랜트 등 판매 관련 정보와 가용성 점검그룹·상차그룹 같은 출하 관련 정보를 확인한다.

**③ Sales Condition(가격조건): 얼마에 파는가?**

제품 제조원가(BOM·생산비)와 판매가격은 다르다. SD에는 기본 판매가격, 할인, 운송비, 세금 등 조건 마스터가 사용될 수 있다. 첫 번째 테스트에서는 **카카오바를 어느 판매영역에서 얼마에 판매할지** 담당자와 합의하고 가격 데이터가 실제 등록되어 있는지 확인한다.

**자료:** 「SD 강의노트」 p.13~21; 「L04_SD 모듈 컨피규레이션_260915_175509」 p.57~67.

### 26-7. SD Configuration의 주요 네 가지 규칙

**① Shipping Point Determination(출하지점 결정)**

출하지점은 일반적으로 아래 조합으로 결정하도록 설정한다.

    Shipping Condition(배송조건: 일반/긴급 등)
      + Loading Group(상차그룹: 물품을 싣는 방식)
      + Delivering Plant(출고 플랜트)
      → Shipping Point(출하지점)

배송조건은 고객·판매오더와, 상차그룹은 자재마스터와 관련된다. **일반배송 + 단백질바의 상차그룹 + 생산공장 → 공장 출하지점**처럼 팀의 실제 설정값을 정해야 한다.

**② Pricing(가격결정)**

| 용어 | 뜻 | 쉽게 기억하면 |
|---|---|---|
| Condition Type(조건유형) | 가격·할인·운송비·세금 등의 **금액 종류** | 무엇의 금액인가? |
| Condition Record(조건레코드) | 특정 조건에 등록된 **실제 값** | 실제 얼마인가? |
| Condition Table(조건테이블) | 어떤 기준 조합으로 값을 찾는지 | 어떤 고객·자재·조직 조건인가? |
| Access Sequence(접근순서) | 조건레코드를 조회하는 우선순위 | 어디부터 찾아볼까? |
| Pricing Procedure(가격결정절차) | 여러 가격 요소의 계산 순서 | 기본가격·할인·세금 등을 어떻게 적용할까? |

강의자료의 PR00(기본가격), KF00(운송비), 조건테이블 004/033은 **강의의 GBI 설명 예시**다. 실제 수업 시스템에 준비된 조건유형·절차가 무엇인지는 확인해야 한다.

**③ Availability Check / ATP(가용성 점검)**

'현재 창고에 몇 개 있는가?'뿐 아니라 **고객이 요청한 날짜에 몇 개를 공급할 수 있는가?**를 확인한다. 재고상태, 예정 입고·출고, 보충 소요시간 등이 설정에 따라 영향을 준다.

- Checking Rule: 판매오더·출고 등 어느 단계에서 점검하는지.
- Checking Group: 자재마스터에 지정된 점검 방식(강의의 일별/개별 요구량 예시).
- Scope of Check: 어떤 재고·입출고 정보를 포함할지.

**예:** 모카바 주문 100 EA, 즉시 가용한 재고 40 EA라면 전량 당일 출고는 어려울 수 있다. 추가 60개를 언제 공급할 수 있는지는 생산·입고예정과 점검 설정을 봐야 한다. **부족분 60개를 SAP가 자동 생산한다고 단정하지 않는다.**

**④ Automatic Account Determination(자동 계정결정): SD와 FI 연결**

| 단계 | 일반적인 회계 효과(세금 등 생략) |
|---|---|
| 주문 생성·피킹 | 이것만으로 매출·매출원가 전표가 반드시 발생하는 단계는 아님 |
| PGI(출고전기) | 차변: 매출원가 / 대변: 재고 |
| Billing(청구) | 차변: 매출채권 / 대변: 매출 |
| Payment(수금) | 차변: 은행 등 / 대변: 매출채권 |

**출고 = 재고와 매출원가에 영향, 청구 = 매출·매출채권에 영향, 수금 = 현금성 자산과 채권에 영향.** 실제 전기는 FI 계정·세금·SAP 설정에 따라 달라지므로 팀에서 확인한다.

**자료:** 「L04_SD 모듈 컨피규레이션_260915_175509」 p.20~55; 「SD 강의노트」 p.35~38, 44~51.

### 26-8. 납품일·부분납품·문서흐름

- **Delivery Scheduling(납품일정):** 고객 요청일을 기준으로 피킹·포장·상차·운송 시간을 계산. Backward Scheduling은 요청일에서 거꾸로 준비일을 잡고, Forward Scheduling은 그 날짜를 맞출 수 없을 때 가능한 일정을 앞으로 계산하는 방식.
- **Partial Delivery(부분납품):** 100 EA 중 60 EA와 40 EA를 서로 다른 날짜에 보내는 방식. 고객·납품조건과 설정에 따른다.
- **Returns(반품):** 강의자료에 정상 출하와 별도로 반품용 출하지점 결정 예시가 있다. 반품 시나리오는 첫 기본 출고 테스트 이후 범위 검토.
- **Document Flow(문서흐름):** 한 판매오더에 연결된 납품·출고·청구 문서를 확인해 어디까지 처리됐는지 추적할 수 있다.

**자료:** 「SD 강의노트」 p.31~35, 39~43, 52~53; 「L04_SD 모듈 컨피규레이션_260915_175509」 p.24~25.

### 26-9. 머슬앤허슬 SD 실습 준비 순서

| 순서 | SD에서 준비·확인할 것 | 다른 모듈과 연결 |
|---|---|---|
| 1. 조직 | 회사코드·영업조직 관계, 도매 채널, 단백질바 제품군, 판매영역, 플랜트·출하지점 | FI 회사코드, MM·PP 플랜트 |
| 2. 규칙 | 출하조건·출하지점, 가격결정, 가용성 점검, 청구·계정 연결 | MM 재고, FI 계정 |
| 3. 마스터 | 고객마스터, 완제품 판매정보, 가격조건 | MM 자재마스터, FI 고객 회계정보 |
| 4. 거래 테스트 | 카카오바 100 EA 수주 → 가용성 → 납품문서 → 피킹·포장 → PGI → 청구 → 문서흐름 | PP 생산·MM 완제품 재고, FI 청구·수금 |

**팀에서 먼저 정할 사항:** 완제품 3종 자재코드·EA 단위, 고객과 실제 배송지, 판매영역, 출고 플랜트·저장위치·출하지점, 가격·납품조건, 첫 테스트에 사용할 재고수량.

**테스트 제안:** (1) 먼저 **재고가 충분한 카카오바 100 EA**의 수주부터 청구까지 확인. (2) 이후 모카바 재고 부족이나 카카오 전용 필름 부족을 추가해 PP/MM과 연결. 아직 설정되지 않은 기능이 자동 실행된다고 발표하지 않는다.

**실습서 순서:** 「SD_Configuration_실습과제」 p.9~38 조직구조 → p.39~56 업무 규칙 → p.57~71 마스터데이터 → p.72~85 전체 거래 실행. 해당 실습서는 **GBI 회사의 예시**이므로 GBI 회사코드·날짜·가격 등을 머슬앤허슬 값으로 그대로 사용하지 않는다.

### 26-10. 핵심 용어 빠르게 찾기

| 용어 | 한 줄 뜻 |
|---|---|
| SD / O2C | 판매·출하·청구 / 주문부터 수금까지 |
| Sales Order | 고객 주문을 시스템에 등록한 판매오더 |
| Sales Area | 영업조직 + 유통경로 + 제품군 |
| Distribution Chain | 영업조직 + 유통경로 |
| Shipping Point | 제품 출하작업을 담당하는 지점 |
| Customer Master | 고객 주문·배송·청구·지급에 필요한 기본정보 |
| Material Sales Data | 어떤 판매영역에서 자재를 판매할지에 관한 기본정보 |
| Pricing / PR00 | 가격결정 / 강의자료의 기본가격 조건유형 예시 |
| ATP | 납기 시점에 약속 가능한 수량 확인 |
| Delivery / Picking | 납품문서 / 창고에서 제품을 꺼내는 작업 |
| Packing / PGI | 운송용 포장 / 실제 출고를 SAP에 전기 |
| Billing / Payment | 대금 청구 / 실제 수금 |
| A/R | 고객에게 받을 돈(매출채권) |
| SPRO / IMG | SAP 조직·프로세스 설정 메뉴 |
| Document Flow | 판매오더부터 납품·청구까지 문서 연결 확인 |

**정리:** SD는 **누가 어떤 단백질바를 몇 개 주문했고, 어느 날짜에 어디에서 출고하며 얼마를 청구할지**를 관리한다. 주문·출고·청구·수금은 서로 다른 단계이며 PP·MM·FI·CO와 연결된다.
