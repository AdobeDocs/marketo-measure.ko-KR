---
unique-page-id: 18874539
description: 사용자 지정 만들기 [!DNL Marketo Measure] 보고서 유형 - [!DNL Marketo Measure] - 제품 설명서
title: 사용자 지정 만들기 [!DNL Marketo Measure] 보고서 유형
exl-id: 1d72a04f-6a2d-4607-ad09-3b025125156a
source-git-commit: f13e55f009f33140ff36523212ed8b9ed5449a4d
workflow-type: tm+mt
source-wordcount: '266'
ht-degree: 0%

---

# 사용자 지정 만들기 [!DNL Marketo Measure] 보고서 유형 {#creating-custom-marketo-measure-report-types}

>[!NOTE]
>
>&quot;[!DNL Marketo Measure]&quot;&quot;은(는) 설명서에 있지만 여전히 &quot;&quot;가 표시됩니다.[!DNL Bizible]&quot;&quot;을 클릭합니다. 업데이트를 위해 노력하고 있으며 리브랜딩이 곧 CRM에 반영됩니다.

사용자 정의 작성 방법 알아보기 [!DNL Marketo Measure] [!DNL Salesforce] 보고서 유형. 다음과 같은 세 가지 보고서 유형을 만드는 것이 좋습니다. 구매자 터치포인트(사용자 지정), [!DNL Marketo Measure] 구매자 터치포인트(사용자 지정), 구매자 기여도 분석 터치포인트를 사용하는 기회(사용자 지정).

## 구매자 터치포인트를 사용한 리드(사용자 지정) {#leads-with-buyer-touchpoints-custom}

1. 이동 **[!UICONTROL Setup]** > **[!UICONTROL Build]** > **[!UICONTROL Report Types]** > **[!UICONTROL New Custom Report Types]**.

   ![](assets/1.png)

1. 사용자 지정 보고서 유형을 정의합니다.

   * [!UICONTROL Report Type Focus] > [!UICONTROL [!UICONTROL Primary Object]]: 리드
   * 식별 > [!UICONTROL Report Type Label]: 구매자 터치포인트를 사용한 리드(사용자 지정)
   * [!UICONTROL Store in Category]: 기타 보고서
   * [!UICONTROL Deployment] > [!UICONTROL Deployment Status]: 배포됨

   ![](assets/2.png)

1. 객체 관계를 정의합니다.

   * 리드 개체(A)를 [!DNL Marketo Measure] 개인 객체(B)를 선택한 다음 구매자 터치포인트 객체(C)로
   * 다음 사항을 확인합니다.[!UICONTROL Each A/B record must have at least one B/C]&quot; 레코드를 선택했습니다.
   * [!UICONTROL Save]

   ![](assets/3.png)

## [!DNL Marketo Measure] 구매자 터치포인트를 가진 개인(사용자 지정) {#marketo-measure-person-with-buyer-touchpoints-custom}

1. 이동 **[!UICONTROL Setup]** > **[!UICONTROL Build]** > **[!UICONTROL Report Types]** > **[!UICONTROL New Custom Report Types]**.

   ![](assets/4.png)

1. 사용자 지정 보고서 유형을 정의합니다.

   * [!UICONTROL Report Type Focus] > [!UICONTROL Primary Object]: [!DNL Marketo Measure] 사람
   * [!UICONTROL Identification] > [!UICONTROL Report Type Label]: [!DNL Marketo Measure] 구매자 터치포인트를 가진 개인(사용자 지정)
   * [!UICONTROL Store in Category]: 기타 보고서
   * [!UICONTROL Deployment] > [!UICONTROL Deployment Status]: 배포됨

   ![](assets/5.png)

1. 객체 관계를 정의합니다.

   * 관련 [!DNL Marketo Measure] 구매자 터치포인트 객체에 대한 개인 객체(A)(B)
   * 다음 사항을 확인합니다.[!UICONTROL Each A record must have at least one B]&quot; 레코드를 선택했습니다.
   * [!UICONTROL Save]

   ![](assets/6.png)

## 구매자 속성 터치포인트를 사용하는 기회(사용자 지정) {#opportunities-with-buyer-attribution-touchpoint-custom}

1. 이동 **[!UICONTROL Setup]** > **[!UICONTROL Build]** > **[!UICONTROL Report Types]** > **[!UICONTROL New Custom Report Types]**.

   ![](assets/7.png)

1. 사용자 지정 보고서 유형을 정의합니다.

   * [!UICONTROL Report Type Focus] > [!UICONTROL Primary Object]: 기회
   * [!UICONTROL Identification] > [!UICONTROL Report Type Label]: 구매자 속성 터치포인트를 사용하는 기회(사용자 지정)
   * [!UICONTROL Store in Category]: 기타 보고서
   * [!UICONTROL Deployment] > [!UICONTROL Deployment Status]: 배포됨

   ![](assets/8.png)

1. 객체 관계를 정의합니다.

   * Opportunity 객체(A)를 Buyer Attribution Touchpoint 객체(B)에 연결
   * 다음 사항을 확인합니다.[!UICONTROL Each A record must have at least one B]&quot; 레코드를 선택했습니다.
   * [!UICONTROL Save]

   ![](assets/9.png)

## 사용자 지정 보고서 유형에 사용자 지정 필드 추가 {#adding-custom-fields-to-custom-report-types}

1. 보고서가 만들어지면 보고서 유형의 개요로 리디렉션됩니다. 클릭 **[!UICONTROL Edit Layout]**.

   ![](assets/10.png)

1. 보고서에 추가하려는 사용자 지정 필드가 필드 레이아웃 속성 섹션에 표시되는지 확인하십시오. 추가할 다른 필드가 있으면 &quot;[!UICONTROL Add fields related via lookup]&quot; 옵션을 선택합니다.

   ![](assets/11.png)
