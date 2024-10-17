---
unique-page-id: 18874564
description: ' [!DNL Marketo Measure] 웹 세션 정의 - [!DNL Marketo Measure]'
title: ' [!DNL Marketo Measure] 웹 세션 정의'
exl-id: ddf4f19d-2024-413a-b0ae-4efd468c24de
feature: Tracking
source-git-commit: 9a5e267b4b268d067fbbe89a00a4da96752a44db
workflow-type: tm+mt
source-wordcount: '807'
ht-degree: 0%

---

# [!DNL Marketo Measure] 웹 세션 정의 {#definition-of-marketo-measure-web-sessions}

[!DNL Marketo Measure]이(가) 웹 세션을 정의하는 방법을 알아봅니다.

**웹 세션**&#x200B;은(는) 일정 시간 동안 개인이 웹 사이트와 상호 작용하는 것을 의미합니다. 사용자가 웹 사이트에 도달하면 세션이 시작됩니다.

예를 들어, Haley는 adobe.com을 방문합니다. 그녀의 사이트 방문은 세션을 시작합니다. 헤일리가 사이트를 떠날 때, 탭/웹 브라우저를 닫거나 사이트에서 멀리 이동하여, 세션은 끝난다.

한 사용자가 여러 세션을 동시에 열 수 없습니다. Haley가 10개의 개별 탭에서 [!DNL adobe.com]을(를) 열면 웹 사이트 방문과 관련하여 하나의 세션만 만들어집니다.

## [!DNL Marketo Measure]에서 새 세션을 정의하는 방법 {#how-does-marketo-measure-define-a-new-session}

세션이 종료되는 시점과 새 세션이 시작되는 시점을 결정하는 몇 가지 사항이 있습니다. [!DNL Marketo Measure] 세션이 종료될 수 있는 두 가지 주요 방법은 다음과 같습니다.

* **시간 기반 만료**
* **채널 기반 만료**

## 시간 기반 만료 {#time-based-expiration}

### 레거시 동작 {#legacy-behavior}

**세션이 얼마나 오래 지속됩니까?**

[!UICONTROL Marketo Measure]개의 세션은 웹 사이트에서 30분 동안 활동이 없으면 종료됩니다. For example:

헤일리가 adobe.com을 방문하면, 세션이 시작된다. 그녀는 몇 분 동안 웹사이트를 탐색한 후 컴퓨터에서 한 걸음 떨어져서 사이트를 열어두었다. 30분 동안 활동이 없으면 세션이 종료됩니다.

현재 [!UICONTROL Marketo Measure]은(는) 페이지 탐색 및 양식 제출만 활동으로 간주합니다. 웹 페이지를 스크롤하거나 페이지의 요소 위로 마우스를 가져가면 활동으로 간주되지 않습니다. 헤일리가 adobe.com을 방문하여 블로그 게시물을 읽는데 한 시간이 걸리는 경우, 페이지의 내용을 스크롤하고 있더라도 그녀의 웹 세션은 30분 후에도 여전히 종료됩니다.

### 새로운 비헤이비어 {#new-behavior}

새 사용자의 경우 기본 동작이 됩니다.

기존 사용자는 **설정** > **모든 터치 속성** > **세션 채널 이월**&#x200B;에서 토글을 켜서 새 동작을 채택할 수 있습니다. 활성화되면 이 설정을 되돌릴 수 없습니다.

30분 동안 활동이 없다가 새 세션이 만들어지면 7일 내에 새 세션이 시작되면 이전 세션의 채널이 이월됩니다. 이 이월은 직접 방문(레퍼러 또는 내부 레퍼러 없음)에만 적용됩니다. 활동이 7일을 초과하는 경우 새 세션에 대한 채널은 기본적으로 직접/기타 로 설정됩니다. 예를 들어 헤일리가 Google에서 landingpage.com을 방문하고 30분 이상 비활성 상태이고 7일 이내에 재방문하는 경우 새 세션은 Google 채널을 유지합니다. 그러나 동일한 사용자가 다른 채널을 통해 페이지를 다시 방문하는 경우 비직접 채널은 이전 Google 채널에 의해 재정의되지 않습니다.

캠페인이나 레퍼러 세부 사항을 제외하고 채널만 전달됩니다. 채널 분류는 Marketo Measure이 처리하는 반면 다른 데이터 포인트는 따로 수집하기 때문이다.

**소셜 로그인**

방문자가 Google, Microsoft 또는 Apple을 통해 소셜 로그인을 사용하면 세션이 하나의 연속 세션으로 병합됩니다. 예를 들어 방문자가 LinkedIn에서 페이지에 도달하고, Google 소셜 로그인을 완료하고, 감사 페이지에 도달하면 모두 단일 세션으로 계산됩니다. 세션 채널 이월을 켜지 않으면 외부 레퍼러로 인해 소셜 로그인이 별도의 세션을 만듭니다.

## 채널 기반 만료 {#channel-based-expiration}

[!DNL Marketo Measure]은(는) 사용자가 다른 디지털 마케팅 채널 또는 외부 웹 사이트에서 웹 사이트로 이동할 때마다 새 세션을 시작합니다. 여기에는 다음 항목이 포함되어 있습니다.

* 추천 웹 사이트
* 소셜 채널([!DNL Facebook], [!DNL LinkedIn] 등)
* 유료 또는 유기 검색 채널([!DNL Google/Bing])

**참조 웹 사이트 및 소셜 채널**

방문자가 참조 웹 사이트 또는 소셜 채널에서 웹 사이트를 방문할 때마다 새 세션이 시작됩니다.

Haley가 LinkedIn에 있고 [!DNL Marketo Measure] 게시물을 클릭하여 Adobe 웹 사이트로 리디렉션된다고 가정해 보십시오. [!DNL Facebook]을(를) 스크롤하는 동안 Haley는 다른 [!DNL Marketo Measure] 게시물을 봅니다. 이 게시물을 클릭하고 Adobe 사이트로 리디렉션되면 [!DNL LinkedIn]과(와) 관련된 첫 번째 웹 세션이 종료되고 [!DNL Facebook]과(와) 관련된 새 세션이 시작됩니다.

**유료 또는 유기 검색 채널**

새 세션은 사용자가 유료 또는 유기 검색 채널을 통해 사이트를 방문할 때마다 시작됩니다. 헤일리가 유기적 검색을 통해 Adobe 웹사이트에 찾아온 뒤 곧바로 Google 유료 광고를 통해 여러분의 웹사이트를 방문하면 두 개의 별도 세션이 만들어진다.

**웹 직접 트래픽**

방문자가 주소 표시줄에 웹 사이트의 URL을 입력하여 웹 사이트를 방문하는 경우 새 세션이 항상 시작되는 것은 아닙니다.

헤일리의 첫 웹 세션이 추천 사이트, 소셜 채널, 또는 유료/유기 검색 채널로부터의 방문의 결과로 시작되고 나서 그녀가 웹 다이렉트를 통해 사이트를 방문한다면, 이것은 새로운 세션을 시작하게 하지 않을 것이다.

_그러나_ 헤일리의 첫 번째 웹 세션이 Web Direct에서 시작된 후 _외부/참조 사이트_&#x200B;를 통해 웹 사이트를 방문하는 경우 첫 번째 세션이 종료되고 외부/참조 사이트와 관련된 새 세션이 열립니다.

## Google Analytics 세션 {#google-analytics-sessions}

[!DNL Marketo Measure]과(와) Google Analytics이 세션을 정의하는 방법과 몇 가지 유사성이 있습니다. Google Analytics이 세션을 정의하는 방법에 대한 자세한 내용은 [https://support.google.com/analytics/answer/2731565?hl=en](https://support.google.com/analytics/answer/2731565?hl=en){target="_blank"}을(를) 참조하십시오.
