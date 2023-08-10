---
unique-page-id: 30082018
description: 쿠키 동기화 지연 - [!DNL Marketo Measure] - 제품 설명서
title: 쿠키 동기화 지연
exl-id: 394053ed-5642-48e4-b83c-c483a58ebbd7
feature: Tracking
source-git-commit: 8ac315e7c4110d14811e77ef0586bd663ea1f8ab
workflow-type: tm+mt
source-wordcount: '186'
ht-degree: 0%

---

# 쿠키 동기화 지연 {#delayed-cookie-sync}

이 기본값에 대한 수정 [!DNL Marketo Measure] Javascript는 다음을 제공합니다. [!DNL bizible.js] API를 지원하므로 방문자의 사용자 활동을 일시적으로 저장하도록 JS를 구성할 수 있지만 정보를에 보내서는 안 됩니다 [!DNL Marketo Measure] 사용자가 동의할 때까지 서버.

## 방법 {#how-to}

기본값 바꾸기 [!DNL bizible.js] 다음을 포함하는 스크립트 태그:

`<script id="bizible-settings" type="text/javascript" src="https://cdn.bizible.com/scripts/bizible.js" async="" data-consent-button-id="ConsentButtonId"></script>`

data-consent-button-id=&quot;ConsentButtonId&quot; 속성은 다음을 알려줍니다. [!DNL bizible.js] 를 입력하여 해당 id를 가진 HTML 요소를 클릭할 때까지 분석 데이터를 전송하지 않습니다.

또는 고객이 [!UICONTROL data-consent-button-id] 존재하지 않는 것(예: &quot;foobar&quot;)으로 가정하고 다음 API를 사용하여 [!DNL bizible.js] 사용자가 동의했다는 내용:

`window['Bizible'] = window['Bizible'] || { _queue: [], Push: function (o, p) {this._queue.push({ type: o, data: p }); } };`
`Bizible.Push("Consent", true });`

>[!NOTE]
>
>사용자 동의는 쿠키에 저장됩니다. 즉, 사용자가 동의하면 후속 페이지에서 이 호출을 수행할 필요가 없습니다.

## 제한 사항 {#limitation}

이유 [!DNL bizible.js] 전송되지 않은 웹 활동을 고객의 자사 쿠키에 일시적으로 저장하고 자사 쿠키 크기가 제한되므로 언제든지 전송되지 않은 3개의 요청만 저장할 수 있습니다.

이미 3개의 보류 중인 요청이 있는 경우 후속 활동이 무시됩니다. 이는 중요한 레퍼러 정보가 포함된 첫 번째 페이지 보기를 유지하기 위한 것입니다.
