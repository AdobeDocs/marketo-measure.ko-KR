---
unique-page-id: 18874747
description: Sitecore 페이지에  [!DNL Marketo Measure] 스크립트 추가 - [!DNL Marketo Measure]
title: Sitecore 페이지에  [!DNL Marketo Measure] 스크립트 추가 중
exl-id: 87ce1857-7532-45a7-8c39-255c6118b50a
feature: Tracking
source-git-commit: 915e9c5a968ffd9de713b4308cadb91768613fc5
workflow-type: tm+mt
source-wordcount: '115'
ht-degree: 0%

---

# Sitecore 페이지에 [!DNL Marketo Measure] 스크립트를 추가하는 중 {#adding-marketo-measure-script-to-sitecore-pages}

콘텐츠 관리 시스템에서는 [!DNL Marketo Measure]이(가) 양식 제출을 인식하기 위해 표준 스크립트 구현 이상의 추가 단계를 수행해야 할 수 있습니다. 아래 프로세스에서는 [!DNL Sitecore] 페이지에 [!DNL Marketo Measure] Javascript를 추가하는 방법에 대해 간략히 설명합니다.

Sitecore 페이지가 있는 사이트의 경우:

1. Sitecore에 로그인하고 웹 사이트로 이동합니다. [!UICONTROL Home] 항목 및 [!UICONTROL Metadata] 폴더와 동일한 수준에 있는 [!UICONTROL Configuration] 폴더를 찾습니다.
1. [!UICONTROL Configuration] 폴더 옆의 **[!UICONTROL +]**&#x200B;을(를) 클릭합니다.
1. [!UICONTROL Tools] 폴더 옆의 **[!UICONTROL +]**&#x200B;을(를) 클릭합니다.
1. [!UICONTROL Javascript]개 항목을 선택하십시오.
1. [!UICONTROL Content] 탭에서 **[!UICONTROL Lock and Edit]** 링크를 클릭하여 편집할 항목의 잠금을 해제합니다.
1. [!UICONTROL 'JavaScript'] 섹션을 찾습니다. 아직 확장되지 않은 경우 **[!UICONTROL +]**&#x200B;을(를) 클릭합니다.
1. 스크립트 입력: `<script type="text/javascript" src="https://cdn.bizible.com/scripts/bizible.js"async=""></script>`
1. 왼쪽 위 모서리에서 **[!UICONTROL Save]**&#x200B;을(를) 클릭합니다.
