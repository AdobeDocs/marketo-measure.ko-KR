---
unique-page-id: 18874799
description: 페이지 레이아웃 지침 - [!DNL Marketo Measure]
title: 페이지 레이아웃 지침
exl-id: 627377f0-d0cf-448c-a7b5-7eb5634b9627
feature: Salesforce
source-git-commit: 9e672d0c568ee0b889461bb8ba6fc6333edf31ce
workflow-type: tm+mt
source-wordcount: '757'
ht-degree: 0%

---

# 페이지 레이아웃 지침 {#page-layout-instructions}

>[!NOTE]
>
>설명서에 &quot;[!DNL Marketo Measure]&quot;을(를) 지정하는 지침이 표시될 수 있지만 CRM에는 &quot;Bizible&quot;이 표시됩니다. 이를 업데이트하고 리브랜딩이 곧 CRM에 반영되도록 노력하고 있습니다.

[!DNL Marketo Measure] 데이터를 쉽게 보려면 [!UICONTROL Account], [!UICONTROL Contact], [!UICONTROL Lead], [!UICONTROL Opportunity] 및 [!UICONTROL Campaign] 개체에 대한 페이지 레이아웃을 업데이트하는 것이 좋습니다. 지침은 아래의 각 오브젝트 페이지 레이아웃에 대해 자세히 설명되어 있습니다.

시작하려면 먼저 [!DNL Salesforce] 설정 설정으로 이동하여 [!UICONTROL Customize] 탭을 찾습니다.

## Campaign 개체 {#campaign-object}

샌드박스에 대해서만 SFDC Campaign에 [!DNL Marketo Measure] 필드를 추가하는 것이 좋습니다. 필드는 터치포인트 생성을 테스트하는 데 사용할 수 있습니다. 프로덕션에서는 [!DNL Marketo Measure] 터치포인트 날짜 일괄 업데이트 단추만 추가하는 것이 좋습니다. Campaign 동기화 규칙을 만들 수 있으므로 프로덕션에 [!DNL Marketo Measure] 필드를 추가하지 않는 것이 좋습니다.

1. 빌드 옵션에서 **[!UICONTROL Campaigns]**&#x200B;을(를) 선택합니다.

1. **[!UICONTROL Page Layouts]**&#x200B;을(를) 클릭합니다.

   ![](assets/1-1.jpg)

1. 업데이트할 페이지 레이아웃 옆에 있는 **[!UICONTROL Edit]**&#x200B;을(를) 클릭합니다.

   ![](assets/2-1.jpg)

1. [!UICONTROL fields] 옵션에서 **[!UICONTROL Enable Buyer Touchpoints]** 필드를 선택하고 페이지에서 원하는 위치로 드래그합니다. 그런 다음 **[!UICONTROL Touchpoint Start Date]** 및 **[!UICONTROL Touchpoint End Date]** 필드를 추가합니다.

   ![](assets/3-2.png)

1. 그런 다음 페이지 맨 위에서 빠른 찾기 메뉴의 &quot;[!UICONTROL Buttons]&quot; 옵션을 클릭합니다.

1. **[!UICONTROL Bulk Update Touchpoint Date]** 단추를 사용자 지정 단추 섹션으로 끕니다.

   ![](assets/4-1.jpg)

1. **[!UICONTROL Save]**&#x200B;을(를) 클릭합니다.

   >[!NOTE]
   >
   >여러 캠페인 레코드 유형을 사용하는 경우 **[!UICONTROL Enable Buyer Touchpoints]** 필드에 대한 선택 목록 값을 업데이트해야 합니다. 자세한 내용은 [이 문서](/help/channel-tracking-and-setup/offline-channels/configurations-for-multiple-campaign-record-types.md)를 참조하세요.

## 잠재 고객 {#leads}

1. 빌드 옵션에서 **[!UICONTROL Leads]**&#x200B;을(를) 선택합니다.

1. **[!UICONTROL Page Layouts]**&#x200B;을(를) 클릭합니다.

1. 업데이트할 페이지 레이아웃 옆에 있는 **[!UICONTROL Edit]**&#x200B;을(를) 클릭합니다. 여러 페이지 레이아웃에는 구매자 터치포인트 섹션이 포함될 수 있습니다.

1. 빠른 찾기 메뉴 내에서 왼쪽의 VisualForce 페이지 옵션을 클릭합니다.

1. 섹션을 만들고 이름을 &quot;구매자 터치포인트&quot;로 지정합니다.

   >[!NOTE]
   >
   >이러한 각 섹션에 대해 &quot;한 열&quot; 형식을 선택합니다.

1. **[!UICONTROL Marketo Measure Lead Related List]** VisualForce 페이지를 페이지 레이아웃 섹션으로 끌어옵니다.

   ![](assets/5-1.png)

1. [!DNL VisualForce] 페이지에서 렌치를 클릭하고 높이를 100으로 변경한 후 스크롤 막대를 활성화합니다.

1. 메뉴로 돌아가서 [!UICONTROL Canvas Apps] 섹션을 선택하고 만든 터치포인트 [!DNL VisualForce] 섹션 아래에 &quot;Marketo Measure 인사이트&quot;라는 섹션을 만듭니다.

   >[!NOTE]
   >
   >이러한 각 섹션에 대해 &quot;한 열&quot; 형식을 선택합니다.

1. [!DNL Marketo Measure Insights] 캔버스 앱을 새로 만든 섹션으로 끌어옵니다. **저장**&#x200B;을 클릭합니다. Salesforce가 즉시 인식하지 못하므로 캔버스 앱에 드롭하기 전에 페이지 레이아웃을 먼저 저장해야 하는 경우가 있습니다. 따라서 섹션을 만든 후 페이지 레이아웃을 저장한 다음 다시 편집하여 해당 섹션 내에 캔버스 앱을 드래그합니다. 이는 모든 객체에 적용됩니다.

   >[!NOTE]
   >
   >[!DNL Marketo Measure Insights] 캔버스 앱이 제대로 작동하려면 [권한이 올바르게 구성되어야 합니다](/help/configuration-and-setup/marketo-measure-insights-canvas-app/marketo-measure-insights-configuration.md).

   >[!TIP]
   >
   >[!DNL Marketo Measure] 터치포인트가 개체로 존재하기 전의 기존 필드이므로 대부분의 고객은 (FT) 또는 (LC)로 끝나는 필드를 사용하지 않습니다.

[!DNL Marketo Measure] ABM 기능을 사용하는 경우 [추가 페이지 레이아웃 지침을 보려면 여기를 클릭](/help/advanced-marketo-measure-features/account-based-marketing/account-based-marketing-overview.md)하십시오.

## 연락처 {#contacts}

1. 빌드 옵션에서 **[!UICONTROL Contacts]**&#x200B;을(를) 선택합니다.

1. **[!UICONTROL Page Layouts]**&#x200B;을(를) 클릭합니다.

1. 편집할 페이지 레이아웃을 선택합니다.

   빠른 찾기 메뉴의 관련 목록 옵션으로 이동하여 **[!UICONTROL Buyer Touchpoints]** 관련 목록을 추가하십시오.

1. 렌치 아이콘을 클릭하고 다음 열을 이 순서로 추가합니다.

   * Buyer Touchpoint
   * 마케팅 채널
   * 터치포인트 Source
   * 광고 캠페인 이름
   * 접점 위치
   * 접점 날짜

1. 정렬 기준: 터치포인트 날짜, 오름차순

   ![](assets/6.jpg)

1. 단추 옵션을 확장하고 **[!UICONTROL New]**&#x200B;을(를) 선택 취소합니다.

   ![](assets/7.png)

1. 메뉴의 [!UICONTROL Related List] 옵션으로 돌아가서 이제 **[!UICONTROL Buyer Attribution Touchpoint]** 관련 목록을 추가하십시오.

1. 렌치 아이콘을 클릭하고 다음 열을 이 순서로 추가합니다.

   * 속성 접점
   * 마케팅 채널
   * 기회
   * 광고 캠페인 이름
   * 접점 유형
   * 접점 위치
   * 기여도 분석 % W자형(_또는 전체 경로 또는 사용자 지정 같은 가장 강력한 기여도 분석 모델_)
   * 매출 W자형(_또는 전체 경로 또는 사용자 지정 같은 가장 강력한 속성 모델_)
   * 접점 날짜

1. 터치포인트 [!UICONTROL Date] > [!UICONTROL Ascending]을(를) 기준으로 정렬합니다.

1. 단추 섹션을 확장하고 **[!UICONTROL New]**&#x200B;을(를) 선택 취소합니다.

1. **[!UICONTROL Save]**&#x200B;을(를) 클릭합니다.

## 기회 {#opportunities}

1. 빌드 옵션에서 **[!UICONTROL Opportunities]**&#x200B;을(를) 선택합니다.

1. **[!UICONTROL Page Layouts]**&#x200B;을(를) 클릭합니다.

1. 편집할 페이지 레이아웃을 선택합니다.

1. **[!UICONTROL Buyer Attribution Touchpoint]** 관련 목록을 추가하고 렌치를 클릭하여 Opportunities에 대해 다음 열을 추가합니다.

   * 속성 접점
   * 마케팅 채널
   * 연락처
   * 광고 캠페인 이름
   * 접점 유형
   * 접점 위치
   * 기여도 분석 % W자형(_또는 전체 경로 또는 사용자 지정 같은 가장 강력한 기여도 분석 모델_)
   * 매출 W자형(_또는 전체 경로 또는 사용자 지정 같은 가장 강력한 속성 모델_)
   * 접점 날짜

1. [!UICONTROL Touchpoint Date] > [!UICONTROL Ascending]을(를) 기준으로 정렬합니다.

1. [!UICONTROL Buttons] 섹션 내에서 **[!UICONTROL New]**&#x200B;을(를) 선택 취소합니다.

1. **[!UICONTROL Save]**&#x200B;을(를) 클릭합니다.

## 계정 {#accounts}

1. 빌드 옵션에서 **[!UICONTROL Accounts]**&#x200B;을(를) 선택합니다.

1. **[!UICONTROL Page Layouts]**&#x200B;을(를) 클릭합니다.

1. 편집할 페이지 레이아웃을 선택합니다.

1. **[!UICONTROL Buyer Attribution Touchpoint]** 관련 목록을 추가하고 렌치를 클릭하여 다음 열을 추가합니다.

   * 속성 접점
   * 마케팅 채널
   * 기회
   * 광고 캠페인 이름
   * 접점 유형
   * 접점 위치
   * 기여도 분석 % W자형(_또는 전체 경로 또는 사용자 지정 같은 가장 강력한 기여도 분석 모델_)
   * 매출 W자형(_또는 전체 경로 또는 사용자 지정 같은 가장 강력한 속성 모델_)
   * 접점 날짜

1. 접점 날짜 > 오름차순으로 정렬합니다.

1. [!UICONTROL Buttons] 섹션 내에서 **[!UICONTROL New]**&#x200B;을(를) 선택 취소합니다.

1. **[!UICONTROL Save]**&#x200B;을(를) 클릭합니다.

[!DNL Marketo Measure] ABM 기능을 사용하는 경우 [추가 페이지 레이아웃 지침](/help/advanced-marketo-measure-features/account-based-marketing/account-based-marketing-overview.md)을 검토하십시오.
