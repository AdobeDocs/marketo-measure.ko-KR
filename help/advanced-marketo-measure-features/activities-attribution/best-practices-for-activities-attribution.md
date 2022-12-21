---
description: 활동 속성에 대한 우수 사례 - [!DNL Marketo Measure] - 제품 설명서
title: 활동 속성에 대한 우수 사례
exl-id: 66fb9f47-3912-40a6-b112-3efca789f321
source-git-commit: b59c79236d3e324e8c8b07c5a6d68bd8176fc8a9
workflow-type: tm+mt
source-wordcount: '526'
ht-degree: 0%

---

# 활동 속성에 대한 우수 사례 {#best-practices-for-activities-attribution}

## 개요 {#overview}

다음 [!DNL Marketo Measure] 활동 속성 기능을 사용하면 고객이 CRM의 활동 레코드에서 터치포인트를 만들 수 있습니다. 터치포인트를 만드는 이 방법은 작업 또는 이벤트 필드를 기반으로 규칙을 만들어 알릴 수 있다는 점에서 유연합니다 [!DNL Marketo Measure] 터치포인트를 생성하고 그 후에 속성 크레딧을 받아야 하는 활동 레코드.

이 기능의 가장 일반적인 사용 사례는 Buyer Touchpoint 데이터에 판매 상호 작용을 통합하는 규칙을 만드는 것입니다. 활동 속성을 사용하면 판매 및 마케팅 데이터를 하나의 여정으로 정렬할 수 있습니다.

많은 경우 [!DNL Salesforce] 인스턴스, 활동 개체에는 다양한 레코드 유형이 포함될 수 있으므로, 활동 규칙이 구체적이고 터치포인트로 변환하려는 레코드에 맞게 조정되는 것이 중요합니다. 다음 우수 사례는 활동 속성을 통해 의미 있고 중요한 터치포인트를 만드는 데 도움이 됩니다.

## 우수 사례 {#best-practice}

처음 활동 규칙을 정의하든, 이전에 설정한 활동 규칙을 검토하든 간에 다음 우수 사례를 기억하십시오.

* 단순 시작
   * 에 통합할 몇 가지 주요 활동 유형을 식별합니다 [!DNL Marketo Measure] 데이터를 추가한 다음 이러한 터치포인트가 분류되는 방식에 익숙해지도록 유형을 더 추가합니다
   * 언급했듯이 이 기능의 기본 사용 사례는 판매 개발 팀, 특히 아웃바운드 전화 및 아웃바운드 이메일의 효능을 추적하는 터치포인트를 만드는 것입니다

>[!NOTE]
>
>그렇습니다 **NOT** Sales Executives 프로세스를 추적하여 Opportunity 가 생성된 이후에 발생하는 Sales Activity 를 추적하는 것이 좋습니다. 목표는 마케팅 영향과 함께 Sales 영향을 추적하는 것이며, 주로 새로운 Opportunity/Pipeline 생성 개발에 있습니다

* 수식 필드를 사용하여 규칙을 정의하지 마십시오
* 구체적이고 정확한 규칙 만들기
   * 활동 터치포인트 만들기에 대한 임계값은 양식 채우기 또는 캠페인 멤버십과 동일하거나 유사하게 하려는 경우, (아웃바운드 전자 메일 또는 완료된 전화 대화에 회신)
* 항상 의 새 규칙의 유효성을 검사합니다 [!DNL Salesforce] 저장 및 처리
   * 작업 및 이벤트 보고서 유형에 활동 규칙을 복제하면 해당 규칙에서 만들어지는 터치포인트 수에 대한 명확한 이해를 제공할 수 있습니다
* 영업 Opp 팀과 협력
   * 활동 레코드 또는 판매 지원 도구와 가장 가까운 작업을 하는 팀에 가져오면 올바른 필드를 사용하여 규칙을 정의할 수 있습니다

## 유지 관리 우수 사례 {#best-practice-for-maintenance}

활동 속성 규칙을 연 두 번 이상 검토하면 활동 접점이 정확하고 최신 상태인지 확인할 수 있습니다. 이러한 규칙이 구매자 속성 데이터를 희석하는 원치 않는 터치포인트를 만들지 않도록 해야 합니다. 규칙이 정의된 방식에 대한 검토를 통해 사용자와 팀이 활동 속성 및 사용자의 역할에서 자신 있게 작업할 수 있습니다 [!DNL Marketo Measure] 데이터.

활동 규칙 검토를 트리거할 수 있는 기타 이유는 다음과 같습니다.

* 마케팅 팀의 이직률
* 활동 레코드를 정의하는 데 사용되는 필드 변경
* 영업 지원 도구 변경 또는 업데이트

>[!MORELIKETHIS]
>
>* [활동 속성](/help/advanced-marketo-measure-features/activities-attribution/salesforce-activities-attribution.md)
>* [영업 활동 속성 FAQ](/help/advanced-marketo-measure-features/activities-attribution/activities-attribution-faq.md)


