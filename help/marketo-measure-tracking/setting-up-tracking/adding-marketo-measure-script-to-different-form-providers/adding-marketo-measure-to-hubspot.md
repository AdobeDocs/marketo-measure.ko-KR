---
unique-page-id: 18874759
description: ' [!DNL Marketo Measure] to [!DNL Hubspot] - [!DNL Marketo Measure] 추가 중'
title: ' [!DNL Marketo Measure] to [!DNL Hubspot] 추가 중'
exl-id: 633e7ef7-7959-461e-881f-dcc543595b66
feature: Tracking
source-git-commit: 9e672d0c568ee0b889461bb8ba6fc6333edf31ce
workflow-type: tm+mt
source-wordcount: '175'
ht-degree: 1%

---

# [!DNL Hubspot]에 [!DNL Marketo Measure] 추가 중 {#adding-marketo-measure-to-hubspot}

[!DNL Marketo Measure] JavaScript을 추가하여 [!DNL Hubspot] 랜딩 페이지 및 양식 제출을 추적하는 방법에 대해 알아봅니다.

Hubspot은 랜딩 페이지/양식 및 웹 사이트를 호스팅할 수 있다는 점에서 다른 마케팅 자동화 시스템과 약간 다릅니다. 아래 지침은 [!DNL Hubspot] 호스팅 페이지에서 [!DNL Marketo Measure] 추적 활동을 사용하는 것입니다. [!DNL Hubspot]이(가) 아닌 CMS로 웹 사이트를 지원하는 경우(예: Wordpress) 해당 CMS에 [!DNL Marketo Measure] JavaScript도 추가해야 합니다.

>[!NOTE]
>
>[!DNL Google Tag Manager]과(와) 같은 태그 관리 공급자를 통해 JavaScript을 배포하는 경우 [!DNL Marketo Measure] JavaScript을 웹 사이트로 수동으로 하드 코딩할 필요가 없습니다.

## 시작하기 {#getting-started}

[!DNL Hubspot] 계정에 로그인했으면 다음 단계를 수행합니다.

1. 컨텐츠로 이동합니다.

1. **[!UICONTROL Content Settings]**&#x200B;을(를) 클릭합니다.

1. [!UICONTROL Content Settings] 내에서 사이트 헤더 HTML을 클릭합니다(아래 이미지 참조).

1. `<header>` 내에 다음 스크립트를 추가하십시오.

   `<script type="text/javascript" src="https://cdn.bizible.com/scripts/bizible.js" async=""></script>`

   다음과 같이 표시되어야 합니다.

```text
<!-- Marketo Measure Javascript -->
<script type="text/javascript" src="https://cdn.bizible.com/scripts/bizible.js" async="">
```

>[!TIP]
>
>이 영역에는 Google Analytics 코드와 같은 다른 추적 코드 조각이 이미 있을 수 있습니다. 세미콜론 `;`과 같은 단일 공백으로 구분하십시오.
>
>`<script type="text/javascript" src="https://cdn.bizible.com/scripts/bizible.js" async=""></script>; <script async="true" type="someothercode" src="someotherfile.js" ></script>`
