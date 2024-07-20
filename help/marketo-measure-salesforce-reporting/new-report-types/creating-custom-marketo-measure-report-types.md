---
unique-page-id: 18874539
description: 사용자 지정 [!DNL Marketo Measure] 보고서 유형 만들기 - [!DNL Marketo Measure]
title: 사용자 지정 [!DNL Marketo Measure] 보고서 유형을 만드는 중
exl-id: 1d72a04f-6a2d-4607-ad09-3b025125156a
feature: Reporting
source-git-commit: 915e9c5a968ffd9de713b4308cadb91768613fc5
workflow-type: tm+mt
source-wordcount: '265'
ht-degree: 0%

---

# 사용자 지정 [!DNL Marketo Measure] 보고서 유형을 만드는 중 {#creating-custom-marketo-measure-report-types}

>[!NOTE]
>
>설명서에는 &quot;[!DNL Marketo Measure]&quot;을(를) 지정하는 지침이 표시되지만 CRM에는 여전히 &quot;[!DNL Bizible]&quot;이 표시됩니다. 이를 업데이트하고 리브랜딩이 곧 CRM에 반영되도록 노력하고 있습니다.

사용자 지정 [!DNL Marketo Measure] [!DNL Salesforce] 보고서 유형을 만드는 방법을 알아봅니다. 만드는 데 권장되는 세 가지 보고서 유형은 구매자 터치포인트가 있는 잠재 고객(사용자 지정), 구매자 터치포인트가 있는 [!DNL Marketo Measure]명(사용자 지정), Buyer Attribution Touchpoint이 있는 기회(사용자 지정)입니다.

## 구매자 터치포인트로 리드(사용자 지정) {#leads-with-buyer-touchpoints-custom}

1. **[!UICONTROL Setup]** > **[!UICONTROL Build]** > **[!UICONTROL Report Types]** > **[!UICONTROL New Custom Report Types]**(으)로 이동합니다.

   ![](assets/1.png)

1. 사용자 지정 보고서 유형을 정의합니다.

   * [!UICONTROL Report Type Focus] > [!UICONTROL [!UICONTROL Primary Object]]: 잠재 고객
   * 식별 > [!UICONTROL Report Type Label]: 구매자 터치포인트로 리드(사용자 지정)
   * [!UICONTROL Store in Category]: 기타 보고서
   * [!UICONTROL Deployment] > [!UICONTROL Deployment Status]: 배포됨

   ![](assets/2.png)

1. 객체 관계를 정의합니다.

   * 잠재 고객 개체(A)를 [!DNL Marketo Measure] 개인 개체(B)와 연결한 다음 Buyer Touchpoint 개체(C)와 연결
   * &quot;[!UICONTROL Each A/B record must have at least one B/C]&quot; 레코드가 선택되었는지 확인합니다.
   * [!UICONTROL Save]

   ![](assets/3.png)

## 구매자 터치포인트가 있는 [!DNL Marketo Measure]명(사용자 지정) {#marketo-measure-person-with-buyer-touchpoints-custom}

1. **[!UICONTROL Setup]** > **[!UICONTROL Build]** > **[!UICONTROL Report Types]** > **[!UICONTROL New Custom Report Types]**(으)로 이동합니다.

   ![](assets/4.png)

1. 사용자 지정 보고서 유형을 정의합니다.

   * [!UICONTROL Report Type Focus] > [!UICONTROL Primary Object]: [!DNL Marketo Measure]명
   * [!UICONTROL Identification] > [!UICONTROL Report Type Label]: [!DNL Marketo Measure]명의 사용자(구매자 터치포인트 포함)
   * [!UICONTROL Store in Category]: 기타 보고서
   * [!UICONTROL Deployment] > [!UICONTROL Deployment Status]: 배포됨

   ![](assets/5.png)

1. 객체 관계를 정의합니다.

   * [!DNL Marketo Measure] 개인 개체(A)를 Buyer Touchpoint 개체(B)와 연결
   * &quot;[!UICONTROL Each A record must have at least one B]&quot; 레코드가 선택되었는지 확인합니다.
   * [!UICONTROL Save]

   ![](assets/6.png)

## Buyer Attribution Touchpoint을 사용한 기회 (사용자 지정) {#opportunities-with-buyer-attribution-touchpoint-custom}

1. **[!UICONTROL Setup]** > **[!UICONTROL Build]** > **[!UICONTROL Report Types]** > **[!UICONTROL New Custom Report Types]**(으)로 이동합니다.

   ![](assets/7.png)

1. 사용자 지정 보고서 유형을 정의합니다.

   * [!UICONTROL Report Type Focus] > [!UICONTROL Primary Object]: 기회
   * [!UICONTROL Identification] > [!UICONTROL Report Type Label]: Buyer Attribution Touchpoint이 있는 기회(사용자 지정)
   * [!UICONTROL Store in Category]: 기타 보고서
   * [!UICONTROL Deployment] > [!UICONTROL Deployment Status]: 배포됨

   ![](assets/8.png)

1. 객체 관계를 정의합니다.

   * Opportunities 개체(A)를 Buyer Attribution Touchpoint 개체(B)와 연결
   * &quot;[!UICONTROL Each A record must have at least one B]&quot; 레코드가 선택되었는지 확인합니다.
   * [!UICONTROL Save]

   ![](assets/9.png)

## 사용자 지정 보고서 유형에 사용자 지정 필드 추가 {#adding-custom-fields-to-custom-report-types}

1. 보고서가 생성되면 보고서 유형 개요로 리디렉션됩니다. **[!UICONTROL Edit Layout]**&#x200B;을(를) 클릭합니다.

   ![](assets/10.png)

1. 보고서에 추가하려는 사용자 정의 필드가 필드 레이아웃 속성 섹션에 나타나는지 확인합니다. 추가할 다른 필드가 있으면 &quot;[!UICONTROL Add fields related via lookup]&quot; 옵션을 사용하십시오.

   ![](assets/11.png)
