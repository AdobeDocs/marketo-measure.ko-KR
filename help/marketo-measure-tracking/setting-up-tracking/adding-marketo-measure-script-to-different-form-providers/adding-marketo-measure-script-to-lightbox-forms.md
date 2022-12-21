---
unique-page-id: 18874519
description: 추가 중 [!DNL Marketo Measure] Lightbox Forms에 스크립트 - [!DNL Marketo Measure] - 제품 설명서
title: 추가 중 [!DNL Marketo Measure] Lightbox Forms에 스크립트
exl-id: fa9ce480-fc4f-4abd-8555-dbb74849747e
source-git-commit: ae5b77744d523606ce6cfcf48d7e8d5049d5ccb7
workflow-type: tm+mt
source-wordcount: '195'
ht-degree: 0%

---

# 추가 중 [!DNL Marketo Measure] Lightbox Forms에 스크립트 {#adding-marketo-measure-script-to-lightbox-forms}

을(를) 올바르게 추가하는 방법을 알아봅니다. [!DNL Marketo Measure] JavaScript를 Lightbox 내에 있는 양식에 추가합니다.

Lightbox는 방문자가 특정 작업을 수행할 때(즉, 페이지의 특정 부분을 클릭, 페이지에서 특정 기간 체류 등) 컨텐츠 앞에 양식을 엽니다. 일반적으로 우리는 [!DNL Marketo Measure] 랜딩 페이지의 헤드에 배치된 JavaScript지만, Lightbox 내에 있는 양식의 경우 한 가지 추가 단계가 필요합니다.

Lightbox 내의 양식은 기본적으로 iFrame 내의 양식이므로 해당 iFrame 내에 스크립트가 삽입되어 있어야 합니다.

먼저 iFrame을 [!UICONTROL lightbox] 생활방식

![](assets/1.png)

다음으로, [!DNL Marketo Measure] iFrame 내의 JavaScript입니다.

![](assets/2.png)

마지막으로 JavaScript가 추가되면 다음 지침에 따라 양식 제출이 추적되고 있는지 확인할 것을 권장합니다.

1. 랜딩 페이지가 포함된 URL을 복사합니다 [!UICONTROL lightbox] 양식.
1. Incognito 브라우저를 열고 URL을 붙여넣습니다.
1. 고유한 이메일 주소를 사용하여 양식을 제출합니다.
1. CRM에서 사용된 고유한 이메일 주소를 확인하여 테스트가 추적되었는지 확인하고 Touchpoint 데이터가 채워지는지 확인합니다.
