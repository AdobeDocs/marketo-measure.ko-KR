---
unique-page-id: 18874523
description: "[!DNL Marketo Measure] Dynamics 스키마 - [!DNL Marketo Measure]"
title: "[!DNL Marketo Measure] Dynamics 스키마"
exl-id: f8da47b1-d844-4bd2-8125-8689cbb5cc30
feature: Microsoft Dynamics
source-git-commit: 9e672d0c568ee0b889461bb8ba6fc6333edf31ce
workflow-type: tm+mt
source-wordcount: '1070'
ht-degree: 22%

---

# [!DNL Marketo Measure] Dynamics 스키마 {#marketo-measure-dynamics-schema}

>[!NOTE]
>
>&quot; &quot;을 지정하는 지침이 표시될 수 있습니다.[!DNL Marketo Measure]설명서에는 &quot;가 있지만 CRM에는 &quot;Bizible&quot;이 표시됩니다. 이를 업데이트하고 리브랜딩이 곧 CRM에 반영되도록 노력하고 있습니다.

다음은 시작하는 데 필요한 Dynamics 스키마입니다 [!DNL Marketo Measure]. 필요한 읽기 및/또는 쓰기 권한과 함께 모든 엔티티와 필드가 나열됩니다.

## 구매자 접점 {#buyer-touchpoints}

구매자 접점은 [!DNL Marketo Measure] 연락처 및 리드에 대한 마케팅 상호 작용을 캡슐화할 사용자 지정 엔티티.

## 구매자 접점 관계 {#buyer-touchpoint-relationships}

이 다이어그램은 Dynamics Stock 엔티티와 구매자 접점 간의 관계에 대한 높은 수준의 시각화입니다.

## 구매자 접점 {#buyer-touchpoint}

<table> 
 <tbody> 
  <tr> 
   <th><p>스키마 이름</p></th> 
   <th><p>Standard/Custom</p></th> 
   <th><p>읽기</p></th> 
   <th><p>쓰기</p></th> 
  </tr> 
  <tr> 
   <td><p>bizible2_Ad_Campaign_Id</p></td> 
   <td><p>맞춤형</p></td> 
   <td><p>x</p></td> 
   <td><p>x</p></td> 
  </tr> 
  <tr> 
   <td><p>bizible2_Ad_Campaign_Name</p></td> 
   <td><p>맞춤형</p></td> 
   <td><p>x</p></td> 
   <td><p>x</p></td> 
  </tr> 
  <tr> 
   <td><p>bizible2_Ad_Content</p></td> 
   <td><p>맞춤형</p></td> 
   <td><p>x</p></td> 
   <td><p>x</p></td> 
  </tr> 
  <tr> 
   <td><p>bizible2_Ad_Destination_URL</p></td> 
   <td><p>맞춤형</p></td> 
   <td><p>x</p></td> 
   <td><p>x</p></td> 
  </tr> 
  <tr> 
   <td><p>bizible2_Ad_Group_Id</p></td> 
   <td><p>맞춤형</p></td> 
   <td><p>x</p></td> 
   <td><p>x</p></td> 
  </tr> 
  <tr> 
   <td><p>bizible2_Ad_Group_Name</p></td> 
   <td><p>맞춤형</p></td> 
   <td><p>x</p></td> 
   <td><p>x</p></td> 
  </tr> 
  <tr> 
   <td><p>bizible2_Ad_Id</p></td> 
   <td><p>맞춤형</p></td> 
   <td><p>x</p></td> 
   <td><p>x</p></td> 
  </tr> 
  <tr> 
   <td><p>bizible2_Bizible_TouchpointId</p></td> 
   <td><p>맞춤형</p></td> 
   <td><p>x</p></td> 
   <td><p>x</p></td> 
  </tr> 
  <tr> 
   <td><p>bizible2_Browser</p></td> 
   <td><p>맞춤형</p></td> 
   <td><p>x</p></td> 
   <td><p>x</p></td> 
  </tr> 
  <tr> 
   <td><p>bizible2_CampaignId</p></td> 
   <td><p>맞춤형</p></td> 
   <td><p>x</p></td> 
   <td><p>x</p></td> 
  </tr> 
  <tr> 
   <td><p>bizible2_ContactId</p></td> 
   <td><p>맞춤형</p></td> 
   <td><p>x</p></td> 
   <td><p>x</p></td> 
  </tr> 
  <tr> 
   <td><p>bizible2_Count_First_Touch</p></td> 
   <td><p>맞춤형</p></td> 
   <td><p>x</p></td> 
   <td><p>x</p></td> 
  </tr> 
  <tr> 
   <td><p>bizible2_Count_Lead_Conversion_Touch</p></td> 
   <td><p>맞춤형</p></td> 
   <td><p>x</p></td> 
   <td><p>x</p></td> 
  </tr> 
  <tr> 
   <td><p>bizible2_Count_U_Shaped</p></td> 
   <td><p>맞춤형</p></td> 
   <td><p>x</p></td> 
   <td><p>x</p></td> 
  </tr> 
  <tr> 
   <td><p>bizible2_Form_URL</p></td> 
   <td><p>맞춤형</p></td> 
   <td><p>x</p></td> 
   <td><p>x</p></td> 
  </tr> 
  <tr> 
   <td><p>bizible2_Form_URL_Raw</p></td> 
   <td><p>맞춤형</p></td> 
   <td><p>x</p></td> 
   <td><p>x</p></td> 
  </tr> 
  <tr> 
   <td><p>bizible2_Geo_City</p></td> 
   <td><p>맞춤형</p></td> 
   <td><p>x</p></td> 
   <td><p>x</p></td> 
  </tr> 
  <tr> 
   <td><p>bizible2_Geo_Country</p></td> 
   <td><p>맞춤형</p></td> 
   <td><p>x</p></td> 
   <td><p>x</p></td> 
  </tr> 
  <tr> 
   <td><p>bizible2_Geo_Region</p></td> 
   <td><p>맞춤형</p></td> 
   <td><p>x</p></td> 
   <td><p>x</p></td> 
  </tr> 
  <tr> 
   <td><p>bizible2_Keyword_Id</p></td> 
   <td><p>맞춤형</p></td> 
   <td><p>x</p></td> 
   <td><p>x</p></td> 
  </tr> 
  <tr> 
   <td><p>bizible2_Keyword_MatchType</p></td> 
   <td><p>맞춤형</p></td> 
   <td><p>x</p></td> 
   <td><p>x</p></td> 
  </tr> 
  <tr> 
   <td><p>bizible2_Keyword_Text</p></td> 
   <td><p>맞춤형</p></td> 
   <td><p>x</p></td> 
   <td><p>x</p></td> 
  </tr> 
  <tr> 
   <td><p>bizible2_Landing_Page</p></td> 
   <td><p>맞춤형</p></td> 
   <td><p>x</p></td> 
   <td><p>x</p></td> 
  </tr> 
  <tr> 
   <td><p>bizible2_Landing_Page_Raw</p></td> 
   <td><p>맞춤형</p></td> 
   <td><p>x</p></td> 
   <td><p>x</p></td> 
  </tr> 
  <tr> 
   <td><p>bizible2_LeadId</p></td> 
   <td><p>맞춤형</p></td> 
   <td><p>x</p></td> 
   <td><p>x</p></td> 
  </tr> 
  <tr> 
   <td><p>bizible2_Marketing_Channel</p></td> 
   <td><p>맞춤형</p></td> 
   <td><p>x</p></td> 
   <td><p>x</p></td> 
  </tr> 
  <tr> 
   <td><p>bizible2_Marketing_Channel_Path</p></td> 
   <td><p>맞춤형</p></td> 
   <td><p>x</p></td> 
   <td><p>x</p></td> 
  </tr> 
  <tr> 
   <td><p>bizible2_Medium</p></td> 
   <td><p>맞춤형</p></td> 
   <td><p>x</p></td> 
   <td><p>x</p></td> 
  </tr> 
  <tr> 
   <td><p>bizible2_Name</p></td> 
   <td><p>맞춤형</p></td> 
   <td><p>x</p></td> 
   <td><p>x</p></td> 
  </tr> 
  <tr> 
   <td><p>bizible2_Placement_Id</p></td> 
   <td><p>맞춤형</p></td> 
   <td><p>x</p></td> 
   <td><p>x</p></td> 
  </tr> 
  <tr> 
   <td><p>bizible2_Placement_Name</p></td> 
   <td><p>맞춤형</p></td> 
   <td><p>x</p></td> 
   <td><p>x</p></td> 
  </tr> 
  <tr> 
   <td><p>bizible2_Platform</p></td> 
   <td><p>맞춤형</p></td> 
   <td><p>x</p></td> 
   <td><p>x</p></td> 
  </tr> 
  <tr> 
   <td><p>bizible2_Referrer_Page</p></td> 
   <td><p>맞춤형</p></td> 
   <td><p>x</p></td> 
   <td><p>x</p></td> 
  </tr> 
  <tr> 
   <td><p>bizible2_레퍼러_페이지 원시</p></td> 
   <td><p>맞춤형</p></td> 
   <td><p>x</p></td> 
   <td><p>x</p></td> 
  </tr> 
  <tr> 
   <td><p>bizible2_Search_Phrase</p></td> 
   <td><p>맞춤형</p></td> 
   <td><p>x</p></td> 
   <td><p>x</p></td> 
  </tr> 
  <tr> 
   <td><p>bizible2_Segment</p></td> 
   <td><p>맞춤형</p></td> 
   <td><p>x</p></td> 
   <td><p>x</p></td> 
  </tr> 
  <tr> 
   <td><p>bizible2_Site_Id</p></td> 
   <td><p>맞춤형</p></td> 
   <td><p>x</p></td> 
   <td><p>x</p></td> 
  </tr> 
  <tr> 
   <td><p>bizible2_Site_Name</p></td> 
   <td><p>맞춤형</p></td> 
   <td><p>x</p></td> 
   <td><p>x</p></td> 
  </tr> 
  <tr> 
   <td><p>bizible2_Touchpoint_Date</p></td> 
   <td><p>맞춤형</p></td> 
   <td><p>x</p></td> 
   <td><p>x</p></td> 
  </tr> 
  <tr> 
   <td><p>bizible2_Touchpoint_Position</p></td> 
   <td><p>맞춤형</p></td> 
   <td><p>x</p></td> 
   <td><p>x</p></td> 
  </tr> 
  <tr> 
   <td><p>bizible2_Touchpoint_Source</p></td> 
   <td><p>맞춤형</p></td> 
   <td><p>x</p></td> 
   <td><p>x</p></td> 
  </tr> 
  <tr> 
   <td><p>bizible2_Touchpoint_Type</p></td> 
   <td><p>맞춤형</p></td> 
   <td><p>x</p></td> 
   <td><p>x</p></td> 
  </tr> 
  <tr> 
   <td><p>bizible2_UniqueId</p></td> 
   <td><p>맞춤형</p></td> 
   <td><p>x</p></td> 
   <td><p>x</p></td> 
  </tr> 
  <tr> 
   <td><p>bizible2_Account</p></td> 
   <td><p>맞춤형</p></td> 
   <td><p>x</p></td> 
   <td><p>x</p></td> 
  </tr> 
 </tbody> 
</table>

## 구매자 속성 접점 {#buyer-attribution-touchpoint}

구매자 속성 터치포인트는 [!DNL Marketo Measure] 영업 기회에 대한 마케팅의 영향을 캡슐화할 사용자 지정 엔티티입니다.

## 구매자 속성 접점 관계 {#buyer-attribution-touchpoint-relationships}

이 다이어그램은 Dynamics Stock 엔티티와 구매자 속성 접점 간의 관계에 대한 높은 수준의 시각화입니다.

## 구매자 기여도 분석 접점 {#buyer-attribution-touchpoints}

<table> 
 <tbody> 
  <tr> 
   <th><p>스키마 이름</p></th> 
   <th><p>Standard/Custom</p></th> 
   <th><p>읽기</p></th> 
   <th><p>쓰기</p></th> 
  </tr> 
  <tr> 
   <td><p>bizible2_AccountId</p></td> 
   <td><p>맞춤형</p></td> 
   <td><p>x</p></td> 
   <td><p>x</p></td> 
  </tr> 
  <tr> 
   <td><p>bizible2_Ad_Campaign_Id</p></td> 
   <td><p>맞춤형</p></td> 
   <td><p>x</p></td> 
   <td><p>x</p></td> 
  </tr> 
  <tr> 
   <td><p>bizible2_Ad_Campaign_Name</p></td> 
   <td><p>맞춤형</p></td> 
   <td><p>x</p></td> 
   <td><p>x</p></td> 
  </tr> 
  <tr> 
   <td><p>bizible2_Ad_Content</p></td> 
   <td><p>맞춤형</p></td> 
   <td><p>x</p></td> 
   <td><p>x</p></td> 
  </tr> 
  <tr> 
   <td><p>bizible2_Ad_Destination_URL</p></td> 
   <td><p>맞춤형</p></td> 
   <td><p>x</p></td> 
   <td><p>x</p></td> 
  </tr> 
  <tr> 
   <td><p>bizible2_Ad_Group_Id</p></td> 
   <td><p>맞춤형</p></td> 
   <td><p>x</p></td> 
   <td><p>x</p></td> 
  </tr> 
  <tr> 
   <td><p>bizible2_Ad_Group_Name</p></td> 
   <td><p>맞춤형</p></td> 
   <td><p>x</p></td> 
   <td><p>x</p></td> 
  </tr> 
  <tr> 
   <td><p>bizible2_Ad_Id</p></td> 
   <td><p>맞춤형</p></td> 
   <td><p>x</p></td> 
   <td><p>x</p></td> 
  </tr> 
  <tr> 
   <td><p>bizible2_Attribution_Custom_Model</p></td> 
   <td><p>맞춤형</p></td> 
   <td><p>x</p></td> 
   <td><p>x</p></td> 
  </tr> 
  <tr> 
   <td><p>bizible2_Attribution_Custom_Model_2</p></td> 
   <td><p>맞춤형</p></td> 
   <td><p>x</p></td> 
   <td><p>x</p></td> 
  </tr> 
  <tr> 
   <td><p>bizible2_Attribution_First_Touch</p></td> 
   <td><p>맞춤형</p></td> 
   <td><p>x</p></td> 
   <td><p>x</p></td> 
  </tr> 
  <tr> 
   <td><p>bizible2_Attribution_Lead_Conversion_Touch</p></td> 
   <td><p>맞춤형</p></td> 
   <td><p>x</p></td> 
   <td><p>x</p></td> 
  </tr> 
  <tr> 
   <td><p>bizible2_Attribution_U_Shaped</p></td> 
   <td><p>맞춤형</p></td> 
   <td><p>x</p></td> 
   <td><p>x</p></td> 
  </tr> 
  <tr> 
   <td><p>bizible2_Attribution_W_Shaped</p></td> 
   <td><p>맞춤형</p></td> 
   <td><p>x</p></td> 
   <td><p>x</p></td> 
  </tr> 
  <tr> 
   <td><p>bizible2_Bizible_Attribution_TouchpointId</p></td> 
   <td><p>맞춤형</p></td> 
   <td><p>x</p></td> 
   <td><p>x</p></td> 
  </tr> 
  <tr> 
   <td><p>bizible2_Browser</p></td> 
   <td><p>맞춤형</p></td> 
   <td><p>x</p></td> 
   <td><p>x</p></td> 
  </tr> 
  <tr> 
   <td><p>bizible2_CampaignId</p></td> 
   <td><p>맞춤형</p></td> 
   <td><p>x</p></td> 
   <td><p>x</p></td> 
  </tr> 
  <tr> 
   <td><p>bizible2_ContactId</p></td> 
   <td><p>맞춤형</p></td> 
   <td><p>x</p></td> 
   <td><p>x</p></td> 
  </tr> 
  <tr> 
   <td><p>bizible2_Count_Custom_Model</p></td> 
   <td><p>맞춤형</p></td> 
   <td><p>x</p></td> 
   <td><p>x</p></td> 
  </tr> 
  <tr> 
   <td><p>bizible2_Count_Custom_Model_2</p></td> 
   <td><p>맞춤형</p></td> 
   <td><p>x</p></td> 
   <td><p>x</p></td> 
  </tr> 
  <tr> 
   <td><p>bizible2_Count_First_Touch</p></td> 
   <td><p>맞춤형</p></td> 
   <td><p>x</p></td> 
   <td><p>x</p></td> 
  </tr> 
  <tr> 
   <td><p>bizible2_Count_Lead_Creation_Touch</p></td> 
   <td><p>맞춤형</p></td> 
   <td><p>x</p></td> 
   <td><p>x</p></td> 
  </tr> 
  <tr> 
   <td><p>bizible2_Count_U_Shaped</p></td> 
   <td><p>맞춤형</p></td> 
   <td><p>x</p></td> 
   <td><p>x</p></td> 
  </tr> 
  <tr> 
   <td><p>bizible2_Count_W_Shaped</p></td> 
   <td><p>맞춤형</p></td> 
   <td><p>x</p></td> 
   <td><p>x</p></td> 
  </tr> 
  <tr> 
   <td><p>bizible2_Form_URL</p></td> 
   <td><p>맞춤형</p></td> 
   <td><p>x</p></td> 
   <td><p>x</p></td> 
  </tr> 
  <tr> 
   <td><p>bizible2_Form_URL_Raw</p></td> 
   <td><p>맞춤형</p></td> 
   <td><p>x</p></td> 
   <td><p>x</p></td> 
  </tr> 
  <tr> 
   <td><p>bizible2_Geo_City</p></td> 
   <td><p>맞춤형</p></td> 
   <td><p>x</p></td> 
   <td><p>x</p></td> 
  </tr> 
  <tr> 
   <td><p>bizible2_Geo_Country</p></td> 
   <td><p>맞춤형</p></td> 
   <td><p>x</p></td> 
   <td><p>x</p></td> 
  </tr> 
  <tr> 
   <td><p>bizible2_Geo_Region</p></td> 
   <td><p>맞춤형</p></td> 
   <td><p>x</p></td> 
   <td><p>x</p></td> 
  </tr> 
  <tr> 
   <td><p>bizible2_Keyword_Id</p></td> 
   <td><p>맞춤형</p></td> 
   <td><p>x</p></td> 
   <td><p>x</p></td> 
  </tr> 
  <tr> 
   <td><p>bizible2_Keyword_MatchType</p></td> 
   <td><p>맞춤형</p></td> 
   <td><p>x</p></td> 
   <td><p>x</p></td> 
  </tr> 
  <tr> 
   <td><p>bizible2_Keyword_Text</p></td> 
   <td><p>맞춤형</p></td> 
   <td><p>x</p></td> 
   <td><p>x</p></td> 
  </tr> 
  <tr> 
   <td><p>bizible2_Landing_Page</p></td> 
   <td><p>맞춤형</p></td> 
   <td><p>x</p></td> 
   <td><p>x</p></td> 
  </tr> 
  <tr> 
   <td><p>bizible2_Landing_Page_Raw</p></td> 
   <td><p>맞춤형</p></td> 
   <td><p>x</p></td> 
   <td><p>x</p></td> 
  </tr> 
  <tr> 
   <td><p>bizible2_Marketing_Channel</p></td> 
   <td><p>맞춤형</p></td> 
   <td><p>x</p></td> 
   <td><p>x</p></td> 
  </tr> 
  <tr> 
   <td><p>bizible2_Marketing_Channel_Path</p></td> 
   <td><p>맞춤형</p></td> 
   <td><p>x</p></td> 
   <td><p>x</p></td> 
  </tr> 
  <tr> 
   <td><p>bizible2_Medium</p></td> 
   <td><p>맞춤형</p></td> 
   <td><p>x</p></td> 
   <td><p>x</p></td> 
  </tr> 
  <tr> 
   <td><p>bizible2_Name</p></td> 
   <td><p>맞춤형</p></td> 
   <td><p>x</p></td> 
   <td><p>x</p></td> 
  </tr> 
  <tr> 
   <td><p>bizible2_OpportunityId</p></td> 
   <td><p>맞춤형</p></td> 
   <td><p>x</p></td> 
   <td><p>x</p></td> 
  </tr> 
  <tr> 
   <td><p>bizible2_Placement_Id</p></td> 
   <td><p>맞춤형</p></td> 
   <td><p>x</p></td> 
   <td><p>x</p></td> 
  </tr> 
  <tr> 
   <td><p>bizible2_Placement_Name</p></td> 
   <td><p>맞춤형</p></td> 
   <td><p>x</p></td> 
   <td><p>x</p></td> 
  </tr> 
  <tr> 
   <td><p>bizible2_Platform</p></td> 
   <td><p>맞춤형</p></td> 
   <td><p>x</p></td> 
   <td><p>x</p></td> 
  </tr> 
  <tr> 
   <td><p>bizible2_Referrer_Page</p></td> 
   <td><p>맞춤형</p></td> 
   <td><p>x</p></td> 
   <td><p>x</p></td> 
  </tr> 
  <tr> 
   <td><p>bizible2_레퍼러_페이지 원시</p></td> 
   <td><p>맞춤형</p></td> 
   <td><p>x</p></td> 
   <td><p>x</p></td> 
  </tr> 
  <tr> 
   <td><p>bizible2_Revenue_Custom_Model</p></td> 
   <td><p>맞춤형</p></td> 
   <td><p>x</p></td> 
   <td><p>x</p></td> 
  </tr> 
  <tr> 
   <td><p>bizible2_Revenue_Custom_Model_2</p></td> 
   <td><p>맞춤형</p></td> 
   <td><p>x</p></td> 
   <td><p>x</p></td> 
  </tr> 
  <tr> 
   <td><p>bizible2_revenue_custom_model_2_Base</p></td> 
   <td><p>맞춤형</p></td> 
   <td><p>x</p></td> 
   <td><p>x</p></td> 
  </tr> 
  <tr> 
   <td><p>bizible2_revenue_custom_model_Base</p></td> 
   <td><p>맞춤형</p></td> 
   <td><p>x</p></td> 
   <td><p>x</p></td> 
  </tr> 
  <tr> 
   <td><p>bizible2_Revenue_First_Touch</p></td> 
   <td><p>맞춤형</p></td> 
   <td><p>x</p></td> 
   <td><p>x</p></td> 
  </tr> 
  <tr> 
   <td><p>bizible2_revenue_first_touch_Base</p></td> 
   <td><p>맞춤형</p></td> 
   <td><p>x</p></td> 
   <td><p>x</p></td> 
  </tr> 
  <tr> 
   <td><p>bizible2_Revenue_Lead_Conversion_Touch</p></td> 
   <td><p>맞춤형</p></td> 
   <td><p>x</p></td> 
   <td><p>x</p></td> 
  </tr> 
  <tr> 
   <td><p>bizible2_revenue_lead_conversion_Base</p></td> 
   <td><p>맞춤형</p></td> 
   <td><p>x</p></td> 
   <td><p>x</p></td> 
  </tr> 
  <tr> 
   <td><p>bizible2_Revenue_U_Shaped</p></td> 
   <td><p>맞춤형</p></td> 
   <td><p>x</p></td> 
   <td><p>x</p></td> 
  </tr> 
  <tr> 
   <td><p>bizible2_revenue_u_shaped_Base</p></td> 
   <td><p>맞춤형</p></td> 
   <td><p>x</p></td> 
   <td><p>x</p></td> 
  </tr> 
  <tr> 
   <td><p>bizible2_Revenue_W_Shaped</p></td> 
   <td><p>맞춤형</p></td> 
   <td><p>x</p></td> 
   <td><p>x</p></td> 
  </tr> 
  <tr> 
   <td><p>bizible2_revenue_w_shaped_Base</p></td> 
   <td><p>맞춤형</p></td> 
   <td><p>x</p></td> 
   <td><p>x</p></td> 
  </tr> 
  <tr> 
   <td><p>bizible2_Search_Phrase</p></td> 
   <td><p>맞춤형</p></td> 
   <td><p>x</p></td> 
   <td><p>x</p></td> 
  </tr> 
  <tr> 
   <td><p>bizible2_Segment</p></td> 
   <td><p>맞춤형</p></td> 
   <td><p>x</p></td> 
   <td><p>x</p></td> 
  </tr> 
  <tr> 
   <td><p>bizible2_Site_Id</p></td> 
   <td><p>맞춤형</p></td> 
   <td><p>x</p></td> 
   <td><p>x</p></td> 
  </tr> 
  <tr> 
   <td><p>bizible2_Site_Name</p></td> 
   <td><p>맞춤형</p></td> 
   <td><p>x</p></td> 
   <td><p>x</p></td> 
  </tr> 
  <tr> 
   <td><p>bizible2_Touchpoint_Date</p></td> 
   <td><p>맞춤형</p></td> 
   <td><p>x</p></td> 
   <td><p>x</p></td> 
  </tr> 
  <tr> 
   <td><p>bizible2_Touchpoint_Position</p></td> 
   <td><p>맞춤형</p></td> 
   <td><p>x</p></td> 
   <td><p>x</p></td> 
  </tr> 
  <tr> 
   <td><p>bizible2_Touchpoint_Source</p></td> 
   <td><p>맞춤형</p></td> 
   <td><p>x</p></td> 
   <td><p>x</p></td> 
  </tr> 
  <tr> 
   <td><p>bizible2_Touchpoint_Type</p></td> 
   <td><p>맞춤형</p></td> 
   <td><p>x</p></td> 
   <td><p>x</p></td> 
  </tr> 
  <tr> 
   <td><p>bizible2_UniqueId</p></td> 
   <td><p>맞춤형</p></td> 
   <td><p>x</p></td> 
   <td><p>x</p></td> 
  </tr> 
 </tbody> 
</table>

## [!DNL Marketo Measure] AB 테스트 {#marketo-measure-ab-tests}

<table> 
 <tbody> 
  <tr> 
   <th><p>스키마 이름</p></th> 
   <th><p>Standard/Custom</p></th> 
   <th><p>읽기</p></th> 
   <th><p>쓰기</p></th> 
  </tr> 
  <tr> 
   <td><p>bizible2_Bizible_ABTestId</p></td> 
   <td><p>맞춤형</p></td> 
   <td><p>x</p></td> 
   <td><p>x</p></td> 
  </tr> 
  <tr> 
   <td><p>bizible2_BizibleId</p></td> 
   <td><p>맞춤형</p></td> 
   <td><p>x</p></td> 
   <td><p>x</p></td> 
  </tr> 
  <tr> 
   <td><p>bizible2_ContactId</p></td> 
   <td><p>맞춤형</p></td> 
   <td><p>x</p></td> 
   <td><p>x</p></td> 
  </tr> 
  <tr> 
   <td><p>bizible2_DateReported</p></td> 
   <td><p>맞춤형</p></td> 
   <td><p>x</p></td> 
   <td><p>x</p></td> 
  </tr> 
  <tr> 
   <td><p>bizible2_Experiment</p></td> 
   <td><p>맞춤형</p></td> 
   <td><p>x</p></td> 
   <td><p>x</p></td> 
  </tr> 
  <tr> 
   <td><p>bizible2_ExperimentId</p></td> 
   <td><p>맞춤형</p></td> 
   <td><p>x</p></td> 
   <td><p>x</p></td> 
  </tr> 
  <tr> 
   <td><p>bizible2_LeadId</p></td> 
   <td><p>맞춤형</p></td> 
   <td><p>x</p></td> 
   <td><p>x</p></td> 
  </tr> 
  <tr> 
   <td><p>bizible2_Name</p></td> 
   <td><p>맞춤형</p></td> 
   <td><p>x</p></td> 
   <td><p>x</p></td> 
  </tr> 
  <tr> 
   <td><p>bizible2_OpportunityId</p></td> 
   <td><p>맞춤형</p></td> 
   <td><p>x</p></td> 
   <td><p>x</p></td> 
  </tr> 
  <tr> 
   <td><p>bizible2_UserId</p></td> 
   <td><p>맞춤형</p></td> 
   <td><p>x</p></td> 
   <td><p>x</p></td> 
  </tr> 
  <tr> 
   <td><p>bizible2_Variation</p></td> 
   <td><p>맞춤형</p></td> 
   <td><p>x</p></td> 
   <td><p>x</p></td> 
  </tr> 
  <tr> 
   <td><p>bizible2_VariationId</p></td> 
   <td><p>맞춤형</p></td> 
   <td><p>x</p></td> 
   <td><p>x</p></td> 
  </tr> 
 </tbody> 
</table>

## [!DNL Marketo Measure] 이벤트 {#marketo-measure-events}

<table> 
 <tbody> 
  <tr> 
   <th><p>스키마 이름</p></th> 
   <th><p>Standard/Custom</p></th> 
   <th><p>읽기</p></th> 
   <th><p>쓰기</p></th> 
  </tr> 
  <tr> 
   <td><p>bizible2_Bizible_EventId</p></td> 
   <td><p>맞춤형</p></td> 
   <td><p>x</p></td> 
   <td><p>x</p></td> 
  </tr> 
  <tr> 
   <td><p>bizible2_BizibleId</p></td> 
   <td><p>맞춤형</p></td> 
   <td><p>x</p></td> 
   <td><p>x</p></td> 
  </tr> 
  <tr> 
   <td><p>bizible2_ContactId</p></td> 
   <td><p>맞춤형</p></td> 
   <td><p>x</p></td> 
   <td><p>x</p></td> 
  </tr> 
  <tr> 
   <td><p>bizible2_DateReported</p></td> 
   <td><p>맞춤형</p></td> 
   <td><p>x</p></td> 
   <td><p>x</p></td> 
  </tr> 
  <tr> 
   <td><p>bizible2_EventName</p></td> 
   <td><p>맞춤형</p></td> 
   <td><p>x</p></td> 
   <td><p>x</p></td> 
  </tr> 
  <tr> 
   <td><p>bizible2_EventValue</p></td> 
   <td><p>맞춤형</p></td> 
   <td><p>x</p></td> 
   <td><p>x</p></td> 
  </tr> 
  <tr> 
   <td><p>bizible2_LeadId</p></td> 
   <td><p>맞춤형</p></td> 
   <td><p>x</p></td> 
   <td><p>x</p></td> 
  </tr> 
  <tr> 
   <td><p>bizible2_Name</p></td> 
   <td><p>맞춤형</p></td> 
   <td><p>x</p></td> 
   <td><p>x</p></td> 
  </tr> 
  <tr> 
   <td><p>bizible2_OpportunityId</p></td> 
   <td><p>맞춤형</p></td> 
   <td><p>x</p></td> 
   <td><p>x</p></td> 
  </tr> 
 </tbody> 
</table>

## [!DNL Marketo Measure] 기록 {#marketo-measure-history}

<table> 
 <tbody> 
  <tr> 
   <th><p>스키마 이름</p></th> 
   <th><p>Standard/Custom</p></th> 
   <th><p>읽기</p></th> 
   <th><p>쓰기</p></th> 
  </tr> 
  <tr> 
   <td><p>bizible2_Bizible_HistoryId</p></td> 
   <td><p>맞춤형</p></td> 
   <td><p>x</p></td> 
   <td><p>x</p></td> 
  </tr> 
  <tr> 
   <td><p>bizible2_Entity_Type</p></td> 
   <td><p>맞춤형</p></td> 
   <td><p>x</p></td> 
   <td><p>x</p></td> 
  </tr> 
  <tr> 
   <td><p>bizible2_EntityId</p></td> 
   <td><p>맞춤형</p></td> 
   <td><p>x</p></td> 
   <td><p>x</p></td> 
  </tr> 
  <tr> 
   <td><p>bizible2_EntityLogicalName</p></td> 
   <td><p>맞춤형</p></td> 
   <td><p>x</p></td> 
   <td><p>x</p></td> 
  </tr> 
  <tr> 
   <td><p>bizible2_Name</p></td> 
   <td><p>맞춤형</p></td> 
   <td><p>x</p></td> 
   <td><p>x</p></td> 
  </tr> 
 </tbody> 
</table>

## Dynamics 표준 엔티티 {#dynamics-standard-entities}

이 목록은 다음을 제공하는 Dynamics 표준 엔터티를 제공합니다. [!DNL Marketo Measure] 는 와 상호 작용하며, 이러한 엔티티에 추가하는 사용자 정의 필드와 상호 작용합니다.

**리드**

<table> 
 <tbody> 
  <tr> 
   <th><p>스키마 이름</p></th> 
   <th><p>Standard/Custom</p></th> 
   <th><p>읽기</p></th> 
   <th><p>쓰기</p></th> 
  </tr> 
  <tr> 
   <td><p>leadid</p></td> 
   <td><p>표준</p></td> 
   <td><p>x</p></td> 
   <td> </td> 
  </tr> 
  <tr> 
   <td><p>emailaddress1</p></td> 
   <td><p>표준</p></td> 
   <td><p>x</p></td> 
   <td> </td> 
  </tr> 
  <tr> 
   <td><p>statecode</p></td> 
   <td><p>표준</p></td> 
   <td><p>x</p></td> 
   <td> </td> 
  </tr> 
  <tr> 
   <td><p>statuscode</p></td> 
   <td><p>표준</p></td> 
   <td><p>x</p></td> 
   <td> </td> 
  </tr> 
  <tr> 
   <td><p>createdon</p></td> 
   <td><p>표준</p></td> 
   <td><p>x</p></td> 
   <td> </td> 
  </tr> 
  <tr> 
   <td><p>수정됨</p></td> 
   <td><p>표준</p></td> 
   <td><p>x</p></td> 
   <td> </td> 
  </tr> 
  <tr> 
   <td><p>contactid</p></td> 
   <td><p>표준</p></td> 
   <td><p>x</p></td> 
   <td> </td> 
  </tr> 
  <tr> 
   <td><p>qualfyingopportunityid</p></td> 
   <td><p>표준</p></td> 
   <td><p>x</p></td> 
   <td> </td> 
  </tr> 
  <tr> 
   <td><p>websiteurl</p></td> 
   <td><p>표준</p></td> 
   <td><p>x</p></td> 
   <td> </td> 
  </tr> 
  <tr> 
   <td><p>companyname</p></td> 
   <td><p>표준</p></td> 
   <td><p>x</p></td> 
   <td> </td> 
  </tr> 
  <tr> 
   <td><p>bizible2_Account</p></td> 
   <td><p>맞춤형</p></td> 
   <td><p>x</p></td> 
   <td><p>x</p></td> 
  </tr> 
  <tr> 
   <td><p>bizible2_BizibleId</p></td> 
   <td><p>맞춤형</p></td> 
   <td><p>x</p></td> 
   <td><p>x</p></td> 
  </tr> 
 </tbody> 
</table>

**연락처**

<table> 
 <tbody> 
  <tr> 
   <th><p>스키마 이름</p></th> 
   <th><p>Standard/Custom</p></th> 
   <th><p>읽기</p></th> 
   <th><p>쓰기</p></th> 
  </tr> 
  <tr> 
   <td><p>contactid</p></td> 
   <td><p>표준</p></td> 
   <td><p>x</p></td> 
   <td> </td> 
  </tr> 
  <tr> 
   <td><p>emailaddress1</p></td> 
   <td><p>표준</p></td> 
   <td><p>x</p></td> 
   <td> </td> 
  </tr> 
  <tr> 
   <td><p>accountid</p></td> 
   <td><p>표준</p></td> 
   <td><p>x</p></td> 
   <td> </td> 
  </tr> 
  <tr> 
   <td><p>createdon</p></td> 
   <td><p>표준</p></td> 
   <td><p>x</p></td> 
   <td> </td> 
  </tr> 
  <tr> 
   <td><p>수정됨</p></td> 
   <td><p>표준</p></td> 
   <td><p>x</p></td> 
   <td> </td> 
  </tr> 
  <tr> 
   <td><p>bizible2_BizibleId</p></td> 
   <td><p>맞춤형</p></td> 
   <td><p>x</p></td> 
   <td><p>x</p></td> 
  </tr> 
 </tbody> 
</table>

**계정**

<table> 
 <tbody> 
  <tr> 
   <th><p>스키마 이름</p></th> 
   <th><p>Standard/Custom</p></th> 
   <th><p>읽기</p></th> 
   <th><p>쓰기</p></th> 
  </tr> 
  <tr> 
   <td><p>accountid</p></td> 
   <td><p>표준</p></td> 
   <td><p>x</p></td> 
   <td> </td> 
  </tr> 
  <tr> 
   <td><p>websiteurl</p></td> 
   <td><p>표준</p></td> 
   <td><p>x</p></td> 
   <td> </td> 
  </tr> 
  <tr> 
   <td><p>createdon</p></td> 
   <td><p>표준</p></td> 
   <td><p>x</p></td> 
   <td> </td> 
  </tr> 
  <tr> 
   <td><p>수정됨</p></td> 
   <td><p>표준</p></td> 
   <td><p>x</p></td> 
   <td> </td> 
  </tr> 
  <tr> 
   <td><p>bizible2_Engagement_Score</p></td> 
   <td><p>맞춤형</p></td> 
   <td><p>x</p></td> 
   <td><p>x</p></td> 
  </tr> 
 </tbody> 
</table>

**영업 기회**

<table> 
 <tbody> 
  <tr> 
   <th><p>스키마 이름</p></th> 
   <th><p>Standard/Custom</p></th> 
   <th><p>읽기</p></th> 
   <th><p>쓰기</p></th> 
  </tr> 
  <tr> 
   <td><p>opportunityid</p></td> 
   <td><p>표준</p></td> 
   <td><p>x</p></td> 
   <td> </td> 
  </tr> 
  <tr> 
   <td><p>accountid</p></td> 
   <td><p>표준</p></td> 
   <td><p>x</p></td> 
   <td> </td> 
  </tr> 
  <tr> 
   <td><p>createdon</p></td> 
   <td><p>표준</p></td> 
   <td><p>x</p></td> 
   <td> </td> 
  </tr> 
  <tr> 
   <td><p>수정됨</p></td> 
   <td><p>표준</p></td> 
   <td><p>x</p></td> 
   <td> </td> 
  </tr> 
  <tr> 
   <td><p>statecode</p></td> 
   <td><p>표준</p></td> 
   <td><p>x</p></td> 
   <td> </td> 
  </tr> 
  <tr> 
   <td><p>statecodename</p></td> 
   <td><p>표준</p></td> 
   <td><p>x</p></td> 
   <td> </td> 
  </tr> 
  <tr> 
   <td><p>salesstage</p></td> 
   <td><p>표준</p></td> 
   <td><p>x</p></td> 
   <td> </td> 
  </tr> 
  <tr> 
   <td><p>salesstagecode</p></td> 
   <td><p>표준</p></td> 
   <td><p>x</p></td> 
   <td> </td> 
  </tr> 
  <tr> 
   <td><p>estimatedclosedate</p></td> 
   <td><p>표준</p></td> 
   <td><p>x</p></td> 
   <td> </td> 
  </tr> 
  <tr> 
   <td><p>실제 값</p></td> 
   <td><p>표준</p></td> 
   <td><p>x</p></td> 
   <td> </td> 
  </tr> 
  <tr> 
   <td><p>bizible2_Bizible_Opportunity_Amount</p></td> 
   <td><p>맞춤형</p></td> 
   <td><p>x</p></td> 
   <td><p>x</p></td> 
  </tr> 
  <tr> 
   <td><p>bizible2_bizible_opportunity_amount_Base</p></td> 
   <td><p>맞춤형</p></td> 
   <td><p>x</p></td> 
   <td><p>x</p></td> 
  </tr> 
 </tbody> 
</table>

**캠페인**

<table> 
 <tbody> 
  <tr> 
   <th><p>스키마 이름</p></th> 
   <th><p>Standard/Custom</p></th> 
   <th><p>읽기</p></th> 
   <th><p>쓰기</p></th> 
  </tr> 
  <tr> 
   <td><p>campaignid</p></td> 
   <td><p>표준</p></td> 
   <td><p>x</p></td> 
   <td> </td> 
  </tr> 
  <tr> 
   <td><p>타이프 코드</p></td> 
   <td><p>표준</p></td> 
   <td><p>x</p></td> 
   <td> </td> 
  </tr> 
  <tr> 
   <td><p>타이프코드명</p></td> 
   <td><p>표준</p></td> 
   <td><p>x</p></td> 
   <td> </td> 
  </tr> 
  <tr> 
   <td><p>createdon</p></td> 
   <td><p>표준</p></td> 
   <td><p>x</p></td> 
   <td> </td> 
  </tr> 
  <tr> 
   <td><p>수정됨</p></td> 
   <td><p>표준</p></td> 
   <td><p>x</p></td> 
   <td> </td> 
  </tr> 
  <tr> 
   <td><p>bizible2_Bizible_Attribution_SyncType</p></td> 
   <td><p>맞춤형</p></td> 
   <td><p>x</p></td> 
   <td><p>x</p></td> 
  </tr> 
  <tr> 
   <td><p>bizible2_Marketing_Lists_Sync</p></td> 
   <td><p>맞춤형</p></td> 
   <td><p>x</p></td> 
   <td><p>x</p></td> 
  </tr> 
  <tr> 
   <td><p>bizible2_UniqueId</p></td> 
   <td><p>맞춤형</p></td> 
   <td><p>x</p></td> 
   <td><p>x</p></td> 
  </tr> 
  <tr> 
   <td><p>bizible2_Touchpoint_End_Date</p></td> 
   <td><p>맞춤형</p></td> 
   <td><p>x</p></td> 
   <td><p>x</p></td> 
  </tr> 
  <tr> 
   <td><p>bizible2_Touchpoint_Start_Date</p></td> 
   <td><p>맞춤형</p></td> 
   <td><p>x</p></td> 
   <td><p>x</p></td> 
  </tr> 
 </tbody> 
</table>

**캠페인 응답**

<table> 
 <tbody> 
  <tr> 
   <th><p>스키마 이름</p></th> 
   <th><p>Standard/Custom</p></th> 
   <th><p>읽기</p></th> 
   <th><p>쓰기</p></th> 
  </tr> 
  <tr> 
   <td><p>activityid</p></td> 
   <td><p>표준</p></td> 
   <td><p>x</p></td> 
   <td> </td> 
  </tr> 
  <tr> 
   <td><p>activitytypecode</p></td> 
   <td><p>표준</p></td> 
   <td><p>x</p></td> 
   <td> </td> 
  </tr> 
  <tr> 
   <td><p>activitytypecodename</p></td> 
   <td><p>표준</p></td> 
   <td><p>x</p></td> 
   <td> </td> 
  </tr> 
  <tr> 
   <td><p>createdon</p></td> 
   <td><p>표준</p></td> 
   <td><p>x</p></td> 
   <td> </td> 
  </tr> 
  <tr> 
   <td><p>수정됨</p></td> 
   <td><p>표준</p></td> 
   <td><p>x</p></td> 
   <td> </td> 
  </tr> 
  <tr> 
   <td><p>응답 코드</p></td> 
   <td><p>표준</p></td> 
   <td><p>x</p></td> 
   <td> </td> 
  </tr> 
  <tr> 
   <td><p>응답형</p></td> 
   <td><p>표준</p></td> 
   <td><p>x</p></td> 
   <td> </td> 
  </tr> 
  <tr> 
   <td><p>고객</p></td> 
   <td><p>표준</p></td> 
   <td><p>x</p></td> 
   <td> </td> 
  </tr> 
  <tr> 
   <td><p>레가딘고베스티드</p></td> 
   <td><p>표준</p></td> 
   <td><p>x</p></td> 
   <td> </td> 
  </tr> 
  <tr> 
   <td><p>bizible2_Bizible_Touchpoint_Date</p></td> 
   <td><p>맞춤형</p></td> 
   <td><p>x</p></td> 
   <td><p>x</p></td> 
  </tr> 
  <tr> 
   <td><p>bizible2_Touchpoint_Status_Date</p></td> 
   <td><p>맞춤형</p></td> 
   <td><p>x</p></td> 
   <td><p>x</p></td> 
  </tr> 
  <tr> 
   <td><p>bizible2_Touchpoint_Status_Contact</p></td> 
   <td><p>맞춤형</p></td> 
   <td><p>x</p></td> 
   <td><p>x</p></td> 
  </tr> 
  <tr> 
   <td><p>bizible2_Touchpoint_Status_Leade</p></td> 
   <td><p>맞춤형</p></td> 
   <td><p>x</p></td> 
   <td><p>x</p></td> 
  </tr> 
  <tr> 
   <td><p>bizible2_Touchpoint_Status_Opportunity</p></td> 
   <td><p>맞춤형</p></td> 
   <td><p>x</p></td> 
   <td><p>x</p></td> 
  </tr> 
 </tbody> 
</table>

**목록**

<table> 
 <tbody> 
  <tr> 
   <th><p>스키마 이름</p></th> 
   <th><p>Standard/Custom</p></th> 
   <th><p>읽기</p></th> 
   <th><p>쓰기</p></th> 
  </tr> 
  <tr> 
   <td><p>listid</p></td> 
   <td><p>표준</p></td> 
   <td><p>x</p></td> 
   <td> </td> 
  </tr> 
  <tr> 
   <td><p>createdfromcode</p></td> 
   <td><p>표준</p></td> 
   <td><p>x</p></td> 
   <td> </td> 
  </tr> 
  <tr> 
   <td><p>membertype</p></td> 
   <td><p>표준</p></td> 
   <td><p>x</p></td> 
   <td> </td> 
  </tr> 
  <tr> 
   <td><p>createdon</p></td> 
   <td><p>표준</p></td> 
   <td><p>x</p></td> 
   <td> </td> 
  </tr> 
  <tr> 
   <td><p>수정됨</p></td> 
   <td><p>표준</p></td> 
   <td><p>x</p></td> 
   <td> </td> 
  </tr> 
  <tr> 
   <td><p>bizible2_Bizible_Touchpoint_Date</p></td> 
   <td><p>맞춤형</p></td> 
   <td><p>x</p></td> 
   <td><p>x</p></td> 
  </tr> 
 </tbody> 
</table>

**ListMember**

<table> 
 <tbody> 
  <tr> 
   <th><p>스키마 이름</p></th> 
   <th><p>Standard/Custom</p></th> 
   <th><p>읽기</p></th> 
   <th><p>쓰기</p></th> 
  </tr> 
  <tr> 
   <td><p>listid</p></td> 
   <td><p>표준</p></td> 
   <td><p>x</p></td> 
   <td> </td> 
  </tr> 
  <tr> 
   <td><p>entityid</p></td> 
   <td><p>표준</p></td> 
   <td><p>x</p></td> 
   <td> </td> 
  </tr> 
  <tr> 
   <td><p>listmemberid</p></td> 
   <td><p>표준</p></td> 
   <td><p>x</p></td> 
   <td> </td> 
  </tr> 
  <tr> 
   <td><p>createdon</p></td> 
   <td><p>표준</p></td> 
   <td><p>x</p></td> 
   <td> </td> 
  </tr> 
  <tr> 
   <td><p>수정됨</p></td> 
   <td><p>표준</p></td> 
   <td><p>x</p></td> 
   <td> </td> 
  </tr> 
 </tbody> 
</table>

**전화**

<table> 
 <tbody> 
  <tr> 
   <th><p>스키마 이름</p></th> 
   <th><p>Standard/Custom</p></th> 
   <th><p>읽기</p></th> 
   <th><p>쓰기</p></th> 
  </tr> 
  <tr> 
   <td><p>activityid</p></td> 
   <td><p>표준</p></td> 
   <td><p>x</p></td> 
   <td> </td> 
  </tr> 
  <tr> 
   <td><p>activitytypecode</p></td> 
   <td><p>표준</p></td> 
   <td><p>x</p></td> 
   <td> </td> 
  </tr> 
  <tr> 
   <td><p>activitytypecodename</p></td> 
   <td><p>표준</p></td> 
   <td><p>x</p></td> 
   <td> </td> 
  </tr> 
  <tr> 
   <td><p>createdon</p></td> 
   <td><p>표준</p></td> 
   <td><p>x</p></td> 
   <td> </td> 
  </tr> 
  <tr> 
   <td><p>수정됨</p></td> 
   <td><p>표준</p></td> 
   <td><p>x</p></td> 
   <td> </td> 
  </tr> 
  <tr> 
   <td><p>고객</p></td> 
   <td><p>표준</p></td> 
   <td><p>x</p></td> 
   <td> </td> 
  </tr> 
  <tr> 
   <td><p>레가딘고베스티드</p></td> 
   <td><p>표준</p></td> 
   <td><p>x</p></td> 
   <td> </td> 
  </tr> 
  <tr> 
   <td><p>bizible2_Bizible_Touchpoint_Date</p></td> 
   <td><p>맞춤형</p></td> 
   <td><p>x</p></td> 
   <td><p>x</p></td> 
  </tr> 
  <tr> 
   <td><p>bizible2_BizibleId</p></td> 
   <td><p>맞춤형</p></td> 
   <td><p>x</p></td> 
   <td><p>x</p></td> 
  </tr> 
 </tbody> 
</table>

[] = V1 기존 고객만
