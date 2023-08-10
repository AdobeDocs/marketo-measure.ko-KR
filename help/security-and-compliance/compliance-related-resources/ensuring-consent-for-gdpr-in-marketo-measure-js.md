---
unique-page-id: 35586069
description: Marketo Measure Js - Marketo Measure - 제품 설명서에서 GDPR에 대한 동의 확인
title: Marketo Measure Js에서 GDPR에 대한 동의 확인
exl-id: 9afc5e4d-cf97-4c49-b9ee-ee1cc99c1f90
feature: Tracking
source-git-commit: 8ac315e7c4110d14811e77ef0586bd663ea1f8ab
workflow-type: tm+mt
source-wordcount: '425'
ht-degree: 0%

---

# Marketo Measure Js에서 GDPR에 대한 동의 확인 {#ensuring-consent-for-gdpr-in-marketo-measure-js}

GDPR(General Data Protection Regulation)은 2018년 5월 25일에 발효된 유럽 연합 법률입니다.

## 개요 {#overview}

GDPR의 목적은 유럽연합(EU) 및 유럽 경제 지역(EEA) 내에서 개인 데이터의 사용 및 보호 방법과 관련하여 데이터 주체의 권리를 강화하는 것입니다. &quot;개인 데이터&quot;는 식별되거나 식별 가능한 자연인과 관련된 모든 정보를 의미합니다. GDPR은 EU 및 EEA 내에서 데이터 주체에 대한 상품 또는 서비스를 마케팅 및/또는 행동을 추적하는 EU 내부 또는 외부의 모든 조직에 적용됩니다. 귀하가 유럽의 데이터 주체와 비즈니스를 하며 개인 데이터의 처리와 관련된 경우, 이 법률은 귀하에게 적용됩니다. 규정 위반에 따른 벌금은 매우 크며, 규정 위반에 따른 벌금은 큰 금액입니다. 규정 위반에 따른 최대 벌금은 2,000만 유로 또는 연간 전 세계 매출액의 4% 중 더 큰 금액입니다.

기본적으로, [!DNL bizible.js] 동의를 기다리도록 특별히 구성되지 않은 경우 사용자의 분석 데이터를 수집합니다. 날짜 [!DNL bizible.js] 은 사용자 동의를 기다리도록 구성되어 있으며 동의에 도달할 때까지 쿠키를 만들거나 analytics 데이터를 전송하지 않습니다.

## 동의를 기다리는 방법 {#how-to-wait-for-consent}

설정하는 방법에는 두 가지가 있습니다 [!DNL bizible.js] 동의를 기다립니다.

옵션 1 - 기본값 바꾸기 [!DNL bizible.js] 다음을 포함하는 스크립트 태그:

`<script id="bizible-settings" type="text/javascript" src="https://cdn.bizible.com/scripts/bizible.js" async="" data-consent-button-id="ConsentButtonId"></script>`

**를 사용하는 경우 [!DNL Google Tag Manager] 스크립트를 설치하려면**, GTM에서는 데이터 속성이 제거된다는 점을 유의하십시오. 따라서 다음 스크립트를 대신 사용하십시오.

`<span id="bizible-settings" data-consent-button-id="ConsentButtonId"></span>`
`<script type="text/javascript" src=https://cdn.bizible.com/scripts/bizible.js async=""></script>`

>[!NOTE]
>
>이 경우, [!DNL bizible.js] 는 ID가 &quot;ConsentButtonId&quot;인 HTML 요소에 클릭 시 이벤트를 첨부합니다.

이 HTML 요소를 클릭하면 [!DNL bizible.js] 는 사용자의 동의를 받았음을 기억하고 평소대로 analytics 데이터를 수집하기 위한 쿠키를 만듭니다.

**-또는-**

옵션 2 - 기본값 바꾸기 [!DNL bizible.js] 다음을 포함하는 스크립트 태그:

`<script id="bizible-settings" type="text/javascript" src="https://cdn.bizible.com/scripts/bizible.js" async="" data-requires-user-consent="true"></script>`

이는 다음을 말해줍니다. [!DNL bizible.js] 다음 JS API를 사용하여 수행할 수 있는, 동의에 도달할 때까지 추적하지 않음:

*창[&#39;Bizible&#39;] = window[&#39;Bizible&#39;] { _queue: [], 푸시: 함수 (o, p) { this._queue.push({ type: o, data: p }); } };*

*Bizible.Push(&#39;동의&#39;, true);*

**를 사용하는 경우 [!DNL Google Tag Manager] 스크립트를 설치하려면**, GTM에서는 데이터 속성이 제거된다는 점을 유의하십시오. 따라서 다음 스크립트를 대신 사용하십시오.

`<span id="bizible-settings" data-requires-user-consent="true"></span>`
`<script type="text/javascript" src=https://cdn.bizible.com/scripts/bizible.js async=""></script>`

>[!NOTE]
>
>bizible.js는 사용자의 동의를 받았다는 것을 기억하는 쿠키를 만들고 JS API가 호출된 후에만 평소와 같이 분석 데이터를 수집하기 시작합니다.

반대로 고객은 이 API를 사용하여 사용자의 동의를 철회할 수도 있습니다.

`window['Bizible'] = window['Bizible'] || { _queue: [], Push: function (o, p) { this._queue.push({ type: o, data: p }); } };`

`Bizible.Push('Consent', false);`

이 코드가 실행되면 [!DNL bizible.js] 이전에 만들었으며 사용자가 다시 동의하는 경우에만 analytics 데이터 수집을 다시 시작합니다.
