---
unique-page-id: 18874759
description: 추가 중 [!DNL Marketo Measure] to [!DNL Hubspot] - [!DNL Marketo Measure] - 제품 설명서
title: 추가 중 [!DNL Marketo Measure] to [!DNL Hubspot]
exl-id: 633e7ef7-7959-461e-881f-dcc543595b66
source-git-commit: b59c79236d3e324e8c8b07c5a6d68bd8176fc8a9
workflow-type: tm+mt
source-wordcount: '178'
ht-degree: 0%

---

# 추가 중 [!DNL Marketo Measure] to [!DNL Hubspot] {#adding-marketo-measure-to-hubspot}

를 추가하는 방법을 알아봅니다 [!DNL Marketo Measure] JavaScript를 사용하여 [!DNL Hubspot] 랜딩 페이지 및 양식 제출.

Hub는 랜딩 페이지/양식 및 웹 사이트를 호스팅할 수 있다는 점에서 다른 마케팅 자동화 시스템과 약간 다릅니다. 아래 지침은 다음을 수행하기 위한 것입니다 [!DNL Marketo Measure] 활동 추적 [!DNL Hubspot]-호스팅된 페이지. 웹 사이트에 다른 CMS를 사용하여 웹 사이트를 제공하는 경우 [!DNL Hubspot] (예: Wordpress) [!DNL Marketo Measure] JavaScript를 해당 CMS에도 추가합니다.

>[!NOTE]
>
>와 같은 태그 관리 공급자를 통해 JavaScript를 배포하는 경우 [!DNL Google Tag Manager]를 채울 때는 수동으로 [!DNL Marketo Measure] JavaScript를 웹 사이트에 추가합니다.

## 시작하기 {#getting-started}

로그인하면 [!DNL Hubspot] account, 다음 단계를 수행합니다.

1. 컨텐츠로 이동합니다.

1. 클릭 **[!UICONTROL Content Settings]**.

1. 내 [!UICONTROL Content Settings]를 클릭하고 사이트 헤더 HTML을 클릭합니다(아래 이미지 참조).

1. 사용자 내에 다음 스크립트를 추가합니다. `<header>`:

   `<script type="text/javascript" src="https://cdn.bizible.com/scripts/bizible.js" async=""></script>`

   다음과 같이 표시되어야 합니다.

```text
<!-- Marketo Measure Javascript -->
<script type="text/javascript" src="https://cdn.bizible.com/scripts/bizible.js" async="">
```

>[!TIP]
>
>이 영역에는 Google Analytics 코드와 같은 다른 추적 코드 조각이 이미 있을 수 있습니다. 반드시 세미콜론으로 구분하십시오 `;` 그리고 다음과 같은 단일 공간:
>
>`<script type="text/javascript" src="https://cdn.bizible.com/scripts/bizible.js" async=""></script>; <script async="true" type="someothercode" src="someotherfile.js" ></script>`
