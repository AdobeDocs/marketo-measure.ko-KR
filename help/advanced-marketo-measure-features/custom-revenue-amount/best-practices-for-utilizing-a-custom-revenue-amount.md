---
description: 사용자 지정 수익 금액 활용 모범 사례 - [!DNL Marketo Measure]
title: 사용자 지정 수익 금액 활용에 대한 우수 사례
exl-id: 553bd75a-512a-4733-a24b-8112eb420afc
feature: Custom Revenue Amount
source-git-commit: 9e672d0c568ee0b889461bb8ba6fc6333edf31ce
workflow-type: tm+mt
source-wordcount: '419'
ht-degree: 0%

---

# 사용자 지정 수익 금액 활용에 대한 우수 사례 {#best-practices-for-utilizing-a-custom-revenue-amount}

## 개요 {#overview}

[!DNL Marketo Measure]의 핵심 기능은 구매자의 여정 전체에서 마케팅 접점에 매출 크레딧을 할당하는 기능입니다. 정확한 매출 기여도 분석의 핵심은 [!DNL Marketo Measure]이(가) 기회에서 올바른 매출 금액을 참조할 수 있는 능력이며, 이는 결과적으로 다양한 기여도 분석 모델을 통해 마케팅 접점에 분산됩니다.

구현 중에 달리 지정하지 않는 한 [!DNL Marketo Measure] 인스턴스는 매출 기여도 분석에 대한 표준 영업 기회 금액(SFDC 기본값)을 참조하도록 설정됩니다. 그러나 많은 [!DNL Marketo Measure] 계정의 경우 이 필드에 Opportunity에 대한 정확한 매출액이 반영되어 있지 않습니다. 이러한 경우 [!DNL Marketo Measure]은(는) [!DNL Marketo Measure]이(가) BAT(Attribution Touchpoints)를 참조하고 배포하도록 사용자 지정 수익 금액을 설정할 수 있는 기능을 제공합니다.

## 우수 사례 {#best-practice}

사용자 지정 수익 금액을 설정할 때는 [!DNL Marketo Measure] 속성 데이터가 정확하고 일관되도록 다음 모범 사례를 염두에 두십시오!

명심해야 할 사항:

* 모든 Opportunity에 대해 정확하고 활용도가 높은 Revenue 필드 선택
   * ARR 또는 총 계약 금액 권장
* 공식 필드 사용 안 함
* 통화 전환에 사용자 지정 수익 금액을 사용하는 경우 대신 [!UICONTROL Marketo Measure Multiple Currencies] 기능이 기본 방법입니다.
   * [!DNL Marketo Measure] 복수 통화 기능은 통화 전환 간의 정렬을 가장 잘 보장하기 위해 [!DNL Salesforce]에서 설정된 전환율을 참조합니다. 이를 통해 표준 &#39;금액&#39;(SFDC 기본값) 또는 [!DNL Salesforce] 전환율과 관련된 기타 사용자 지정 금액 필드를 계속 사용할 수 있습니다.
* [!DNL Marketo Measure]에서 참조할 금액 필드를 업데이트하는 경우 데이터 로더를 사용하여 과거 기회를 업데이트하여 매출 데이터가 일관되고 워크플로우를 통해 적절한 필드가 채워지도록 합니다

## 유지 관리에 대한 우수 사례 {#best-practice-for-maintenance}

연간 수익 금액 설정을 검토하면 속성 데이터가 정확하고 조직의 나머지 수익 보고와 정렬됩니다.

사용자 정의 수익 금액을 활용하는 경우 다음과 같이 수익 설정을 확인합니다.

* [!DNL Marketo Measure] 계정의 CRM의 &#39;[!UICONTROL Opportunities]&#39; 섹션으로 이동합니다.
* [!UICONTROL Custom Opportunity Amount] 필드를 식별하십시오. 여기에 [!UICONTROL custom revenue amount API] 필드가 나열되어야 합니다.
* 여전히 올바른 필드인지 확인합니다.
* [!DNL Salesforce] 관리자에게 [!DNL Salesforce]의 사용자 지정 수익 금액 워크플로우가 여전히 실행 중인지 확인하도록 합니다.

연간 검토 외에, 특정 조직 변경은 수익 금액 설정을 검토해야 한다는 신호를 보낼 수 있습니다.

* 마케팅 팀에서의 이직률
* 사용자 정의 수익 필드 변경
* 수익 보고 방식의 조직 변경

>[!MORELIKETHIS]
>
>* [사용자 지정 수익 금액 필드 사용](/help/advanced-marketo-measure-features/custom-revenue-amount/using-a-custom-revenue-amount-field.md)
>* [데이터 로더를 사용하여 사용자 지정 금액 필드 업데이트](/help/advanced-marketo-measure-features/custom-revenue-amount/using-data-loader-to-update-marketo-measure-custom-amount-field.md)
>* [다중 통화 개요](/help/advanced-marketo-measure-features/multi-currency/overview.md)
>* [다중 통화 설정](/help/advanced-marketo-measure-features/multi-currency/settings.md)
