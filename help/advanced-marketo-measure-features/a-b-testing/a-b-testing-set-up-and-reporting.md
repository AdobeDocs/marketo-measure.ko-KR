---
unique-page-id: 18874773
description: A/B 테스트 설정 및 보고 - [!DNL Marketo Measure]
title: A/B 테스트 설정 및 보고
exl-id: 9a3f0731-5909-4fbf-a35a-9608ff561061
feature: A/B Testing
source-git-commit: 915e9c5a968ffd9de713b4308cadb91768613fc5
workflow-type: tm+mt
source-wordcount: '399'
ht-degree: 0%

---

# A/B 테스트 설정 및 보고 {#a-b-testing-set-up-and-reporting}

[!DNL Marketo Measure] A/B 테스트 통합을 통해 [최적](https://www.optimizely.com/){target="_blank"} 및 VWO 사이트 실험의 매출 영향을 추적할 수 있습니다. 이 문서에서는 리드, [!UICONTROL Contact], 사례 및 [!UICONTROL Opportunity] 페이지 레이아웃에 [!DNL Marketo Measure] A/B 테스트 섹션을 추가하는 방법에 대한 지침을 제공합니다. 또한 [!DNL Marketo Measure] A/B 보고서 유형을 실행하기 위한 일반적인 보고 사례 및 권장 사항도 다룹니다.

## 설정 {#set-up}

잠재 고객, 연락처, 사례 및 기회에 대한 [!DNL Marketo Measure] A/B 테스트 섹션을 추가합니다. [!DNL Marketo Measure] A/B 테스트 통합을 통해 [최적](https://www.optimizely.com/){target="_blank"} 및 [VWO](https://vwo.com/){target="_blank"} 사이트 실험의 매출 영향을 추적할 수 있습니다.

1. 패키지 [!DNL Marketo Measure] v3.9 이상을 사용 중인지 확인하십시오. [!UICONTROL Salesforce] >[!UICONTROL Set Up] > [!UICONTROL Installed packages](으)로 이동하여 이 작업을 수행할 수 있습니다.
1. 리드 페이지 레이아웃을 편집하고 **[!DNL Marketo Measure]A/B 테스트** 관련 목록을 페이지에 추가하십시오.

   ![](assets/1.png)

1. [!UICONTROL Wrench] 단추를 클릭합니다. 선택한 필드 목록에서 스톡 &quot;ID&quot; 필드를 제거합니다. **[!UICONTROL Experiment]**, **[!UICONTROL Variation]** 및 **[!UICONTROL DateReported]** 필드를 추가합니다. &quot;[!UICONTROL Sort by]&quot;을(를) **[!UICONTROL Date Reported]**(으)로 변경하고 드롭다운에서 **[!UICONTROL Descending]**&#x200B;을(를) 선택합니다.

   ![](assets/2.png)

1. [!UICONTROL Buttons]에서 **[!UICONTROL New]** 선택을 취소합니다.

   ![](assets/3.png)

1. 이 기능을 사용하려면 [!DNL Marketo Measure] 담당자 또는 [Marketo 지원](https://nation.marketo.com/t5/support/ct-p/Support){target="_blank"}에 문의하십시오.

## 보고 {#reporting}

고객은 리드, 연락처 및 기회와 관련하여 A/B 테스트에 대해 보고할 수 있는 두 가지 [!DNL Marketo Measure] A/B 보고서 유형에 액세스할 수 있습니다.

* [!DNL Marketo Measure] A/BTests
* 연락처가 있는 A/BT 집합 [!DNL Marketo Measure]개
* 리드가 있는 A/BT 테스트 [!DNL Marketo Measure]개
* 영업 기회가 있는 A/BT 세트 [!DNL Marketo Measure]개

![](assets/4.png)

A/B 보고서 유형은 A/B 테스트에 노출된 잠재 고객, 연락처 또는 기회를 보고하는 데 사용됩니다. 또한 이 보고서는 A/B 테스트에 노출된 Opportunity 와 관련된 매출액을 보여 줍니다.

Optimizely/VWO는 콘텐츠 변형 플랫폼이며 마케팅 채널이 아닙니다. 따라서 이러한 [!DNL Marketo Measure] A/B 보고서 유형은 Buyer Touchpoint 보고서와 다르게 사용됩니다. 구매자 접점 보고서 유형은 어떤 마케팅 채널(유료 광고, 웹 다이렉트, 소셜)이 잠재 고객 또는 연락처를 특정 페이지로 유도했는지 파악하는 데 사용됩니다. 그러나 [!DNL Marketo Measure] A/B 보고서 유형은 변형이 잠재 고객 또는 기회에 어떤 영향을 주었는지 보고하는 데 사용할 수 없습니다. A/B 테스트 변형은 채널이 아니므로 변형에 대한 세부 사항이 구매자 접점에 표시되지 않습니다.

다음은 A/B 테스트에 대해 보고할 때 명확성과 통찰력을 높이는 데 도움이 되는 몇 가지 권장 필드입니다.

* 전환된 잠재 고객
* 실험
* 실험 ID
* 변형
* 변형 ID
* 보고된 날짜

## [!DNL Salesforce] 예제 보고서 {#salesforce-example-reports}

리드를 사용한 **[!DNL Marketo Measure]A/B 테스트**

![](assets/5.png)

**[!DNL Marketo Measure]A/B 테스트(영업 기회 포함)**

![](assets/6.png)
