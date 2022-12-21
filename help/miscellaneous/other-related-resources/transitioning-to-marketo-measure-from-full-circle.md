---
unique-page-id: 18874535
description: 다음으로 전환 [!DNL Marketo Measure] 전체 원 - [!DNL Marketo Measure] - 제품 설명서
title: 다음으로 전환 [!DNL Marketo Measure] 전체 원
exl-id: fd471771-33e2-413a-b155-02ba6e32e10c
source-git-commit: 09ffdbb0b1baeed870a3145268997e63a3707c97
workflow-type: tm+mt
source-wordcount: '637'
ht-degree: 0%

---

# 다음으로 전환 [!DNL Marketo Measure] 전체 원 {#transitioning-to-marketo-measure-from-full-circle}

전체 원에서 다음으로 이동 [!DNL Marketo Measure]? 당신만 그런 게 아니에요 다음은 이 제품을 구입한 다른 고객으로부터 얻은 가장 큰 고려 사항 및 단점입니다.

## 캠페인 기반 추적과 다중 소스 추적 {#campaign-based-tracking-vs-multi-source-tracking}

의 모든 상호 작용 [!UICONTROL Full Circle] CRM 캠페인 멤버십을 통해 추적됩니다. 사용 [!DNL Marketo Measure], 구매 여정은 JavaScript, CRM 캠페인 멤버십 및 CRM 활동 레코드 조합을 통해 컴파일됩니다. 기여도 분석 보고가 작동하려면 &quot;CRM 캠페인에서 모든 상호 작용을 추적해야 함&quot;에서 &quot;기여도 분석 보고가 작동되도록 하려면 CRM 캠페인에서 이 상호 작용 하위 집합만 추적해야 함&quot;으로 정신 이동을 하는 것은 까다로울 수 있습니다.

일반적으로 말해서, 다음과 같은 방법이 있습니다 [!DNL Marketo Measure] 는 주요 유형의 상호 작용에 대한 터치 포인트 레코드를 만듭니다.

* 사이트에 양식 채우기: [!DNL Marketo Measure] Javascript
* 사이트의 페이지 보기 수: 작성자 [!DNL Marketo Measure] 이 페이지 보기가 지정된 CRM 이정표(예: 리드 또는 기회 생성)를 유도하는 경우에만 Javascript
* 전화 회의 또는 박람회 등의 오프라인 상호 작용: CRM 캠페인 멤버십
* 사이트가 아닌 인터넷의 어디에서든 발생하는 디지털 상호 작용(예: 목록 업로드를 생성하는 타사 사이트에서 호스팅되는 웨비나)은 CRM 캠페인 멤버십
* 영업 팀과의 상호 작용: CRM 활동 레코드

CRM 캠페인 관리에 익숙하고 기존 프로세스를 제자리에 유지하는 것을 선호하는 경우, 괜찮습니다. 아프지 않아요 [!DNL Marketo Measure] CRM 캠페인에서 모든 상호 작용을 계속 추적하려면 다음을 수행하십시오. 터치 포인트 중복을 방지하기 위해 원하는 캠페인 하위 집합에서 터치포인트만 만드는 논리를 디자인할 수 있습니다.

## 가시성과 속성 비교 {#visibility-vs-attribution}

대부분의 전체 원 설정을 사용하면 사용자가 마케팅 또는 판매 활동으로 가지고 있는 모든 상호 작용을 볼 수 있습니다. 페이지 보기, 반복 페이지 방문, 중복되는 멤버십 및 중복 캠페인 3개 - 전체 원은 이러한 모든 것을 나타냅니다. 페이지를 300번 보면 전체 원이 300개의 중복 캠페인을 만들어 각 캠페인에 멤버십을 제공합니다. [!DNL Marketo Measure] 그렇지 않습니다. 그리고 그것은 우리의 입장에서 의식적인 디자인 결정이었습니다.

[!DNL Marketo Measure] 의미 있는 상호 작용을 나타내고 가장 영향력 있는 터치포인트 간에 가중치를 적절히 분배하는 속성 스토리를 제공하는 것을 목표로 합니다. 예: [!DNL Marketo Measure] 프레임워크는 일반적인 터치포인트로 페이지 보기(양식 채우기 없음)를 표시하지 않습니다. 독립형 페이지 보기는 구매 여정을 추진하는 데 영향을 줄 수 없지만, 지정된 CRM 이정표(예: 리드 또는 기회 생성) 전에 가장 최근 상호 작용인 경우 터치포인트를 만듭니다. 모든 것을 보여주고 싶지 않습니다. 우리는 속성 관점에서 중요한 것을 여러분께 보여드리고자 합니다.

작업 [!DNL Marketo Measure] rep 는 더 이상 팀에서 사용할 수 없는 데이터에 대해 적절한 기대치를 설정할 것입니다.

## 사전[!DNL Marketo Measure] 데이터 {#pre-marketo-measure-data}

표준 권장 사항은 를 배포한 날로부터 보고 및 데이터 수집을 시작하는 것입니다 [!DNL Marketo Measure] JavaScript를 앞으로 전환하면 이전 Full Circle 고객의 경우 두 배가 됩니다. 위의 두 섹션에 대해 생각해 보십시오. 더 많은 양의 데이터를 보는 데 익숙하며 CRM 캠페인 멤버십에서 오는 모든 데이터에 사용됩니다. 사용자 앞에 있는 해당 데이터의 일부 또는 전부를 포함하도록 선택하는 경우 [!DNL Marketo Measure] 구현에서는 JavaScript 구현 날짜에 사과와 사과를 비교하지 않습니다.

즉, 우리는 많은 고객들이 이러한 역사적인 데이터를 필요로 한다는 것을 확실히 이해합니다. 특히 판매 주기가 더 긴 경우(90일 이상) 다음과 같은 작업을 수행할 수 있습니다 [!DNL Marketo Measure] 사전[!DNL Marketo Measure] 데이터. 이 문제를 고객과 함께 자세히 논의하십시오 [!DNL Marketo Measure] rep, 및 항상 구현 날짜를 왜곡하면 채널 성능이나 참여가 개선되거나 감소할 수 있을 뿐만 아니라 잠재적으로 잘못된 추론도 나타날 수 있다는 점을 기억하십시오.

## 요약에서 {#in-summary}

Dell은 이러한 변경 사항을 처리하는 데 많은 고객을 지원하고 있습니다. 작업 [!DNL Marketo Measure] 대표자는 위의 영향과 사용자가 가질 수 있는 다른 문제를 파악합니다.
