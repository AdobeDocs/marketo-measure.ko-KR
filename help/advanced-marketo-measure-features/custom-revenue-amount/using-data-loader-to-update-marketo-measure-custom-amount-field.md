---
unique-page-id: 18874771
description: Data Loader를 사용하여 업데이트 [!DNL Marketo Measure] 사용자 지정 금액 필드 - [!DNL Marketo Measure] - 제품 설명서
title: Data Loader를 사용하여 Marketo Measure 사용자 지정 금액 필드 업데이트
exl-id: 55e91ac4-a835-48e0-a6ce-1d85b32aeac0
source-git-commit: b59c79236d3e324e8c8b07c5a6d68bd8176fc8a9
workflow-type: tm+mt
source-wordcount: '194'
ht-degree: 0%

---

# Data Loader를 사용하여 업데이트 [!DNL Marketo Measure] 사용자 지정 금액 필드 {#using-data-loader-to-update-marketo-measure-custom-amount-field}

[!DNL Marketo Measure] 에서는 의 사용자 지정 수익 필드를 사용할 때 기회 값을 업데이트하기 위한 편리한 옵션으로 Data Loader를 사용하는 것이 좋습니다(즉시 금액 필드를 사용). [!DNL Marketo Measure]. Data Loader가 [!DNL Marketo Measure] 스크립트를 스크립트로 업데이트하기 위해 사용자는 [!DNL Marketo Measure] 스크립트가 실행됩니다.

## Data Loader를 사용하여 업데이트 [!DNL Marketo Measure] 사용자 지정 금액 필드{#using-data-loader-to-update-marketo-measure-custom-amount-field-1}

1. 다음을 사용하여 Excel 시트를 만듭니다.

   * 영업 기회 Id
   * Custom Opportunity Amount 필드(선호하는 수익 필드)
   * [!DNL Marketo Measure] Opportunity Amount 필드

1. 기본 수익 필드의 값을 복사하여 [!UICONTROL [!DNL Marketo Measure] Opportunity Amount] 필드. 그런 다음 .csv 파일을 사용하여 이러한 Opps를 업데이트합니다.

**_또는 Salesforce로 이동하여 사용자 지정 목록 보기를 사용하여 모든 기회를 일괄 편집할 수 있습니다._**

1. 모든 기회에 대한 사용자 지정 목록 보기를 생성합니다.
1. 선호하는 수입 필드에 대한 필터 추가가 비어 있지 않습니다 _및_ [!UICONTROL Marketo] 측정값 기회 금액 필드가 비어 있습니다.
1. 클릭 **[!UICONTROL Mass Edit]**&#x200B;하지만 실제로 아무것도 바꾸지 마세요.
1. 클릭 **[!UICONTROL Save]**. 그러면 워크플로우를 트리거하여 [!DNL Marketo Measure] Software Revenue 필드의 Opportunity Amount 필드입니다.
