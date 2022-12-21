---
unique-page-id: 42762628
description: Passport Dashboard 설명서 - [!DNL Marketo Measure] - 제품 설명서
title: Passport Dashboard 설명서
exl-id: 43cb01a8-d02e-4086-af57-d7ec9275f87a
source-git-commit: f13e55f009f33140ff36523212ed8b9ed5449a4d
workflow-type: tm+mt
source-wordcount: '391'
ht-degree: 0%

---

# Passport Dashboard 설명서 {#passport-dashboard-documentation}

Passport 대시보드를 사용하면 마케터가 지정된 기간 동안 각 파이프라인 단계를 거친 리드/연락처 및 기회를 볼 수 있습니다.

이 대시보드에는 두 개의 타일이 있습니다.

* 기회: 지정된 기간 동안 각 단계를 통과한 Opportunity 레코드 수입니다.
* 리드/연락처: 지정된 기간 동안 각 단계를 통과한 리드 또는 연락처 레코드 수입니다.

>[!NOTE]
>
>모든 Discover 대시보드에서 Lead 또는 Contact 중 하나의 개인 객체만 보고할 수 있습니다. 이 설정값은 [!UICONTROL Settings] > [!UICONTROL Reporting] > [!UICONTROL Attribution Settings] > [!UICONTROL Default Dashboard Object].

이 대시보드는 다음 필터를 지원합니다(모든 필터가 두 타일에 모두 적용됨).

* 날짜: 시간대를 선택합니다.
* 채널: 채널별로 레코드를 필터링합니다. 터치 포인트가 채널에 연결된 경우 레코드는 채널에 연결됩니다.
* 하위 채널: 하위 채널별로 레코드를 필터링합니다. 터치 포인트가 하위 채널과 연결된 경우 레코드가 하위 채널에 연결됩니다.
* 캠페인: 캠페인별로 레코드를 필터링합니다. 터치 포인트가 캠페인에 연결된 경우 레코드가 캠페인에 연결됩니다.
* 캠페인 소스: 캠페인 소스별로 레코드를 필터링합니다. 캠페인 소스의 예로는 Adwords, BingAds, Facebook, LinkedIn 등이 있습니다. 터치 포인트가 캠페인 소스와 연결된 경우 레코드가 캠페인 소스에 연결됩니다.
* CRM 계정 이름: CRM 계정 이름별로 레코드를 필터링합니다.
* 세그먼트 필터: 사용자 지정 세그먼트별로 레코드를 필터링합니다. 터치 포인트가 세그먼트에 연결된 경우 레코드가 세그먼트에 연결됩니다.

모든 필터에서 &quot;AND&quot; 논리가 사용됩니다.

>[!NOTE]
>
>레코드가 선택한 날짜의 단계를 변경하는 경우 부터 및 까지 단계와 모든 통과 단계에 대해 레코드가 계산됩니다.

## 기회 {#opportunities}

![](assets/one-1.png)

단계에는 OC, 선택한 단계 단계 단계(Open Opportunity 단계)가 포함됩니다.[!UICONTROL Settings] > [!UICONTROL CRM] > [!UICONTROL Stage Mapping]) 및 Won Opportunity 단계 ([!UICONTROL Settings] > [!UICONTROL CRM] > [!UICONTROL Stage Mapping]).

>[!NOTE]
>
>원 단계의 경우 레코드 수는 선택한 기간 동안 스테이지로 전환된 레코드에만 해당됩니다.

각 막대에서 드릴다운하여 각 단계에 대한 Opportunity 레코드를 볼 수 있습니다.

## 리드/연락처 {#leads-contacts}

![](assets/two-1.png)

스테이지에는 설정 - CRM - 단계 매핑 및 설정 - CRM - 단계 매핑의 변환된 리드/연락처 단계의 FT, LC, 선택한 단계 단계가 포함됩니다.

>[!NOTE]
>
>변환된 단계의 경우 레코드 수는 선택한 기간 동안 스테이지로 전환된 레코드에 대해서만 계산됩니다.

각 막대에서 드릴다운하여 각 단계에 대한 리드/연락처 레코드를 볼 수 있습니다.
