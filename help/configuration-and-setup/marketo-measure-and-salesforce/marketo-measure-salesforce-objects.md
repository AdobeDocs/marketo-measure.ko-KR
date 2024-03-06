---
unique-page-id: 18874582
description: "[!DNL Marketo Measure] Salesforce 개체 - [!DNL Marketo Measure]"
title: "[!DNL Marketo Measure] Salesforce 개체"
exl-id: d5d6f334-6531-40fa-b043-75b49d8f43d5
feature: Salesforce
source-git-commit: 9e672d0c568ee0b889461bb8ba6fc6333edf31ce
workflow-type: tm+mt
source-wordcount: '924'
ht-degree: 0%

---

# [!DNL Marketo Measure] Salesforce 개체 {#marketo-measure-salesforce-objects}

>[!NOTE]
>
>&quot; &quot;을 지정하는 지침이 표시될 수 있습니다.[!DNL Marketo Measure]설명서에는 &quot;가 있지만 CRM에는 &quot;Bizible&quot;이 표시됩니다. 이를 업데이트하고 리브랜딩이 곧 CRM에 반영되도록 노력하고 있습니다.

날짜 [!DNL Marketo Measure] 이(가)에 설치되었습니다. [!DNL Salesforce] (SFDC), 여러 사용자 지정 [!DNL Marketo Measure] 개체가 추가됩니다. 이 문서에서는 이러한 사용자 정의 중 일부에 대해 설명합니다 [!DNL Marketo Measure] 개체. 다음과 같은 일부 개체 [!DNL Marketo Measure] 에 추가 [!DNL Salesforce] 은(는)

* [구매자 접점](#touchpoint)
* [구매자 속성 접점](#attribution)
* [[!DNL Marketo Measure] 개인](#person)
* [[!DNL Marketo Measure] A/B 테스트](#ab)
* [[!DNL Marketo Measure] 이벤트](#events)

추적하려는 항목에서 캡처한 터치포인트는 설치 시 만들어진 사용자 지정 개체에 기록됩니다. [!DNL Bizible Salesforce] 패키지.

[!DNL Marketo Measure] 특정 표준과 관련된 객체 [!DNL Salesforce] 개체. 이를 통해 다음을 보고할 수 있습니다. [!DNL Marketo Measure] 및 [!DNL Salesforce] 개체를 함께 사용합니다. 아래 표에는 다음 항목이 표시됩니다. [!DNL Salesforce] 개체 [!DNL Marketo Measure] 객체와 관련된 항목입니다.

![](assets/1-1.png)

## 구매자 접점 {#buyer-touchpoint}

다음 [!UICONTROL Buyer Touchpoint] (BT) 오브젝트는 한 개인의 마케팅 이야기를 들려줍니다. 여기에는 리드 및 연락처에서 생성된 마케팅 터치포인트와 관련된 모든 데이터가 포함됩니다. BT는 터치포인트의 출처 또는 특정 리드/연락처를 웹 사이트로 가져온 광고 캠페인과 같은 정보를 제공합니다.

BT 개체는 리드 및 연락처 페이지에 다음으로 표시됩니다. **관련 목록** (아래 이미지 참조)

![](assets/2-1.png)

BT Related List 에는 Lead 또는 Contact에 속하는 모든 터치포인트가 표시됩니다. 목록 내에서 사용자 정의 [!DNL Marketo Measure] 각 터치포인트에 대한 세부 정보를 제공하는 필드. 구매자 접점 ID 번호를 클릭하면 구매자 접점 세부 정보 페이지로 이동합니다. 이 페이지는 해당 웹 세션 동안 잠재 고객/연락처가 방문한 첫 번째 웹 페이지(**랜딩 페이지**).

## 구매자 속성 접점 {#buyer-attribution-touchpoint}

다음 [!UICONTROL Buyer Attribution Touchpoint] 오브젝트는 기회와 관련된 연락처의 마케팅 상호 작용 스토리를 제공합니다. 다음을 표시합니다. *속성* 마케팅 접점 관련 데이터. 이 개체를 사용하면 각 마케팅 접점에 기여하는 매출 크레딧의 양을 확인할 수 있습니다. 사용 중인 속성 모델 유형에 따라 터치포인트에 속하는 매출의 비율이 결정됩니다.

구매자 속성 터치포인트(BAT)는 구매자 터치포인트(BT) 데이터가 있는 연락처와 관련된 기회가 생성된 후에만 생성됩니다. BAT는 Opportunity 가 없으면 생성되지 않습니다. Opportunity 가 생성되면 BAT 오브젝트는 [!DNL Salesforce] *금액* 터치포인트에 기여할 매출액을 파악하는 영업 기회의 필드.

A **워크플로우** 을(를) 사용하는 경우 만들어야 합니다. [사용자 정의 금액 필드](/help/advanced-marketo-measure-features/custom-revenue-amount/using-a-custom-revenue-amount-field.md) 영업 기회 개체에 매출을 표시합니다. [!DNL Marketo Measure] 은 사용자 정의 금액 필드에 표시되는 정보를 읽을 수 없으므로, 터치포인트에서 매출 기여도 분석 데이터를 채울 수 없습니다. 이 워크플로에서는 **[!DNL Marketo Measure]영업 기회 금액** 필드, 다음 중 하나 [!DNL Marketo Measure] 사용자 정의 필드 - 사용자 정의 금액 필드의 수익 값을 Opportunity Amount 필드에 매핑합니다.

![](assets/3-1.png)

BAT 개체는 [!UICONTROL Opportunity], [!UICONTROL Contact], 및 [!UICONTROL Account] 개체를 관련 목록으로 표시합니다. 이 목록에는 Opportunity에 속한 Attribution 데이터가 있는 모든 터치포인트가 표시됩니다. 구매자 속성 접점 ID를 클릭하면 구매자 속성 접점 세부 정보 페이지로 이동합니다. 여기에서 터치포인트가 어디에서 왔는지에 대한 보다 구체적인 속성 데이터와 정보를 볼 수 있습니다(구매자 터치포인트 오브젝트에서 제공되는 것과 유사).

## [!DNL Marketo Measure] 개인 {#marketo-measure-person}

다음 [!DNL Marketo Measure] 개인 개체는 리드 및 연락처 개체와 관련이 있습니다. 기본적으로 Salesforce는 동일한 보고서에서 리드 및 연락처 개체를 사용하여 보고서를 만들 수 있는 옵션을 제공하지 않습니다. Lead 및 Contact Object 와 관련된 [!DNL Marketo Measure] 개인을 사용하면 동일한 보고서 내에서 두 객체에 대해 보고할 수 있습니다. 이 기능은 잠재 고객이 연락처로 전환된 경우 특히 유용합니다. 다음에서: [!DNL Marketo Measure] 개인 레코드 해당 리드 및/또는 연락처 레코드에 대한 조회, 해당 사용자와 연결된 터치포인트의 관련 목록, 개인 ID(항상 리드/연락처의 이메일 주소)를 볼 수 있습니다. 다음 이후 [!DNL Marketo Measure] 사용자 는 리드 및 연락처 오브젝트와 관련이 있으며, [!DNL Marketo Measure] 구매자 속성 터치포인트에 연결된 개인 레코드. 다음은 의 예입니다 [!DNL Marketo Measure] Salesforce 내의 개인 레코드:

![](assets/4.png)

## [!DNL Marketo Measure] A/B 테스트 {#marketo-measure-a-b-test}

다음을 통해 A/B 테스트를 실행하는 경우 [!DNL Optimizely] 또는 VWO(Visual Web Optimizer)를 사용하여 이러한 계정을 [!DNL Marketo Measure] 계정 을 사용하여 Salesforce 내에서 A/B 테스트 데이터를 볼 수 있습니다. 다음 [!DNL Marketo Measure] A/B 테스트 개체를 사용하면 Optimizely/VWO에서 A/B 테스트 데이터를 가져와서 리드 및 연락처에 연결할 수 있습니다.

![](assets/5.png)

다음 [!DNL Marketo Measure] A/B 테스트 개체가에 관련 목록으로 표시됨 [!UICONTROL Leads], [!UICONTROL Contacts] 및 [!UICONTROL Opportunity] 페이지. 이 목록은 Optimizly 또는 VWO를 통해 실행 중인 모든 실험 및 변형을 표시하며, 이를 통해 특정 리드 및 연락처와 관련된 실험/변형을 확인할 수 있습니다.

## [!DNL Marketo Measure] 이벤트 {#marketo-measure-events}

다음 [!DNL Marketo Measure] 이벤트 개체를 사용하면 웹 사이트에서 발생하는 특정 이벤트를 추적할 수 있습니다. 웹 사이트에서 발생하는 특정 이벤트를 추적하려면 페이지에 [!DNL Marketo Measure] Javascript. 캡처된 정보는 [!DNL Marketo Measure] 개체 관련 목록: 다음에서 찾을 수 있음: [!UICONTROL Leads], [!UICONTROL Contacts] 및 [!UICONTROL Opportunity] 페이지. 다음 [!DNL Marketo Measure] Events 개체 *다음이 아님* 속성 데이터에 연결합니다. 이 개체의 목적은 사람들이 웹 사이트에서 특정 작업을 수행하는지 확인하는 것입니다.

## [!DNL Marketo Measure] 필드 {#marketo-measure-fields}

에 의해 캡처된 데이터 [!DNL Marketo Measure] JavaScript가 사용자 지정으로 푸시됨 [!DNL Marketo Measure] 내 필드 [!DNL Marketo Measure] 개체. 특정 필드는 특정 개체에만 있습니다. 다음을 검토할 수 있습니다. [용어집[!DNL Marketo Measure] 필드]](/help/introduction-to-marketo-measure/overview-resources/glossary-of-marketo-measure-fields.md) 및 a [관련 항목 시각화 [!DNL Marketo Measure] 오브젝트](/help/configuration-and-setup/marketo-measure-and-salesforce/marketo-measure-object-and-field-taxonomy.md).

## [!DNL Marketo Measure] 보고서 및 대시보드 {#marketo-measure-reports-and-dashboards}

다음 [!DNL Marketo Measure] 에 추가된 보고서 및 대시보드 [!DNL Salesforce] 에서는 즉시 사용 가능한 보고 및 데이터 시각화 기능을 제공합니다. 기본입니다 [!DNL Marketo Measure] 접점 데이터를 빠르게 구성, 분석 및 이해할 수 있는 보고서입니다.
