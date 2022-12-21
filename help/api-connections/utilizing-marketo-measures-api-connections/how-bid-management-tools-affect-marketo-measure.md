---
unique-page-id: 18874720
description: 입찰 관리 도구가 영향을 미치는 방식 [!DNL Marketo Measure] - [!DNL Marketo Measure] - 제품 설명서
title: 입찰 관리 도구가 영향을 미치는 방식 [!DNL Marketo Measure]
exl-id: 67c00ad9-8b12-4238-8a1f-2d2f5ed04423
source-git-commit: 65e7f8bc198ceba2f873ded23c94601080ad0546
workflow-type: tm+mt
source-wordcount: '261'
ht-degree: 0%

---

# 입찰 관리 도구가 영향을 미치는 방식 [!DNL Marketo Measure] {#how-bid-management-tools-affect-marketo-measure}

입찰 관리 플랫폼이 [!DNL Marketo Measure] 모든 것이 올바르게 추적되도록 매개 변수로 추적 템플릿을 설정하는 방법과 함께 AdWords 및 BingAds를 추적하는 기능.

Kenshoo 및 Marin은 마케터가 다양한 검색 엔진을 사용하여 광고 캠페인을 추적, 관리 및 최적화할 수 있는 훌륭한 도구입니다. 대상 [!DNL Marketo Measure] 이러한 광고 URL에 추가할 매개 변수는 다음과 같이 추적 템플릿을 설정해야 합니다 [!DNL Marketo Measure] 매개 변수. 광고 플랫폼을 [!DNL Marketo Measure] 계정을 설정하고 이로 인해 자동 태그 지정을 활성화합니다 [!DNL Marketo Measure] Kenshoo/Marin의 태깅 시스템과 경쟁할 태깅 시스템. 이렇게 하면 매개 변수가 변경되고 잘못 추가됩니다. 이를 피하기 위해 다음을 사용하여 템플릿을 추적합니다 [!DNL Marketo Measure] Kenshoo 및 Marin 내에서 매개 변수를 설정해야 합니다.

## 대상 [!DNL Adwords] 계정 {#for-adwords-accounts}

다음과 같이 추적 템플릿을 설정합니다.

* 을(를) 클릭합니다. **[!UICONTROL Campaigns]** 탭.
* 을(를) 클릭합니다. **[!UICONTROL Shared library]** 링크를 클릭합니다.
* 클릭 **URL 옵션**.
* 추적 템플릿 옆의 **편집**.
* URL을 입력합니다.

   * 모든 광고 URL에 &quot;?&quot;가 있는 경우 이 URL에서 다음 URL을 사용합니다.
      * `{lpurl}&_bk={keyword}&_bt={creative}&_bm={matchtype}&_bn={network}&_bg={adgroupid}`
   * 광고 URL에 &quot;?&quot;가 없는 경우 이 URL에서 다음 URL을 사용합니다.
      * `{lpurl}?_bk={keyword}&_bt={creative}&_bm={matchtype}&_bn={network}&_bg={adgroupid}`


## 대상 [!DNL Bing Ads] 계정 {#for-bing-ads-accounts}

다음과 같이 추적 템플릿을 설정합니다.

* 을(를) 클릭합니다. **[!UICONTROL Campaigns]** 탭.
* 을(를) 클릭합니다. **[!UICONTROL Shared library]** 링크를 클릭합니다.
* 클릭 **URL 옵션**.
* 추적 템플릿 옆의 **편집**.
* URL을 입력합니다.

   * 모든 광고 URL에 &quot;?&quot;가 있는 경우 이 URL에서 다음 URL을 사용합니다.
      * `{lpurl}&_bt={adid}&utm_term={keyword}&utm_source=Bing_Yahoo&utm_medium=CPC`
   * 광고 URL에 &quot;?&quot;가 없는 경우 이 URL에서 다음 URL을 사용합니다.
      * `{lpurl}?_bt={adid}&utm_term={keyword}&utm_source=Bing_Yahoo&utm_medium=CPC`
