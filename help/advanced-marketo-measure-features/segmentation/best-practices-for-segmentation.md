---
description: 세그먼테이션 우수 사례 - [!DNL Marketo Measure]
title: 세그먼테이션 우수 사례
exl-id: 68281210-383b-4688-86e9-27fbdc1fabbb
feature: Segmentation
source-git-commit: 518a984b0d8d640290bd9b637221fcdc0948e5b9
workflow-type: tm+mt
source-wordcount: '447'
ht-degree: 0%

---

# 세그먼테이션 우수 사례 {#best-practices-for-segmentation}

## 개요 {#overview}

[!DNL Marketo Measure] 세그멘테이션을 사용하면 CRM 필드를 기반으로 하여 기본적으로 필터인 규칙을 정의하여 개별 세그먼트로 버킷할 수 있습니다. 그러면 이러한 세그먼트를 Discover 대시보드뿐만 아니라 [!DNL Salesforce] 보고.

세그먼테이션은 을(를) 활용하는 데 매우 중요합니다. [!DNL Marketo Measure] 계정, 특히 내 Discover 보드. 이유: [!DNL Marketo Measure] 검색 보드는 사전 결정된 필터 세트로 제한되며, 세그멘테이션을 사용하면 검색 에서와 마찬가지로 데이터 탐색 기능을 사용할 수 있습니다. [!DNL Salesforce] 보고.

로 푸시될 때 [!DNL Salesforce], 세그먼트 값은 &quot;세그먼트&quot; 필드에 기록되며 모든 구매자 터치포인트 보고서 유형 내에 있습니다. 이를 통해 두 플랫폼 간에 동일한 보고를 수행할 수 있습니다. 세그먼트는 터치 포인트의 &#39;터치 포인트 세부 사항&#39;에서도 찾을 수 있습니다.

로 푸시될 때 [!UICONTROL Discover], 세그먼트는 모든 보드에 있는 필터 드롭다운 메뉴에 사용 가능한 필터로 나타납니다.

## 우수 사례 {#best-practice}

세그먼테이션을 처음 정의하거나 이전에 설정된 세그먼테이션을 검토하는 경우 다음 모범 사례를 염두에 두십시오.

* 단순하게 유지하십시오!
* 세그먼트 이름을 조직의 명명법에 맞게 정렬합니다(예: 범주 = 필터 이름, 세그먼트 = 필터 값).
* 규칙에 공식 필드 사용 안 함
* 가능하면 전체 단계에서 사용할 수 있도록 Lead/Contact 및 Opportunity에 세분화를 구축하십시오.
   * Marketo Measure Ultimate 고객이고 기본 대시보드 개체를 연락처로 설정한 경우 잠재 고객용 아래 두 필드를 사용하지 마십시오([여기에서 자세히 알아보기](/help/marketo-measure-ultimate/data-integrity-requirement.md){target="_blank"}).
      * b2b.personStatus
      * b2b.isConverted
   * 모든 세그먼트 범주가 전체 단계를 기준으로 정렬되는 것은 아닙니다.
      * 예를 들어 &#39;Opportunity Type&#39; 의 Segment 범주는 Lead 와 관련이 없지만 &#39;Region&#39; 과 관련된 Segment 는 전체 단계에서 정의할 수 있는 범주일 수 있습니다.
* CRM이든 BI 툴이든, 현재 데이터를 분할하려는 방법을 생각하고 이 를 의 세그먼트로 빌드하는 것을 고려하십시오. [!DNL Marketo Measure] 따라서 Discover에서 동일한 보고를 수행할 수 있습니다.

## 유지 관리에 대한 우수 사례 {#best-practice-for-maintenance}

최소 1년에 두 번 세분화를 검토하면 세분화가 최신 상태로 유지됩니다. 가장 좋은 방법은 내에서 규칙을 검토하는 것입니다.[!UICONTROL Segments]의 &#39; 탭 [!DNL Marketo Measure] 계정 설정 및 내에서 보고서 가져오기 [!DNL Salesforce] 작업 중인 세그먼트를 검토합니다. 이러한 단계는 귀하와 귀하의 팀이 귀하의 세분화에 대해 자신감을 갖는 데 도움이 될 것입니다. [!DNL Marketo Measure] 보고.

세분화 검토를 트리거할 수 있는 다른 이유는 다음과 같습니다.

* 마케팅 팀에서의 이직률
* 세그먼트 정의에 사용되는 필드 변경 사항
* 이미 설정된 세그먼트에 대한 추가 또는 변경 사항

>[!MORELIKETHIS]
>
>[사용자 정의 세분화를 설정하는 방법](/help/advanced-marketo-measure-features/segmentation/custom-segmentation.md)
