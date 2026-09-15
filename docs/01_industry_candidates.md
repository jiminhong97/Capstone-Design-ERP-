# Industry Candidates

ERP 캡스톤디자인 프로젝트의 고객사 산업 후보를 비교하고 선정 과정을 기록한다.

> 단순히 구현하기 쉬운 산업을 선택하기보다는 실제 제조기업으로서 타당한 생산공정을 가지면서도 SAP 프로젝트에서 지나치게 복잡하지 않은 산업을 선정하는 것을 목표로 한다.

---

## 1. 산업 선정 방향

초기에는 운동하는 소비자를 위한 맛있는 닭가슴살 제조기업을 고려하였다.

아이디어 자체는 대중적이고 명확했지만, 기존 ERP 프로젝트에서 식품·닭가슴살과 유사한 사례가 사용된 적이 있어 새로운 산업 후보를 다시 탐색하기로 하였다.

새로운 산업을 선정할 때는 다음 기준을 고려한다.

### 필수 조건

1. **실제로 존재하는 제조공정을 기반으로 할 것**
   - 단순히 완제품을 구매하여 이름만 바꾸거나 포장하는 기업은 지양한다.
   - 해당 산업의 제조기업이라고 설명할 수 있을 정도의 공정이 존재해야 한다.

2. **공정을 지나치게 단순화하지 않을 것**
   - 예를 들어 향수회사라면 완성된 향료를 구매하여 병에 담는 과정만 수행하는 식의 설정은 지양한다.
   - 반대로 실제 제조공정의 모든 화학적·기술적 세부사항까지 구현할 필요도 없다.

3. **BOM이 지나치게 복잡하지 않을 것**
   - 제품 1개에 수십~수백 개의 부품 또는 원재료가 필요한 산업은 피한다.
   - 주요 원재료 약 5~10개 수준에서 제품 구조를 설명할 수 있는 것이 이상적이다.

4. **제품 종류가 달라져도 기본 생산공정을 재사용할 수 있을 것**
   - 맛, 향, 색상 또는 일부 원재료만 변경하여 여러 완제품을 구성할 수 있는 산업을 선호한다.

5. **PP / MM / SD / FI / CO 모듈을 자연스럽게 연결할 수 있을 것**
   - 원재료 구매
   - 생산
   - 재고
   - 판매
   - 회계
   - 원가 분석
   
   전체 프로세스가 하나의 시나리오로 연결되어야 한다.

6. **특정 유행에 지나치게 의존하지 않을 것**
   - 짧게 유행하고 사라지는 제품보다는 건강, 운동, 편의성 등 지속적인 소비 수요가 있는 제품을 선호한다.

7. **팀원 모두가 이해하기 쉬운 제품일 것**
   - 남녀 또는 특정 취향에 지나치게 편향되지 않고 누구나 제품과 생산과정을 쉽게 이해할 수 있는 것이 좋다.

---

## 2. 현재 제외하거나 우선순위를 낮춘 산업

### 제외

- 커피 제조업
- 닭가슴살 제조업
- 가구 제조업
- 컴퓨터 조립·제조업
- 키캡 키링 등 단기 유행성 굿즈
- 러닝화 제조업

### 우선순위를 낮춘 산업

#### 향수

향수 자체는 제품 차별화와 SD 구성 측면에서는 흥미롭다.

하지만 실제 향수 제조를 고려하면 향료, 에탄올, 정제수 등의 배합뿐 아니라 향료 조성 및 숙성 등에 대한 이해가 필요하다.

반대로 완성된 향료 베이스를 외부에서 구매한 뒤 단순 혼합·충전만 수행하면 프로젝트는 쉬워지지만, 팀에서 생각하는 "향수 제조기업"의 정체성이 약해질 수 있다.

따라서 현재는 우선순위를 낮춘다.

---

## Table of Contents

1. [Candidate 1. 고단백 영양바 제조업](#candidate-1)
2. [Candidate 2. 고단백 스낵 / Protein Chips 제조업](#candidate-2)
3. [Candidate 3. RTD 단백질 음료 제조업](#candidate-3)
4. [Candidate 4. 반려동물 기능성 간식 제조업](#candidate-4)
5. [Candidate 5. 고체 샴푸·클렌징바 제조업](#candidate-5)
6. [Candidate 6. 홈 프래그런스 캔들 제조업](#candidate-6)

---

<a id="candidate-1"></a>
# Candidate 1. 고단백 영양바 제조업

## Concept

### 운동하는 사람뿐 아니라 누구나 맛있게 먹을 수 있는 고단백 간식

초기 닭가슴살 아이디어에서 중요하게 생각했던

> **"운동하는 사람들이 영양성분 때문에 억지로 먹는 제품이 아니라 맛 때문에도 선택할 수 있는 제품"**

이라는 방향을 유지한다.

헬스 이용자뿐만 아니라 바쁜 직장인, 학생, 간편한 아침식사를 원하는 소비자까지 고객으로 설정할 수 있다.

---

## Product Example

제품은 맛만 다르게 구성하고 기본 제품 구조와 생산공정은 동일하게 유지한다.

### FG01 - Choco Peanut Protein Bar
초콜릿과 땅콩 맛

### FG02 - Salted Caramel Protein Bar
솔티드 카라멜 맛

### FG03 - Berry Yogurt Protein Bar
베리 요거트 맛

세 제품은 기본적인 단백질바 생산공정을 공유한다.

```text
Choco Peanut
        │
Salted Caramel
        │
Berry Yogurt
        │
        ▼
동일한 기본 생산공정 사용
```

제품별로 Flavor, Topping, Coating 등 일부 원재료만 변경한다.

---

## 실제 산업과의 유사성

실제 영양바·단백질바 제조라인에서는 일반적으로 다음과 같은 공정을 사용한다.

```text
원재료 입고
↓
계량
↓
Syrup / Binder 준비
↓
원재료 혼합
↓
Extrusion 또는 Forming
↓
냉각
↓
절단
↓
Coating
↓
포장
```

실제 단백질바 전문 제조시설에서도 Mixing, Extrusion, Enrobing, Packing 등의 공정을 사용한다.

따라서 ERP 프로젝트에서는 실제 제조공정을 지나치게 단순화하지 않으면서도 주요 단계만 추려서 구현할 수 있다.

---

## Preliminary BOM

> 아래 BOM은 산업 후보 비교를 위한 개념적 BOM이다. 정확한 배합량은 산업 선정 후 결정한다.

### Common Raw Materials

| Type | Material | 예상 단위 | 설명 |
|---|---|---|---|
| RM | Protein Powder | KG | 유청 또는 식물성 단백질 |
| RM | Oats / Grain Base | KG | 바의 기본 원재료 |
| RM | Syrup / Binder | KG | 원재료를 결합하는 역할 |
| RM | Nut / Protein Crisp | KG | 식감 및 영양 구성 |
| RM | Oil / Fat | KG | 식감 조절 |
| RM | Flavor Ingredient | KG | 제품별 맛 차별화 |
| RM | Coating Material | KG | 초콜릿 또는 요거트 코팅 |
| PK | Individual Wrapper | EA | 개별 포장재 |
| PK | Carton Box | EA | 판매·배송용 박스 |

---

## 제품별 차이

공통 BOM은 최대한 유지하고 일부 자재만 변경한다.

| Product | 변경되는 주요 자재 |
|---|---|
| Choco Peanut | Chocolate Flavor + Peanut |
| Salted Caramel | Caramel Flavor + Salt |
| Berry Yogurt | Berry Flavor + Yogurt Coating |

즉,

```text
공통 Protein Bar Base
+
제품별 Flavor
+
제품별 Coating

=
각각 다른 완제품
```

구조로 설계할 수 있다.

---

## Production Process

### 1. Raw Material Receiving
단백질 원료, 곡물, 시럽, 견과류, 포장재 등을 입고한다.

### 2. Weighing & Batching
생산할 Batch에 필요한 원재료의 양을 계량한다.

### 3. Binder Preparation
시럽 등의 결합 원료를 준비한다.

### 4. Mixing
Protein Powder, Oats, Binder, Flavor 등을 균일하게 혼합한다.

### 5. Forming / Extrusion
혼합된 원료를 일정한 두께와 형태의 Bar로 성형한다.

### 6. Cooling
성형된 Bar를 냉각하여 형태를 안정화한다.

### 7. Cutting
일정한 중량과 크기로 절단한다.

### 8. Coating
Chocolate 또는 Yogurt 등의 코팅을 적용한다.

### 9. Final Cooling
코팅된 제품을 다시 냉각한다.

### 10. Packaging
개별 포장 후 Box 단위로 포장한다.

---

## Work Center Example

```text
WC01 - Mixing
WC02 - Forming
WC03 - Cooling & Cutting
WC04 - Coating
WC05 - Packaging
```

---

## Module Connection

### MM

구매 대상:

- Protein Powder
- Oats
- Syrup
- Nuts
- Flavor
- Coating
- Packaging Material

주요 업무:

```text
원재료 필요
↓
Purchase Requisition
↓
Purchase Order
↓
Vendor
↓
Goods Receipt
↓
원재료 재고 증가
```

### PP

주요 업무:

- 제품별 BOM 관리
- 생산 수량 결정
- 생산계획 생성
- Work Center 관리
- Routing 관리
- 생산오더 실행

### SD

판매채널 예시:

```text
Online
Wholesale
```

Customer 예시:

- 자사몰 고객
- 헬스장
- 편의점 또는 소매점
- 온라인 유통업체

판매 흐름:

```text
Sales Order
↓
Availability Check
↓
Delivery
↓
Picking
↓
Goods Issue
↓
Billing
```

### FI

- 원재료 구매에 따른 A/P 발생
- 제품 판매에 따른 A/R 발생
- Vendor Payment
- Customer Payment

### CO

제품별 원가를 비교할 수 있다.

예:

```text
Choco Peanut 원가
vs
Salted Caramel 원가
vs
Berry Yogurt 원가
```

Flavor와 Coating 가격 차이에 따른 제품별 수익성 분석도 가능하다.

---

## 장점

- 운동·건강이라는 대중적인 주제를 유지할 수 있음
- 남녀 모두 쉽게 이해할 수 있는 제품
- 맛만 변경하여 여러 완제품 생성 가능
- 기본 생산공정을 모든 제품에 재사용 가능
- 실제 제조공정이 충분히 존재함
- BOM이 지나치게 복잡하지 않음
- PP / MM / SD / FI / CO 연결이 자연스러움
- 제품별 원가 차이가 있어 CO에도 적합함
- 자사몰과 B2B 유통을 모두 SD에서 설정하기 쉬움

## 단점

- 식품이므로 유통기한과 품질관리 이슈가 존재함
- 실제 배합비는 전문적인 식품 지식이 필요함
- 너무 많은 원재료를 추가하면 BOM이 복잡해질 수 있음

### 프로젝트 대응 방향

정확한 식품 레시피 자체를 구현하는 것이 목적은 아니므로 배합 공정은 실제 산업 구조를 참고하되 주요 원재료 중심으로 단순화한다.

---

<a id="candidate-2"></a>
# Candidate 2. 고단백 스낵 / Protein Chips 제조업

## Concept

### 운동을 하더라도 맛있는 과자를 포기하고 싶지 않은 소비자를 위한 고단백 스낵

일반 감자칩과 같은 간식을 먹고 싶지만 단백질 섭취도 고려하는 소비자를 대상으로 한다.

단순한 헬스 보충제가 아니라

> **"일반 과자처럼 맛있지만 단백질을 강화한 스낵"**

이라는 방향이다.

단백질바보다 일반적인 스낵에 가까워 대중적인 브랜드를 만들기 쉽다.

---

## Product Example

### FG01 - Sea Salt Protein Chips
오리지널 소금 맛

### FG02 - BBQ Protein Chips
바비큐 맛

### FG03 - Spicy Protein Chips
매콤한 맛

세 제품은 Base가 동일하고 **Seasoning만 변경**한다.

```text
공통 Protein Chip Base
        │
        ├── Sea Salt Seasoning
        ├── BBQ Seasoning
        └── Spicy Seasoning
```

이 구조는 ERP 프로젝트에서 매우 큰 장점이 있다.

제품은 여러 종류이지만 BOM과 Routing 대부분을 공유할 수 있다.

---

## 실제 산업과의 유사성

산업용 압출 스낵 제조는 실제로 다음과 같은 공정을 사용한다.

```text
Raw Material Receiving
↓
Batching
↓
Powder Mixing
↓
Extrusion
↓
Forming / Cutting
↓
Drying
↓
Coating / Seasoning
↓
Cooling
↓
Packaging
```

실제 식품설비 기업들은 원재료 취급부터 Extrusion, Drying, Flavoring까지 연결된 스낵 생산라인을 공급한다.

따라서 단순히 완성된 과자를 받아 시즈닝만 뿌리는 회사가 아니라 **Base Snack 자체를 생산하는 제조기업**으로 설정할 수 있다.

---

## Preliminary BOM

| Type | Material | 예상 단위 | 설명 |
|---|---|---|---|
| RM | Protein Powder | KG | 단백질 강화 원료 |
| RM | Corn / Rice Flour | KG | Snack Base |
| RM | Starch | KG | 성형 및 식감 |
| RM | Oil | KG | 코팅 및 식감 |
| RM | Salt | KG | 기본 조미 |
| RM | Seasoning | KG | 제품별 맛 |
| PK | Snack Pouch | EA | 개별 포장 |
| PK | Carton Box | EA | 운송·판매용 포장 |

---

## 제품별 차이

| Product | Base | Variable Material |
|---|---|---|
| Sea Salt | 동일 | Sea Salt Seasoning |
| BBQ | 동일 | BBQ Seasoning |
| Spicy | 동일 | Spicy Seasoning |

즉 제품 이름과 맛은 달라도 생산공정은 동일하다.

---

## Production Process

### 1. Raw Material Receiving
단백질 분말, 곡물가루, 전분, Seasoning 등을 입고한다.

### 2. Weighing
생산계획에 따라 원재료를 계량한다.

### 3. Dry Mixing
Protein Powder, Flour, Starch 등을 혼합한다.

### 4. Extrusion
혼합물을 Extruder에서 열과 압력을 이용하여 가공한다.

### 5. Forming & Cutting
원하는 Snack 형태로 성형하고 절단한다.

### 6. Drying / Baking
수분을 감소시켜 바삭한 식감을 형성한다.

### 7. Oil & Seasoning
Oil과 제품별 Seasoning을 적용한다.

### 8. Cooling
제품을 냉각한다.

### 9. Packaging
정량 포장 후 박스 포장한다.

---

## Work Center Example

```text
WC01 - Material Mixing
WC02 - Extrusion
WC03 - Drying
WC04 - Seasoning
WC05 - Packaging
```

---

## 실제 원재료 조달 가능성

고단백 Snack용 단백질 원료를 공급하는 글로벌 식품원료 업체가 실제 존재한다.

예를 들어 Pea Protein은 다음과 같은 제품에 실제 적용된다.

- Bakery
- Cereal Bar
- Breakfast Cereal
- Salty Snack

또한 Snack 제조기업을 대상으로 BBQ, Salt 등의 Seasoning을 전문적으로 공급하는 식품원료 기업도 존재한다.

따라서

```text
Protein Ingredient Vendor
Seasoning Vendor
Packaging Vendor
```

등의 Vendor 구조를 현실적으로 설정할 수 있다.

---

## Module Connection

### MM

구매:

- Protein Powder
- Flour
- Starch
- Oil
- Seasoning
- Packaging Material

### PP

생산:

```text
Mixing
↓
Extrusion
↓
Drying
↓
Seasoning
↓
Packaging
```

### SD

판매채널:

```text
Online
Retail / Wholesale
```

Customer:

- 편의점
- 온라인 쇼핑몰
- 헬스 관련 판매점
- 일반 소매점

### FI

- 원재료 구매
- Vendor Invoice
- 제품 판매
- Customer Billing

### CO

제품별 Seasoning 가격과 판매가격 차이를 기반으로 수익성 분석 가능

---

## 장점

- 일반 소비자가 쉽게 이해할 수 있음
- 헬스 전용 제품이라는 느낌이 지나치게 강하지 않음
- 제품 맛만 변경하여 여러 SKU 생성 가능
- 생산공정이 모든 제품에 거의 동일함
- 실제 제조공정이 충분히 존재하여 제조기업 느낌이 강함
- MM과 PP가 할 일이 명확함
- 소매점과 온라인 판매를 모두 SD에서 구성하기 좋음
- 발표 시 제품 컨셉을 설명하기 쉬움

## 단점

- Extrusion이라는 공정이 처음에는 생소할 수 있음
- 실제 Extruder의 세부 공정까지 이해할 필요는 없음
- 단백질바보다 생산설비 설명이 조금 어려울 수 있음

### 프로젝트 대응 방향

Extruder의 내부 물리적 원리는 구현하지 않고 SAP에서는 하나의 Work Center와 Operation으로 관리한다.

즉,

```text
Extrusion이 실제로 존재한다는 현실성은 유지

하지만

기계 내부의 온도·압력·스크루 설정까지는 구현하지 않음
```

으로 범위를 제한한다.

---

<a id="candidate-3"></a>
# Candidate 3. RTD 단백질 음료 제조업

## Concept

### 운동 직후뿐 아니라 아침이나 간식으로 편하게 마시는 고단백 음료

**RTD = Ready To Drink**

즉, 단백질 파우더를 소비자가 직접 물에 섞어 마시는 것이 아니라 바로 마실 수 있도록 완제품으로 판매하는 음료이다.

타깃을 헬스 이용자로만 제한하지 않고

- 운동 후 영양보충
- 간편한 아침식사
- 직장인 간식
- 학생 간식

등으로 확장할 수 있다.

---

## Product Example

### FG01 - Chocolate Protein Drink

### FG02 - Vanilla Protein Drink

### FG03 - Banana Protein Drink

세 제품은 Flavor만 변경하고 기본 생산공정은 동일하게 구성한다.

---

## 실제 산업과의 유사성

단백질 RTD는 실제 식품산업에서 생산되고 있으며 유청단백 또는 식물성 단백질을 이용한 음료용 원료도 실제 공급된다.

산업용 음료라인에서는 다음과 같은 공정을 사용할 수 있다.

```text
Raw Material Receiving
↓
Weighing
↓
Mixing / Dissolving
↓
Homogenization
↓
Heat Treatment
↓
Cooling
↓
Filling
↓
Capping
↓
Labeling
↓
Case Packing
```

제품 특성에 따라 UHT 등의 열처리와 무균충전 방식이 사용될 수 있다.

---

## Preliminary BOM

| Type | Material | 예상 단위 | 설명 |
|---|---|---|---|
| RM | Water / Milk Base | L | 음료 Base |
| RM | Protein Ingredient | KG | Whey 또는 Plant Protein |
| RM | Sweetener | KG | 단맛 조절 |
| RM | Flavor | KG | 제품별 맛 |
| RM | Stabilizer | KG | 제품 안정성 |
| PK | Bottle | EA | 용기 |
| PK | Cap | EA | 병뚜껑 |
| PK | Label | EA | 제품 라벨 |
| PK | Carton Box | EA | 운송용 박스 |

---

## 제품별 차이

| Product | Variable Material |
|---|---|
| Chocolate | Chocolate Flavor |
| Vanilla | Vanilla Flavor |
| Banana | Banana Flavor |

Base와 생산공정은 동일하게 유지할 수 있다.

---

## Production Process

### 1. Raw Material Receiving
단백질 원료, Flavor, Bottle 등의 자재를 입고한다.

### 2. Weighing
Batch별 원재료를 계량한다.

### 3. Mixing / Dissolving
Base에 Protein Powder 및 기타 원료를 혼합·용해한다.

### 4. Homogenization
음료 성분을 균일하게 만든다.

### 5. Heat Treatment
제품의 안정성과 보존을 위한 열처리를 수행한다.

### 6. Cooling
충전 가능한 상태로 냉각한다.

### 7. Filling
Bottle에 음료를 정량 충전한다.

### 8. Capping
Cap을 장착한다.

### 9. Labeling
제품별 Label을 부착한다.

### 10. Case Packing
완제품을 Box 단위로 포장한다.

---

## Work Center Example

```text
WC01 - Mixing
WC02 - Homogenization
WC03 - Heat Treatment
WC04 - Filling
WC05 - Packaging
```

---

## Module Connection

### MM

구매:

- Protein Ingredient
- Flavor
- Sweetener
- Stabilizer
- Bottle
- Cap
- Label
- Carton

### PP

생산:

```text
Mixing
↓
Homogenization
↓
Heat Treatment
↓
Filling
↓
Packaging
```

### SD

판매채널:

- Online
- Convenience / Retail
- Gym / Fitness Center
- Wholesale

### FI

- 원재료 구매에 따른 Vendor 거래
- 완제품 판매에 따른 Customer 거래

### CO

Flavor 또는 Protein Ingredient에 따른 제품별 제조원가 비교 가능

---

## 장점

- 매우 대중적인 제품
- 운동 및 건강이라는 프로젝트 컨셉과 잘 맞음
- 남녀 모두 쉽게 이해 가능
- 제품별 맛만 변경하여 다양한 SKU를 구성할 수 있음
- 용기, Cap, Label 등 MM에서 관리할 자재가 명확함
- 제조공정이 단순 조립이 아니므로 제조기업 느낌이 충분함
- 온라인·편의점·헬스장 등 SD 판매채널을 다양하게 구성할 수 있음

## 단점

- 세 후보 중 실제 식품공정이 가장 복잡함
- Homogenization, UHT 등의 용어가 생소할 수 있음
- 실제 음료 제조에서는 품질·위생 관리가 중요함
- 현재 프로젝트에 QM 모듈 담당자가 없기 때문에 품질관리 범위를 과도하게 확장하면 어려워질 수 있음

### 프로젝트 대응 방향

식품공학적인 세부조건은 제외하고 SAP에서는 공정을 다음 수준까지만 관리한다.

```text
Mixing
↓
Homogenization
↓
Heat Treatment
↓
Filling
↓
Packaging
```

---

# 4. 후보 비교

| 평가항목 | 고단백 영양바 | 고단백 스낵 | RTD 단백질 음료 |
|---|---:|---:|---:|
| 대중성 | ★★★★★ | ★★★★★ | ★★★★★ |
| 운동·건강 컨셉 | ★★★★★ | ★★★★☆ | ★★★★★ |
| 제조기업 느낌 | ★★★★☆ | ★★★★★ | ★★★★★ |
| BOM 난이도 | ★★★★☆ | ★★★★☆ | ★★★☆☆ |
| 생산공정 난이도 | ★★★★☆ | ★★★☆☆ | ★★★☆☆ |
| 제품 공정 재사용 | ★★★★★ | ★★★★★ | ★★★★★ |
| MM 적합성 | ★★★★★ | ★★★★★ | ★★★★★ |
| PP 적합성 | ★★★★★ | ★★★★★ | ★★★★★ |
| SD 적합성 | ★★★★★ | ★★★★★ | ★★★★★ |
| FI/CO 적합성 | ★★★★★ | ★★★★★ | ★★★★☆ |
| ERP 초보자 적합성 | ★★★★★ | ★★★★☆ | ★★★☆☆ |

---

# 5. 현재 추천 순위

## 1순위 - 고단백 영양바 제조업

현재 가장 균형이 좋은 후보이다.

### 이유

- 초기 닭가슴살 아이디어의 운동·건강 컨셉을 유지할 수 있음
- 맛을 강조하여 대중적인 브랜드로 확장 가능
- 실제 제조공정이 존재함
- 제조공정이 지나치게 단순하지 않음
- Flavor만 변경하여 여러 완제품 생성 가능
- BOM 관리가 어렵지 않음
- PP / MM / SD / FI / CO가 모두 자연스럽게 연결됨

특히

```text
원재료 구매
↓
혼합
↓
성형
↓
냉각
↓
절단
↓
코팅
↓
포장
↓
판매
```

라는 생산 흐름이 명확하기 때문에 ERP 프로젝트의 고객사로 설명하기 좋다.

---

## 2순위 - 고단백 스낵 / Protein Chips 제조업

고단백 영양바보다 조금 더 독특하면서도 지나치게 유행성 제품은 아니다.

특히

```text
공통 Snack Base
+
제품별 Seasoning
```

구조가 명확해서 제품 종류를 늘려도 BOM과 생산공정을 재사용하기 쉽다.

다만 Extrusion 공정에 대한 최소한의 이해가 필요하다.

---

## 3순위 - RTD 단백질 음료 제조업

제품 자체는 가장 대중적이고 판매 시나리오도 다양하게 만들 수 있다.

하지만 실제 음료공정에는 Homogenization, Heat Treatment, Filling 등 다른 후보보다 전문적인 공정이 포함되므로 프로젝트 난이도가 조금 높을 수 있다.

---

# 6. 중요한 설계 원칙

## 제품을 다양하게 만들기 위해 공정을 억지로 늘리지 않는다.

좋은 예:

```text
Protein Bar Base

├── Chocolate Flavor
├── Caramel Flavor
└── Berry Flavor
```

기본 BOM과 Routing은 동일하고 일부 자재만 다르게 한다.

---

## 반제품(SFG)을 억지로 만들지 않는다.

ERP 구조를 복잡하게 보이게 하기 위해 실제로 별도 관리하지 않을 중간 제품을 SFG로 만드는 것은 지양한다.

예를 들어 연속적으로

```text
Mixing
→ Forming
→ Cooling
→ Cutting
→ Packaging
```

되는 제품이라면 각 공정 사이의 결과물을 모두 별도 반제품 Material로 만들 필요는 없다.

실제로 중간재를 보관하거나 별도의 Production Order로 관리할 필요가 있을 때 SFG 사용을 고려한다.

---

## 실제 공정을 그대로 모두 구현할 필요도 없다.

예를 들어 Protein Chips의 Extrusion 공정에는 실제로

- Temperature
- Pressure
- Screw Speed
- Moisture
- Die Shape

등 여러 기술적 변수가 존재한다.

하지만 이번 프로젝트의 목적은 식품공학 설비를 설계하는 것이 아니라 ERP 프로세스를 구현하는 것이다.

따라서 SAP에서는

```text
Operation 20
Extrusion
```

이라는 하나의 주요 생산공정으로 관리해도 된다.

즉,

> **산업의 현실성은 유지하되 ERP에 필요하지 않은 공학적 세부사항은 적절히 추상화한다.**

---

# 7. 실제 산업 조사 근거

후보 산업의 현실성을 확인하기 위해 실제 식품원료 및 생산설비 업체의 자료를 참고하였다.

### Protein Bar

실제 단백질바 생산시설 및 생산라인에서 다음 공정이 사용된다.

- Mixing
- Extrusion / Forming
- Cooling
- Cutting
- Enrobing / Coating
- Packing

참고 기업 및 자료:

- PROMAX Food Industries
- Nutrition Bar Production Line 관련 산업설비 자료

### Protein Snack

실제 압출 스낵 생산에서는 다음 공정이 사용된다.

- Raw Material Handling
- Batching
- Mixing
- Extrusion
- Drying
- Coating / Flavoring
- Packaging

참고 기업:

- Coperion
- GEA
- Bühler

단백질 및 Seasoning 원료를 실제 식품 제조사에 공급하는 기업도 존재한다.

- Roquette - Pea Protein Ingredients
- Kerry - Snack Seasoning Solutions

### Protein RTD

실제 스포츠·기능성 음료용 단백질 원료와 산업용 음료 생산설비가 존재한다.

참고 기업:

- Arla Foods Ingredients - Whey Protein Ingredients
- Tetra Pak - Mixing / Homogenization / UHT / Filling Equipment

---

---

<a id="candidate-4"></a>
# Candidate 4. 반려동물 기능성 간식 제조업

## Concept

### 반려동물의 건강과 기호성을 함께 고려한 기능성 간식 제조기업

단순히 강아지에게 맛있는 간식을 판매하는 것이 아니라 기능별로 제품을 구분한다.

예를 들어 다음과 같이 제품을 구성할 수 있다.

- 구강관리
- 장 건강
- 피부·모질
- 일반 영양 간식

제품의 기능은 달라도 기본적인 생산공정은 동일하게 유지한다.

즉,

```text
공통 Treat Base
+
기능별 Ingredient
+
제품별 Flavor

=
각기 다른 완제품
```

형태로 구성한다.

반려동물 산업 자체도 특정 성별이나 연령대에 크게 제한되지 않고 대중적으로 이해하기 쉬운 장점이 있다.

---

## Product Example

### FG01 - Dental Care Treat
구강관리를 위한 간식

### FG02 - Digestive Care Treat
장 건강을 위한 간식

### FG03 - Skin & Coat Treat
피부·모질 관리를 위한 간식

세 제품 모두 동일한 기본 제조공정을 사용하고 기능성 원료 일부만 변경한다.

```text
              Common Treat Base
                     │
        ┌────────────┼────────────┐
        │            │            │
     Dental       Digestive    Skin & Coat
    Ingredient    Ingredient    Ingredient
        │            │            │
        ▼            ▼            ▼
      FG01          FG02         FG03
```

---

## 실제 산업과의 유사성

실제 반려동물 간식 제조에서는 다음과 같은 공정이 사용될 수 있다.

```text
Raw Material Receiving
↓
Weighing
↓
Mixing
↓
Forming / Extrusion
↓
Cutting
↓
Baking / Drying
↓
Coating
↓
Cooling
↓
Packaging
```

실제 Pet Treat 생산라인에서도 Mixing, Extrusion 또는 Molding, Drying/Baking, Coating, Cooling, Packaging 등의 공정이 사용된다.

따라서 단순히 이미 만들어진 간식을 구매해 포장만 하는 회사가 아니라, 원재료에서 완제품까지 직접 생산하는 제조기업으로 설정할 수 있다.

---

## Preliminary BOM

> 아래 BOM은 ERP 산업 후보 비교를 위한 개념적 구조이며 실제 배합비는 산업 최종 선정 후 결정한다.

| Type | Material | 예상 단위 | 설명 |
|---|---|---|---|
| RM | Chicken / Protein Base | KG | 주요 단백질 원료 |
| RM | Grain / Starch Base | KG | 제품 형태와 식감 구성 |
| RM | Vegetable Powder | KG | 기본 영양 원료 |
| RM | Oil | KG | 식감 및 기호성 |
| RM | Functional Ingredient | KG | 제품별 기능성 원료 |
| RM | Flavor / Palatant | KG | 기호성 강화 |
| PK | Individual Pouch | EA | 개별 포장 |
| PK | Carton Box | EA | 운송용 박스 |

---

## 제품별 BOM 차이

기본 BOM은 최대한 동일하게 사용한다.

| Product | 변경되는 주요 자재 |
|---|---|
| Dental Care | Dental Functional Ingredient |
| Digestive Care | Digestive Functional Ingredient |
| Skin & Coat | Skin & Coat Functional Ingredient |

즉,

```text
Protein Base
+
Grain / Starch
+
Vegetable Powder
+
Oil
+
기능별 Ingredient
+
Flavor
```

구조이다.

제품이 달라져도 대부분의 원재료와 생산공정은 그대로 사용할 수 있다.

---

## Production Process

### 1. Raw Material Receiving
단백질 원료, 곡물원료, 기능성 원료, 포장재 등을 입고한다.

### 2. Weighing & Batching
생산할 제품과 수량에 맞게 원재료를 계량한다.

### 3. Mixing
기본 원재료와 기능성 원료를 균일하게 혼합한다.

### 4. Forming / Extrusion
혼합물을 일정한 형태로 성형한다.

예:

```text
Stick
Cube
Bite
```

### 5. Cutting
제품을 일정한 크기와 중량으로 절단한다.

### 6. Baking / Drying
제품을 가열 또는 건조하여 원하는 식감과 보관성을 형성한다.

### 7. Coating
제품의 기호성을 높이기 위한 Flavor 또는 Coating을 적용한다.

### 8. Cooling
포장 전에 제품을 냉각한다.

### 9. Packaging
정량 계량하여 Pouch에 담고 최종 포장한다.

---

## Work Center Example

```text
WC01 - Mixing
WC02 - Forming
WC03 - Baking / Drying
WC04 - Coating & Cooling
WC05 - Packaging
```

---

## Module Connection

### MM

구매 대상:

- Protein Base
- Grain / Starch
- Vegetable Powder
- Functional Ingredient
- Oil
- Flavor
- Packaging Material

```text
Purchase Requisition
↓
Purchase Order
↓
Vendor
↓
Goods Receipt
↓
Raw Material Inventory
```

### PP

관리 대상:

- 제품별 BOM
- 생산계획
- 생산오더
- Work Center
- Routing
- 완제품 생산

```text
Mixing
↓
Forming
↓
Drying
↓
Coating
↓
Packaging
```

### SD

판매채널 예시:

```text
Online
Pet Shop / Wholesale
```

Customer 예시:

- 온라인 유통업체
- 반려동물 전문 매장
- 동물병원
- 대형 소매업체

판매 흐름:

```text
Sales Order
↓
Availability Check
↓
Delivery
↓
Picking
↓
Goods Issue
↓
Billing
```

### FI

- 원재료 구매에 따른 A/P
- 완제품 판매에 따른 A/R
- Vendor Payment
- Customer Payment

### CO

기능성 원료 가격 차이에 따른 제품별 제조원가 비교가 가능하다.

예:

```text
Dental Care 제조원가
vs
Digestive Care 제조원가
vs
Skin & Coat 제조원가
```

---

## 장점

- 최근 성장하고 있는 반려동물 산업을 반영할 수 있음
- 특정 유행 상품에 의존하지 않음
- 남녀 모두 이해하기 쉬운 제품
- 실제 제조공정이 명확함
- 제품별 기능만 달라지고 기본 공정을 재사용할 수 있음
- MM에서 관리할 원재료와 Vendor가 충분함
- PP의 BOM과 Routing을 구성하기 좋음
- 온라인과 B2B 판매 모두 SD에 적용 가능함
- 기능성 원료 가격에 따라 CO 원가 분석도 가능함

## 단점

- 식품과 마찬가지로 품질 및 위생 이슈가 존재함
- 기능성 원료를 너무 많이 설정하면 BOM이 복잡해질 수 있음
- 실제 Pet Food 규제까지 다루면 프로젝트 범위가 커질 수 있음

### 프로젝트 대응 방향

식품영양 또는 수의학적 효능을 직접 검증하는 것이 프로젝트 목적은 아니다.

따라서

```text
실제 제조공정
+
현실적인 원재료 구조
+
SAP 생산·구매·판매 프로세스
```

까지만 구현하고 세부 기능성 배합과 품질검사는 범위에서 제외한다.

---

<a id="candidate-5"></a>
# Candidate 5. 고체 샴푸·클렌징바 제조업

## Concept

### 플라스틱 용기를 줄이고 사용 목적에 따라 선택할 수 있는 Solid Personal Care 브랜드

일반적인 액체 샴푸가 아니라 고체 형태로 생산되는 Shampoo Bar 또는 Cleansing Bar를 제조한다.

제품 기능에 따라 다음과 같이 구분할 수 있다.

- Moisture
- Refresh
- Sensitive

특정 성별보다는 생활용품·퍼스널케어 시장 전체를 타깃으로 할 수 있다.

---

## Product Example

### FG01 - Moisture Shampoo Bar
건조한 두피용

### FG02 - Refresh Shampoo Bar
상쾌한 사용감을 강조한 제품

### FG03 - Sensitive Shampoo Bar
순한 사용감을 강조한 제품

기본 Shampoo Bar Base와 생산공정은 동일하게 유지하고 일부 첨가원료와 향만 변경한다.

```text
           Common Shampoo Bar Base
                      │
        ┌─────────────┼─────────────┐
        │             │             │
     Moisture       Refresh      Sensitive
     Additive       Additive      Additive
        │             │             │
        ▼             ▼             ▼
      FG01           FG02          FG03
```

---

## 실제 산업과의 유사성

실제 고체 샴푸 제조에서는 Powder 또는 Granule 형태의 Surfactant와 기타 원료를 사용하여 다음과 같은 공정을 적용할 수 있다.

```text
Raw Material Receiving
↓
Weighing
↓
Mixing
↓
Homogenizing
↓
Extrusion
↓
Cutting
↓
Pressing / Stamping
↓
Cooling
↓
Packaging
```

또는 제조방식에 따라 원료를 가열하여 혼합한 후 Mold에서 굳히는 방식도 존재한다.

따라서 단순히 이미 완성된 Soap Base를 구매하여 포장만 하는 기업으로 설정하지 않고, 원료 배합부터 고형 제품 성형까지 직접 수행하는 제조기업으로 설계할 수 있다.

---

## Preliminary BOM

| Type | Material | 예상 단위 | 설명 |
|---|---|---|---|
| RM | Surfactant Base | KG | 세정 기능의 주요 원료 |
| RM | Conditioning Agent | KG | 사용감 개선 |
| RM | Plant Oil / Butter | KG | 제품 특성 부여 |
| RM | Starch / Filler | KG | 형태 및 물성 조절 |
| RM | Functional Additive | KG | 제품별 기능성 원료 |
| RM | Fragrance | KG | 제품별 향 |
| PK | Paper Wrapper | EA | 개별 포장 |
| PK | Carton Box | EA | 최종 포장 |

---

## 제품별 BOM 차이

| Product | 주요 변경 자재 |
|---|---|
| Moisture | Moisturizing Additive + Fragrance A |
| Refresh | Refreshing Additive + Fragrance B |
| Sensitive | Mild Additive + Fragrance C |

공통 Base는 동일하게 유지한다.

```text
Common Surfactant Base
+
Conditioning Agent
+
Oil
+
제품별 Additive
+
제품별 Fragrance
```

---

## Production Process

### 1. Raw Material Receiving
Surfactant, Oil, Additive, Fragrance, Packaging Material 등을 입고한다.

### 2. Weighing
제품별 BOM에 따라 원료를 계량한다.

### 3. Mixing
분말 및 액상 원료를 혼합한다.

### 4. Homogenizing
혼합물을 균일한 상태로 만든다.

### 5. Extrusion
혼합된 원료를 일정한 형태의 Bar로 압출한다.

### 6. Cutting
긴 Bar를 일정 크기와 중량으로 절단한다.

### 7. Pressing / Stamping
최종 제품의 모양을 만들고 브랜드 Logo 등을 압인할 수 있다.

### 8. Cooling
제품 형태를 안정화한다.

### 9. Packaging
종이 포장 또는 Carton에 포장한다.

---

## Work Center Example

```text
WC01 - Mixing
WC02 - Homogenizing
WC03 - Extrusion
WC04 - Cutting & Pressing
WC05 - Packaging
```

---

## Module Connection

### MM

구매 대상:

- Surfactant
- Conditioning Agent
- Oil
- Additive
- Fragrance
- Packaging

### PP

```text
Mixing
↓
Homogenizing
↓
Extrusion
↓
Cutting
↓
Pressing
↓
Packaging
```

### SD

판매채널 예시:

```text
Online
Lifestyle / Beauty Retail
```

Customer 예시:

- 온라인 유통업체
- 생활용품 편집숍
- 드럭스토어
- 호텔·숙박업체 B2B

### FI

원료 구매와 제품 판매에 따른 회계 거래를 처리한다.

### CO

제품별 기능성 Additive와 Fragrance 가격 차이에 따른 원가 분석이 가능하다.

---

## 장점

- 제조공정이 단순 포장 수준이 아님
- Mixing, Extrusion, Cutting 등 PP 공정이 명확함
- 제품 종류가 달라도 Routing을 거의 그대로 사용할 수 있음
- 포장재까지 포함하여 MM 구성이 쉬움
- 액체 샴푸보다 Bottle 등의 복잡성을 줄일 수 있음
- 제품 디자인과 브랜드 컨셉을 만들기 좋음
- 온라인 및 B2B 판매 시나리오 모두 가능함

## 단점

- 화장품 원료명이 처음에는 생소할 수 있음
- 실제 제품 Formula를 정교하게 만들려 하면 복잡해짐
- 품질관리와 화장품 규정까지 포함하면 프로젝트 범위가 커질 수 있음

### 프로젝트 대응 방향

세부 화학 Formula를 직접 개발하지 않는다.

ERP에서는 다음 수준까지만 관리한다.

```text
주요 원재료
↓
배합
↓
성형
↓
절단
↓
포장
```

즉, 실제 산업의 제조공정은 유지하면서 화학적인 세부 배합기술은 프로젝트 범위에서 제외한다.

---

<a id="candidate-6"></a>
# Candidate 6. 홈 프래그런스 캔들 제조업

## Concept

### 공간과 상황에 따라 향을 선택하는 Home Fragrance Candle 브랜드

단순한 장식용 초가 아니라 거실, 침실, 업무공간 등 사용환경에 따라 향을 선택하는 생활용품 브랜드로 설정한다.

예:

- Relax
- Focus
- Fresh

향수보다 제조공정이 단순하지만 단순히 완제품을 구매하여 포장하는 구조는 아니다.

Wax를 직접 용융하고 Fragrance와 Color를 배합한 뒤 심지를 설치하여 충전·냉각·검수하는 실제 제조공정을 가진다.

---

## Product Example

### FG01 - Forest Candle
우디 계열 향

### FG02 - Citrus Candle
상쾌한 시트러스 향

### FG03 - Cotton Candle
깨끗한 코튼 계열 향

세 제품은 Fragrance만 달라지고 기본적인 Wax Base, Container 및 생산공정은 동일하게 사용할 수 있다.

```text
                Common Wax Base
                      │
        ┌─────────────┼─────────────┐
        │             │             │
      Forest        Citrus        Cotton
     Fragrance      Fragrance     Fragrance
        │             │             │
        ▼             ▼             ▼
      FG01           FG02          FG03
```

---

## 실제 산업과의 유사성

실제 Candle 제조에서는 다음과 같은 과정이 사용된다.

```text
Raw Material Receiving
↓
Wick Preparation
↓
Wax Melting
↓
Color / Fragrance Mixing
↓
Container Preparation
↓
Pouring
↓
Cooling
↓
Finishing
↓
Inspection
↓
Packaging
```

따라서

> "향료 완제품을 받아서 포장만 하는 회사"

와는 다르다.

Fragrance Oil 자체는 전문 원료업체로부터 구매할 수 있지만,

```text
Wax 선정
+
Fragrance 배합
+
Wick 선정
+
Wax 용융
+
Pouring
+
Cooling
+
Finishing
```

과정을 직접 수행하기 때문에 충분히 Candle 제조기업으로 볼 수 있다.

---

## Preliminary BOM

| Type | Material | 예상 단위 | 설명 |
|---|---|---|---|
| RM | Soy / Plant Wax | KG | Candle Base |
| RM | Fragrance Oil | KG | 제품별 향 |
| RM | Dye | KG | 색상 조절 |
| RM | Wick | EA | 심지 |
| RM | Wick Holder | EA | 심지 고정 |
| PK | Glass Container | EA | Candle 용기 |
| PK | Lid | EA | 뚜껑 |
| PK | Label | EA | 제품별 Label |
| PK | Carton Box | EA | 최종 포장 |

---

## 제품별 BOM 차이

| Product | 변경되는 주요 자재 |
|---|---|
| Forest | Forest Fragrance |
| Citrus | Citrus Fragrance |
| Cotton | Cotton Fragrance |

나머지 주요 원재료는 공통으로 사용할 수 있다.

---

## Production Process

### 1. Raw Material Receiving
Wax, Wick, Fragrance, Container, Packaging 등을 입고한다.

### 2. Wick Preparation
심지를 일정 길이로 준비한다.

### 3. Wax Melting
고체 Wax를 가열하여 액체 상태로 만든다.

### 4. Fragrance / Color Mixing
제품 종류에 맞는 Fragrance와 Dye를 Wax에 혼합한다.

### 5. Container Preparation
Glass Container에 Wick을 고정한다.

### 6. Pouring
혼합된 Wax를 Container에 정량 충전한다.

### 7. Cooling
충전된 Candle을 일정 시간 냉각하여 굳힌다.

### 8. Finishing
Wick 길이를 조정하고 표면을 정리한다.

### 9. Inspection
외관, 용량, Wick 위치 등을 확인한다.

### 10. Packaging
Label을 부착하고 Carton에 포장한다.

---

## Work Center Example

```text
WC01 - Wax Melting
WC02 - Mixing
WC03 - Pouring
WC04 - Cooling & Finishing
WC05 - Packaging
```

---

## Module Connection

### MM

구매:

- Wax
- Wick
- Fragrance
- Dye
- Glass Container
- Lid
- Label
- Carton

### PP

```text
Melting
↓
Mixing
↓
Pouring
↓
Cooling
↓
Finishing
↓
Packaging
```

### SD

판매채널 예시:

```text
Online
Lifestyle / Wholesale
```

Customer 예시:

- 온라인 유통업체
- 인테리어 소품샵
- 편집숍
- 호텔 및 숙박업체
- 기업 선물 고객

### FI

- 원재료 및 부자재 구매
- 제품 판매
- Vendor / Customer 거래

### CO

제품별 Fragrance 가격 및 Container 가격의 차이에 따라 제조원가와 수익성을 비교할 수 있다.

---

## 장점

- 제품 자체가 대중적이고 이해하기 쉬움
- 성별에 크게 제한되지 않음
- 향만 변경하여 여러 제품을 만들 수 있음
- 동일 Routing을 반복해서 활용할 수 있음
- Wax, Wick, Container, Fragrance 등 BOM이 명확함
- 실제 제조공정이 존재함
- 식품보다 유통기한 문제를 덜 고려해도 됨
- B2C와 B2B 모두 SD 시나리오 구성이 쉬움
- 패키지 디자인 등을 활용하여 발표자료를 만들기 좋음

## 단점

- 단백질바나 Pet Treat에 비해 생산공정이 조금 단순해 보일 수 있음
- 향 종류를 너무 많이 설정하면 Material Master가 불필요하게 많아질 수 있음
- Candle 제조에서도 품질 및 안전관리가 중요하지만 현재 프로젝트에 QM 모듈은 없음

### 프로젝트 대응 방향

단순한 Handmade Candle 공방으로 설정하기보다는 일정 규모 이상의 제조기업으로 설정한다.

따라서

```text
원재료 구매
↓
Batch 생산
↓
Wax Melting
↓
Fragrance Mixing
↓
Automated / Semi-Automated Pouring
↓
Cooling
↓
Packaging
↓
완제품 재고
```

구조를 사용한다.

---

# 추가 후보 비교

| 평가항목 | 반려동물 기능성 간식 | 고체 샴푸·클렌징바 | 홈 프래그런스 캔들 |
|---|---:|---:|---:|
| 대중성 | ★★★★★ | ★★★★☆ | ★★★★★ |
| 제조기업 느낌 | ★★★★★ | ★★★★★ | ★★★★☆ |
| BOM 난이도 | ★★★★☆ | ★★★☆☆ | ★★★★★ |
| 생산공정 난이도 | ★★★★☆ | ★★★☆☆ | ★★★★★ |
| 제품별 공정 재사용 | ★★★★★ | ★★★★★ | ★★★★★ |
| MM 적합성 | ★★★★★ | ★★★★★ | ★★★★★ |
| PP 적합성 | ★★★★★ | ★★★★★ | ★★★★☆ |
| SD 적합성 | ★★★★★ | ★★★★☆ | ★★★★★ |
| FI / CO 적합성 | ★★★★★ | ★★★★☆ | ★★★★★ |
| ERP 초보자 적합성 | ★★★★☆ | ★★★☆☆ | ★★★★★ |
| 발표 소재의 재미 | ★★★★★ | ★★★★☆ | ★★★★☆ |

---

# 추가 후보 추천 순위

## 1순위 - 반려동물 기능성 간식

세 후보 중 ERP 프로젝트와 현실적인 제조공정의 균형이 가장 좋다.

```text
원재료 구매
↓
혼합
↓
성형
↓
건조
↓
코팅
↓
포장
↓
판매
```

라는 전체 흐름이 명확하다.

제품별 기능성 Ingredient만 변경하여 여러 완제품을 만들 수 있기 때문에 BOM과 Routing도 재사용하기 쉽다.

---

## 2순위 - 홈 프래그런스 캔들

ERP를 처음 배우는 팀이라는 점까지 고려하면 가장 구현하기 편한 후보이다.

단순하지만

```text
Wax Melting
→ Mixing
→ Pouring
→ Cooling
→ Finishing
→ Packaging
```

이라는 실제 제조공정이 존재하기 때문에 단순 완제품 유통회사와는 차이가 있다.

식품처럼 복잡한 유통기한이나 배합문제도 비교적 적다.

---

## 3순위 - 고체 샴푸·클렌징바

제조업다운 느낌은 세 후보 중 상당히 강하다.

특히

```text
Mixing
→ Homogenizing
→ Extrusion
→ Cutting
→ Pressing
→ Packaging
```

공정이 PP 프로젝트에 잘 맞는다.

다만 Surfactant 등의 화장품 원료가 처음 접하는 사람에게 조금 생소하고, 산업을 깊게 조사하기 시작하면 배합과 품질관리가 복잡해질 수 있다는 점이 단점이다.

---

---

# ERP 구현용 생산공정 축약안

실제 제조기업의 생산공정을 모두 SAP에 세부적으로 구현할 필요는 없다.

이번 프로젝트에서는 실제 산업의 제조공정과 기업 정체성은 유지하되, SAP ERP에서 관리할 필요가 있는 핵심 생산단계만 추려서 **4~5개의 주요 Operation 또는 Work Center**로 단순화하는 방향을 고려한다.

즉,

```text
실제 제조현장
= 세부 작업이 많음

↓

ERP 프로젝트

↓

핵심 생산단계 4~5개로 추상화
```

하는 방식이다.

---

## 기본 설계 원칙

초보자가 처음 SAP ERP를 구축한다는 점을 고려하여 생산공정은 다음 수준을 권장한다.

| 항목 | 권장 규모 |
|---|---:|
| 완제품 FG | 2~3개 |
| 원재료 RM | 약 5~8개 |
| 반제품 SFG | 0~1개 |
| Plant | 1개 |
| Storage Location | 2~3개 |
| Vendor | 2~3개 |
| Work Center | 3~5개 |
| 핵심 생산 Operation | 4~5개 |
| Sales Organization | 1개 |
| Distribution Channel | 2개 |
| Shipping Point | 1개 |

가능하면 제품별로 별도의 생산라인을 만들지 않고 **공통 Routing을 재사용**한다.

---

# Candidate 1. 고단백 영양바

## 실제 제조공정

실제 생산과정은 다음과 같이 세분화할 수 있다.

```text
Raw Material Receiving
↓
Weighing & Batching
↓
Binder Preparation
↓
Mixing
↓
Forming / Extrusion
↓
Cooling
↓
Cutting
↓
Coating
↓
Final Cooling
↓
Packaging
```

하지만 ERP에서는 모든 단계를 각각 별도의 Work Center로 만들 필요는 없다.

---

## SAP 구현용 축약 공정

```text
Mixing
↓
Forming
↓
Cooling & Cutting
↓
Coating
↓
Packaging
```

### Work Center 예시

```text
WC01 - Mixing
WC02 - Forming
WC03 - Cooling & Cutting
WC04 - Coating
WC05 - Packaging
```

### 통합되는 실제 작업

| SAP Operation | 포함되는 실제 작업 |
|---|---|
| Mixing | 원재료 계량 + Binder 준비 + 혼합 |
| Forming | Extrusion 또는 성형 |
| Cooling & Cutting | 냉각 + 절단 |
| Coating | 제품별 Chocolate / Yogurt Coating |
| Packaging | 개별포장 + 박스포장 |

### 평가

**난이도: 보통**

맛이 바뀌더라도 동일한 Routing을 사용할 수 있다.

```text
Choco Peanut
Salted Caramel
Berry Yogurt

→ 모두 동일 Routing 사용
```

제품별 차이는 Flavor와 Coating 등 일부 BOM 자재로 표현한다.

---

# Candidate 2. 고단백 스낵 / Protein Chips

## 실제 제조공정

```text
Raw Material Receiving
↓
Weighing
↓
Dry Mixing
↓
Extrusion
↓
Forming
↓
Cutting
↓
Drying
↓
Oil Coating
↓
Seasoning
↓
Cooling
↓
Packaging
```

실제 생산라인에서는 더 세분화될 수 있지만 ERP에서는 핵심 단계만 관리한다.

---

## SAP 구현용 축약 공정

```text
Mixing
↓
Extrusion & Forming
↓
Drying
↓
Seasoning
↓
Packaging
```

### Work Center 예시

```text
WC01 - Mixing
WC02 - Extrusion
WC03 - Drying
WC04 - Seasoning
WC05 - Packaging
```

### 통합되는 실제 작업

| SAP Operation | 포함되는 실제 작업 |
|---|---|
| Mixing | 계량 + 원재료 혼합 |
| Extrusion & Forming | 압출 + 성형 + 절단 |
| Drying | 건조 또는 Baking |
| Seasoning | Oil Coating + 제품별 Seasoning |
| Packaging | 냉각 + 포장 |

### 평가

**난이도: 보통~약간 어려움**

제품별 생산공정은 동일하게 유지하고 Seasoning만 변경할 수 있다.

```text
Common Protein Chip Base
+
Sea Salt Seasoning
BBQ Seasoning
Spicy Seasoning
```

단, `Extrusion`이라는 생산공정이 처음에는 다소 생소할 수 있다.

---

# Candidate 3. RTD 단백질 음료

## 실제 제조공정

```text
Raw Material Receiving
↓
Weighing
↓
Mixing / Dissolving
↓
Homogenization
↓
Heat Treatment
↓
Cooling
↓
Filling
↓
Capping
↓
Labeling
↓
Case Packing
```

---

## SAP 구현용 축약 공정

```text
Mixing
↓
Homogenization
↓
Heat Treatment
↓
Filling
↓
Packaging
```

### Work Center 예시

```text
WC01 - Mixing
WC02 - Homogenization
WC03 - Heat Treatment
WC04 - Filling
WC05 - Packaging
```

### 통합되는 실제 작업

| SAP Operation | 포함되는 실제 작업 |
|---|---|
| Mixing | 계량 + 용해 + 혼합 |
| Homogenization | 균질화 |
| Heat Treatment | 살균 또는 UHT 등 열처리 |
| Filling | 충전 + Capping |
| Packaging | Labeling + Case Packing |

### 평가

**난이도: 어려운 편**

제품별 Flavor만 변경할 수 있다는 장점은 있지만,

```text
Homogenization
Heat Treatment
Filling
```

등 음료 제조 특유의 공정이 있어 다른 후보보다 이해해야 할 개념이 많다.

SAP ERP를 처음 구현하는 팀이라면 우선순위를 낮추는 것이 안전하다.

---

# Candidate 4. 반려동물 기능성 간식

## 실제 제조공정

```text
Raw Material Receiving
↓
Weighing & Batching
↓
Mixing
↓
Forming / Extrusion
↓
Cutting
↓
Baking / Drying
↓
Coating
↓
Cooling
↓
Packaging
```

---

## SAP 구현용 축약 공정

```text
Mixing
↓
Forming
↓
Drying
↓
Coating
↓
Packaging
```

### Work Center 예시

```text
WC01 - Mixing
WC02 - Forming
WC03 - Drying
WC04 - Coating
WC05 - Packaging
```

### 통합되는 실제 작업

| SAP Operation | 포함되는 실제 작업 |
|---|---|
| Mixing | 계량 + 기본 원료 + 기능성 원료 혼합 |
| Forming | 압출 또는 성형 + 절단 |
| Drying | Baking 또는 Drying |
| Coating | Flavor / Palatant 적용 + Cooling |
| Packaging | 계량 + Pouch 포장 + Carton 포장 |

### 평가

**난이도: 보통**

제품 기능이 달라도 동일 Routing을 사용하기 쉽다.

```text
Common Treat Base
+
Dental Ingredient

Common Treat Base
+
Digestive Ingredient

Common Treat Base
+
Skin & Coat Ingredient
```

따라서 제품별 차이는 BOM에서 표현하고 생산공정은 그대로 유지할 수 있다.

---

# Candidate 5. 고체 샴푸·클렌징바

## 실제 제조공정

```text
Raw Material Receiving
↓
Weighing
↓
Powder Mixing
↓
Liquid Ingredient Mixing
↓
Homogenizing
↓
Extrusion
↓
Cutting
↓
Pressing / Stamping
↓
Cooling
↓
Inspection
↓
Packaging
```

---

## SAP 구현용 축약 공정

```text
Mixing
↓
Homogenizing
↓
Extrusion
↓
Cutting & Pressing
↓
Packaging
```

### Work Center 예시

```text
WC01 - Mixing
WC02 - Homogenizing
WC03 - Extrusion
WC04 - Cutting & Pressing
WC05 - Packaging
```

### 통합되는 실제 작업

| SAP Operation | 포함되는 실제 작업 |
|---|---|
| Mixing | 계량 + 분말/액상 원료 혼합 |
| Homogenizing | 원료 균질화 |
| Extrusion | Bar 형태로 성형 |
| Cutting & Pressing | 절단 + 모양 성형 + Stamping |
| Packaging | 냉각 + 검사 + 포장 |

### 평가

**난이도: 보통~약간 어려움**

생산공정 자체는 SAP에 적용하기 좋지만 원재료명이 다소 전문적이다.

예:

```text
Surfactant
Conditioning Agent
Functional Additive
Fragrance
```

따라서 화학적인 세부 Formula까지 다루지 않고 주요 원재료만 BOM에 포함하는 것이 적절하다.

---

# Candidate 6. 홈 프래그런스 캔들

## 실제 제조공정

```text
Raw Material Receiving
↓
Wax Melting
↓
Wick Preparation
↓
Container Preparation
↓
Fragrance / Color Mixing
↓
Pouring
↓
Cooling
↓
Finishing
↓
Inspection
↓
Labeling
↓
Packaging
```

---

## SAP 구현용 축약 공정

```text
Melting & Mixing
↓
Filling
↓
Cooling
↓
Finishing & Inspection
↓
Packaging
```

또는 프로젝트를 더 단순하게 하고 싶다면 다음 4단계로도 구성할 수 있다.

```text
Mixing
↓
Filling
↓
Cooling & Inspection
↓
Packaging
```

### Work Center 예시

#### 5단계 버전

```text
WC01 - Melting & Mixing
WC02 - Filling
WC03 - Cooling
WC04 - Finishing & Inspection
WC05 - Packaging
```

#### 단순화 버전

```text
WC01 - Mixing
WC02 - Filling
WC03 - Cooling & Inspection
WC04 - Packaging
```

### 통합되는 실제 작업

| SAP Operation | 포함되는 실제 작업 |
|---|---|
| Melting & Mixing | Wax 용융 + Fragrance / Color 혼합 |
| Filling | Wick 및 Container 준비 + Wax Pouring |
| Cooling | Wax 냉각 및 고형화 |
| Finishing & Inspection | Wick 정리 + 외관 검사 |
| Packaging | Label + Lid + Carton 포장 |

### 평가

**난이도: 쉬움**

제품별 향만 변경하고 동일한 Routing을 사용할 수 있다.

```text
Forest Candle
Citrus Candle
Cotton Candle

→ 동일 생산공정
→ Fragrance만 변경
```

ERP를 처음 구축하는 팀에게 가장 부담이 적은 후보 중 하나이다.

---

# 후보별 SAP 축약 공정 비교

| Candidate | SAP에서 사용할 핵심 공정 | 공정 수 | 예상 난이도 |
|---|---|---:|---|
| 고단백 영양바 | Mixing → Forming → Cooling & Cutting → Coating → Packaging | 5 | 보통 |
| Protein Chips | Mixing → Extrusion → Drying → Seasoning → Packaging | 5 | 보통~약간 어려움 |
| RTD 단백질 음료 | Mixing → Homogenization → Heat Treatment → Filling → Packaging | 5 | 어려움 |
| 반려동물 기능성 간식 | Mixing → Forming → Drying → Coating → Packaging | 5 | 보통 |
| 고체 샴푸 | Mixing → Homogenizing → Extrusion → Cutting & Pressing → Packaging | 5 | 보통~약간 어려움 |
| 캔들 | Mixing → Filling → Cooling & Inspection → Packaging | 4 | 쉬움 |

---

# ERP 초보자 기준 추천

SAP ERP를 처음 설계하는 팀이라는 점을 고려하면 다음 정도의 복잡도가 적절하다.

## 가장 안전한 수준

```text
원재료
↓
Operation 1
↓
Operation 2
↓
Operation 3
↓
Operation 4
↓
완제품
```

즉 **4개 정도의 핵심 생산공정**만으로 제품을 설명할 수 있는 산업이 가장 편하다.

---

## 적당한 수준

```text
원재료
↓
Operation 1
↓
Operation 2
↓
Operation 3
↓
Operation 4
↓
Operation 5
↓
완제품
```

**5개 정도의 핵심 생산공정**까지는 충분히 관리 가능한 수준으로 본다.

---

## 지양하는 수준

```text
원재료
↓
공정 1
↓
공정 2
↓
공정 3
↓
공정 4
↓
공정 5
↓
공정 6
↓
공정 7
↓
공정 8
↓
공정 9
↓
공정 10
↓
완제품
```

실제 공장에서 작업이 10단계라고 하더라도 SAP 프로젝트에서 모든 단계를 별도의 Work Center나 Operation으로 구성할 필요는 없다.

---

# 현재 권장 프로젝트 스케일

산업 최종 선정 후 최초 설계는 다음 규모에서 시작한다.

```text
Company Code
1개

Plant
1개

Storage Location
2~3개

Finished Goods
2~3개

Raw Materials
5~8개

Semi-Finished Goods
0~1개

Vendor
2~3개

Customer
2~3개

Work Center
3~5개

Routing
공통 Routing 1개 중심

Sales Organization
1개

Distribution Channel
2개

Shipping Point
1개
```

먼저 위 규모로 기본 프로세스를 완성한 뒤, 실제 SAP Configuration 과정에서 필요성이 확인될 경우 조직이나 자재를 추가한다.

---

# 핵심 원칙

> **실제 제조공정을 없애는 것이 아니라, ERP에서 관리할 필요가 있는 핵심 작업 단위로 묶는다.**

예를 들어 실제 공장에서

```text
계량
↓
Binder 준비
↓
분말 투입
↓
액상 원료 투입
↓
혼합
```

의 다섯 작업이 있더라도 SAP에서는

```text
Mixing
```

하나의 Operation으로 표현할 수 있다.

반대로

```text
원재료 구매
↓
완제품 포장
```

처럼 해당 산업의 핵심 제조공정 자체를 제거하는 수준까지 단순화하지 않는다.

따라서 산업 선정 시 가장 중요한 기준은

> **"실제 공정을 4~5개의 SAP Operation으로 줄였을 때도 해당 산업의 제조기업처럼 보이는가?"**

이다.

# 8. 현재 Decision

아직 최종 산업은 확정하지 않는다.

현재 우선 검토 순위는 다음과 같다.

```text
1. 고단백 영양바 제조업
2. 고단백 스낵 / Protein Chips 제조업
3. RTD 단백질 음료 제조업
```

팀 회의에서 다음 사항을 함께 검토한 뒤 최종 산업을 결정한다.

- 팀원별 선호도
- BOM 난이도
- PP 구현 난이도
- 생산공정 현실성
- SAP Configuration 가능 범위
- SD 판매 프로세스 구성 가능성
- 제품별 원가 차이
- 최종 발표에서의 차별성

---

# 9. Next Action

산업 최종 선정 후 다음 작업을 진행한다.

1. 고객사명 결정
2. 대표 완제품 2~3개 선정
3. Material Code 설계
4. 실제 BOM 수량 결정
5. Vendor 설정
6. Plant 및 Storage Location 결정
7. Work Center 결정
8. Routing 확정
9. Sales Organization 결정
10. Distribution Channel 결정
11. Division 결정
12. Customer 설정
13. AS-IS 문제 구체화
14. TO-BE 프로세스 설계
15. PP / MM / SD / FI / CO 모듈 간 연결 구조 설계
