---
unique-page-id: 35586069
description: Marketo Measure Js에서 GDPR에 대한 동의 확인 - Marketo Measure - 제품 설명서
title: Marketo Measure Js에서 GDPR에 대한 동의 보장
exl-id: 9afc5e4d-cf97-4c49-b9ee-ee1cc99c1f90
source-git-commit: c7d3bbce1f0c6a99409822c06c43961c93cd9458
workflow-type: tm+mt
source-wordcount: '425'
ht-degree: 0%

---

# Marketo Measure Js에서 GDPR에 대한 동의 보장 {#ensuring-consent-for-gdpr-in-marketo-measure-js}

GDPR(General Data Protection Regulation)은 2018년 5월 25일부터 시행된 유럽 연합 법입니다.

## 개요 {#overview}

GDPR의 목표는 개인 데이터가 사용 및 보호되는 방법에 대해 유럽 연합(EU)과 유럽 경제 지역(EEA) 내에서 데이터 주체의 권리를 강화하는 것입니다. 개인 데이터(Personal Data)는 식별되거나 식별 가능한 자연인과 관련된 모든 정보를 의미합니다. GDPR은 EU 및 EEA 내의 데이터 주체에 대한 마케팅 상품 또는 서비스를 제공 및/또는 추적하는 EU 내부 또는 외부의 모든 조직에 적용됩니다. 개인 데이터 처리가 포함된 유럽의 데이터 주체와 거래를 하는 경우, 이 규정이 사용자에게 적용됩니다. 규정 위반 행위에 대한 벌금은 중요하며, 규정을 위반한 사람에게는 큰 벌금이 부과됩니다. 한 번에 위반될 경우 최고 배상액은 전 세계 매출 연계의 4%인 2000만유로(약200억원)보다 많다.

기본적으로 [!DNL bizible.js] 동의할 때까지 기다리도록 특별히 구성되지 않은 경우 사용자의 analytics 데이터를 수집합니다. When [!DNL bizible.js] 는 사용자 동의를 기다리도록 구성되어 있으며, 동의를 얻은 후 까지 쿠키를 만들거나 analytics 데이터를 전송하지 않습니다.

## 동의를 기다리는 방법 {#how-to-wait-for-consent}

설정하는 방법에는 두 가지가 있습니다 [!DNL bizible.js] 동의할 때까지 기다리라는 겁니다

옵션 1 - 기본값 바꾸기 [!DNL bizible.js] 다음을 사용하는 스크립트 태그:

`<script id="bizible-settings" type="text/javascript" src="https://cdn.bizible.com/scripts/bizible.js" async="" data-consent-button-id="ConsentButtonId"></script>`

**만약 [!DNL Google Tag Manager] 스크립트를 설치합니다.**&#x200B;를 GTM에서 데이터 속성을 제거한다는 점에 유의하십시오. 따라서 대신 다음 스크립트를 사용하십시오.

`<span id="bizible-settings" data-consent-button-id="ConsentButtonId"></span>`
`<script type="text/javascript" src=https://cdn.bizible.com/scripts/bizible.js async=""></script>`

>[!NOTE]
>
>이 경우 [!DNL bizible.js] 은 클릭 이벤트를 id &quot;ConsentButtonId&quot;가 있는 HTML 요소에 연결합니다.

이 HTML 요소를 클릭하면 [!DNL bizible.js] 은 사용자의 동의를 받았음을 기억하기 위한 쿠키를 만들고 평소대로 analytics 데이터 수집을 시작합니다.

**-또는-**

옵션 2 - 기본값 바꾸기 [!DNL bizible.js] 다음을 사용하는 스크립트 태그:

`<script id="bizible-settings" type="text/javascript" src="https://cdn.bizible.com/scripts/bizible.js" async="" data-requires-user-consent="true"></script>`

이것은 [!DNL bizible.js] 동의를 얻을 때까지 추적하지 않도록 합니다. 이 작업은 다음 JS API로 수행할 수 있습니다.

*창[&#39;Bizible&#39;] = 창[&#39;Bizible&#39;] || { _queue: [], 푸시: 함수(o, p) { this._queue.push({ type: o, 데이터: p }); } };*

*Bizible.Push(&#39;Consent&#39;, true);*

**만약 [!DNL Google Tag Manager] 스크립트를 설치합니다.**&#x200B;를 GTM에서 데이터 속성을 제거한다는 점에 유의하십시오. 따라서 대신 다음 스크립트를 사용하십시오.

`<span id="bizible-settings" data-requires-user-consent="true"></span>`
`<script type="text/javascript" src=https://cdn.bizible.com/scripts/bizible.js async=""></script>`

>[!NOTE]
>
>bizible.js는 사용자의 동의를 받았음을 기억하기 위한 쿠키를 만들고 JS API가 호출된 후에만 평소대로 analytics 데이터를 수집하기 시작합니다.

그와 대조적으로, 고객은 이 API를 사용하여 사용자의 동의를 철회할 수도 있습니다.

`window['Bizible'] = window['Bizible'] || { _queue: [], Push: function (o, p) { this._queue.push({ type: o, data: p }); } };`

`Bizible.Push('Consent', false);`

이 코드가 실행되면 [!DNL bizible.js] 이전에 만들었으며 사용자가 다시 동의한 경우에만 analytics 데이터 컬렉션을 다시 시작합니다.
