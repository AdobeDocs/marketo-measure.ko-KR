---
unique-page-id: 18874582
description: "[!DNL Marketo Measure] Salesforce 개체 - [!DNL Marketo Measure] - 제품 설명서"
title: "[!DNL Marketo Measure] Salesforce 개체"
exl-id: d5d6f334-6531-40fa-b043-75b49d8f43d5
source-git-commit: b59c79236d3e324e8c8b07c5a6d68bd8176fc8a9
workflow-type: tm+mt
source-wordcount: '935'
ht-degree: 0%

---

# [!DNL Marketo Measure] Salesforce 개체 {#marketo-measure-salesforce-objects}

>[!NOTE]
>
>&quot;[!DNL Marketo Measure]&quot;은 설명서이지만 CRM에서 &quot;Bizible&quot;을 참조하십시오. 업데이트를 위해 노력하고 있으며 리브랜딩이 곧 CRM에 반영됩니다.

When [!DNL Marketo Measure] 에 설치되어 있습니다. [!DNL Salesforce] (SFDC), 여러 사용자 지정 [!DNL Marketo Measure] 개체가 추가됩니다. 이 문서에서는 이러한 사용자 정의 중 몇 가지에 대해 설명합니다 [!DNL Marketo Measure] 개체. 일부 객체 [!DNL Marketo Measure] 에 추가 [!DNL Salesforce] 입니다.

* [구매자 터치포인트](#touchpoint)
* [구매자 기여도 분석 터치포인트](#attribution)
* [[!DNL Marketo Measure] 개인](#person)
* [[!DNL Marketo Measure] A/B 테스트](#ab)
* [[!DNL Marketo Measure] 이벤트](#events)

추적하려는 항목으로 캡처된 터치포인트는 [!DNL Bizible Salesforce] 패키지.

[!DNL Marketo Measure] 특정 표준과 관련된 객체 [!DNL Salesforce] 개체. 이에 대해 보고할 수 있습니다 [!DNL Marketo Measure] 및 [!DNL Salesforce] 개체를 함께 사용합니다. 아래 표에는 어떤 것이 나와 있는지 나와 있습니다 [!DNL Salesforce] 개체 [!DNL Marketo Measure] 개체는 와(과) 관련되어 있습니다.

![](assets/1-1.png)

## 구매자 터치포인트 {#buyer-touchpoint}

다음 [!UICONTROL Buyer Touchpoint] (BT) 개체는 개인의 마케팅 스토리를 알려줍니다. 여기에는 리드 및 연락처에서 생성한 마케팅 접점과 관련된 모든 데이터가 포함됩니다. BT는 터치포인트에서 가져온 마케팅 채널 또는 특정 리드/연락처를 웹 사이트로 가져온 광고 캠페인과 같은 정보를 표시합니다.

BT 개체는 Lead 및 Contacts 페이지에 **관련 목록** (아래 이미지 참조).

![](assets/2-1.png)

BT 관련 목록에는 Lead 또는 Contact에 속하는 모든 터치포인트가 표시됩니다. 목록 내에 사용자 지정 항목이 있습니다 [!DNL Marketo Measure] 각 터치 포인트에 대한 세부 사항을 제공하는 필드. 구매자 터치포인트 ID 번호를 클릭하면 구매자 터치포인트 세부 사항 페이지로 이동합니다. 이 페이지는 웹 세션 동안 방문했던 첫 번째 웹 페이지(**랜딩 페이지**).

## 구매자 기여도 분석 터치포인트 {#buyer-attribution-touchpoint}

다음 [!UICONTROL Buyer Attribution Touchpoint] 개체는 기회와 관련된 연락처의 마케팅 상호 작용에 대한 이야기를 알려줍니다. 이 구성 요소는 *기여도 분석* 마케팅 접점과 관련된 데이터. 이 개체를 사용하면 각 마케팅 접점에 속하는 매출 크레딧의 양을 볼 수 있습니다. 사용 중인 속성 모델 유형은 터치포인트에 속하는 매출액의 비율을 결정합니다.

구매자 기여도 분석 터치포인트(BAT)는 구매자 터치포인트(BT) 데이터가 있는 연락처와 관련된 Opportunity가 생성된 후에만 생성됩니다. Opportunity 가 없으면 BAT 가 생성되지 않습니다. Opportunity 가 생성되면 BAT 객체가 [!DNL Salesforce] *금액* 터치포인트에 표시할 매출액을 파악할 수 있는 Opportunity 의 필드입니다.

A **워크플로우** 는 [사용자 지정 금액 필드](/help/advanced-marketo-measure-features/custom-revenue-amount/using-a-custom-revenue-amount-field.md) Opportunity Object에 대한 수익을 표시할 수 있습니다. [!DNL Marketo Measure] 은 사용자 지정 금액 필드에 나타난 정보를 읽을 수 없으므로 터치포인트에서 매출 속성 데이터를 채울 수 없습니다. 이 워크플로우에서는 **[!DNL Marketo Measure]기회 금액** 필드, 다음 중 하나 [!DNL Marketo Measure] 사용자 정의 필드 - 사용자 정의 금액 필드의 수익 값을 기회 금액 필드에 매핑합니다.

![](assets/3-1.png)

BAT 객체는 [!UICONTROL Opportunity], [!UICONTROL Contact], 및 [!UICONTROL Account] 개체를 관련 목록으로 사용 이 목록에는 Opportunity에 속하는 속성 데이터가 있는 모든 터치포인트가 표시됩니다. 구매자 속성 터치포인트 ID를 클릭하면 구매자 속성 터치포인트 세부 사항 페이지로 이동합니다. 여기에는 터치포인트가 있었던 위치(구매자 터치포인트 객체에서 제공된 것과 유사)에 대한 보다 구체적인 속성 데이터 및 정보가 표시됩니다.

## [!DNL Marketo Measure] 개인 {#marketo-measure-person}

다음 [!DNL Marketo Measure] Person Object 는 Lead 및 Contact 객체를 함께 연관시킵니다. 기본적으로 Salesforce에서는 동일한 보고서에서 리드 및 연락처 개체를 사용하여 보고서를 만들 수 있는 옵션을 제공하지 않습니다. Lead 및 Contact 객체와 관련하여 [!DNL Marketo Measure] 개인 사용자는 동일한 보고서 내에서 두 객체에 대해 보고할 수 있습니다. 이는 리드가 연락처로 전환되었을 때 특히 유용합니다. 다음 [!DNL Marketo Measure] 개인 레코드에는 해당 리드 및/또는 연락처 레코드에 대한 조회, 개인에게 연결된 터치포인트의 관련 목록 및 개인 ID(항상 리드/연락처의 이메일 주소)가 표시됩니다. 다음 이후 [!DNL Marketo Measure] Lead 및 Contact Object에 관련된 사람은 [!DNL Marketo Measure] 구매자 속성 터치포인트에 연결된 개인 레코드. 아래는 의 예입니다 [!DNL Marketo Measure] Salesforce 내 개인 레코드:

![](assets/4.png)

## [!DNL Marketo Measure] A/B 테스트 {#marketo-measure-a-b-test}

A/B 테스트를 [!DNL Optimizely] 또는 VWO(Visual Web Optimizer)를 사용하여 해당 계정을 [!DNL Marketo Measure] Salesforce 내에서 A/B 테스트 데이터를 보는 계정. 다음 [!DNL Marketo Measure] A/B 테스트 개체를 사용하면 기본적으로 A/B 테스트 데이터를 Optimizely/VIEW에서 가져와 데이터를 Lead 및 Contact에 연결할 수 있습니다.

![](assets/5.png)

다음 [!DNL Marketo Measure] A/B 테스트 객체가 [!UICONTROL Leads], [!UICONTROL Contacts] 및 [!UICONTROL Opportunity] 페이지. 이 목록에는 Optimizely 또는 VWO를 통해 실행 중인 모든 실험 및 변형이 표시되며 특정 리드 및 담당자와 관련된 실험/변형을 볼 수 있습니다.

## [!DNL Marketo Measure] 이벤트 {#marketo-measure-events}

다음 [!DNL Marketo Measure] 이벤트 개체를 사용하면 웹 사이트에서 발생하는 특정 이벤트를 추적할 수 있습니다. 웹 사이트에서 발생하는 특정 이벤트를 추적하려면 사용자 지정 코드를 [!DNL Marketo Measure] Javascript. 캡처된 정보는 [!DNL Marketo Measure] 객체 관련 목록(Object Related List)은 [!UICONTROL Leads], [!UICONTROL Contacts] 및 [!UICONTROL Opportunity] 페이지. 다음 [!DNL Marketo Measure] Events 개체 *포함하지 않음* 속성 데이터에 연결합니다. 이 개체의 목적은 사람들이 웹 사이트에서 특정 작업을 수행하는지 확인하는 것입니다.

## [!DNL Marketo Measure] 필드 {#marketo-measure-fields}

에 의해 캡처된 데이터 [!DNL Marketo Measure] Javascript가 사용자 지정으로 푸시됩니다 [!DNL Marketo Measure] 내 필드 [!DNL Marketo Measure] 개체. 특정 필드는 특정 개체에만 표시됩니다. 모든 [!DNL Marketo Measure] 필드 부탁합니다 [여기를 클릭하십시오.](/help/introduction-to-marketo-measure/overview-resources/glossary-of-marketo-measure-fields.md). 다음 항목의 시각화에 대해 [!DNL Marketo Measure] 개체 각 [!DNL Marketo Measure] 필드 관련 내용을 입력하십시오. [여기를 클릭하십시오.](/help/configuration-and-setup/marketo-measure-and-salesforce/marketo-measure-object-and-field-taxonomy.md).

## [!DNL Marketo Measure] 보고서 및 대시보드 {#marketo-measure-reports-and-dashboards}

다음 [!DNL Marketo Measure] 에 추가된 보고서 및 대시보드 [!DNL Salesforce] 는 기본 보고 및 데이터 시각화 기능을 제공합니다. 기본 사항입니다 [!DNL Marketo Measure] 보고서를 사용하면 터치 포인트 데이터를 빠르게 구성, 분석 및 이해할 수 있습니다.
