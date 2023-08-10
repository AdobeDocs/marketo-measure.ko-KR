---
description: 사용자 지정 수익 금액 활용에 대한 우수 사례 - [!DNL Marketo Measure] - 제품 설명서
title: 사용자 지정 수익 금액 활용에 대한 우수 사례
exl-id: 553bd75a-512a-4733-a24b-8112eb420afc
feature: Custom Revenue Amount
source-git-commit: 8ac315e7c4110d14811e77ef0586bd663ea1f8ab
workflow-type: tm+mt
source-wordcount: '419'
ht-degree: 0%

---

# 사용자 지정 수익 금액 활용에 대한 우수 사례 {#best-practices-for-utilizing-a-custom-revenue-amount}

## 개요 {#overview}

의 핵심 기능 [!DNL Marketo Measure] 은 구매자의 여정 전반에 걸쳐 마케팅 접점에 매출 크레딧을 할당하는 기능입니다. 정확한 매출 기여도 분석의 핵심은 [!DNL Marketo Measure] 영업 기회에서 올바른 매출액을 참조하기 위해, 다양한 속성 모델을 통해 마케팅 접점 간에 배포됩니다.

구현 중에 별도로 지정하지 않는 한 [!DNL Marketo Measure] 인스턴스는 매출 기여도 분석에 대한 표준 영업 기회 금액(SFDC 기본값)을 참조하도록 설정됩니다. 그러나 많은 경우 [!DNL Marketo Measure] 이 필드에는 Opportunity에 대한 정확한 매출액이 반영되지 않습니다. 이러한 경우 [!DNL Marketo Measure] 는에 대한 사용자 정의 수익 금액을 설정하는 기능을 제공합니다. [!DNL Marketo Measure] 를 참조하여 기여도 분석 접점(BAT) 전체에 배포합니다.

## 우수 사례 {#best-practice}

사용자 지정 수익 금액을 설정할 때는 다음 모범 사례를 염두에 두고 다음을 확인하십시오. [!DNL Marketo Measure] 기여도 분석 데이터는 정확하고 일관적입니다.

명심해야 할 사항:

* 모든 Opportunity에 대해 정확하고 활용도가 높은 Revenue 필드 선택
   * ARR 또는 총 계약 금액 권장
* 공식 필드 사용 안 함
* 통화 전환에 사용자 지정 수익 금액을 사용하는 경우 [!UICONTROL Marketo Measure Multiple Currencies] 대신 기능이 기본 방법입니다.
   * 다음 [!DNL Marketo Measure] 여러 통화 기능은에서 설정한 전환율을 참조합니다. [!DNL Salesforce] 통화 전환 간 정렬을 가장 잘 보장하기 위해. 이렇게 하면 표준 &#39;금액&#39;(SFDC 기본값) 또는 과 관련된 다른 모든 사용자 지정 금액 필드를 계속 활용할 수 있습니다. [!DNL Salesforce] 전환율.
* 원하는 금액 필드를 업데이트하는 경우 [!DNL Marketo Measure] 참조하려면 데이터 로더 를 사용하여 지난 Opportunity 를 업데이트하여 매출 데이터가 일관되고 워크플로우를 통해 적절한 필드가 채워지도록 합니다

## 유지 관리에 대한 우수 사례 {#best-practice-for-maintenance}

연간 수익 금액 설정을 검토하면 속성 데이터가 정확하고 조직의 나머지 수익 보고와 정렬됩니다.

사용자 정의 수익 금액을 활용하는 경우 다음과 같이 수익 설정을 확인합니다.

* 내 [!DNL Marketo Measure] 계정, (으)로 이동[!UICONTROL Opportunities]CRM의 섹션
* 다음 항목 식별 [!UICONTROL Custom Opportunity Amount] 필드, 여기 [!UICONTROL custom revenue amount API] 필드는 나열되어야 합니다.
* 여전히 올바른 필드인지 확인합니다.
* 다음 항목도 포함 [!DNL Salesforce] 관리자 확인 의 사용자 정의 수익 금액 워크플로 [!DNL Salesforce] 은(는) 아직 실행 중입니다.

연간 검토 외에, 특정 조직 변경은 수익 금액 설정을 검토해야 한다는 신호를 보낼 수 있습니다.

* 마케팅 팀에서의 이직률
* 사용자 정의 수익 필드 변경
* 수익 보고 방식의 조직 변경

>[!MORELIKETHIS]
>
>* [사용자 정의 수익 금액 필드 사용](/help/advanced-marketo-measure-features/custom-revenue-amount/using-a-custom-revenue-amount-field.md)
>* [데이터 로더를 사용하여 사용자 정의 금액 필드 갱신](/help/advanced-marketo-measure-features/custom-revenue-amount/using-data-loader-to-update-marketo-measure-custom-amount-field.md)
>* [다중 통화 개요](/help/advanced-marketo-measure-features/multi-currency/overview.md)
>* [다중 통화 설정](/help/advanced-marketo-measure-features/multi-currency/settings.md)
