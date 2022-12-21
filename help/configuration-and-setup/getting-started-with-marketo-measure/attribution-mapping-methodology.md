---
unique-page-id: 18874716
description: 속성 매핑 방법 - [!DNL Marketo Measure] - 제품 설명서
title: 속성 매핑 방법
exl-id: 4d54dd20-9a82-4b87-8908-ced2bd9c0f2f
source-git-commit: 993a326c377b3b6ff48c4e0114b59297f9ca2ca6
workflow-type: tm+mt
source-wordcount: '599'
ht-degree: 0%

---

# 속성 매핑 방법 {#attribution-mapping-methodology}

속성 매핑 방법론은 CRM(연락처, 기회, 계정)에서 특정 객체를 조회하여 연관된 기회에 속성 터치포인트를 생성하는 프로세스입니다. 즉, [!DNL Marketo Measure] 현재 CRM의 프로세스를 기반으로 속성 모델에 포함할 터치포인트를 이해하는 방법입니다.

## 계정 ID 매핑 {#account-id-mapping}

즉시 [!DNL Marketo Measure] 계정 ID 매핑을 제공합니다. 이것은 [!DNL Marketo Measure] Account 및 Contacts 마케팅 정보를 확인하여 Opportunity 와 연관된 Attribution Touchpoint 를 만듭니다. 아래는 해당 프로세스를 간단하게 나타냅니다.

![](assets/1-1.png)

주의 사항 **모두 아님** 연락처의 터치포인트는 기여도 분석 터치포인트로 Opportunity에 푸시됩니다. Opportunity 의 타임라인(첫 번째 터치 날짜 - 종료 날짜)은 Touchpoint가 Opportunity에 영향을 주는지 여부를 결정합니다. 따라서 Contact A 의 터치포인트가 Opportunity 가 Closed Won/Lost 후 발생한 경우, [!DNL Marketo Measure] 은 해당 터치포인트를 Opportunity에 푸시하지 않습니다. 이 타임라인 프로시저는 다른 모든 속성 개체 매핑에서 실행됩니다.

장점: 이 속성 방식은 대부분의 회사에 매우 효과적입니다. 마케팅 팀은 모든 연락처를 특정 영업 기회(종종 문제)에 연관시키기 위해 영업 팀에 의존하지 않아도 됩니다. 또한 영업 팀이 연락 역할을 연관시키는 경우에도 마케팅 자료와의 다른 연락처의 많은 상호 작용이 누락될 수 있습니다. 마지막으로, 이 방법은 특정 영향력자가 아닌 계정의 전체성에 영향을 미치도록 노력하는 ABM 전략을 지원합니다.

단점: 어떤 항목에 대한 크레딧을 받을 사람을 정의하는 강력한 마케팅 및 판매 SLA가 있는 경우 이 방법은 문제가 될 수 있습니다. 또한 계정 계층을 사용하여 더 큰 계정 내에서 특정 비즈니스 단위를 정의하지 않는 경우(예: IBM)이 되면 한 비즈니스 단위에 고유한 마케팅 상호 작용이 다른 비즈니스 단위 영업 기회에 걸쳐 분산될 수 있습니다.

## 기회 연락처 역할 매핑 {#opportunity-contact-role-mapping}

대부분의 클라이언트는 계정 ID 매핑을 활용하지만, [!DNL Marketo Measure] 는 Opportunity 내에서 Contact 역할(Opportunity 와 연관된 연락처)을 조회하여 속성 프로세스를 분류할 수 있습니다. 이것은 [!DNL Marketo Measure] 에서는 Opportunity의 Contact 역할과 연관된 마케팅 상호 작용만 Buyer Attribution Touchpoint로 푸시합니다. 아래는 이 프로세스를 나타냅니다.

![](assets/2-1.png)

장점: 팀에 매우 정의된 연락처 역할 프로세스가 있는 경우 이러한 유형의 속성 매핑이 이상적입니다. 모든 사람이 속성을 어떻게 분류하는지 완전히 이해하므로 매출과 마케팅을 약간 더 연계할 수 있습니다. 이 프로세스는 조직에서 한 대기업 내의 여러 비즈니스 단위뿐만 아니라 서로 다른 제품을 동시에 판매할 때에도 매우 유용합니다.

단점: 하지만, 적절한 연락 역할 프로세스가 없다면 마케팅은 많은 마케팅 데이터를 잃게 되고 결국 해당 팀은 영업 기회에 영향을 미치는 마케팅 활동에 대해 더 적은 크레딧을 받게 됩니다.

## 영업 기회 기본 연락처 역할 매핑 {#opportunity-primary-contact-role-mapping}

영업 기회에 대한 연락 역할을 단순히 살펴보는 것 외에도 [!DNL Marketo Measure] Opportunity 의 기본 연락처만 볼 수 있도록 더 많은 포커스를 둘 수 있습니다. 이 설정을 염두에 두고, [!DNL Marketo Measure] 은 영업 기회의 기본 연락처와 연관된 마케팅 접점만 선택하고 해당 정보를 특정 기회의 속성 스토리에 푸시합니다. 아래 이미지를 참조하십시오.

![](assets/3.png)

장점: 팀이 영업 기회에 &#39;기본&#39;으로 설정된 연락처에 대한 마케팅 영향을 이해에만 관심이 있는 경우 이 유형의 매핑은 팀에 가장 적합합니다.

단점: 이것은 확실히 가장 덜 사용되는 매핑 프로세스이며 다른 연락처들 간에 기회를 주고 받는 마케팅 영향을 크게 저해할 수 있습니다.
