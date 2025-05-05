---
description: 세분화 모범 사례 - [!DNL Marketo Measure]
title: 세그먼테이션 우수 사례
exl-id: 68281210-383b-4688-86e9-27fbdc1fabbb
feature: Segmentation
source-git-commit: 9e672d0c568ee0b889461bb8ba6fc6333edf31ce
workflow-type: tm+mt
source-wordcount: '448'
ht-degree: 0%

---

# 세그먼테이션 우수 사례 {#best-practices-for-segmentation}

## 개요 {#overview}

[!DNL Marketo Measure] 세그먼테이션을 사용하면 CRM 필드를 기반으로 하여 개별 세그먼트로 버킷할 수 있는 기본 필터인 규칙을 정의할 수 있습니다. 이러한 세그먼트는 Discover 대시보드와 [!DNL Salesforce] 보고에서 사용할 수 있습니다.

세그먼테이션은 [!DNL Marketo Measure] 계정, 특히 Discover 보드 내에서 사용하는 데 중요합니다. [!DNL Marketo Measure] 검색 보드는 미리 결정된 필터 세트로 제한되어 있으므로 세분화를 통해 [!DNL Salesforce] 보고에서와 마찬가지로 검색 시 데이터를 구분할 수 있습니다.

[!DNL Salesforce] (으)로 푸시되면 세그먼트 값이 &quot;세그먼트&quot; 필드에 기록되며 구매자 접점 보고서 유형 내에 있습니다. 이를 통해 두 플랫폼 간에 동일한 보고를 수행할 수 있습니다. 세그먼트는 터치 포인트의 &#39;터치 포인트 세부 사항&#39;에서도 찾을 수 있습니다.

[!UICONTROL Discover]에 푸시하면 세그먼트가 모든 게시판에 있는 필터 드롭다운 메뉴에 사용 가능한 필터로 나타납니다.

## 우수 사례 {#best-practice}

세그먼테이션을 처음 정의하든 아니면 이전에 설정된 세그먼테이션을 검토하든 관계없이 다음 모범 사례를 고려하십시오.

* 단순하게 유지하십시오!
* 세그먼트 이름을 조직의 명명법에 맞게 정렬합니다(예: 범주 = 필터 이름, 세그먼트 = 필터 값).
* 규칙에 공식 필드 사용 안 함
* 가능하면 전체 단계에서 사용할 수 있도록 Lead/Contact 및 Opportunity에 세분화를 구축하십시오.
   * Marketo Measure Ultimate 고객이고 기본 대시보드 개체를 연락처로 설정한 경우 아래 두 필드를 리드와 관련된 것으로 사용하지 마십시오([자세히 알아보기](/help/marketo-measure-ultimate/data-integrity-requirement.md){target="_blank"}).
      * b2b.personStatus
      * b2b.isConverted
   * 모든 세그먼트 범주가 전체 단계를 기준으로 정렬되는 것은 아닙니다.
      * 예를 들어 &#39;Opportunity Type&#39; 의 Segment 범주는 Lead 와 관련이 없지만 &#39;Region&#39; 과 관련된 Segment 는 전체 단계에서 정의할 수 있는 범주일 수 있습니다.
* CRM이든 BI 도구이든 현재 데이터를 분할하는 방법을 생각해 보고, [!DNL Marketo Measure]에서 세그먼트로 빌드하여 Discover에서 동일한 보고를 수행할 수 있도록 하십시오.

## 유지 관리에 대한 우수 사례 {#best-practice-for-maintenance}

최소 1년에 두 번 세분화를 검토하면 세분화가 최신 상태로 유지됩니다. 가장 좋은 방법은 [!DNL Marketo Measure] 계정 설정의 &#39;[!UICONTROL Segments]&#39; 탭에서 규칙을 검토하고 [!DNL Salesforce] 내에서 보고서를 가져와 작동 중인 세그먼트를 검토하는 것입니다. 이러한 단계를 통해 귀하와 귀하의 팀이 세분화와 그에 따른 [!DNL Marketo Measure] 보고에 자신감을 가질 수 있습니다.

세분화 검토를 트리거할 수 있는 다른 이유는 다음과 같습니다.

* 마케팅 팀에서의 이직률
* 세그먼트 정의에 사용되는 필드 변경 사항
* 이미 설정된 세그먼트에 대한 추가 또는 변경 사항

>[!MORELIKETHIS]
>
>[사용자 지정 세그먼테이션을 설정하는 방법](/help/advanced-marketo-measure-features/segmentation/custom-segmentation.md)
