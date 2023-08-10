---
description: '[!DNL Salesforce] 패키지 통합 - [!DNL Marketo Measure] - 제품 설명서'
title: '[!DNL Salesforce] 패키지 통합'
exl-id: f1bd5dcb-d021-4140-b6b9-cdb40e566c4b
feature: Salesforce
source-git-commit: 8ac315e7c4110d14811e77ef0586bd663ea1f8ab
workflow-type: tm+mt
source-wordcount: '502'
ht-degree: 0%

---

# [!DNL Salesforce] 패키지 통합 {#salesforce-package-consolidation}

Marketo Measure Salesforce 패키지에 대한 향후 변경 사항을 발표하게 되어 기쁩니다. 사용자 경험을 향상시키고 사용을 단순화하기 위해 기존의 모든 패키지를 포괄적인 단일 패키지로 통합하고 있습니다.

## 패키지 사용 중지 {#package-retirement}

이 통합의 결과로 현재 V1, V2_EXT, V2_Security 및 모든 보고 패키지는 2023년 8월 이후 중단됩니다. V2 패키지가 이미 설치되어 있는 경우 새 통합 버전으로 업데이트해야 합니다.

## 새로운 통합 패키지 {#new-consolidated-package}

새로운 통합 V2 패키지는 이전 패키지의 모든 기능과 결합되어 향상된 사용자 경험을 제공합니다. 이 업데이트된 패키지를 통해 보다 효율적인 마케팅 및 판매 성과 추적을 가능하게 하고 고객 행동에 대한 심층적인 통찰력을 얻을 수 있습니다.

보고 기능을 향상시키기 위해 두 개의 새 필드가 추가되었습니다.

* form_name: 이제 BT/BAT 객체에서 사용할 수 있으며, 이 필드를 통해 사용자는 양식 이름을 기반으로 보고서를 작성할 수 있습니다.
* user_touchpoint_id: 이 필드를 사용하면 사용자가 고유한 사용자 터치포인트 카운트로 보고서를 만들 수 있습니다.

## 지원 및 전환 {#support-and-transition}

이러한 변경은 조정이 필요할 수 있음을 잘 알고 있으며, 이 과정 전반에 걸쳐 여러분을 지원하기 위해 최선을 다하고 있습니다. 당사 [지원 팀](https://nation.marketo.com/t5/support/ct-p/Support){target="_blank"} 는 모든 질문에 쉽게 답변할 수 있으며 새로운 통합 패키지로 원활하게 전환할 수 있도록 지원합니다.

## 필수 작업 {#retired-actions}

* V2 패키지가 이미 설치되어 있는 경우 새 통합 버전으로 업데이트해야 합니다.
* 보고 패키지의 보고서나 대시보드가 있는 경우, 활용된 모든 필드가 통합 패키지에 존재하므로 수정 없이 보고서 또는 대시보드를 쉽게 다시 만들 수 있습니다.
* V2_EXT 패키지의 필드를 사용하는 보고서가 있는 경우 아래 단계를 통해 통합 패키지에서 보고서를 다시 만들 수 있습니다.
   * V2_EXT 필드의 모든 데이터는 터치포인트 필드에서 사용할 수 있으므로, 터치포인트 위치에 필터를 추가하여 해당 V2 터치포인트 필드에서 데이터를 가져오도록 보고서를 수정할 수 있습니다.
   * &quot;Outreach&quot; 텍스트가 포함된 광고 콘텐츠 FT를 사용하는 모든 리드를 가져오는 보고서 예.
      * V2_EXT 쿼리:
         * bizible2_ext__Ad_Content_FT__c에 Outreach 포함

![](assets/package-consolidation-1.png)

* 통합 패키지의 해당 쿼리:
   * bizible2__Touchpoint_Position__c에 FT 및
   * bizible2__Ad_Content__c에 Outreach 포함

![](assets/salesforce-package-consolidation-2.png)

## FAQ {#faq}

**통합 패키지가 기존 패키지의 필드와 충돌합니까?**

통합 패키지를 설치하기 전에 패키지를 제거할 필요가 없습니다. 필드는 다른 네임스페이스에 있으므로 충돌하지 않습니다.

**현재 패키지의 데이터를 채우려면 어떻게 해야 합니까?**

티켓을 접수하실 수 있습니다 [지원 포함](https://nation.marketo.com/t5/support/ct-p/Support){target="_blank"} BT/BAT 데이터를 다시 채우고 재처리하여 터치포인트 ID 및 양식 ID 필드를 채울 수 있습니다.

**V1 및 V2_EXT 패키지의 필드를 통합 패키지에서 사용할 수 있습니까?**

예. 통합 패키지는 V1에 동일한 필드를 포함하고 객체별로 추가 분류하며 터치포인트 필드를 통한 V2_EXT 필드를 포함합니다.

**V2_EXT 필드를 사용하는 보고서를 통합 패키지에서 다시 만들 수 있습니까?**

예. 다음 단계를 따르십시오. [필수 작업](#retired-actions) 위의 섹션.
