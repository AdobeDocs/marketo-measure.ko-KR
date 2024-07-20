---
unique-page-id: 18874535
description: 전체 서클에서  [!DNL Marketo Measure] 로 전환 - [!DNL Marketo Measure]
title: 전체 서클에서  [!DNL Marketo Measure] 로 전환
exl-id: fd471771-33e2-413a-b155-02ba6e32e10c
feature: Attribution, Fundamentals
source-git-commit: 4787f765348da71bc149c997470ce678ba498772
workflow-type: tm+mt
source-wordcount: '630'
ht-degree: 0%

---

# 전체 서클에서 [!DNL Marketo Measure](으)로 전환 {#transitioning-to-marketo-measure-from-full-circle}

전체 동그라미에서 [!DNL Marketo Measure](으)로 이동하시겠습니까? 넌 혼자가 아니야. 다음은 명심해야 할 가장 큰 고려 사항과 전환을 수행한 다른 고객으로부터 얻은 교훈입니다.

## 캠페인 기반 추적과 다중 Source 추적 비교 {#campaign-based-tracking-vs-multi-source-tracking}

[!UICONTROL Full Circle]의 모든 상호 작용은 CRM 캠페인 멤버십을 통해 추적됩니다. [!DNL Marketo Measure]에서 구매 여정은 JavaScript, CRM 캠페인 멤버십 및 CRM 활동 레코드의 조합을 통해 컴파일됩니다. &quot;속성 보고가 작동하려면 CRM 캠페인에서 모든 상호 작용을 추적해야 함&quot;에서 &quot;속성 보고가 작동하려면 CRM 캠페인에서 이 하위 집합만 추적해야 함&quot;으로 정신적인 전환을 설정하는 것은 까다로울 수 있습니다.

일반적으로 [!DNL Marketo Measure]에서 주요 상호 작용 유형에 대한 터치포인트 레코드를 만드는 방법은 다음과 같습니다.

* 사이트의 양식 채우기: [!DNL Marketo Measure] JavaScript
* 사이트의 페이지 보기: 이 페이지 보기가 지정된 CRM 마일스톤(예: 잠재 고객 또는 영업 기회 만들기)을 유도한 경우에만 [!DNL Marketo Measure] JavaScript에서 만듭니다.
* 전화 회의 또는 트레이드쇼와 같은 오프라인 상호 작용: CRM 캠페인 멤버십
* 사이트가 아닌 인터넷의 어느 곳에서든 발생하는 디지털 상호 작용(예: 목록 업로드를 생성하는 서드파티 사이트에서 호스팅되는 웨비나): CRM 캠페인 멤버십
* 영업 팀과의 상호 작용: CRM 활동 레코드

CRM 캠페인 관리에 익숙하고 기존 프로세스를 제자리에 유지하고자 하는 경우 좋습니다. CRM 캠페인에서 모든 상호 작용을 계속 추적하는 것은 [!DNL Marketo Measure]에게 영향을 주지 않습니다. 터치포인트 중복을 방지하기 위해 원하는 캠페인 하위 집합에서 터치포인트만 생성하는 논리를 디자인할 수 있습니다.

## 가시성과 기여도 비교 {#visibility-vs-attribution}

대부분의 전체 원 설정을 사용하면 마케팅 또는 판매 노력과 관련하여 개인이 수행하는 모든 상호 작용을 볼 수 있습니다. 페이지 보기 수, 반복된 페이지 방문 수, 세 가지 캠페인의 멤버십 - 전체 원이 이러한 모든 항목을 표시합니다. 페이지를 300번 보면, 전체 원은 300개의 중복 캠페인을 만들고 각 캠페인에 멤버십을 부여합니다. [!DNL Marketo Measure]은(는) 그렇지 않습니다. 이는 우리 측의 의식적인 설계 결정이었습니다.

[!DNL Marketo Measure]은(는) 의미 있는 상호 작용을 노출하고 가장 영향력 있는 터치포인트 간에 가중치를 적절하게 분배하는 기여도 분석 스토리를 제공하는 것을 목표로 합니다. 예를 들어 [!DNL Marketo Measure] 프레임워크는 페이지 보기(양식 채우기 없음)를 일상적인 터치포인트로 표시하지 않습니다. 독립형 페이지 보기는 구매 여정을 앞당기는 데 영향을 주지 않지만, 지정된 CRM 마일스톤(예: 리드 또는 영업 기회 생성) 이전의 가장 최근 상호 작용인 경우 접점을 만듭니다. 모든 것을 보여 주고 싶지는 않습니다. 기여도 분석의 관점에서 중요한 사항을 보여 드리겠습니다.

[!DNL Marketo Measure] 담당자와 협력하여 팀에서 더 이상 사용할 수 없는 데이터에 대한 적절한 기대를 설정하십시오.

## [!DNL Marketo Measure] 이전 데이터 {#pre-marketo-measure-data}

표준 권장 사항은 [!DNL Marketo Measure] JavaScript을 배포한 날부터 보고 및 데이터 수집을 시작하는 것입니다. 이전 Full Circle 고객은 이 두 배가 됩니다. 위의 두 섹션을 생각해 보십시오. 더 많은 양의 데이터를 보는 데 사용되고 CRM 캠페인 멤버십에서 오는 모든 데이터에 사용됩니다. [!DNL Marketo Measure] 구현 전에 해당 데이터의 일부 또는 전부를 포함하도록 선택하면 JavaScript 구현 날짜의 사과와 사과를 비교할 수 없습니다.

즉, 많은 고객이 이 기록 데이터를 필요로 한다는 것을 확실히 알고 있습니다. 특히 판매 주기가 더 긴 경우(90일 이상) [!DNL Marketo Measure] 이전 데이터에 대한 [!DNL Marketo Measure] 가시성을 제공할 수 있습니다. [!DNL Marketo Measure] 담당자와 이 문제에 대해 자세히 논의하십시오. 항상 구현 날짜를 잘못 변경하면 채널 성능 또는 참여가 개선되거나 저하될 수 있으며, 기타 잘못된 추론이 발생할 수 있습니다.

## 요약 {#in-summary}

귀사는 좋은 회사에 있으며, 많은 다른 고객이 이러한 변경 사항을 처리할 수 있도록 지원해 왔습니다. [!DNL Marketo Measure] 담당자와 협력하여 위의 영향 및 기타 문제를 파악하십시오.
