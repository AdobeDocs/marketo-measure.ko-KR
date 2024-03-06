---
unique-page-id: 18874759
description: 추가 중 [!DNL Marketo Measure] 끝 [!DNL Hubspot] - [!DNL Marketo Measure]
title: 추가 중 [!DNL Marketo Measure] 끝 [!DNL Hubspot]
exl-id: 633e7ef7-7959-461e-881f-dcc543595b66
feature: Tracking
source-git-commit: 9e672d0c568ee0b889461bb8ba6fc6333edf31ce
workflow-type: tm+mt
source-wordcount: '175'
ht-degree: 1%

---

# 추가 중 [!DNL Marketo Measure] 끝 [!DNL Hubspot] {#adding-marketo-measure-to-hubspot}

추가 방법 알아보기 [!DNL Marketo Measure] 추적할 JavaScript [!DNL Hubspot] 랜딩 페이지 및 양식 제출.

Hubspot은 랜딩 페이지/양식 및 웹 사이트를 호스팅할 수 있다는 점에서 다른 마케팅 자동화 시스템과 약간 다릅니다. 아래 지침은 다음 사항에 대한 것입니다. [!DNL Marketo Measure] 활동 추적 [!DNL Hubspot]-호스팅된 페이지. 다음 이외의 CMS를 사용하여 웹 사이트 전원을 켜는 경우 [!DNL Hubspot] (예: Wordpress) [!DNL Marketo Measure] 해당 CMS에 대한 JavaScript도 참조하십시오.

>[!NOTE]
>
>와 같은 태그 관리 공급자를 통해 JavaScript를 배포하는 경우 [!DNL Google Tag Manager]를 수동으로 하드 코딩할 필요가 없습니다. [!DNL Marketo Measure] 웹 사이트에 JavaScript를 넣습니다.

## 시작하기 {#getting-started}

에 로그인한 후 [!DNL Hubspot] 계정, 다음 단계를 따르십시오.

1. 컨텐츠로 이동합니다.

1. 클릭 **[!UICONTROL Content Settings]**.

1. 다음 범위 내 [!UICONTROL Content Settings]사이트 헤더 HTML을 클릭합니다(아래 이미지 참조).

1. 내에 다음 스크립트를 추가합니다 `<header>`:

   `<script type="text/javascript" src="https://cdn.bizible.com/scripts/bizible.js" async=""></script>`

   다음과 같이 표시되어야 합니다.

```text
<!-- Marketo Measure Javascript -->
<script type="text/javascript" src="https://cdn.bizible.com/scripts/bizible.js" async="">
```

>[!TIP]
>
>이 영역에는 Google Analytics 코드와 같은 다른 추적 코드 조각이 이미 있을 수 있습니다. 그것들을 세미콜론으로 구분해야 한다 `;` 그리고 다음과 같은 단일 공간:
>
>`<script type="text/javascript" src="https://cdn.bizible.com/scripts/bizible.js" async=""></script>; <script async="true" type="someothercode" src="someotherfile.js" ></script>`
