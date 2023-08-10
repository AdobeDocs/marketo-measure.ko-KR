---
unique-page-id: 18874682
description: 마케팅 채널 및 하위 채널 - [!DNL Marketo Measure] - 제품 설명서
title: 마케팅 채널 및 하위 채널
exl-id: fbe2a994-cf6d-439c-af96-a562216434cc
feature: Channels
source-git-commit: 8ac315e7c4110d14811e77ef0586bd663ea1f8ab
workflow-type: tm+mt
source-wordcount: '472'
ht-degree: 1%

---

# 마케팅 채널 및 하위 채널 {#marketing-channels-and-subchannels}

## 목적 {#purpose}

채널 및 하위 채널이 포함되는 항목 정의 [!DNL Marketo Measure], 컨텐츠와 관련된 방법, 두 분류의 차이점 및 내에서 활용되는 방법 [!DNL Marketo Measure] 앱.

## 개요 {#overview}

마케팅 채널은 모두에서 쉽게 보고할 수 있도록 마케팅 활동을 분류 (또는 &quot;버킷&quot;)하는 데 사용됩니다. [!DNL Marketo Measure] CRM뿐만 아니라 ROI 대시입니다. [!DNL Marketo Measure] 에는 12개의 기본 제공 채널(조직의 규칙에 맞게 사용자 지정/이름 변경할 수 있음)과 함께 제공되며, 보다 세분화된 필터링을 위해 사용자 지정 채널을 추가로 만들 수 있는 기능도 있습니다.

사이트에서 컨텐츠 페이지(해당 컨텐츠가 웹 페이지, 백서 다운로드, 페이지 URL 등이든)에 대한 방문자를 받을 때마다 리드는 URL에 있는 여러 UTM 매개 변수를 기반으로 채널/하위 채널에 &quot;그룹화됩니다.

* 미디엄
* 소스
* 캠페인
* 랜딩 페이지
* 참조 웹 사이트

UTM 매개 변수를 기반으로 리드가 포함될 &quot;버킷&quot;을 사용자 지정하려면 채널 규칙을 사용할 수 있습니다. 채널 규칙 설정 및 유지 관리에 대한 자세한 내용은 다음을 참조하십시오. [여기를 클릭하십시오](/help/channel-tracking-and-setup/online-channels/online-custom-channel-setup.md).

을(를) 설정하는 방법 알아보기 [온라인 채널](/help/channel-tracking-and-setup/online-channels/online-custom-channel-setup.md) 및 [오프라인 채널](/help/channel-tracking-and-setup/offline-channels/offline-custom-channel-setup.md), 그리고 차이점.

**마케팅 채널**

마케팅 채널은 가장 광범위한 분류 수준이며 다양한 하위 채널을 포함할 수 있습니다. 이러한 &quot;유형&quot;의 잠재 고객이 속한 하위 채널을 고려할 수 있습니다. 마케팅 채널의 예로는 **유료 검색, 유기 검색, 디스플레이,** 및 **유료 소셜**. 마케팅 채널은 일반적으로 URL에 있는 utm_medium 매개 변수 값에 해당합니다.

**부채널**

하위 채널은 들어오는 리드를 그룹화할 때 퍼즐의 두 번째 조각입니다. 하위 채널은 정확히 다음과 같은 스토리를 전달합니다. _다음 중_ 마케팅 채널의 반복이 사용되었습니다. 예를 들어 유료 소셜 마케팅 채널 내에서 다음에 대한 하위 채널이 있을 수 있습니다 **애드워즈**, **BingAd**, **Facebook**&#x200B;등 일반적으로 하위 채널은 URL에 있는 utm_source 매개 변수 값에 해당합니다.

## 사용 사례 예 {#use-case-example}

아래 다이어그램은 다음 URL을 사용하는 웹 페이지를 기반으로 하는 마케팅 채널, 하위 채널 및 컨텐츠의 예를 보여 줍니다.

* [http://info.bizible.com/intro-guide-b2b-marketing-attribution?utm_source=linkedin&amp;utm_medium=paidsocial](http://info.bizible.com/intro-guide-b2b-marketing-attribution?utm_source=linkedin&amp;utm_medium=paidsocial)*

이 경우 사용자가 액세스하려는 콘텐츠는 B2B 마케팅 속성에 대한 소개 안내서입니다. [!DNL Marketo Measure] 은(는) 이 조직에 설정된 채널 규칙을 사용하여 이 컨텐츠로 이어지는 URL을 분석하고 이를 사용하여 마케팅 채널 &quot;유료 소셜&quot; 및 하위 채널 &quot;LinkedIn&quot;로 이어지는 &quot;버킷&quot;을 만듭니다.

![](assets/1.jpg)

추가 예...

**마케팅 채널(중간)**

* PPC
* 유료 소셜
* 유기적 사회
* 이메일
* 이벤트 및 전화 회의
* 유기 검색/SEO
* PR
* 참조 프로그램

**하위 채널(터치포인트 소스)**

* Google AdWords
* BingAd
* Facebook 광고
* Adroll
* 두 번 클릭
* 캡테라
* Drip 캠페인
* LinkedIn 광고

**컨텐츠(백서, 페이지 URL, 블로그 게시물)**

* www.adobe.com/blog1
* www.adobe.com/whitepaper
* www.adobe.com/sign-up-now
