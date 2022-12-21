---
unique-page-id: 18874564
description: 정의 [!DNL Marketo Measure] 웹 세션 - [!DNL Marketo Measure] - 제품 설명서
title: 정의 [!DNL Marketo Measure] 웹 세션
exl-id: ddf4f19d-2024-413a-b0ae-4efd468c24de
source-git-commit: ae5b77744d523606ce6cfcf48d7e8d5049d5ccb7
workflow-type: tm+mt
source-wordcount: '581'
ht-degree: 0%

---

# 정의 [!DNL Marketo Measure] 웹 세션 {#definition-of-marketo-measure-web-sessions}

방법 알아보기 [!DNL Marketo Measure] 웹 세션을 정의합니다.

A **웹 세션** 는 특정 시간 동안 웹사이트와 상호 작용한 개인의 인터랙션을 나타냅니다. 세션은 사용자가 웹 사이트에 도달하면 시작됩니다.

예를 들어 Haley는 adobe.com을 방문합니다. 그녀의 사이트 방문은 세션을 시작합니다. 헤일리가 사이트를 떠날 때 탭/웹 브라우저를 닫거나 사이트에서 멀리 탐색하면 세션이 종료됩니다.

한 사용자가 여러 세션을 동시에 열 수 없습니다. 헤일리가 [!DNL adobe.com] 10개의 별도 탭에서 웹 사이트 방문과 관련하여 세션이 하나만 생성되었습니다.

## 어떻게 [!DNL Marketo Measure] 새 세션을 정의하시겠습니까? {#how-does-marketo-measure-define-a-new-session}

세션이 종료되는 시간과 새 세션이 시작되는 시기를 결정하는 몇 가지 사항이 있습니다. 두 가지 주요 방법 [!DNL Marketo Measure] 세션을 종료할 수 있는 대상:

* **시간 기반 만료**
* **채널 기반 만료**

## 시간 기반 만료 {#time-based-expiration}

**세션이 얼마나 지속됩니까?**

[!DNL Marketo Measure] 세션은 웹 사이트에서 30분 동안 활동이 없으면 종료됩니다. For example:

Haley가 adobe.com을 방문하면 세션이 시작됩니다. 그녀는 몇 분 동안 웹 사이트를 탐구하고, 그 다음 컴퓨터에서 몇 걸음 떨어져 있지만, 웹 사이트를 열어 둡니다. 30분 동안 활동이 없으면 세션이 종료됩니다.

현재, [!DNL Marketo Measure] 는 페이지 탐색 및 양식 제출만 활동으로 간주합니다. 웹 페이지를 스크롤하거나 페이지의 요소를 마우스로 가리키면 활동이 고려되지 않습니다. 그래서 헤일리가 블로그 게시물을 읽기 위해 adobe.com에 방문한다면, 그녀가 페이지의 컨텐츠를 스크롤하고 있더라도 그녀의 웹 세션은 여전히 30분 후에 끝나게 될 것입니다.

## 채널 기반 만료 {#channel-based-expiration}

[!DNL Marketo Measure] 사용자가 다른 디지털 마케팅 채널이나 외부 웹 사이트에서 웹 사이트를 방문할 때마다 새 세션을 시작합니다. 여기에는 다음이 포함됩니다.

* 참조 웹 사이트
* 소셜 채널 ([!DNL Facebook], [!DNL LinkedIn]등)
* 유료 또는 유기 검색 채널([!DNL Google/Bing])

**참조 웹 사이트 및 소셜 채널**

방문자가 참조 웹 사이트 또는 소셜 채널에서 웹 사이트를 방문할 때마다 새 세션이 시작됩니다.

헤일리는 LinkedIn에 있고, [!DNL Marketo Measure] 게시물 및 가 Adobe 웹 사이트로 리디렉션됩니다. 그리고 스크롤하는 동안 [!DNL Facebook]헤일리는 다른 걸 보거든 [!DNL Marketo Measure] 게시물. 이 게시물을 클릭하고 Adobe 사이트로 리디렉션되면 와 관련된 첫 번째 웹 세션이 발생합니다 [!DNL LinkedIn] 종료하기 전, 및 [!DNL Facebook] 가 시작됩니다.

**유료 또는 유기 검색 채널**

사용자가 유료 또는 유기 검색 채널을 통해 사이트를 방문할 때마다 새 세션이 시작됩니다. 헤일리가 유기 검색을 통해 Adobe 웹 사이트에 왔다가 곧바로 Google의 유료 광고를 통해 웹 사이트를 방문하면 두 개의 개별 세션이 만들어집니다.

**웹 직접 트래픽**

방문자가 웹 사이트의 URL을 주소 표시줄에 입력하여 웹 사이트를 방문하는 경우 새 세션이 항상 시작되는 것은 아닙니다.

헤일리의 첫 번째 웹 세션이 참조 사이트, 소셜 채널 또는 유료/유기 검색 채널에서 온 방문 결과로서 시작된 후 웹 다이렉트를 통해 사이트를 방문하는 경우, 새 세션이 시작되지 않습니다.

_하지만_&#x200B;헤일리의 첫 웹 세션이 Web Direct에서 시작되었다면, _외부/참조 사이트_&#x200B;첫 번째 세션이 끝나고 외부/참조 사이트와 관련된 새 세션이 열립니다.

## Google Analytics 세션 {#google-analytics-sessions}

비슷한 점이 있습니다 [!DNL Marketo Measure] 및 Google Analytics은 세션을 정의합니다. Google Analytics이 세션을 정의하는 방법에 대한 자세한 내용은 다음을 참조하십시오. [https://support.google.com/analytics/answer/2731565?hl=en](http://support.google.com/analytics/answer/2731565?hl=en){target=&quot;_blank&quot;}
