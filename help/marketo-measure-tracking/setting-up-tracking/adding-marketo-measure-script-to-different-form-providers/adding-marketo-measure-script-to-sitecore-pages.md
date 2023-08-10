---
unique-page-id: 18874747
description: 추가 중 [!DNL Marketo Measure] 사이트 코어 페이지에 스크립팅 - [!DNL Marketo Measure] - 제품 설명서
title: 추가 중 [!DNL Marketo Measure] Sitecore 페이지에 스크립트
exl-id: 87ce1857-7532-45a7-8c39-255c6118b50a
feature: Tracking
source-git-commit: 8ac315e7c4110d14811e77ef0586bd663ea1f8ab
workflow-type: tm+mt
source-wordcount: '117'
ht-degree: 0%

---

# 추가 중 [!DNL Marketo Measure] Sitecore 페이지에 스크립트 {#adding-marketo-measure-script-to-sitecore-pages}

컨텐츠 관리 시스템에는 표준 스크립트 구현 이상의 추가 단계가 필요할 수 있습니다. [!DNL Marketo Measure] 양식 제출을 인식하기 위해 아래 프로세스에서는 다음을 추가하는 방법에 대해 간략하게 설명합니다. [!DNL Marketo Measure] 에 대한 javascript [!DNL Sitecore] 페이지.

Sitecore 페이지가 있는 사이트의 경우:

1. Sitecore에 로그인하고 웹 사이트로 이동합니다. 를 찾습니다. [!UICONTROL Configuration] 와 동일한 수준에 있는 폴더 [!UICONTROL Home] 항목 및 [!UICONTROL Metadata] 폴더를 삭제합니다.
1. 다음을 클릭합니다. **[!UICONTROL +]** 다음 옆에 [!UICONTROL Configuration] 폴더를 삭제합니다.
1. 다음을 클릭합니다. **[!UICONTROL +]** 다음 옆에 [!UICONTROL Tools] 폴더를 삭제합니다.
1. 다음 항목 선택 [!UICONTROL Javascript] 항목.
1. 다음에서 [!UICONTROL Content] 탭을 클릭하고 **[!UICONTROL Lock and Edit]** 링크하여 편집할 항목의 잠금을 해제합니다.
1. 다음 찾기 [!UICONTROL 'JavaScript'] 섹션. 아직 확장되지 않은 경우 **[!UICONTROL +]**.
1. 스크립트 입력: `<script type="text/javascript" src="https://cdn.bizible.com/scripts/bizible.js"async=""></script>`
1. 클릭 **[!UICONTROL Save]** 왼쪽 상단 모서리입니다.
