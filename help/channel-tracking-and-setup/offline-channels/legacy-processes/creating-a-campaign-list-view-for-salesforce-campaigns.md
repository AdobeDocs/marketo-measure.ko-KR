---
unique-page-id: 18874718
description: 캠페인 목록 보기 만들기 [!DNL Salesforce Campaigns] - [!DNL Marketo Measure] - 제품 설명서
title: 캠페인 목록 보기 만들기 [!DNL Salesforce] 캠페인
exl-id: 8c673ea3-ac24-4b3d-b67d-76888179c07a
feature: Channels
source-git-commit: 38c721d10ac33ae85da1d425b6af53b9e3dfd0a1
workflow-type: tm+mt
source-wordcount: '434'
ht-degree: 0%

---

# 캠페인 목록 보기 만들기 [!DNL Salesforce] 캠페인 {#creating-a-campaign-list-view-for-salesforce-campaigns}

구매자 터치포인트와 동기화하려는 캠페인에 대한 목록 보기를 만드는 방법을 알아봅니다.

>[!NOTE]
>
>이 문서에서는 오래된 프로세스를 다룹니다. 사용자는 다음을 사용할 것을 권장합니다. [새롭고 개선된 인앱 프로세스](/help/channel-tracking-and-setup/offline-channels/custom-campaign-sync.md){target="_blank"}.

만들 수 있는 캠페인 목록 보기를 통해 &#39;이동&#39; 위치를 통해 &#39;유형&#39; 및 &#39;구매자 터치포인트 활성화&#39; 필드를 확인하고 관리하여 각 항목을 확인할 수 있습니다. [!DNL Salesforce] 오프라인 마케팅 채널을 알리는 캠페인이 제대로 설정되어 있습니다.

1. 에서 캠페인 탭으로 이동 [!DNL Salesforce] 새 목록 보기 만들기
1. 보기 이름을 &quot;동기화할 캠페인&quot;으로 지정합니다. [!DNL Marketo Measure].&quot;
1. 이 목록에는 동기화하려는 캠페인만 표시됩니다. [!DNL Marketo Measure] 따라서 몇 가지 필터가 필요합니다.

   * **유형** [다음과 같음] &#39;오프라인 채널에 매핑된 모든 캠페인 유형&#39;. 에서 구현 계획 또는 오프라인 채널 탭을 참조하십시오. [!DNL Marketo Measure] ([experience.adobe.com/marketo-measure](https://experience.adobe.com/marketo-measure){target="_blank"} -> 내 계정 -> 설정 -> 오프라인 채널). 돋보기 아이콘을 통해 원하는 유형(오프라인 마케팅 채널에 매핑된 유형)을 선택할 수 있습니다.

      * 각 필터에 대해 최대 3개의 유형을 선택합니다. 필터 필드에는 포함할 수 있는 문자 수가 제한됩니다. 필터당 3개의 유형으로 시작하고 필요한 경우 &#39;유형&#39; 필터의 행을 더 추가합니다.

   * **만든 날짜** [크거나 같음] 본인 [!DNL Marketo Measure] 시작일. ROI 대시보드의 다음 위치에서 시작 날짜를 찾을 수 있습니다. [!DNL Marketo Measure] 앱. 대시의 날짜 범위에서 &#39;생성 날짜 이후&#39;를 선택하면 시작 날짜가 표시됩니다.
   * **&#42;레코드 유형&#42;** - 목록 보기에서 편집하려면 레코드 종류에 대한 필터를 추가해야 합니다. 편집해야 할 각 캠페인 레코드는 동일한 레코드 유형이어야 합니다.

1. 목록 보기에 표시되도록 선택한 필드를 편집합니다. 목록 보기의 전체 설정은 아래 예제와 같아야 합니다.

   이 보기를 사용하면 캠페인을 보고 필요한 경우 &#39;유형&#39; 및 &#39;구매자 터치포인트 활성화&#39; 필드를 편집할 수 있습니다. 동기화할 새 캠페인을 만들 때 [!DNL Marketo Measure], 이 보기에 표시되며, 목록 내에서 해당 캠페인에 대한 모든 설정을 바로 관리할 수 있습니다.

   목록 보기에서 인라인 편집을 수행하려면 [!DNL Salesforce] 설정:

   * **[!UICONTROL Setup]** > **[!UICONTROL User Interface]** > **[!UICONTROL Enable Inline Editing]**
   * 또한 고급 목록을 활성화해야 합니다(인라인 편집을 위해 상자 바로 아래).
   * 필드에 대한 권한이 있는지 확인하십시오.

>[!MORELIKETHIS]
>
>[목록 보기 인라인 편집의 일반적인 문제 해결](http://help.salesforce.com/articleView?id=000003911&amp;language=en_US&amp;type=1){target="_blank"}
