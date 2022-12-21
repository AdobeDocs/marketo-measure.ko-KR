---
unique-page-id: 18874749
description: 추가 중 [!DNL Marketo Measure] 스크립트 [!DNL Uberflip] Forms - [!DNL Marketo Measure] - 제품 설명서
title: 추가 중 [!DNL Marketo Measure] 스크립트 [!DNL Uberflip] Forms
exl-id: fb123e15-523d-4931-b4c1-705fe49be3d0
source-git-commit: b59c79236d3e324e8c8b07c5a6d68bd8176fc8a9
workflow-type: tm+mt
source-wordcount: '210'
ht-degree: 0%

---

# 추가 중 [!DNL Marketo Measure] 스크립트 [!DNL Uberflip] Forms {#adding-marketo-measure-script-to-uberflip-forms}

현재 [!DNL Uberflip] 컨텐츠를 관리하려면 다음과 같은 필요한 단계를 수행하여 [!DNL Marketo Measure] 는 이러한 양식 제출을 추적하고 있습니다. 성공 관리자 위치 [!DNL Uberflip] 이 문제를 해결할 수도 있습니다.

1. 이 스크립트를 [!DNL Uberflip]s [!UICONTROL Custom Code>HTML] 섹션을 참조하십시오.

   `<script type="text/javascript" src="https://cdn.bizible.com/scripts/bizible.js" async=""></script>`

1. 확인 [!DNL Marketo Measure] 프리앰블 코드는 페이지 로드와 AJAX 페이지 변경 모두에서 실행됩니다. 내에서 다음을 수행하십시오 [!UICONTROL Custom Code>JS] 섹션

   `window['Bizible'] = window['Bizible'] || { _queue: [], Push: function (o, p) {this._queue.push({ type: o, data: p }); } };`

   이 프리앰블을 두 파일에 모두 추가합니다 [!DNL Hubs.onLoad] 그리고 [!DNL Hubs.onPageChange] AJAX Javascript 이벤트 후크는 아래에 있습니다. (참고: 이러한 이벤트 후크에 다른 코드가 있을 수도 있습니다. 프리앰블도 반드시 포함시키세요.)

   `Hubs.onLoad = function () {`

   `window['Bizible'] = window['Bizible'] || { _queue: [], Push: function (o, p) {this._queue.push({ type: o, data: p }); } };`

   `}`

   `Hubs.onPageChange = function () {`

   `window['Bizible'] = window['Bizible'] || { _queue: [], Push: function (o, p) {this._queue.push({ type: o, data: p }); } };`

   `}`

1. 양식 CTA 제출 시 Bizible에 데이터를 푸시할 함수를 만들고 정의합니다. 이 작업은 [!UICONTROL Custom Code>Javascript] 섹션을 참조하십시오. (참고: 이 함수에는 Uberflip에서 제공하는 ctaData 매개 변수만 필요하지만 사용자가 이 데이터를 전달하도록 코드를 사용자 지정하려는 경우 다른 매개 변수 ctaId 및 ctaName을 포함할 수 있습니다.

   `function bizibleFormCode(ctaId, ctaData, ctaName) {`
   `var email = ctaData["email"];`
   `if(email){`
   `Bizible.Push('User', {`
   `eMail: email, // required`
   `}); }`

   `}`

1. 양식 CTA가 제출되면 [!DNL Marketo Measure] 함수는 아래에 대해 실행됩니다. 이 작업은 [!UICONTROL Custom Code>JS] 섹션을 참조하십시오. (참고: Hub.onCtaFormSubmitSuccessJavascript 이벤트 후크 내에 다른 코드가 있을 수 있으며, 이 함수 호출도 포함해야 합니다.

   `Hubs.onCtaFormSubmitSuccess = function (ctaId, ctaData, ctaName) {`
   `bizibleFormCode(ctaId, ctaData, ctaName);`\
   `}`
