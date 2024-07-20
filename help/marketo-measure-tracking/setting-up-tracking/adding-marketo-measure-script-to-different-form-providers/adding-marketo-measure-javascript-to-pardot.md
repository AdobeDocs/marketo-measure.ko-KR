---
unique-page-id: 18874757
description: ' [!DNL Pardot] - [!DNL Marketo Measure]에  [!DNL Marketo Measure] JavaScript 추가 중'
title: ' [!DNL Pardot]에  [!DNL Marketo Measure] JavaScript 추가 중'
exl-id: e49190ad-aa86-4f8f-a9ed-48de9e937a7e
feature: Tracking
source-git-commit: 9e672d0c568ee0b889461bb8ba6fc6333edf31ce
workflow-type: tm+mt
source-wordcount: '219'
ht-degree: 0%

---

# [!DNL Pardot]에 [!DNL Marketo Measure] JavaScript 추가 중 {#adding-marketo-measure-javascript-to-pardot}

[!DNL Pardot]개 양식을 사용하려면 양식 제출을 인식하기 위해 [!DNL Marketo Measure]을(를) 위해 사이트에 스크립트를 추가하는 것 외에 양식 서식 파일 내에서 추가 처리가 필요합니다. 프로세스는 간단합니다. [!DNL Marketo Measure] 추적 스크립트를 [!DNL Pardot] 양식 템플릿에 배치하기만 하면 됩니다.

## 단계별 지침 {#step-by-step-instructions}

[!DNL Pardot] 계정에 로그인했으면 아래 단계를 따르십시오.

1. **[!UICONTROL Marketing]**(으)로 이동합니다.

1. **[!UICONTROL Landing Pages]**&#x200B;을(를) 클릭합니다.

1. **[!UICONTROL Layout Template]**&#x200B;을(를) 선택합니다.

   ![](assets/1-3.png)

1. 적절한 레이아웃 템플릿을 결정하고 오른쪽에 있는 **[!UICONTROL Edit]**&#x200B;을(를) 클릭합니다.

   ![](assets/2-1.png)

1. HTML 페이지에서 닫기 헤더 태그 바로 앞에 [!DNL Marketo Measure] JavaScript 코드를 복사하여 붙여 넣습니다.

   `<script type="text/javascript" src="https://cdn.bizible.com/scripts/bizible.js" async=""></script>`

1. 해당하는 모든 랜딩 페이지 레이아웃 템플릿에 대해 다음 단계를 수행합니다.

1. [!DNL Marketo Measure] JavaScript도 일반 사이트 페이지에 있는지 확인하십시오.

   [!DNL Pardot] 레이아웃 템플릿 내에서 코드는 다음과 같습니다.

```text
<script type="text/javascript" src="https://cdn.bizible.com/scripts/bizible.js" async=""></script>
   </head>
   <body>
```

## 추가 참고 사항 {#additional-notes}

[!DNL Pardot] IFrame에 다음 HTML 태그가 있는 경우:

`<base href="http://go.pardot.com">`

_및_ IFrame 자체는 실제로 안전하지 않은 페이지(HTTP)가 아닌 보안 페이지(HTTPS)입니다. [!DNL Pardot] IFrame에서 스크립트를 로드할 때 브라우저가 HTTPS 페이지에서 스크립트의 HTTP 버전을 로드하려고 시도하면 실패하고 추적이 중단됩니다. 해결 방법은 [!DNL Pardot] IFrame에서 스크립트를 업데이트하여 보안 버전의 스크립트를 로드하는 것입니다.

`<script type="text/javascript" src="https://cdn.bizible.com/scripts/bizible.js" async=""></script>`

이 영역에 [!DNL Google Analytics] 코드와 같은 다른 추적 코드 조각이 이미 있을 수 있습니다. 다음 예제와 같이 세미콜론 `;`과 단일 공백으로 구분하십시오.

`<script type="text/javascript" src="https://cdn.bizible.com/scripts/bizible.js" async=""></script>; <script async="true" type="othercode_example" src="otherfile_example.js" ></script>`
