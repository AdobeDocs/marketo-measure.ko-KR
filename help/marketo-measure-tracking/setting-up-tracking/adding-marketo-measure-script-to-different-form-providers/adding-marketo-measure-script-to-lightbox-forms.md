---
unique-page-id: 18874519
description: 추가 중 [!DNL Marketo Measure] Lightbox Forms에 스크립트 - [!DNL Marketo Measure]
title: 추가 중 [!DNL Marketo Measure] Lightbox Forms에 스크립트
exl-id: fa9ce480-fc4f-4abd-8555-dbb74849747e
feature: Tracking
source-git-commit: 9e672d0c568ee0b889461bb8ba6fc6333edf31ce
workflow-type: tm+mt
source-wordcount: '189'
ht-degree: 0%

---

# 추가 중 [!DNL Marketo Measure] Lightbox Forms에 스크립트 {#adding-marketo-measure-script-to-lightbox-forms}

을(를) 올바르게 추가하는 방법 알아보기 [!DNL Marketo Measure] Lightbox 내의 양식에 대한 JavaScript.

라이트박스는 방문자가 특정 작업(즉, 페이지의 특정 부분을 클릭하고, 페이지에서 특정 시간을 보내는 등)을 수행할 때 콘텐츠 앞에 있는 양식을 엽니다. 일반적으로 다음을 요청합니다. [!DNL Marketo Measure] JavaScript는 랜딩 페이지의 헤드에 배치되지만, 라이트박스 내의 양식에는 한 개의 추가 단계가 필요합니다.

Lightbox 내의 양식은 기본적으로 iFrame 내의 양식이므로 스크립트는 해당 iFrame 내에 배치됩니다.

먼저 iFrame을 찾습니다. [!UICONTROL lightbox] 폼은 안에 있습니다.

![](assets/1.png)

다음, [!DNL Marketo Measure] iFrame 내의 JavaScript입니다.

![](assets/2.png)

마지막으로, JavaScript가 추가되면 양식 제출이 다음 지침에 따라 추적되는지 확인합니다.

1. 를 포함하는 랜딩 페이지의 URL을 복사합니다. [!UICONTROL lightbox] 양식.
1. 시크릿 브라우저를 열고 URL을 붙여넣습니다.
1. 고유한 이메일 주소를 사용하여 양식을 제출합니다.
1. 사용된 고유 이메일 주소에 대한 CRM을 확인하여 테스트가 추적되었는지 확인하고 터치포인트 데이터가 채워져 있는지 확인하십시오.
