---
unique-page-id: 18874678
description: ' [!DNL Marketo Measure] AdWords 태그 지정 이해 - [!DNL Marketo Measure]'
title: ' [!DNL Marketo Measure] AdWords 태그 지정 이해'
exl-id: c6658766-d3a8-46ed-b2d2-826eb61ce269
feature: APIs, Integration, UTM Parameters
source-git-commit: 9e672d0c568ee0b889461bb8ba6fc6333edf31ce
workflow-type: tm+mt
source-wordcount: '565'
ht-degree: 0%

---

# [!DNL Marketo Measure]개 AdWords 태그 지정 이해 {#understanding-marketo-measure-adwords-tagging}

광고를 세분화된 수준에서 추적하려면 광고 대상 URL이 고유해야 합니다. 이를 위해 [!DNL Marketo Measure] 자동 태깅은 [!DNL AdWords] 광고의 광고 대상 URL에 추적 매개 변수를 자동으로 추가합니다. 아래의 예를 살펴보겠습니다.

다음 URL은 세부적인 데이터를 제공하지 않습니다.

* `http://example.com/landing-page?myParam=foo`

그러나 [!DNL Marketo Measure] 매개 변수로 인해 동일한 URL에서 세분화된 데이터를 제공합니다.

* `http://example.com/landing-page?myParam=foo&_bt={creative}&_bk={keyword}&_bm={matchtype}&_bn={network}&_bg={adgroupid}`

## [!DNL Marketo Measure] 자동 태그 지정 작동 방식 {#how-marketo-measure-auto-tagging-works}

**[!DNL Marketo Measure]이(가) 추적 템플릿을 찾은 경우:**

* [!DNL Marketo Measure]이(가) 추적 템플릿에 매개 변수를 추가합니다.
* Kenshoo 또는 Marin과 같은 추적 템플릿에 서드파티 리디렉션이 있으면 [!DNL Marketo Measure]이(가) 아무 작업도 수행하지 않습니다. 대신 계정의 타사 도구에 [매개 변수를 추가 [!DNL Marketo Measure] 해야 합니다](/help/api-connections/utilizing-marketo-measures-api-connections/how-bid-management-tools-affect-marketo-measure.md){target="_blank"}.

그러나 추적 템플릿이 없으면 [!DNL Marketo Measure]에서 다음을 수행합니다.

* [!DNL Marketo Measure] 매개 변수에 대한 모든 광고 대상 URL을 검사합니다.
* 만약 발견되면, 당신은 갈 수 있습니다.
* 찾을 수 없으면 [!DNL Marketo Measure]에서 광고 대상 URL 끝에 매개 변수를 추가합니다. 새 광고의 경우 [!DNL Marketo Measure]은(는) 2시간 안에 광고 대상 URL에 매개 변수를 추가합니다.
* [!DNL Marketo Measure]이(가) 연결할 수 있도록 자동 태그 지정을 활성화하기 전에 추적 템플릿을 만들어 광고 기록이 재설정되지 않도록 하는 것이 중요합니다.

[!DNL Marketo Measure]에서는 모든 광고에 대해 광고 기록이 중단되거나 삭제될 위험 없이 매개 변수를 추가하거나 뺄 수 있으므로 계정 수준, 캠페인 수준 또는 광고 그룹 수준 추적 템플릿을 사용하는 것이 좋습니다.

## 추적 템플릿 {#tracking-templates}

[!DNL Google AdWords]에서 설명한 대로 추적 템플릿은 랜딩 페이지에 연결하는 데 사용되는 URL입니다. 수집된 추적 정보는 광고 트래픽을 이해하는 데 사용됩니다. Google에서 자세한 내용을 보려면 [여기를 클릭](https://support.google.com/adwords/answer/7197008?hl=en){target="_blank"}하십시오.

[!DNL Marketo Measure]은(는) 계정 수준, 캠페인 수준 또는 광고 그룹 수준 추적 템플릿을 사용하는 것을 권장합니다. 광고 기록이 중단되거나 삭제될 위험 없이 모든 광고에 대한 매개 변수를 추가하거나 뺄 수 있습니다.

[!DNL Marketo Measure]에서 권장하는 두 개의 추적 템플릿이 있습니다. 적합한 버전을 확인하려면 다음을 사용하십시오.

* 모든 광고 URL에 &quot;?&quot;가 있는 경우 여기에서 다음 URL을 사용합니다.

`{lpurl}&_bt={creative}&_bk={keyword}&_bm={matchtype}&_bn={network}&_bg={adgroupid}`

* 광고 URL 중 &quot;?&quot;가 없는 경우 여기에서 다음 URL을 사용합니다.

`{lpurl}?_bt={creative}&_bk={keyword}&_bm={matchtype}&_bn={network}&_bg={adgroupid}`

## 계정 레벨에서 추적 템플릿 설정 {#setting-up-a-tracking-template-at-the-account-level}

1. [!DNL Google AdWords] 계정에 로그인합니다.

1. 확장 창에서 **[!UICONTROL All campaigns]**&#x200B;을(를) 클릭한 다음 **[!UICONTROL Settings]**&#x200B;을(를) 클릭합니다.

   ![](assets/1.png)

1. 맨 위에 있는 **[!UICONTROL Account Settings]**&#x200B;을(를) 클릭한 다음 **[!UICONTROL Tracking Template]**&#x200B;을(를) 클릭합니다. [!DNL Marketo Measure] 추적 템플릿을 입력하십시오.

   ![](assets/2-1.png)

1. **[!UICONTROL Save]**&#x200B;을(를) 클릭합니다.

## 캠페인 수준에서 추적 템플릿 설정 {#setting-up-a-tracking-template-at-the-campaign-level}

1. 확장 창에서 **[!UICONTROL All campaigns]**&#x200B;을(를) 클릭한 다음 **[!UICONTROL Campaigns]**&#x200B;을(를) 클릭합니다.

   ![](assets/3.png)

1. 적용 가능한 모든 캠페인 또는 **[!UICONTROL Select All]**&#x200B;을(를) 선택하고 **[!UICONTROL Edit]**&#x200B;을(를) 클릭한 다음 **[!UICONTROL Change Tracking Templates]**&#x200B;을(를) 클릭합니다.

   ![](assets/4-1.png)

1. [!DNL Marketo Measure] 추적 템플릿을 입력하고 **[!UICONTROL Apply]**&#x200B;을(를) 클릭합니다.

## 광고 그룹 수준에서 추적 템플릿 설정: {#setting-up-a-tracking-template-at-the-ad-group-level}

1. 확장 창에서 **[!UICONTROL All campaigns]**&#x200B;을(를) 클릭한 다음 **[!UICONTROL Ad Groups]**&#x200B;을(를) 클릭합니다.

   ![](assets/5-1.png)

1. 적용 가능한 광고 그룹을 모두 선택하거나 모두 선택을 클릭하고 **[!UICONTROL Edit]**&#x200B;을(를) 클릭한 다음 **[!UICONTROL Change Tracking Templates]**&#x200B;을(를) 클릭합니다.

1. [!DNL Marketo Measure] 추적 템플릿을 입력하고 **[!UICONTROL Apply]**&#x200B;을(를) 클릭합니다.

   ![](assets/6-1.png)

## FAQ {#faq}

**Q: 연결된 사용자에게 필요한 권한은 무엇입니까?**

A: userinfo.email

**Q: 지출 데이터를 가져오는 데 시간이 얼마나 걸립니까?**

A: 6시간

**Q: 광고 데이터를 가져오는 데 시간이 얼마나 걸립니까?**

A: 4시간

**Q: 동적 검색 광고의 경우 제공된 크리에이티브에서 헤드라인, 설명 등의 조합을 추적할 수 있습니까?**

A: 동적 검색 광고에 대한 개별 크리에이티브 세부 정보를 검색할 수 없지만 자동 태깅이 활성화된 경우 크리에이티브 ID 및 속성 매출을 가져올 수 있습니다.

>[!NOTE]
>
>변경이 완료되면 완료됩니다. 설치하는 동안 질문이 있는 경우 언제든지 [Marketo 지원](https://nation.marketo.com/t5/support/ct-p/Support){target="_blank"}에 문의하십시오.

계정 수준 추적 템플릿 만들기에 대한 Google의 지침을 보려면 [여기를 클릭](https://support.google.com/adwords/answer/6076199?hl=en#tracking){target="_blank"}하십시오.
