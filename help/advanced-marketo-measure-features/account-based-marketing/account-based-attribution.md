---
unique-page-id: 18874650
description: 계정 기반 속성 - [!DNL Marketo Measure] - 제품 설명서
title: 계정 기반 속성
exl-id: 9c1a03c8-f884-4c08-97ae-b848cc200038
source-git-commit: b59c79236d3e324e8c8b07c5a6d68bd8176fc8a9
workflow-type: tm+mt
source-wordcount: '276'
ht-degree: 0%

---

# 계정 기반 속성 {#account-based-attribution}

ABM(계정 기반 마케팅)의 증가로 인해 어떻게 해야 하는지 이해하는 것이 중요합니다 [!DNL Marketo Measure] 는 ABM 전략을 보완할 수 있습니다. [!DNL Marketo Measure] 은 각 리드에 대한 각 터치포인트를 표시하고 계정 아래에 연락합니다.

## 다음 [!UICONTROL What] {#the-what}

하나의 Account 아래에 여러 Opportunity 가 있을 경우 다른 Opportunity 는 동일한 처음 두 Touchpoint - 첫 번째 Touch (FT) 및 Lead Creation (LC)을 공유합니다. 새로운 Opportunity 가 생성되면 Opportunity 를 단계 아래로 더 이동시키는 데 기여한 터치포인트에 개별 매출액이 할당됩니다. Opportunity 와 연결된 터치포인트는 Buyer Attribution Touchpoint (BAT)로 간주됩니다.

예를 들어, 아래 계정에는 두 개의 Opportunity 가 있습니다. 첫 번째 Opportunity 의 경우 터치 포인트가 하나만 있습니다. Touchpoint는 FT, LC 및 OC(Opportunity Creation) 터치포인트를 포함합니다. 두 번째 Opportunity 는 첫 번째 Opportunity 와 동일한 FT 및 LC가 있지만 OC Touchpoint 는 다릅니다. 또한 두 번째 Opportunity 에는 첫 번째 Opportunity 의 Closed Date 이후에 발생하는 Opportunity 로 인해 첫 번째 Opportunity 와 연관되지 않은 Touchpoint 가 있습니다.

![](assets/1.jpg)

## 이 기능은 어떤 도움이 됩니까? {#how-does-this-help}

이후 [!DNL Marketo Measure] 는 계정에 연결된 모든 마케팅 상호 작용을 나타냄으로써 마케터는 어떤 계정이 종료될 가능성이 있는지, 회사와 얼마나 자주 관계를 맺고 있는지, 그러한 계약이 어떤 항목인지, 각 참여의 가치가 얼마나 되는지 등을 더 잘 이해할 수 있습니다.

사용 [!DNL Marketo Measure] 그리고 ABM 접근 방식에서는 마케팅 성과가 최종적으로 수익에 따라 결정됩니다. 계정 기반 마케팅 접근 방식으로 이동하려는 경우 다음을 확인하십시오 [ABM Orchestration에 대한 CMO 안내서](https://info.bizible.com/cmos-guide-to-abm-orchestration)ABM 오케스트레이션의 계획, 실행 및 측정 단계를 안내합니다.
