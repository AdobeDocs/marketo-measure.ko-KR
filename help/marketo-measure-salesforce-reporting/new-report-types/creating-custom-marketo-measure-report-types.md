---
unique-page-id: 18874539
description: 사용자 지정 만들기 [!DNL Marketo Measure] 보고서 유형 - [!DNL Marketo Measure]
title: 사용자 지정 만들기 [!DNL Marketo Measure] 보고서 유형
exl-id: 1d72a04f-6a2d-4607-ad09-3b025125156a
feature: Reporting
source-git-commit: 915e9c5a968ffd9de713b4308cadb91768613fc5
workflow-type: tm+mt
source-wordcount: '265'
ht-degree: 0%

---

# 사용자 지정 만들기 [!DNL Marketo Measure] 보고서 유형 {#creating-custom-marketo-measure-report-types}

>[!NOTE]
>
>&quot; &quot;을 지정하는 지침이 표시될 수 있습니다.[!DNL Marketo Measure]설명서에는 &quot;&quot;가 표시되지만, 여전히 &quot;[!DNL Bizible]CRM에 있는 &quot;입니다. 이를 업데이트하고 리브랜딩이 곧 CRM에 반영되도록 노력하고 있습니다.

사용자 지정 항목을 만드는 방법 알아보기 [!DNL Marketo Measure] [!DNL Salesforce] 보고서 유형. 권장되는 세 가지 보고서 유형은 구매자 터치포인트가 있는 리드(사용자 지정), [!DNL Marketo Measure] 구매자 접점(사용자 지정), 구매자 속성 접점(사용자 지정)이 있는 기회

## 구매자 터치포인트로 리드(사용자 지정) {#leads-with-buyer-touchpoints-custom}

1. 다음으로 이동 **[!UICONTROL Setup]** > **[!UICONTROL Build]** > **[!UICONTROL Report Types]** > **[!UICONTROL New Custom Report Types]**.

   ![](assets/1.png)

1. 사용자 지정 보고서 유형을 정의합니다.

   * [!UICONTROL Report Type Focus] > [!UICONTROL [!UICONTROL Primary Object]]: 리드
   * 식별 > [!UICONTROL Report Type Label]: 구매자 터치포인트가 있는 리드(사용자 지정)
   * [!UICONTROL Store in Category]: 기타 보고서
   * [!UICONTROL Deployment] > [!UICONTROL Deployment Status]: 배포됨

   ![](assets/2.png)

1. 객체 관계를 정의합니다.

   * 리드 개체(A)를 [!DNL Marketo Measure] 개인 객체(B)를 선택한 다음 구매자 터치포인트 객체(C)로 이동
   * &quot;&quot;가[!UICONTROL Each A/B record must have at least one B/C]&quot; 레코드가 선택됨
   * [!UICONTROL Save]

   ![](assets/3.png)

## [!DNL Marketo Measure] 구매자 터치포인트가 있는 사람(사용자 정의) {#marketo-measure-person-with-buyer-touchpoints-custom}

1. 다음으로 이동 **[!UICONTROL Setup]** > **[!UICONTROL Build]** > **[!UICONTROL Report Types]** > **[!UICONTROL New Custom Report Types]**.

   ![](assets/4.png)

1. 사용자 지정 보고서 유형을 정의합니다.

   * [!UICONTROL Report Type Focus] > [!UICONTROL Primary Object]: [!DNL Marketo Measure] 개인
   * [!UICONTROL Identification] > [!UICONTROL Report Type Label]: [!DNL Marketo Measure] 구매자 터치포인트가 있는 사람(사용자 정의)
   * [!UICONTROL Store in Category]: 기타 보고서
   * [!UICONTROL Deployment] > [!UICONTROL Deployment Status]: 배포됨

   ![](assets/5.png)

1. 객체 관계를 정의합니다.

   * 연결 [!DNL Marketo Measure] 개인 개체(A)와 구매자 터치포인트 개체(B)
   * &quot;&quot;가[!UICONTROL Each A record must have at least one B]&quot; 레코드가 선택됨
   * [!UICONTROL Save]

   ![](assets/6.png)

## 구매자 속성 접점(사용자 정의)이 있는 기회 {#opportunities-with-buyer-attribution-touchpoint-custom}

1. 다음으로 이동 **[!UICONTROL Setup]** > **[!UICONTROL Build]** > **[!UICONTROL Report Types]** > **[!UICONTROL New Custom Report Types]**.

   ![](assets/7.png)

1. 사용자 지정 보고서 유형을 정의합니다.

   * [!UICONTROL Report Type Focus] > [!UICONTROL Primary Object]: 기회
   * [!UICONTROL Identification] > [!UICONTROL Report Type Label]: 구매자 속성 터치포인트를 사용하는 기회(사용자 지정)
   * [!UICONTROL Store in Category]: 기타 보고서
   * [!UICONTROL Deployment] > [!UICONTROL Deployment Status]: 배포됨

   ![](assets/8.png)

1. 객체 관계를 정의합니다.

   * Opportunities 객체(A)를 구매자 Attribution 터치포인트 객체(B)와 연결
   * &quot;&quot;가[!UICONTROL Each A record must have at least one B]&quot; 레코드가 선택됨
   * [!UICONTROL Save]

   ![](assets/9.png)

## 사용자 지정 보고서 유형에 사용자 지정 필드 추가 {#adding-custom-fields-to-custom-report-types}

1. 보고서가 생성되면 보고서 유형 개요로 리디렉션됩니다. 클릭 **[!UICONTROL Edit Layout]**.

   ![](assets/10.png)

1. 보고서에 추가하려는 사용자 정의 필드가 필드 레이아웃 속성 섹션에 나타나는지 확인합니다. 추가할 다른 필드가 있는 경우 &quot;[!UICONTROL Add fields related via lookup]&quot; 옵션입니다.

   ![](assets/11.png)
