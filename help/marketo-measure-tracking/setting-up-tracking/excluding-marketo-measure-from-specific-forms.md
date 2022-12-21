---
unique-page-id: 18874783
description: 제외 [!DNL Marketo Measure] 특정 Forms에서 - [!DNL Marketo Measure] - 제품 설명서
title: 제외 [!DNL Marketo Measure] 특정 Forms
exl-id: ce39a3b2-2ac6-4385-b6d1-3c36b51c03fa
source-git-commit: b59c79236d3e324e8c8b07c5a6d68bd8176fc8a9
workflow-type: tm+mt
source-wordcount: '97'
ht-degree: 0%

---

# 제외 [!DNL Marketo Measure] 특정 Forms {#excluding-marketo-measure-from-specific-forms}

기본적으로 [!DNL Marketo Measure] 을 사이트의 모든 양식에 연결합니다. 그러나 모든 양식 제출을 반드시 추적하거나 속성 모델에 포함해야 하는 것은 아닙니다. 모든 양식 채우기가 &quot;좋다&quot;로 간주되는 것은 아니기 때문입니다. 예를 들면 가입 해지된 페이지/양식입니다. 또한, 로그인 양식은 일반적으로 속성 모델을 희석하므로 추적되지 않습니다.

## 추가 방법 [!DNL Marketo Measure]-exclude 코드:  {#how-to-add-marketo-measure-exclude-code}

예방하려면 [!DNL Marketo Measure] 특정 양식 추적에서 &quot;[!DNL Bizible-Exclude]&quot; 양식을 &#39;class&#39;로 사용할 수 있습니다. 코드는 다음과 같습니다.

`<form id="myForm" action="/Home/TestPage" method="POST" class="Bizible-Exclude">`
