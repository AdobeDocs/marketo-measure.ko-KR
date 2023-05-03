---
description: "[!DNL Salesforce] 패키지 통합 - [!DNL Marketo Measure] - 제품 설명서"
title: "[!DNL Salesforce] 패키지 통합"
source-git-commit: 279d9a18dca59de9ad99113624f4c9b2bcea0d01
workflow-type: tm+mt
source-wordcount: '458'
ht-degree: 0%

---

# [!DNL Salesforce] 패키지 통합 {#salesforce-package-consolidation}

Marketo Measure Salesforce 패키지에 예정된 변경 사항을 발표하게 되어 매우 기쁘게 생각합니다. 사용자 경험을 향상하고 사용을 단순화하기 위해 기존의 모든 패키지를 하나의 포괄적인 패키지로 통합했습니다.

## 패키지 처분 {#package-retirement}

이 통합의 결과로, 현재 V1, V2_EXT, V2_Security 및 모든 보고 패키지는 2023년 8월 이후에 사용이 중단됩니다. V2 패키지가 이미 설치되어 있다면 새 통합 버전으로 업데이트해야 합니다.

## 새 통합 패키지 {#new-consolidated-package}

새로운 통합 V2 패키지는 이전 패키지의 모든 기능과 기능을 통합하여 향상된 사용자 경험을 제공합니다. 업데이트된 이 패키지를 통해 보다 효율적인 마케팅 및 판매 성능 추적을 수행할 수 있으며 고객 행동에 대한 심층적인 통찰력을 얻을 수 있습니다.

## 지원 및 전환 {#support-and-transition}

우리는 이 변경 사항이 조정이 필요할 수 있다는 것을 알고 있으며, 우리는 이 과정에서 고객을 지원할 것을 약속합니다. Adobe [지원 팀](https://nation.marketo.com/t5/support/ct-p/Support){target="_blank"} 모든 질문에 쉽게 답변할 수 있으며 새로운 통합 패키지로 원활하게 전환할 수 있도록 지원합니다.

## 필수 작업 {#retired-actions}

* V2 패키지가 이미 설치되어 있다면 새 통합 버전으로 업데이트해야 합니다.
* 보고 패키지의 보고서나 대시보드가 있는 경우 사용되는 모든 필드가 통합 패키지에 있으므로 수정 없이 쉽게 다시 만들 수 있습니다.
* V2_EXT 패키지의 필드를 사용하는 보고서가 있는 경우 아래 단계를 통해 통합 패키지에서 보고서를 다시 만들 수 있습니다.
   * V2_EXT 필드의 모든 데이터는 터치 포인트 필드에서 사용할 수 있으므로, 터치 포인트 위치에 필터를 추가하여 해당 V2 터치 포인트 필드에서 데이터를 가져오도록 보고서를 수정할 수 있습니다.
   * 광고 컨텐츠 FT에서 &quot;Outreach&quot; 텍스트가 포함된 모든 리드를 가져오는 보고서 예.
      * V2_EXT 쿼리:
         * bizible2_ext__Ad_Content_FT__c에 Outreach 포함

![](assets/salesforce-package-consolidation-1.png)

* 통합 패키지의 해당 쿼리:
   * bizible2__Touchpoint_Position__c에는 FT 및 FT가 포함되어 있습니다.
   * bizible2__Ad_Content__c에 Outreach 포함

![](assets/salesforce-package-consolidation-2.png)

## FAQ {#faq}

**통합 패키지가 기존 패키지의 필드와 충돌합니까?**

통합 패키지를 설치하기 전에 패키지를 제거할 필요가 없습니다. 필드가 다른 네임스페이스에 있으므로 필드에 충돌이 발생하지 않습니다.

**현재 패키지의 데이터를 채우려면 어떻게 해야 합니까?**

티켓을 제출하시면 됩니다 [지원](https://nation.marketo.com/t5/support/ct-p/Support){target="_blank"} 터치 포인트 ID 및 양식 ID 필드를 채울 BT/BAT 데이터 채우기 및 재처리용.

**V1 및 V2_EXT 패키지의 필드를 통합 패키지에서 사용할 수 있습니까?**

예. 통합 패키지에는 V1에 동일한 필드가 포함되며 객체별로 더 분류되고 Touchpoint 필드를 통한 V2_EXT 필드가 포함됩니다.

**V2_EXT 필드를 사용하는 보고서를 통합 패키지에서 다시 만들 수 있습니까?**

예. 다음 단계를 따르십시오 [필수 작업](#retired-actions) 섹션에 있는 마지막 항목이 될 필요가 없습니다.
