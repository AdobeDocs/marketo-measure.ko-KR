---
description: Passport 대시보드 - [!DNL Marketo Measure] - 제품
title: Passport 대시보드
feature: Reporting
exl-id: 0fbd9714-7d9c-4330-b35f-d011e17c3bfe
source-git-commit: 403b31acce25ddc9c1dcafbd53008b6e2868b3df
workflow-type: tm+mt
source-wordcount: '299'
ht-degree: 0%

---

# Passport 대시보드 {#passport-dashboard}

Passport 대시보드는 마케터에게 지정된 기간 내에 다양한 단계를 통해 전환되는 잠재 고객, 연락처 및 기회에 대한 동적 보기를 제공합니다. 특정 날짜에 대해 필터링하면 해당 날짜의 레코드 스냅샷을 가져올 수도 있습니다.

**질문과 대답은 다음과 같습니다.**

* 선택한 날에 각 비종료 단계에 얼마나 많은 리드, 연락처 또는 기회가 존재했습니까?
* 지정된 기간 동안 각 임시 단계를 통해 진행된 개별 리드 또는 연락처의 수는 몇 개입니까?
   * _예_: 잠재 고객 A가 2023년 1월 1일에 단계 1에 있다가 2023년 3월 31일까지 단계 5로 발전하면 2023년 1분기 여권 분석은 1~5단계에서 잠재 고객 A를 계산합니다.
* 주어진 기간 동안 각 임시 단계를 통해 몇 개의 고유한 기회가 전달됩니까?

## 대시보드 구성 요소 {#dashboard-components}

### 단계 이름별 단계의 기회 {#opportunities-in-stage-by-stage-name}

* 각 단계는 지정된 기간에 터치포인트를 통과한 터치포인트가 있는 기회의 수를 보여줍니다.
   * 영업 기회가 해당 범위 내에서 여러 단계를 통해 진행되는 경우, 해당 영업 기회가 통과하는 모든 단계에서 계산됩니다.
* &quot;Closed Won&quot;, &quot;Closed Lost&quot; 등의 터미널 단계는 제외된다.
* 시작 날짜와 종료 날짜는 모두 포괄적입니다.

![](assets/passport-dashboard-1.png)

### 단계 이름별 단계의 잠재 고객 또는 연락처 {#leads-or-contacts-in-stage-by-stage-name}

* 각 단계에는 지정된 일정에 따라 연결된 터치포인트가 있는 잠재 고객 또는 연락처 수가 표시됩니다.
   * &quot;잠재 고객&quot; 또는 &quot;연락처&quot;를 표시할지 여부는 설정 > 속성 설정 > 기본 대시보드 개체에 설정된 기본 설정에 따라 결정됩니다.
   * Lead 또는 Contact 가 해당 범위 내에서 여러 단계를 거치는 경우 통과하는 모든 단계에서 계산됩니다.
* &quot;Closed Won&quot;, &quot;Closed Lost&quot; 등의 터미널 단계는 제외된다.
* 시작 날짜와 종료 날짜는 모두 포괄적입니다.

![](assets/passport-dashboard-2.png)

## 필터 창 {#filter-pane}

이 대시보드에는 다음 설정 및 필터가 포함되어 있습니다.

* 날짜(전환 날짜 기준)
* 채널, 하위 채널
* Campaign
* 세그먼트

>[!MORELIKETHIS]
>
>* [대시보드 기본 사항 살펴보기](/help/marketo-measure-discover-ui/dashboards/discover-dashboard-basics.md){target="_blank"}
>* [대시보드 데이터 가시성 정책](/help/marketo-measure-discover-ui/dashboards/dashboard-data-visibility-policy.md){target="_blank"}
