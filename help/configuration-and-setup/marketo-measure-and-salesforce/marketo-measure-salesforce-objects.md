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

# [!DNL Marketo Measure]개의 Salesforce 개체 {#marketo-measure-salesforce-objects}

>[!NOTE]
>
>설명서에 &quot;[!DNL Marketo Measure]&quot;을(를) 지정하는 지침이 표시될 수 있지만 CRM에는 &quot;Bizible&quot;이 표시됩니다. 이를 업데이트하고 리브랜딩이 곧 CRM에 반영되도록 노력하고 있습니다.

[!DNL Marketo Measure]이(가) [!DNL Salesforce] (SFDC)에 설치되면 여러 사용자 지정 [!DNL Marketo Measure] 개체가 추가됩니다. 이 문서에서는 이러한 사용자 지정 [!DNL Marketo Measure] 개체에 대한 설명을 제공합니다. [!DNL Marketo Measure]에서 [!DNL Salesforce]에 추가하는 일부 개체는 다음과 같습니다.

* [Buyer Touchpoint](#touchpoint)
* [Buyer Attribution Touchpoint](#attribution)
* [[!DNL Marketo Measure]명](#person)
* [[!DNL Marketo Measure] A/B 테스트](#ab)
* [[!DNL Marketo Measure]개 이벤트](#events)

추적하려는 항목에서 캡처한 터치포인트는 [!DNL Bizible Salesforce] 패키지 설치에서 만든 사용자 지정 개체에 기록됩니다.

[!DNL Marketo Measure]개의 개체가 특정 표준 [!DNL Salesforce]개의 개체와 관련되어 있습니다. 이를 통해 [!DNL Marketo Measure] 및 [!DNL Salesforce] 개체에 대해 함께 보고할 수 있습니다. 아래 표는 [!DNL Marketo Measure] 개체와 관련된 [!DNL Salesforce] 개체를 보여 줍니다.

![](assets/1-1.png)

## Buyer Touchpoint {#buyer-touchpoint}

[!UICONTROL Buyer Touchpoint] (BT) 개체는 개인의 마케팅 스토리를 알려줍니다. 여기에는 리드 및 연락처에서 생성된 마케팅 터치포인트와 관련된 모든 데이터가 포함됩니다. BT는 터치포인트의 출처 또는 해당 특정 리드/연락처를 웹 사이트로 가져온 광고 캠페인과 같은 정보를 보여 줍니다.

BT 개체는 리드 및 연락처 페이지에 **관련 목록**(아래 이미지 참조)으로 표시됩니다.

![](assets/2-1.png)

BT Related List 에는 Lead 또는 Contact에 속하는 모든 터치포인트가 표시됩니다. 목록 내에는 각 터치포인트에 대한 자세한 정보를 제공하는 사용자 지정 [!DNL Marketo Measure] 필드가 있습니다. Buyer Touchpoint ID 번호를 클릭하면 해당 웹 세션(**랜딩 페이지**) 중에 방문한 리드/연락처가 첫 번째 웹 페이지와 같이 터치포인트에 대한 자세한 내용을 제공하는 Buyer Touchpoint 세부 정보 페이지로 이동합니다.

## Buyer Attribution Touchpoint {#buyer-attribution-touchpoint}

[!UICONTROL Buyer Attribution Touchpoint] 개체는 영업 기회와 관련된 연락처의 마케팅 인터랙션에 대한 스토리를 알려줍니다. 마케팅 접점과 관련된 *속성* 데이터를 표시합니다. 이 개체를 사용하면 각 마케팅 접점에 기여하는 매출 크레딧의 양을 확인할 수 있습니다. 사용 중인 속성 모델 유형에 따라 터치포인트에 속하는 매출의 비율이 결정됩니다.

구매자 속성 접점(BAT)은 Buyer Touchpoint(BT) 데이터가 있는 연락처와 관련된 Opportunity가 생성된 후에만 생성됩니다. BAT은 Opportunity 가 없으면 생성되지 않습니다. 영업 기회가 만들어지면 BAT 개체는 영업 기회의 [!DNL Salesforce] *금액* 필드를 사용하여 터치 포인트에 지정할 매출의 크기를 이해합니다.

[사용자 지정 금액 필드](/help/advanced-marketo-measure-features/custom-revenue-amount/using-a-custom-revenue-amount-field.md)를 사용하여 영업 기회 개체에 매출을 표시하는 경우 **워크플로우**&#x200B;을(를) 만들어야 합니다. [!DNL Marketo Measure]이(가) 사용자 지정 금액 필드에 표시되는 정보를 읽을 수 없으므로 접점에서 매출 기여도 분석 데이터를 채울 수 없습니다. 이 워크플로에서는 [!DNL Marketo Measure] 사용자 지정 필드 중 하나인 **[!DNL Marketo Measure]영업 기회 금액** 필드를 사용하여 사용자 지정 금액 필드의 수익 값을 영업 기회 금액 필드에 매핑합니다.

![](assets/3-1.png)

BAT 개체가 [!UICONTROL Opportunity], [!UICONTROL Contact] 및 [!UICONTROL Account] 개체에 관련 목록으로 표시됩니다. 이 목록에는 Opportunity에 속한 Attribution 데이터가 있는 모든 터치포인트가 표시됩니다. Buyer Attribution Touchpoint ID를 클릭하면 Buyer Attribution Touchpoint 세부 사항 페이지로 이동합니다. 여기에서 터치포인트가 어디에서 왔는지에 대한 보다 구체적인 속성 데이터와 정보를 볼 수 있습니다(Buyer Touchpoint 오브젝트에서 제공되는 것과 유사).

## [!DNL Marketo Measure]명 {#marketo-measure-person}

[!DNL Marketo Measure]명의 사용자 개체는 잠재 고객 개체와 연락처 개체를 함께 연결합니다. 기본적으로 Salesforce는 동일한 보고서에서 리드 및 연락처 개체를 사용하여 보고서를 만들 수 있는 옵션을 제공하지 않습니다. [!DNL Marketo Measure]명의 사용자가 잠재 고객 및 연락처 개체와 관련하여 동일한 보고서 내에서 두 개체에 대해 보고할 수 있습니다. 이 기능은 잠재 고객이 연락처로 전환된 경우 특히 유용합니다. [!DNL Marketo Measure] 개인 레코드에는 해당 리드 및/또는 연락처 레코드에 대한 조회, 해당 사용자와 연결된 터치포인트의 관련 목록, 개인 ID(항상 리드/연락처의 이메일 주소)가 표시됩니다. [!DNL Marketo Measure]명의 사용자가 잠재 고객 및 연락처 개체에 연결되어 있으므로 Buyer Attribution Touchpoint에 연결된 [!DNL Marketo Measure]명의 사용자 레코드가 없습니다. 다음은 Salesforce 내 [!DNL Marketo Measure] 개인 레코드의 예입니다.

![](assets/4.png)

## [!DNL Marketo Measure] A/B 테스트 {#marketo-measure-a-b-test}

[!DNL Optimizely] 또는 VWO(Visual Web Optimizer)를 통해 A/B 테스트를 실행하는 경우 해당 계정을 [!DNL Marketo Measure] 계정에 연결하여 Salesforce에서 A/B 테스트 데이터를 볼 수 있습니다. [!DNL Marketo Measure] A/B 테스트 개체를 사용하면 Optimizly/VWO에서 A/B 테스트 데이터를 가져와서 리드 및 연락처에 연결할 수 있습니다.

![](assets/5.png)

[!DNL Marketo Measure] A/B 테스트 개체가 [!UICONTROL Leads], [!UICONTROL Contacts] 및 [!UICONTROL Opportunity] 페이지에 관련 목록으로 표시됩니다. 이 목록은 Optimizly 또는 VWO를 통해 실행 중인 모든 실험 및 변형을 표시하며, 이를 통해 특정 리드 및 연락처와 관련된 실험/변형을 확인할 수 있습니다.

## [!DNL Marketo Measure]개 이벤트 {#marketo-measure-events}

[!DNL Marketo Measure] 이벤트 개체를 사용하면 웹 사이트에서 발생하는 특정 이벤트를 추적할 수 있습니다. 웹 사이트에서 발생하는 특정 이벤트를 추적하려면 [!DNL Marketo Measure] Javascript 외에 사용자 지정 코드를 페이지에 추가해야 합니다. 캡처된 정보는 [!UICONTROL Leads], [!UICONTROL Contacts] 및 [!UICONTROL Opportunity] 페이지에서 찾을 수 있는 [!DNL Marketo Measure] 개체 관련 목록에 표시됩니다. [!DNL Marketo Measure] 이벤트 개체 *은(는) 속성 데이터에 연결되지 않습니다*. 이 개체의 목적은 사람들이 웹 사이트에서 특정 작업을 수행하는지 확인하는 것입니다.

## [!DNL Marketo Measure]개 필드 {#marketo-measure-fields}

[!DNL Marketo Measure] JavaScript에서 캡처한 데이터가 [!DNL Marketo Measure] 개체 내의 사용자 지정 [!DNL Marketo Measure] 필드로 푸시됩니다. 특정 필드는 특정 개체에만 있습니다. [용어집([[!DNL Marketo Measure] 필드]](/help/introduction-to-marketo-measure/overview-resources/glossary-of-marketo-measure-fields.md))과 [관련  [!DNL Marketo Measure] 개체](/help/configuration-and-setup/marketo-measure-and-salesforce/marketo-measure-object-and-field-taxonomy.md)의 시각화를 검토할 수 있습니다.

## [!DNL Marketo Measure]개의 보고서 및 대시보드 {#marketo-measure-reports-and-dashboards}

[!DNL Salesforce]에 추가된 [!DNL Marketo Measure] 보고서 및 대시보드는 기본 보고 및 데이터 시각화 기능을 제공합니다. 터치포인트 데이터를 빠르게 구성, 분석 및 이해할 수 있도록 해 주는 기본 [!DNL Marketo Measure] 보고서입니다.
