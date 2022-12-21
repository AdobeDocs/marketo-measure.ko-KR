---
unique-page-id: 18874757
description: 추가 중 [!DNL Marketo Measure] JavaScript에서 로 [!DNL Pardot] - [!DNL Marketo Measure] - 제품 설명서
title: 추가 중 [!DNL Marketo Measure] JavaScript에서 로 [!DNL Pardot]
exl-id: e49190ad-aa86-4f8f-a9ed-48de9e937a7e
source-git-commit: ae5b77744d523606ce6cfcf48d7e8d5049d5ccb7
workflow-type: tm+mt
source-wordcount: '238'
ht-degree: 0%

---

# 추가 중 [!DNL Marketo Measure] JavaScript에서 로 [!DNL Pardot] {#adding-marketo-measure-javascript-to-pardot}

[!DNL Pardot] 양식에서는 추가적인 처리가 필요한 경우, 사이트에서 스크립트를 작성하는 것 외에 양식 템플릿 내에서 추가적인 처리가 필요합니다 [!DNL Marketo Measure] 로 설정되어야 합니다. 프로세스는 간단합니다. 단지 [!DNL Marketo Measure] 스크립트를 [!DNL Pardot] 양식 서식 파일입니다.

## 단계별 지침 {#step-by-step-instructions}

로그인하면 [!DNL Pardot] account에서 아래 단계를 수행합니다.

1. 다음으로 이동 **[!UICONTROL Marketing]**.

1. 클릭 **[!UICONTROL Landing Pages]**.

1. 선택 **[!UICONTROL Layout Template]**.

   ![](assets/1-3.png)

1. 적절한 레이아웃 템플릿을 확인하고 를 클릭합니다. **[!UICONTROL Edit]** 오른쪽으로요

   ![](assets/2-1.png)

1. 복사 및 붙여넣기 [!DNL Marketo Measure] JavaScript 코드가 HTML 페이지에서 헤더 태그를 닫기 바로 전에 표시됩니다.

   `<script type="text/javascript" src="https://cdn.bizible.com/scripts/bizible.js" async=""></script>`

1. 적용 가능한 모든 랜딩 페이지 레이아웃 템플릿에 대해 다음 단계를 따르십시오.

1. 다음을 확인합니다. [!DNL Marketo Measure] JavaScript는 일반 사이트 페이지에도 있습니다.

   내 [!DNL Pardot] 레이아웃 템플릿 : 코드는 다음과 같습니다.

```text
<script type="text/javascript" src="https://cdn.bizible.com/scripts/bizible.js" async=""></script>
   </head>
   <body>
```

## 추가 참고 사항 {#additional-notes}

만약 [!DNL Pardot] 이름에 다음 HTML 태그가 있는 경우:

`<base href="http://go.pardot.com">`

_및_ IFrame 자체는 실제로 비보안 페이지(HTTP) 대신 보안 페이지(HTTPS)에 있는 경우 [!DNL Pardot] Aem인 경우, 브라우저는 HTTPS 페이지에서 스크립트의 HTTP 버전을 로드하려고 하며 이로 인해 Adobe가 추적을 수행하지 못합니다. 해결 방법은 의 스크립트를 업데이트하는 것입니다 [!DNL Pardot] 스크립트 보안 버전을 로드하는 경우:

`<script type="text/javascript" src="https://cdn.bizible.com/scripts/bizible.js" async=""></script>`

또한, 이 영역에는 다음과 같은 다른 추적 코드 조각이 이미 있을 수 있습니다. [!DNL Google Analytics] 코드가 있어야 합니다. 반드시 세미콜론으로 구분하십시오 `;` 및 이 예와 같이 단일 공간을 사용할 수 있습니다.

`<script type="text/javascript" src="https://cdn.bizible.com/scripts/bizible.js" async=""></script>; <script async="true" type="othercode_example" src="otherfile_example.js" ></script>`
