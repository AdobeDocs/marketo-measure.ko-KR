---
unique-page-id: 18874535
description: 전환 [!DNL Marketo Measure] 전체 원에서 - [!DNL Marketo Measure] - 제품 설명서
title: 전환 [!DNL Marketo Measure] 전체 서클에서
exl-id: fd471771-33e2-413a-b155-02ba6e32e10c
feature: Attribution, Fundamentals
source-git-commit: a2a7657e8377fd5c556d38f6eb815e39d2b8d15e
workflow-type: tm+mt
source-wordcount: '637'
ht-degree: 0%

---

# 전환 [!DNL Marketo Measure] 전체 서클에서 {#transitioning-to-marketo-measure-from-full-circle}

전체 원에서 로 이동 [!DNL Marketo Measure]? 넌 혼자가 아니야. 다음은 명심해야 할 가장 큰 고려 사항과 전환을 수행한 다른 고객으로부터 얻은 교훈입니다.

## 캠페인 기반 추적과 다중 소스 추적 비교 {#campaign-based-tracking-vs-multi-source-tracking}

의 모든 상호 작용 [!UICONTROL Full Circle] CRM 캠페인 멤버십을 통해 추적됩니다. 포함 [!DNL Marketo Measure], 구매 여정은 JavaScript, CRM 캠페인 멤버십 및 CRM 활동 레코드의 조합을 통해 컴파일됩니다. &quot;속성 보고가 작동하려면 CRM 캠페인에서 모든 상호 작용을 추적해야 함&quot;에서 &quot;속성 보고가 작동하려면 CRM 캠페인에서 이 하위 집합만 추적해야 함&quot;으로 정신적인 전환을 하는 것은 까다로울 수 있습니다.

일반적으로 말하자면, 방법은 다음과 같습니다 [!DNL Marketo Measure] 는 다음과 같은 주요 유형의 상호 작용에 대한 접점 레코드를 만듭니다.

* 사이트의 양식 채우기: [!DNL Marketo Measure] Javascript
* 사이트에 대한 페이지 보기 수: 만든 사람 [!DNL Marketo Measure] Javascript는 이 페이지 보기가 지정된 CRM 마일스톤(예: 잠재 고객 또는 영업 기회 생성)을 유도한 경우에만
* 전화 회의 또는 트레이드쇼와 같은 오프라인 상호 작용: CRM 캠페인 멤버십
* 사이트가 아닌 인터넷에서 발생하는 디지털 상호 작용(예: 목록 업로드를 생성하는 서드파티 사이트에서 호스팅되는 웨비나): CRM 캠페인 멤버십
* 영업 팀과의 상호 작용: CRM 활동 레코드

CRM 캠페인 관리에 익숙하고 기존 프로세스를 제자리에 유지하고자 하는 경우 좋습니다. 아프지 않아요 [!DNL Marketo Measure] 를 사용하여 CRM 캠페인의 모든 상호 작용을 추적할 수 있습니다. 터치포인트 중복을 방지하기 위해 원하는 캠페인 하위 집합에서 터치포인트만 생성하는 논리를 디자인할 수 있습니다.

## 가시성과 기여도 비교 {#visibility-vs-attribution}

대부분의 전체 서클 설정을 사용하면 마케팅 또는 판매 활동에 대한 개인의 모든 개별 상호 작용을 볼 수 있습니다. 페이지 보기 수, 반복된 페이지 방문 수, 중복 및 삼중 캠페인의 멤버십 - 전체 원이 이들 모두를 표시합니다. 페이지를 300번 보면, 전체 원은 300개의 중복 캠페인을 만들고 각 캠페인에 멤버십을 부여합니다. [!DNL Marketo Measure] 그렇지 않습니다. 그것은 우리 측의 의식적인 설계 결정이었습니다.

[!DNL Marketo Measure] 은 의미 있는 상호 작용을 노출하고 가장 영향력 있는 터치포인트 간에 가중치를 적절하게 분배하는 기여도 스토리를 제공하는 것을 목표로 합니다. 예를 들어 [!DNL Marketo Measure] 프레임워크는 페이지 보기(양식 채우기 없음)를 일상적인 터치포인트로 표시하지 않습니다. 독립형 페이지 보기는 구매 여정을 앞당기는 데 영향을 주지 않지만, 지정된 CRM 마일스톤(예: 리드 또는 영업 기회 만들기) 이전의 가장 최근 상호 작용인 경우 접점을 만듭니다. 모든 것을 보여 주고 싶지는 않습니다. 기여도 분석의 관점에서 중요한 사항을 보여 드리겠습니다.

을(를) 사용하여 작업 [!DNL Marketo Measure] 담당자는 팀에서 더 이상 사용할 수 없는 데이터에 대해 적절한 기대치를 설정하십시오.

## 사전-[!DNL Marketo Measure] 데이터 {#pre-marketo-measure-data}

표준 권장 사항은 를 배포한 날부터 보고 및 데이터 수집을 시작하는 것입니다. [!DNL Marketo Measure] 이전 전체 서클 고객은 JavaScript를 앞으로 2배로 늘립니다. 위의 두 섹션을 생각해 보십시오. 여러분은 더 많은 양의 데이터를 보는 데 익숙하고 CRM 캠페인 멤버십에서 오는 모든 데이터에 익숙합니다. 이전 데이터의 일부 또는 전부를 포함하도록 선택하는 경우 [!DNL Marketo Measure] 구현에서, JavaScript 구현 날짜 전체에서 사과와 사과를 비교하지 않을 것입니다.

즉, 많은 고객이 이러한 기록 데이터를 필요로 한다는 것을 잘 알고 있습니다. 특히 판매 주기가 더 긴 경우(90일 이상) 다음을 제공할 수 있습니다 [!DNL Marketo Measure] 사전 관리에 대한 가시성[!DNL Marketo Measure] 데이터. 이 문제에 대해 다음 사용자와 신중히 논의하십시오. [!DNL Marketo Measure] rep와 는 항상 구현 날짜 간에 왜곡이 발생하면 채널 성능 또는 참여가 개선되거나 감소하고 기타 잠재적으로 잘못된 추론이 발생할 수 있다는 점을 염두에 두어야 합니다.

## 요약 {#in-summary}

귀사는 좋은 회사에 있으며, 많은 다른 고객이 이러한 변경 사항을 처리할 수 있도록 지원해 왔습니다. 을(를) 사용하여 작업 [!DNL Marketo Measure] 담당자는 위의 영향과 기타 우려사항을 이해해야 합니다.
