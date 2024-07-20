---
unique-page-id: 18874783
description: 특정 Forms에서  [!DNL Marketo Measure] 제외 - [!DNL Marketo Measure]
title: 특정 Forms에서  [!DNL Marketo Measure] 개 제외
exl-id: ce39a3b2-2ac6-4385-b6d1-3c36b51c03fa
feature: Tracking
source-git-commit: 9e672d0c568ee0b889461bb8ba6fc6333edf31ce
workflow-type: tm+mt
source-wordcount: '95'
ht-degree: 0%

---

# 특정 Forms에서 [!DNL Marketo Measure] 제외 {#excluding-marketo-measure-from-specific-forms}

기본적으로 [!DNL Marketo Measure]은(는) 사이트의 모든 양식에 연결됩니다. 그러나 모든 양식 제출을 반드시 추적하거나 속성 모델에 포함해야 하는 것은 아닙니다. 모든 양식 채우기가 &#39;양호&#39;로 여겨지는 것은 아니기 때문이다. 예를 들면 구독 취소 페이지/양식이 있습니다. 또한 기여도 분석 모델을 희석하므로 로그인 양식은 일반적으로 추적되지 않습니다.

## [!DNL Marketo Measure] 제외 코드를 추가하는 방법:  {#how-to-add-marketo-measure-exclude-code}

[!DNL Marketo Measure]이(가) 특정 양식을 추적하지 못하도록 하려면 &quot;[!DNL Bizible-Exclude]&quot;을(를) 양식에 &#39;클래스&#39;로 추가하기만 하면 됩니다. 코드는 다음과 같습니다.

`<form id="myForm" action="/Home/TestPage" method="POST" class="Bizible-Exclude">`
