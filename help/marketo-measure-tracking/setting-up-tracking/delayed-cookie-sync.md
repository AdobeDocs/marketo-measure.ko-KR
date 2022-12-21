---
unique-page-id: 30082018
description: 지연된 쿠키 동기화 - [!DNL Marketo Measure] - 제품 설명서
title: 지연된 쿠키 동기화
exl-id: 394053ed-5642-48e4-b83c-c483a58ebbd7
source-git-commit: ae5b77744d523606ce6cfcf48d7e8d5049d5ccb7
workflow-type: tm+mt
source-wordcount: '186'
ht-degree: 0%

---

# 지연된 쿠키 동기화 {#delayed-cookie-sync}

이 수정 사항은 기본값입니다 [!DNL Marketo Measure] Javascript에서 제공하는 [!DNL bizible.js] API 지원. 방문자의 사용자 활동을 일시적으로 저장하지만 방문자에게 정보를 전송하지 않도록 JS를 구성할 수 있습니다 [!DNL Marketo Measure] 사용자가 동의할 때까지 서버입니다.

## 방법 {#how-to}

기본값 바꾸기 [!DNL bizible.js] 스크립트 태그에 다음 코드를 배치하십시오.

`<script id="bizible-settings" type="text/javascript" src="https://cdn.bizible.com/scripts/bizible.js" async="" data-consent-button-id="ConsentButtonId"></script>`

data-consent-button-id=&quot;ConsentButtonId&quot; 속성은 다음을 알려줍니다 [!DNL bizible.js] 해당 id가 있는 HTML 요소를 클릭할 때까지 분석 데이터를 전송하지 않습니다.

또는 고객이 [!UICONTROL data-consent-button-id] 존재하지 않는 것(예: &quot;foovar&quot;)으로 변경하려는 경우 다음 API를 사용하여 다음을 수행합니다. [!DNL bizible.js] 사용자가 동의했음을 나타냅니다.

`window['Bizible'] = window['Bizible'] || { _queue: [], Push: function (o, p) {this._queue.push({ type: o, data: p }); } };`
`Bizible.Push("Consent", true });`

>[!NOTE]
>
>사용자 동의는 쿠키에 저장됩니다. 즉, 사용자가 동의하면 후속 페이지에서 이 호출을 수행할 필요가 없습니다.

## 제한 사항 {#limitation}

왜냐면 [!DNL bizible.js] 전송되지 않은 웹 활동을 고객의 자사 쿠키에 임시 저장할 수 있으며, 자사 쿠키의 크기가 제한되어 있으므로 지정된 시간에 3개의 미전송 요청만 저장할 수 있습니다.

이미 3개의 보류 중인 요청이 있는 경우 후속 활동이 무시됩니다. 이것은 중요한 레퍼러 정보가 포함된 첫 번째 페이지 보기를 보존하기 위한 것입니다.
