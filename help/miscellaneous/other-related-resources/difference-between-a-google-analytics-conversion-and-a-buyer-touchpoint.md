---
unique-page-id: 18874648
description: Google Analytics 전환과 Buyer Touchpoint 간의 차이점 - [!DNL Marketo Measure]
title: Google Analytics 전환과 Buyer Touchpoint 간의 차이점
exl-id: d09d963c-3207-467c-852a-d1edd49511fa
feature: Touchpoints
source-git-commit: 4787f765348da71bc149c997470ce678ba498772
workflow-type: tm+mt
source-wordcount: '493'
ht-degree: 1%

---

# Google Analytics 전환과 Buyer Touchpoint 간의 차이점 {#difference-between-a-google-analytics-conversion-and-a-buyer-touchpoint}

[!DNL Google Analytics (GA)] 목표가 무엇인지, 그리고 이 목표가 Buyer Touchpoint과 어떻게 다른지 알아봅니다.

**Google Analytics 전환이란?**

[!UICONTROL Google Analytics] 전환은 마케터나 웹 개발자가 특정 웹 사이트에서 &#39;목표&#39; 완료를 코딩하는 방법에 따라 결정됩니다. Google에 따르면 목표는 &quot;구매(전자 상거래 사이트의 경우), 게임 수준 완료(모바일 게임 앱의 경우), 연락처 정보 양식 제출(마케팅 또는 리드 생성 사이트의 경우)&quot;로 생각할 수 있습니다. 대부분의 경우 마케터는 목표/전환을 정보 양식을 작성하는 사람으로 봅니다.

그러나 목표를 특정 동작을 관리하도록 코딩할 수 없습니다. 대신 웹 개발자가 구성할 수 있는 목표 유형이 있습니다. 다음은 이러한 예 중 일부입니다.

<table> 
 <colgroup> 
  <col> 
  <col> 
  <col> 
 </colgroup> 
 <tbody> 
  <tr> 
   <td><strong>목표 유형</strong></td> 
   <td><p><strong>설명</strong></p></td> 
   <td><strong>예</strong></td> 
  </tr> 
  <tr> 
   <td><p>대상</p></td> 
   <td>특정 위치가 로드됨</td> 
   <td><em>등록해 주셔서 감사합니다!</em> 웹 페이지 또는 앱 화면</td> 
  </tr> 
  <tr> 
   <td>기간</td> 
   <td>특정 시간 이상 지속되는 세션</td> 
   <td>지원 사이트에서 보낸 시간(10분 이상)</td> 
  </tr> 
  <tr> 
   <td>세션당 페이지/Screens</td> 
   <td>사용자가 특정 수의 페이지 또는 화면을 봅니다</td> 
   <td>5개 페이지 또는 화면이 로드됨</td> 
  </tr> 
  <tr> 
   <td>이벤트</td> 
   <td>이벤트로 정의된 작업이 트리거됩니다.</td> 
   <td>소셜 추천, 비디오 재생 및 클릭</td> 
  </tr> 
 </tbody> 
</table>

대부분의 마케터는 변환을 &quot;대상 목표&quot;로 구성합니다. 즉, 일반적으로 형식 전환을 고려할 양식 후에 감사 페이지를 만듭니다.

이것은 Google이 감사 페이지 보기를 전환으로 간주한다는 것을 의미합니다. Google Analytics의 관점에서 보면 대부분의 마케터가 괜찮다고 생각하는 것입니다.

하지만 구매자 터치포인트는 다르게 작동합니다.

**구매자 터치포인트는 어떻게 다릅니까?**

[!DNL Marketo Measure] JavaScript은 특정 사이트의 모든 양식에서 세션 데이터 및 양식 제출을 추적합니다. [!DNL Marketo Measure] 관점에서 목표를 코딩할 필요가 없습니다. 이 프로세스는 자동입니다. 양식 제출을 위해 [!DNL Marketo Measure]은(는) 익명 사용자가 특정 양식의 정보 필드를 작성하고 양식 제출 버튼을 클릭할 때마다 양식 완료를 보고합니다. [!DNL Marketo Measure]은(는) 양식 제출을 기록하는 데 감사 페이지가 필요하지 않습니다.

[!DNL Marketo Measure]은(는) 다음 경우에 양식 터치포인트를 만듭니다.

* 해당 전환과 연결된 리드/연락처가 CRM에 표시됩니다.
* [!DNL Marketo Measure] JS가 양식을 포함하는 웹 페이지에 있습니다.
* 양식은 30분 세션 내에 제출됩니다.

[!DNL Marketo Measure]은(는) 다음과 같은 경우 대상 Google 분석 변환을 무시합니다.

* 봇은 웹 사이트에서 양식을 제출합니다(이러한 봇은 일반적으로 클라이언트의 CRM으로 만들지 않음).
* 사용자가 첫 번째 양식 제출 후 더 많은 양식을 제출합니다. [!DNL Marketo Measure]은(는) 해당 세션의 첫 번째 변환만 푸시합니다.
* 사용자가 양식 제출을 여러 번 클릭합니다. [!DNL Marketo Measure]은(는) 첫 번째 양식 제출만 고려합니다.
* 사용자가 감사 페이지를 여러 번 다시 로드합니다.
* 사용자가 광고 차단 도구를 사용하고 있습니다.

GA와 [!DNL Marketo Measure]에서 전환으로 간주하는 것 사이에는 근본적인 차이가 있습니다. 따라서 전환 수와 양식 터치포인트 수가 다를 수 있습니다.
