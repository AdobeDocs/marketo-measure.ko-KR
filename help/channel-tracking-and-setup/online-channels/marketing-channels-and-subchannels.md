---
unique-page-id: 18874682
description: 마케팅 채널 및 하위 채널 - [!DNL Marketo Measure] - 제품 설명서
title: 마케팅 채널 및 하위 채널
exl-id: fbe2a994-cf6d-439c-af96-a562216434cc
source-git-commit: 02f686645e942089df92800d8d14c76215ae558f
workflow-type: tm+mt
source-wordcount: '472'
ht-degree: 1%

---

# 마케팅 채널 및 하위 채널 {#marketing-channels-and-subchannels}

## 목적 {#purpose}

채널 및 하위 채널의 내용을 정의하려면 [!DNL Marketo Measure], 컨텐츠와 어떻게 관련되는지, 두 분류 간의 차이점 및 내에서 어떻게 활용되는지를 설명합니다 [!DNL Marketo Measure] 앱.

## 개요 {#overview}

마케팅 채널은 두 가지 모두를 [!DNL Marketo Measure] CRM뿐만 아니라 ROI 대시(ROI Dash)입니다. [!DNL Marketo Measure] 은 기본 제공 채널 12개와 함께 제공됩니다(조직의 규칙에 맞게 사용자 지정/이름을 변경할 수 있음). 또한 보다 세부적인 필터링을 위해 사용자 지정 채널을 추가로 만들 수 있습니다.

사이트에서 컨텐츠 페이지 중 하나에 대한 방문자를 받을 때마다(해당 컨텐츠가 웹 페이지이든, 백서 다운로드이든, 페이지 URL 등이든), 해당 리드는 URL에 있는 여러 UTM 매개 변수를 기반으로 채널/하위 채널로 &quot;버킷&quot;됩니다.

* 미디엄
* 원문
* 캠페인
* 랜딩 페이지
* 참조 웹 사이트

리드가 UTM 매개 변수를 기반으로 하는 &quot;버킷&quot;을 사용자 지정하려면 채널 규칙을 사용할 수 있습니다. 채널 규칙 설정 및 유지 관리에 대한 자세한 내용은 [여기를 클릭하십시오.](/help/channel-tracking-and-setup/online-channels/online-custom-channel-setup.md).

설정 방법 알아보기 [온라인 채널](/help/channel-tracking-and-setup/online-channels/online-custom-channel-setup.md) 및 [오프라인 채널](/help/channel-tracking-and-setup/offline-channels/offline-custom-channel-setup.md)뿐만 아니라 둘 사이의 차이도 있습니다.

**마케팅 채널**

마케팅 채널은 가장 광범위한 분류 수준이며 다양한 하위 채널을 포함할 수 있습니다. 이러한 경우 리드가 생성되는 하위 채널의 &quot;유형&quot;으로 간주할 수 있습니다. 마케팅 채널의 예는 다음과 같습니다 **유료 검색, 유기 검색, 표시,** 및 **유료 소셜**. 마케팅 채널은 일반적으로 URL에 있는 utm_medium 매개 변수 값에 해당합니다.

**하위 채널**

하위 채널은 들어오는 리드를 그룹화할 때 퍼즐의 두 번째 조각입니다. 하위 채널은 _다음 중_ 마케팅 채널의 반복이 사용되었습니다. 예를 들어, 유료 소셜 마케팅 채널 내에 **AdWords**, **BingAds**, **Facebook**&#x200B;등 하위 채널은 일반적으로 URL에 있는 utm_source 매개 변수 값에 해당합니다.

## 사용 사례 예 {#use-case-example}

아래 다이어그램은 다음 URL을 사용하는 웹 페이지를 기반으로 하는 마케팅 채널, 하위 채널 및 컨텐츠의 예를 보여줍니다.

* [http://info.bizible.com/intro-guide-b2b-marketing-attribution?utm_source=linkedin&amp;utm_medium=paidsocial](http://info.bizible.com/intro-guide-b2b-marketing-attribution?utm_source=linkedin&amp;utm_medium=paidsocial)*

이 경우 사용자가 액세스하려는 컨텐츠는 B2B 마케팅 속성에 대한 소개 안내서입니다. [!DNL Marketo Measure] 은 이 조직에 설정된 채널 규칙을 사용하여 이 컨텐츠로 이어지는 URL을 분석하고, 이 URL을 사용하여 마케팅 채널 &quot;유료 소셜&quot; 및 하위 채널 &quot;LinkedIn&quot;으로 &quot;버킷&quot;합니다.

![](assets/1.jpg)

추가 예..

**마케팅 채널(미디어)**

* PPC
* 유료 소셜
* 유기 소셜
* 이메일
* 이벤트 및 회의
* 유기 검색/SEO
* PR
* 참조 프로그램

**하위 채널(터치 포인트 소스)**

* Google AdWords
* BingAds
* Facebook 광고
* Adroll
* 두 번 클릭
* Capterra
* 드립 캠페인
* LinkedIn 광고

**컨텐츠(백서, 페이지 URL, 블로그 게시물)**

* www.adobe.com/blog1
* www.adobe.com/whitepaper
* www.adobe.com/sign-up-now
