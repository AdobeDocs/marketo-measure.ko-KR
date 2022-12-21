---
unique-page-id: 18874745
description: AJAX 양식 처리 - [!DNL Marketo Measure] - 제품 설명서
title: AJAX 양식 처리
exl-id: 042e42ff-d8d9-4380-b878-aba4934bc4a0
source-git-commit: ae5b77744d523606ce6cfcf48d7e8d5049d5ccb7
workflow-type: tm+mt
source-wordcount: '319'
ht-degree: 0%

---

# AJAX 양식 처리 {#ajax-form-handling}

고객 전환을 수동으로 보고하려면 [!DNL Marketo Measure]를 사용할 수 있는 간단한 API를 제공했습니다. 추적 코드가 있는 경우 이러한 Javascript API는 모두 사이트에서 자동으로 사용할 수 있습니다. 특별한 작업을 수행하지 않아도 됩니다.

## 시나리오 1 - AJAX 제출이 있는 HTML 양식 {#scenario-html-form-with-an-ajax-submit}

AJAX(또는 다른 메커니즘)이 포함된 양식을 사용하여 클라이언트에서 서버에 전환 날짜를 제출하는 경우, [!DNL Marketo Measure] 우리가 모니터링하는 표준 경로를 통해 고객이 전환하는 것을 알지 못할 수 있습니다. 이 시나리오에서는 간단한 API(아래에 제공)를 활용할 수 있습니다.

고유한 양식 제출을 처리하는 경우 명시적으로 를 호출할 수 있습니다 [!DNL Marketo Measure] Javascript에서 생성할 수 있습니다. [!DNL Marketo Measure] 은 양식에서 모든 관련 정보를 수집하고 서버에 비동기식으로 게시합니다.

**다음은 JQuery를 사용하는 코드 샘플입니다(양식의 ID가 &quot;formId&quot;라고 가정).**

```jquery
///////////////////////////////////////////////////////////////////////  
// Preamble for all API usage.  
window['Bizible'] = window['Bizible'] || { _queue: [], Push: function (o, p) {this._queue.push({ type: o, data: p }); } };  
  
// Give Marketo Measure the JQuery Selector for the form and we'll collect the data automatically.  
Bizible.Push('Form',$('#*formId*'));
```

**다음은 JQuery를 사용하지 않는 코드 샘플입니다(양식의 ID가 &quot;formId&quot;라고 가정).**

```jquery
///////////////////////////////////////////////////////////////////////  
// Preamble for all API usage.  
window['Bizible'] = window['Bizible'] || { _queue: [], Push: function (o, p) {this._queue.push({ type: o, data: p }); } };  
  
// Give Marketo Measure the Form ID and we'll collect the data automatically.
Bizible.Push('Form','MyFormID');
```

## 시나리오 2 - 비HTML 양식으로 수집된 리드 정보 {#scenario-lead-information-collected-in-a-non-html-form}

변환된 리드의 정보가 Javascript나 html 양식이 없는 단순 텍스트 필드를 사용하여 수집되는 경우 이 솔루션이 자동으로 작동합니다. 아래 공유된 는 이 시나리오에서 사용할 API입니다.

```jquery
///////////////////////////////////////////////////////////////////////  
// Preamble for all API usage.  
window['Bizible'] = window['Bizible'] || { _queue: [], Push: function (o, p) {this._queue.push({ type: o, data: p }); } };  
  
// If your site is using Ajax, or you are running a secure site, it is best to send us the data directly.  
Bizible.Push('User', {
eMail: 'user@gmail.com' // required  
});  
```

이 코드에서는 [!UICONTROL email] 필수 필드입니다. [!DNL Marketo Measure] 은 이 데이터를 서버에 비동기식으로 게시합니다.

## 시나리오 3 - 감사 인사 페이지에서 사용자 정보 보고 {#scenario-report-user-information-from-the-thank-you-page}

경우에 따라 리드 정보를 로 보고하는 것이 더 편리합니다 [!DNL Marketo Measure] 감사 인사 페이지에서 양식을 제출한 후 이 정보를 보고하는 가장 간단한 방법은 양식 제출의 정보를 포함하는 페이지에 숨겨진 요소를 추가하는 것입니다. [!DNL Bizible.js] 감사 인사 페이지가 로드되면 이 정보가 표시됩니다.

**For example:**

```html
<div id="bizible.reportUser" style="display:none"  
data-email="user@gmail.com">  
```

숨겨진 요소가 div, script 또는 다른 태그 유형인지 여부는 중요하지 않습니다. [!DNL Marketo Measure] 정보를 읽을 id=&quot;bizible.reportUser&quot;를 찾습니다.
