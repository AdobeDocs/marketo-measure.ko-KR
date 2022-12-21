---
description: 사용자 지정 수입 금액 활용을 위한 우수 사례 - [!DNL Marketo Measure] - 제품 설명서
title: 사용자 지정 수입 금액 활용을 위한 우수 사례
exl-id: 553bd75a-512a-4733-a24b-8112eb420afc
source-git-commit: b59c79236d3e324e8c8b07c5a6d68bd8176fc8a9
workflow-type: tm+mt
source-wordcount: '419'
ht-degree: 0%

---

# 사용자 지정 수입 금액 활용을 위한 우수 사례 {#best-practices-for-utilizing-a-custom-revenue-amount}

## 개요 {#overview}

의 핵심 기능 [!DNL Marketo Measure] 구매자의 여정 전체에서 마케팅 터치포인트에 매출 크레딧을 할당하는 기능입니다. 매출 기여도 분석의 핵심은 [!DNL Marketo Measure] Opportunity에 대한 올바른 수익 금액을 참조하기 위해 이 금액은 다양한 속성 모델을 통해 마케팅 터치포인트 간에 배포됩니다.

구현 중에 별도로 지정하지 않는 한, [!DNL Marketo Measure] 수익 기여도 분석에 대한 표준 SFDC(Opportunity Amount) 를 참조하도록 인스턴스가 설정됩니다. 하지만, 많은 경우에 [!DNL Marketo Measure] 계정에서는 이 필드에 Opportunity 의 정확한 수익 금액이 반영되지 않습니다. 이러한 경우 [!DNL Marketo Measure] 은 다음에 대한 사용자 지정 수입 금액을 설정하는 기능을 제공합니다 [!DNL Marketo Measure] BAT(기여도 분석 터치포인트)에서 참조하고 배포할 수 있습니다.

## 우수 사례 {#best-practice}

사용자 지정 수입 금액을 설정할 때에는 다음 우수 사례를 주의 깊게 살펴보십시오 [!DNL Marketo Measure] 속성 데이터는 정확하고 일관됩니다!

주의 사항:

* 모든 Opportunity에 대해 정확하고 사용되는 수익 필드를 선택합니다
   * ARR 또는 총 계약 금액 사용 권장
* 수식 필드를 사용하지 마십시오
* 통화 전환에 사용자 지정 수입 금액을 사용하는 경우, [!UICONTROL Marketo Measure Multiple Currencies] 기능은 대신 기본 방법입니다.
   * 다음 [!DNL Marketo Measure] 복수 통화 기능은 [!DNL Salesforce] 통화 전환 간 정렬을 가장 잘 유지하기 위해. 이를 통해 표준 &#39;금액&#39;(SFDC 기본값) 또는 과 관련된 기타 사용자 지정 금액 필드를 계속 활용할 수 있습니다 [!DNL Salesforce] 전환율.
* 원하는 금액 필드를 업데이트하는 경우 [!DNL Marketo Measure] 참조하려면 Data Loader를 사용하여 과거 Opportunity를 업데이트하여 수익 데이터가 일관되고 워크플로우를 통해 적절한 필드가 채워지도록 하십시오

## 유지 관리 우수 사례 {#best-practice-for-maintenance}

연간 매출액 금액 설정을 검토하면 속성 데이터가 정확하며 조직의 나머지 매출 보고에 맞게 조정됩니다.

사용자 지정 수입 금액을 활용하는 경우, 매출 설정을 다음과 같이 확인하십시오.

* 사용자 [!DNL Marketo Measure] 계정, &#39;[!UICONTROL Opportunities]CRM의 &#39; 섹션
* 다음 식별 [!UICONTROL Custom Opportunity Amount] 필드, 여기 [!UICONTROL custom revenue amount API] 필드가 나열되어 있어야 합니다.
* 여전히 올바른 필드인지 확인합니다
* 또한 [!DNL Salesforce] 관리자는 의 사용자 지정 매출 금액 워크플로우가 [!DNL Salesforce] 아직 실행 중입니다.

연간 검토 외에도 특정 조직의 변경 사항은 수익 금액 설정을 검토해야 한다는 신호를 보낼 수 있습니다.

* 마케팅 팀의 이직률
* 사용자 지정 수입 필드 변경
* 매출 보고 방식의 조직 변경

>[!MORELIKETHIS]
>
>* [사용자 지정 수익 금액 필드 사용](/help/advanced-marketo-measure-features/custom-revenue-amount/using-a-custom-revenue-amount-field.md)
>* [Data Loader를 사용하여 사용자 지정 금액 필드 업데이트](/help/advanced-marketo-measure-features/custom-revenue-amount/using-data-loader-to-update-marketo-measure-custom-amount-field.md)
>* [다중 통화 개요](/help/advanced-marketo-measure-features/multi-currency/overview.md)
>* [다중 통화 설정](/help/advanced-marketo-measure-features/multi-currency/settings.md)

