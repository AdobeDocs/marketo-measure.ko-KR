---
unique-page-id: 42762648
description: 집단 여정 대시보드 설명서 - [!DNL Marketo Measure] - 제품 설명서
title: 집단 여정 대시보드 설명서
exl-id: b139f720-86ae-4f6d-9dfc-cc67b4186f88
feature: Reporting
source-git-commit: f8a37a996afefe78900e57e1eb166cdd50b5347f
workflow-type: tm+mt
source-wordcount: '589'
ht-degree: 0%

---

# 집단 여정 대시보드 설명서 {#cohort-journey-dashboard-documentation}

집단 영향 및 단계 대시보드를 사용하면 마케터는 선택한 시간대에 대한 시작 집단 단계의 진행률을 보고 전환율을 측정할 수 있습니다.

가장 큰 차이는 코호트 단계에서부터 각 개체를 어떻게 계산하느냐이다.

* 집단 단계: 각 단계의 결과는 이전 단계에서 직접 파생됩니다.

   * 설정된 집단 시작 시간 이후 각 단계를 거치는 레코드만 계산됩니다.

![](assets/cohort-journey-dashboard-documentation-1.png)

* 코호트 영향: 각 단계의 결과는 이전 단계가 아닌 코호트 단계에서 파생됩니다.

   * 각 단계의 모든 레코드는 설정된 집단 시작 시간 이후에 발생한 한 계산됩니다. 유입 경로를 통한 이동뿐만 아니라 엔티티가 집단 단계에서 어떻게 영향을 받았는지 살펴보기 때문에 이 대시보드에는 유입 경로 대시보드보다 더 많은 레코드가 있을 것입니다.

![](assets/cohort-journey-dashboard-documentation-2.png)

각 대시보드에는 두 개의 타일이 있습니다.

* 집단 매출: 집단 여정 타일의 거래 단계에 있는 모든 기회의 총 기회 금액.
* 집단 여정: 선택한 기간에 대한 시작 집단 단계에서 각 여정 단계로의 진행입니다.

>[!NOTE]
>
>모든 Discover 대시보드에서 Lead 또는 Contact 중 하나의 개인 객체만 보고할 수 있습니다. 다음에서 설정됩니다. [!UICONTROL Settings] > [!UICONTROL Reporting] > [!UICONTROL Attribution Settings] > [!UICONTROL Default Dashboard Object].

대시보드는 다음 필터를 지원합니다.

* 집단 단계: 시작 집단 단계를 선택합니다. 다음의 모든 단계의 기록은 코호트 단계의 기록에서 진화되었다.
* 집단 날짜 범위: 선택한 집단 단계의 시간대를 선택합니다. 집단 스테이지와 함께 시작 데이터 세트를 정의합니다.
* 마감 일자: 다음 모든 단계에서 레코드 진행이 발생해야 하는 일자를 선택합니다. 기본값은 오늘입니다. 이는 코호트 단계를 제외한 모든 단계에 적용됩니다.
* 채널: 채널을 기준으로 레코드를 필터링합니다. 터치포인트 중 하나가 채널에 연결된 경우 레코드는 채널에 연결됩니다.
* 하위 채널: 하위 채널별로 레코드를 필터링합니다. 터치포인트 중 어느 하나라도 하위 채널에 연결되어 있으면 레코드는 하위 채널에 연결됩니다.
* 캠페인: 캠페인별로 레코드를 필터링합니다. 접점이 캠페인에 연결된 경우 레코드는 캠페인에 연결됩니다.
* 캠페인 소스: 캠페인 소스별로 레코드를 필터링합니다. 캠페인 소스의 예는 다음과 같습니다 [!DNL Adwords], [!DNL BingAds], [!DNL Facebook], [!DNL LinkedIn]등 접점이 캠페인 소스에 연결되어 있는 경우 레코드는 캠페인 소스에 연결됩니다.
* 세그먼트 필터: 사용자 지정 세그먼트별로 레코드를 필터링합니다. 터치포인트 중 하나가 세그먼트에 연결된 경우 레코드는 세그먼트에 연결됩니다.

모든 필터에서 &quot;AND&quot; 논리가 사용됩니다.

>[!NOTE]
>
>세그먼트 필터는 LC 스테이지 및 이후에만 적용됩니다. 집단 단계가 알 수 없음 또는 알려짐 이고 세그먼트 필터 중 하나에 값이 있는 경우 대시보드에서 결과가 반환되지 않습니다.

단계는 알 수 없음, 알려짐, LC, 오픈 리드/연락처 단계의 선택된 단계 단계(설정 > CRM > 단계 매핑), OC, 오픈 기회 단계의 선택된 단계(설정 > CRM > 단계 매핑) 및 거래(마감된 성공 기회)입니다.

>[!NOTE]
>
>집단 단계 이외의 다른 단계로 정의된 여정 단계에 대한 레코드 수에는 선택한 일정의 시작 일자 이후 및 마감 일자 이전에 생성된 집단 레코드와 관련된 모든 신규 레코드가 포함됩니다. 이것은 인과관계라고 추론된다.

각 막대에서 드릴다운하여 각 단계에 대한 레코드를 볼 수 있습니다.

* 알 수 없음의 경우 익명 방문자 세부 정보가 표시됩니다.
* 알려진 경우 알려진 방문자 세부 사항이 표시됩니다.
* LC 및 Open Lead/Contact 단계의 경우 Lead/Contact 세부 정보가 표시됩니다.
* OC, Opportunity 진행 단계 및 Deal 의 경우 Opportunity 세부 정보가 표시됩니다.