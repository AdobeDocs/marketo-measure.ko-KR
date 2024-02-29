---
unique-page-id: 18874720
description: 입찰 관리 도구의 영향 [!DNL Marketo Measure] - [!DNL Marketo Measure]
title: 입찰 관리 도구의 영향 [!DNL Marketo Measure]
exl-id: 67c00ad9-8b12-4238-8a1f-2d2f5ed04423
feature: APIs, Integration, UTM Parameters
source-git-commit: 915e9c5a968ffd9de713b4308cadb91768613fc5
workflow-type: tm+mt
source-wordcount: '259'
ht-degree: 0%

---

# 입찰 관리 도구의 영향 [!DNL Marketo Measure] {#how-bid-management-tools-affect-marketo-measure}

입찰 관리 플랫폼이 [!DNL Marketo Measure] 모든 것이 올바르게 추적되도록 매개 변수를 사용하여 추적 템플릿을 설정하는 방법과 함께 AdWords 및 BingAds를 추적하는 기능이 제공됩니다.

Kenshoo 및 Marin은 마케터가 다양한 검색 엔진을 사용하여 광고 캠페인을 추적, 관리 및 최적화할 수 있는 훌륭한 도구입니다. 주문 [!DNL Marketo Measure] 이러한 광고 URL에 추가할 매개 변수는 [!DNL Marketo Measure] 매개 변수. 광고 플랫폼을 다음에 연결할 수 없습니다. [!DNL Marketo Measure] 계정 및 자동 태깅을 활성화하면 [!DNL Marketo Measure] Kenshoo/Marin의 태깅 시스템과 경쟁할 태깅 시스템. 이로 인해 매개 변수가 변경되고 잘못 추가됩니다. 이를 우회하려면 다음을 사용하여 템플릿 추적 [!DNL Marketo Measure] 매개 변수는 Kenshoo 및 Marin 내에서 설정해야 합니다.

## 대상 [!DNL Adwords] 계정 {#for-adwords-accounts}

다음과 같이 추적 템플릿을 설정합니다.

* 다음을 클릭합니다. **[!UICONTROL Campaigns]** 탭.
* 다음을 클릭합니다. **[!UICONTROL Shared library]** 측면 탐색 모음의 링크.
* 클릭 **URL 옵션**.
* &quot;추적 템플릿&quot; 옆에 있는 **편집**.
* 다음 URL을 입력합니다.

   * 모든 광고 URL에 &quot;?&quot;가 있는 경우 여기에서 다음 URL을 사용합니다.
      * `{lpurl}&_bk={keyword}&_bt={creative}&_bm={matchtype}&_bn={network}&_bg={adgroupid}`
   * 광고 URL 중 &quot;?&quot;가 없는 경우 여기에서 다음 URL을 사용합니다.
      * `{lpurl}?_bk={keyword}&_bt={creative}&_bm={matchtype}&_bn={network}&_bg={adgroupid}`


## 대상 [!DNL Bing Ads] 계정 {#for-bing-ads-accounts}

다음과 같이 추적 템플릿을 설정합니다.

* 다음을 클릭합니다. **[!UICONTROL Campaigns]** 탭.
* 다음을 클릭합니다. **[!UICONTROL Shared library]** 측면 탐색 모음의 링크.
* 클릭 **URL 옵션**.
* &quot;추적 템플릿&quot; 옆에 있는 **편집**.
* 다음 URL을 입력합니다.

   * 모든 광고 URL에 &quot;?&quot;가 있는 경우 여기에서 다음 URL을 사용합니다.
      * `{lpurl}&_bt={adid}&utm_term={keyword}&utm_source=Bing_Yahoo&utm_medium=CPC`
   * 광고 URL 중 &quot;?&quot;가 없는 경우 여기에서 다음 URL을 사용합니다.
      * `{lpurl}?_bt={adid}&utm_term={keyword}&utm_source=Bing_Yahoo&utm_medium=CPC`
