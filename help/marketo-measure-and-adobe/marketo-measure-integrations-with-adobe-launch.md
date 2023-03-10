---
description: '`[!DNL Marketo Measure] Adobe Launch와의 통합 - [!DNL Marketo Measure] - 제품 설명서'''
title: '`[!DNL Marketo Measure] Adobe Launch와의 통합'
exl-id: 316ee8a8-b2d3-42e9-9ee5-c9b1d91c2769
source-git-commit: 19f670505358b04fb26620574b71c2af8d0d9847
workflow-type: tm+mt
source-wordcount: '307'
ht-degree: 0%

---

# [!DNL Marketo Measure] Adobe Launch와의 통합 {#marketo-measure-integrations-with-adobe-launch}

Adobe Launch 확장은 기존 [!DNL Marketo Measure] 이미 웹 사이트에서 Adobe Launch를 활용하는 사용자. 확장은 특정 이벤트 및 조건에 따라 페이지에서 스크립트를 구성하고 동적으로 로드하는 데 사용할 수 있는 태그 관리 솔루션 역할을 합니다.

Launch에서 설치 및 구성한 경우, [!DNL Marketo Measure] 확장은 Launch 스크립트가 있는 페이지에서 bizible.js 스크립트를 로드합니다. 이를 통해 마케터는 웹 페이지를 명시적으로 수정하여 bizible.js 스크립트 태그를 추가하는 것이 아니라 Adobe Launch 구성을 통해 bizible.js를 추가할 수 있습니다.

## Adobe Launch 확장 구성 {#configure-the-adobe-launch-extension}

>[!PREREQUISITES]
>
>Launch 및 해당 확장에 대한 자세한 내용은 다음 링크를 참조하십시오.
>
>* [[!DNL Marketo Measure] 확장](https://experienceleague.adobe.com/docs/experience-platform/destinations/catalog/email/bizible.html?lang=en#catalog){target="_blank"}
>* [Adobe 시작 개요](https://experienceleague.adobe.com/docs/launch-learn/implementing-in-websites-with-launch/index.html?lang=en#prerequisites){target="_blank"}
>* [Adobe Launch 확장 개요](https://experienceleague.adobe.com/docs/launch/using/extension-dev/overview.html?lang=en#extension-configuration){target="_blank"}


1. 단계에 따라 속성을 만듭니다 [이 문서](https://experienceleague.adobe.com/docs/platform-learn/implement-in-websites/configure-tags/create-a-property.html?lang=en#go-to-the-data-collection-interface){target="_blank"}.

1. 방금 만든 속성을 클릭합니다.

   ![](assets/marketo-measure-integrations-with-adobe-launch-1.png)

1. 클릭 **[!UICONTROL Extensions]**.

   ![](assets/marketo-measure-integrations-with-adobe-launch-2.png)

1. 을(를) 클릭합니다. **[!UICONTROL Catalog]** 탭하여 &quot;[!UICONTROL Bizible].&quot;

   ![](assets/marketo-measure-integrations-with-adobe-launch-3.png)

1. 에서 [!UICONTROL Bizible Analytics] 타일, **[!UICONTROL Install]**.

   ![](assets/marketo-measure-integrations-with-adobe-launch-4.png)

1. Bizible AccountId 필드에 웹 사이트의 URL을 입력합니다.

   ![](assets/marketo-measure-integrations-with-adobe-launch-5.png)

   >[!NOTE]
   >
   >이 필드는 Business_Prod.Business 테이블의 &quot;계정 ID&quot;가 아닙니다. 주어진 URL의 모든 웹 활동은 [!DNL Marketo Measure] 임차인.

1. 클릭 **[!UICONTROL Save]**.

   ![](assets/marketo-measure-integrations-with-adobe-launch-6.png)

1. 클릭 **[!UICONTROL Rules]**&#x200B;를 선택하고 을 선택합니다. **[!UICONTROL Create New Rule]**.

   ![](assets/marketo-measure-integrations-with-adobe-launch-7.png)

1. 을(를) 클릭합니다. **[!UICONTROL Add]** 버튼 아래 [!UICONTROL Events].

   ![](assets/marketo-measure-integrations-with-adobe-launch-8.png)

1. 확장 드롭다운에서 을(를) 선택합니다. **[!UICONTROL Core]**. 그런 다음 이벤트 유형 드롭다운에서 을 선택합니다 **[!UICONTROL Library Loaded (Page Top)]**. 이벤트에 이름을 지정하지 않으면 기본 이름이 적용됩니다. 클릭 **[!UICONTROL Keep Changes]** 완료 시.

   ![](assets/marketo-measure-integrations-with-adobe-launch-9.png)

1. 을(를) 클릭합니다. **[!UICONTROL Add]** 단추 아래에 있는 Actions를 클릭하십시오.

   ![](assets/marketo-measure-integrations-with-adobe-launch-10.png)

1. 확장 드롭다운에서 을 선택합니다. **[!UICONTROL Bizible Analytics]**. 그런 다음 작업 유형 드롭다운에서 을 선택합니다 **[!UICONTROL Initialize]**. 작업에 이름을 지정하지 않으면 기본 이름이 적용됩니다. 클릭 **[!UICONTROL Keep Changes]** 완료 시.

   ![](assets/marketo-measure-integrations-with-adobe-launch-11.png)

1. 클릭 **[!UICONTROL Save]**.

   ![](assets/marketo-measure-integrations-with-adobe-launch-12.png)
