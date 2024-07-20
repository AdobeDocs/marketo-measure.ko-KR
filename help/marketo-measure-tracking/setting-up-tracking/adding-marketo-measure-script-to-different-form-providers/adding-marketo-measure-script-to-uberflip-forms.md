---
unique-page-id: 18874749
description: ' [!DNL Uberflip] Forms - [!DNL Marketo Measure]에  [!DNL Marketo Measure] 스크립트 추가 중'
title: ' [!DNL Uberflip] Forms에  [!DNL Marketo Measure] 스크립트 추가 중'
exl-id: fb123e15-523d-4931-b4c1-705fe49be3d0
feature: Tracking
source-git-commit: 9e672d0c568ee0b889461bb8ba6fc6333edf31ce
workflow-type: tm+mt
source-wordcount: '204'
ht-degree: 0%

---

# [!DNL Uberflip] Forms에 [!DNL Marketo Measure] 스크립트 추가 중 {#adding-marketo-measure-script-to-uberflip-forms}

현재 [!DNL Uberflip]을(를) 사용하여 콘텐츠를 관리하고 있는 경우 [!DNL Marketo Measure]이(가) 이러한 양식 제출을 추적하고 있는지 확인하기 위해 필요한 단계를 수행하는 것이 중요합니다. [!DNL Uberflip]의 Success Manager도 이 작업에 대한 지원을 제공할 수 있습니다.

1. [!DNL Uberflip]의 [!UICONTROL Custom Code>HTML] 섹션에 이 스크립트를 추가합니다.

   `<script type="text/javascript" src="https://cdn.bizible.com/scripts/bizible.js" async=""></script>`

1. 이 [!DNL Marketo Measure] 프리앰블 코드가 페이지 로드와 AJAX 페이지 변경 시 모두 실행되는지 확인하십시오. [!UICONTROL Custom Code>JS] 섹션 내에서 수행

   `window['Bizible'] = window['Bizible'] || { _queue: [], Push: function (o, p) {this._queue.push({ type: o, data: p }); } };`

   이 프리앰블을 [!DNL Hubs.onLoad] 및 [!DNL Hubs.onPageChange] AJAX JavaScript 이벤트 후크에 모두 추가합니다. (참고: 이러한 이벤트 후크에 다른 코드도 있을 수 있습니다. 프리앰블도 포함해야 합니다.)

   `Hubs.onLoad = function () {`

   `window['Bizible'] = window['Bizible'] || { _queue: [], Push: function (o, p) {this._queue.push({ type: o, data: p }); } };`

   `}`

   `Hubs.onPageChange = function () {`

   `window['Bizible'] = window['Bizible'] || { _queue: [], Push: function (o, p) {this._queue.push({ type: o, data: p }); } };`

   `}`

1. 양식 CTA 제출 시 데이터를 Bizible로 푸시하는 함수를 만들고 정의합니다. [!UICONTROL Custom Code>JavaScript] 섹션으로 이동합니다. (참고: 이 함수에는 Uberflip이 제공하는 ctaData 매개 변수만 필요하지만, 사용자가 이 데이터를 전달하기 위해 코드를 사용자 정의하려는 경우 다른 매개 변수 ctaId 및 ctaName을 포함할 수 있습니다.)

   `function bizibleFormCode(ctaId, ctaData, ctaName) {`
   `var email = ctaData["email"];`
   `if(email){`
   `Bizible.Push('User', {`
   `eMail: email, // required`
   `}); }`

   `}`

1. 양식 CTA가 제출되면 [!DNL Marketo Measure] 함수가 아래에 따라 실행되는지 확인하십시오. 이 작업은 [!UICONTROL Custom Code>JS] 섹션 내에서 수행됩니다. (참고: Hubs.onCtaFormSubmitSuccess JavaScript 이벤트 후크 내에 다른 코드가 있을 수 있습니다. 이 함수 호출도 포함해야 합니다.)

   `Hubs.onCtaFormSubmitSuccess = function (ctaId, ctaData, ctaName) {`
   `bizibleFormCode(ctaId, ctaData, ctaName);`\
   `}`
