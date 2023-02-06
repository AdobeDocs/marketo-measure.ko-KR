---
unique-page-id: 18874773
description: A/B 테스트 설정 및 보고 - [!DNL Marketo Measure] - 제품 설명서
title: A/B 테스트 설정 및 보고
exl-id: 9a3f0731-5909-4fbf-a35a-9608ff561061
source-git-commit: b59c79236d3e324e8c8b07c5a6d68bd8176fc8a9
workflow-type: tm+mt
source-wordcount: '412'
ht-degree: 0%

---

# A/B 테스트 설정 및 보고 {#a-b-testing-set-up-and-reporting}

다음 [!DNL Marketo Measure] A/B 테스트 통합을 사용하면 사용자의 매출에 미치는 영향을 추적할 수 있습니다 [최적](https://optimizely.com/){target="_blank"} 및 VWO 사이트 실험. 이 문서에서는 추가 방법에 대한 지침을 제공합니다 [!DNL Marketo Measure] A/B 테스트의 리드 섹션, [!UICONTROL Contact], Case 및 [!UICONTROL Opportunity] 페이지 레이아웃. 또한 실행을 위한 일반 보고 작업 및 권장 사항도 다룹니다 [!DNL Marketo Measure] A/B 보고서 유형.

## 설정 {#set-up}

추가 [!DNL Marketo Measure] A/B Lead, Contact, Case 및 Opportunity 의 테스트 섹션 [!DNL Marketo Measure] A/B 테스트 통합을 사용하면 사용자의 매출에 미치는 영향을 추적할 수 있습니다 [최적](https://optimizely.com/){target="_blank"} and [VWO](https://vwo.com/){target="_blank"} 사이트 실험.

1. 패키지를 사용 중인지 확인합니다 [!DNL Marketo Measure] v3.9 이상 이 작업은 [!UICONTROL Salesforce] >[!UICONTROL Set Up] > [!UICONTROL Installed packages].
1. 리드 페이지 레이아웃을 편집하고 **[!DNL Marketo Measure]A/B 테스트** 관련 페이지 목록

   ![](assets/1.png)

1. 을(를) 클릭합니다. [!UICONTROL Wrench] 버튼을 클릭합니다. 선택한 필드 목록에서 스톡 &quot;Id&quot; 필드를 제거합니다. 추가 **[!UICONTROL Experiment]**, **[!UICONTROL Variation]**, 및 **[!UICONTROL DateReported]** 필드. 변경 &quot;[!UICONTROL Sort by]&quot; **[!UICONTROL Date Reported]**, 을(를) 선택하고 을(를) 선택합니다. **[!UICONTROL Descending]** 을 클릭합니다.

   ![](assets/2.png)

1. 아래 [!UICONTROL Buttons], 선택을 취소합니다 . **[!UICONTROL New]**.

   ![](assets/3.png)

1. 다음 사항에 문의하십시오. [!DNL Marketo Measure] 담당자 [Marketo 지원](https://nation.marketo.com/t5/support/ct-p/Support){target="_blank"} 를 클릭하여 기능을 활성화합니다.

## 보고 {#reporting}

고객은 다음 두 가지 액세스 권한을 갖습니다 [!DNL Marketo Measure] A/B 보고서 유형으로서 리드, 연락처 및 기회와 관련하여 A/B 테스트에 대해 보고할 수 있습니다.

* [!DNL Marketo Measure] A/BTest
* [!DNL Marketo Measure] 연락처가 있는 A/BTest
* [!DNL Marketo Measure] 리드가 있는 A/BTest
* [!DNL Marketo Measure] Opportunity가 있는 A/BTest

![](assets/4.png)

A/B 보고서 유형은 A/B 테스트에 노출된 Lead 또는 Contact 또는 Opportunity 를 보고하는 데 사용됩니다. 또한 A/B 테스트에 노출된 Opportunity 와 연결된 매출액을 표시할 수 있습니다.

Optimizely/VWO는 마케팅 채널이 아니라 컨텐츠 변형 플랫폼이라는 점에 유의해야 합니다. 따라서 다음과 같습니다 [!DNL Marketo Measure] A/B 보고서 유형은 구매자 터치 포인트 보고서와 다르게 사용됩니다. 구매자 터치 포인트 보고서 유형은 특정 페이지에 리드나 연락처를 유도하는 마케팅 채널(예: 유료 광고, 웹 직접, 소셜)을 이해하는 데 사용됩니다. 하지만, [!DNL Marketo Measure] A/B 보고서 유형은 변형이 리드 또는 기회에 미치는 영향을 보고하는 데 사용할 수 없습니다. 또한 A/B 테스트 변형이 채널이 아니므로 변형에 대한 세부 사항이 구매자 터치 포인트에 표시되지 않습니다.

다음은 A/B 테스트에 보고할 때 사용하여 명확성과 통찰력을 높이는 데 도움이 되는 몇 가지 일반적인 필드입니다.

* 변환된 리드
* 실험
* 실험 ID
* Variation
* 변형 ID
* 보고된 날짜

## [!DNL Salesforce] 보고서 예 {#salesforce-example-reports}

**[!DNL Marketo Measure]A/B 테스트(리드 포함)**

![](assets/5.png)

**[!DNL Marketo Measure]A/B 테스트와 Opportunity**

![](assets/6.png)
