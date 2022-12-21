---
description: 세그멘테이션 우수 사례 - [!DNL Marketo Measure] - 제품 설명서
title: 세그멘테이션 우수 사례
exl-id: 68281210-383b-4688-86e9-27fbdc1fabbb
source-git-commit: b59c79236d3e324e8c8b07c5a6d68bd8176fc8a9
workflow-type: tm+mt
source-wordcount: '418'
ht-degree: 0%

---

# 세그멘테이션 우수 사례 {#best-practices-for-segmentation}

## 개요 {#overview}

[!DNL Marketo Measure] 세그멘테이션을 사용하면 CRM 필드를 기반으로 규칙을 개별 세그먼트에 버킷하는 필터인 규칙을 정의할 수 있습니다. 그러면 이러한 세그먼트를 Discover 대시보드뿐만 아니라 [!DNL Salesforce] 보고.

세그먼테이션은 [!DNL Marketo Measure] 계정, 특별히 Discover 보드 내에서 사용할 수 있습니다. 왜냐하면 [!DNL Marketo Measure] 검색 보드는 미리 결정된 필터 세트로 제한되며 세그먼테이션을 사용하면 다음과 같이 Discover에서 데이터를 분석할 수 있습니다 [!DNL Salesforce] 보고.

에 푸시될 때 [!DNL Salesforce], 세그먼트 값은 &quot;세그먼트&quot; 필드에 기록되며 구매자 터치 포인트 보고서 유형 내에 있습니다. 이렇게 하면 두 플랫폼 모두에서 동일한 보고를 수행할 수 있습니다. 세그먼트는 모든 터치 포인트의 &#39;터치 포인트 세부 사항&#39;에서도 찾을 수 있습니다.

Discover로 푸시되면 세그먼트는 모든 보드에 있는 필터 드롭다운 메뉴 내에 사용 가능한 필터로 표시됩니다.

## 우수 사례 {#best-practice}

처음 세그멘테이션을 정의하거나 이전에 설정한 세그멘테이션을 복습하든 간에 다음 우수 사례를 기억하십시오.

* 간단해!
* 세그먼트 이름을 조직의 명명법(예: 카테고리 = 필터 이름, 세그먼트 = 필터 값)에 맞춥니다
* 규칙에서 공식 필드를 사용하지 마십시오
* 가능하면 전체 단계에서 사용할 수 있도록 리드/연락처 및 기회 둘 다에 세분화를 작성합니다
   * 모든 세그먼트 카테고리가 전체 단계 전체에서 정렬되지는 않습니다
      * &#39;기회 유형&#39;의 세그먼트 카테고리는 리드와 관련이 없지만 &#39;지역&#39;과 관련된 세그먼트는 단계 전체에서 정의할 수 있는 카테고리일 수 있습니다
* CRM이든 BI 도구이든 현재 데이터를 분할하는 방법을 생각해 보십시오. 에서 세그먼트로 만드십시오 [!DNL Marketo Measure] Discover에서 동일한 보고를 사용할 수 있습니다.

## 유지 관리 우수 사례 {#best-practice-for-maintenance}

세그먼테이션을 연 2회 이상 검토하면 세그먼테이션이 최신 상태로 유지되는지 확인할 수 있습니다. 우수 사례로서, &#39; 내에서 규칙을 검토하는 것이 좋습니다.[!UICONTROL Segments]&#39; 탭 [!DNL Marketo Measure] 계정 설정 및 내에서 보고서 가져오기 [!DNL Salesforce] 세그먼트 작업을 검토하려면 다음을 수행하십시오. 이러한 단계는 사용자 및 팀이 세그먼테이션에 대해 자신감을 가지고 나중에 [!DNL Marketo Measure] 보고.

이러한 이유로 세그먼테이션 검토를 트리거할 수 있는 기타 이유는 다음과 같습니다.

* 마케팅 팀의 이직률
* 세그먼트를 정의하는 데 사용되는 필드 변경
* 이미 설정된 세그먼트에 대한 추가 또는 변경 사항입니다

>[!MORELIKETHIS]
>
>[사용자 지정 세그멘테이션을 설정하는 방법](/help/advanced-marketo-measure-features/segmentation/custom-segmentation.md)
