---
unique-page-id: 18874749
description: 추가 중 [!DNL Marketo Measure] 스크립팅 대상 [!DNL Uberflip] FORMS - [!DNL Marketo Measure] - 제품 설명서
title: 추가 중 [!DNL Marketo Measure] 스크립팅 대상 [!DNL Uberflip] Forms
exl-id: fb123e15-523d-4931-b4c1-705fe49be3d0
feature: Tracking
source-git-commit: 8ac315e7c4110d14811e77ef0586bd663ea1f8ab
workflow-type: tm+mt
source-wordcount: '210'
ht-degree: 0%

---

# 추가 중 [!DNL Marketo Measure] 스크립팅 대상 [!DNL Uberflip] Forms {#adding-marketo-measure-script-to-uberflip-forms}

현재 을 사용 중인 경우 [!DNL Uberflip] 콘텐츠를 관리하려면 다음 필요한 단계를 수행하여 다음을 확인해야 합니다 [!DNL Marketo Measure] 은(는) 이러한 양식 제출을 추적합니다. 의 성공 관리자 [!DNL Uberflip] 을(를) 통해 도움을 받을 수 있습니다.

1. 이 스크립트를 추가할 위치 [!DNL Uberflip]의 [!UICONTROL Custom Code>HTML] 섹션.

   `<script type="text/javascript" src="https://cdn.bizible.com/scripts/bizible.js" async=""></script>`

1. 다음을 확인 [!DNL Marketo Measure] 프리앰블 코드는 페이지 로드와 AJAX 페이지 변경 시 모두 실행됩니다. 다음 작업 내에서 수행 [!UICONTROL Custom Code>JS] 섹션

   `window['Bizible'] = window['Bizible'] || { _queue: [], Push: function (o, p) {this._queue.push({ type: o, data: p }); } };`

   이 프리앰블을 두 위치에 추가합니다. [!DNL Hubs.onLoad] 및 [!DNL Hubs.onPageChange] AJAX Javascript 이벤트 후크는 아래에 따라 다릅니다. (참고: 이러한 이벤트 후크에 다른 코드도 있을 수 있습니다. 전문도 포함시키기만 하십시오.)

   `Hubs.onLoad = function () {`

   `window['Bizible'] = window['Bizible'] || { _queue: [], Push: function (o, p) {this._queue.push({ type: o, data: p }); } };`

   `}`

   `Hubs.onPageChange = function () {`

   `window['Bizible'] = window['Bizible'] || { _queue: [], Push: function (o, p) {this._queue.push({ type: o, data: p }); } };`

   `}`

1. 양식 CTA 제출 시 데이터를 Bizible로 푸시하는 함수를 만들고 정의합니다. 다음으로 이동합니다. [!UICONTROL Custom Code>Javascript] 섹션. (참고: 이 함수에는 Uberflip이 제공하는 ctaData 매개 변수만 필요하지만, 사용자가 이 데이터를 전달하기 위해 코드를 사용자 정의하려는 경우 다른 매개 변수 ctaId 및 ctaName을 포함할 수 있습니다.)

   `function bizibleFormCode(ctaId, ctaData, ctaName) {`
   `var email = ctaData["email"];`
   `if(email){`
   `Bizible.Push('User', {`
   `eMail: email, // required`
   `}); }`

   `}`

1. 양식 CTA가 제출되면 다음을 확인하십시오. [!DNL Marketo Measure] 함수는 아래에 따라 실행됩니다. 이 작업은 다음 기간 내에 수행됩니다. [!UICONTROL Custom Code>JS] 섹션. (참고: Hubs.onCtaFormSubmitSuccess Javascript 이벤트 후크 내에 다른 코드가 있을 수 있습니다. 이 함수 호출도 포함해야 합니다.)

   `Hubs.onCtaFormSubmitSuccess = function (ctaId, ctaData, ctaName) {`
   `bizibleFormCode(ctaId, ctaData, ctaName);`\
   `}`
