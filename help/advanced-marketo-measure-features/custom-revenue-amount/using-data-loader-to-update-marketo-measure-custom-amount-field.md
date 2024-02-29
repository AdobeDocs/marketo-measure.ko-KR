---
unique-page-id: 18874771
description: 데이터 로더를 사용하여 업데이트 [!DNL Marketo Measure] 사용자 정의 금액 필드 - [!DNL Marketo Measure]
title: 데이터 로더를 사용하여 Marketo Measure 사용자 정의 금액 필드 업데이트
exl-id: 55e91ac4-a835-48e0-a6ce-1d85b32aeac0
feature: Custom Revenue Amount
source-git-commit: 915e9c5a968ffd9de713b4308cadb91768613fc5
workflow-type: tm+mt
source-wordcount: '192'
ht-degree: 0%

---

# 데이터 로더를 사용하여 업데이트 [!DNL Marketo Measure] 사용자 정의 금액 필드 {#using-data-loader-to-update-marketo-measure-custom-amount-field}

[!DNL Marketo Measure] 에서는 의 사용자 정의 매출 필드(즉시 금액 필드 사용)를 사용할 때 기회 값을 업데이트하는 편리한 옵션으로 데이터 로더를 사용할 것을 권장합니다. [!DNL Marketo Measure]. 데이터 로더는 를 사용하는 것보다 선호됩니다. [!DNL Marketo Measure] 스크립트를 스크립트로 업데이트하려면 사용자가 다음을 수행하는 동안 모든 Salesforce 유효성 검사 규칙을 비활성화해야 합니다. [!DNL Marketo Measure] 스크립트가 실행됩니다.

## 데이터 로더를 사용하여 업데이트 [!DNL Marketo Measure] 사용자 정의 금액 필드{#using-data-loader-to-update-marketo-measure-custom-amount-field-1}

1. 다음을 사용하여 Excel 시트를 만듭니다.

   * 영업 기회 ID
   * 사용자 정의 영업 기회 금액 필드 (선호하는 매출 필드)
   * [!DNL Marketo Measure] 영업 기회 금액 필드

1. 기본 매출 필드의 값을 복사하여 [!UICONTROL [!DNL Marketo Measure] Opportunity Amount] 필드. 그런 다음 .csv 파일을 사용하여 이러한 Opp 를 업데이트합니다.

**_또는 Salesforce로 이동하여 사용자 지정 목록 보기를 사용하여 모든 기회를 일괄 편집할 수 있습니다._**

1. 모든 기회에 대한 사용자 지정 목록 보기를 만듭니다.
1. 기본 설정 수익 필드에 대한 필터 추가는 비어 있지 않습니다. _및_ [!UICONTROL Marketo] 영업 기회 금액 측정 필드가 비어 있습니다.
1. 클릭 **[!UICONTROL Mass Edit]**, 하지만 실제로 아무것도 변경하지 마십시오.
1. 클릭 **[!UICONTROL Save]**. 이렇게 하면 워크플로우가 [!DNL Marketo Measure] 소프트웨어 매출 필드가 있는 영업 기회 금액 필드.
