---
unique-page-id: 18874523
description: "[!DNL Marketo Measure] Dynamics 스키마 - [!DNL Marketo Measure] - 제품 설명서"
title: "[!DNL Marketo Measure] Dynamics 스키마"
exl-id: f8da47b1-d844-4bd2-8125-8689cbb5cc30
source-git-commit: 54337a0a65b79d80ebeae6531f5e92f4f48721a7
workflow-type: tm+mt
source-wordcount: '1408'
ht-degree: 17%

---

# [!DNL Marketo Measure] Dynamics 스키마 {#marketo-measure-dynamics-schema}

>[!NOTE]
>
>&quot;[!DNL Marketo Measure]&quot;은 설명서이지만 CRM에서 &quot;Bizible&quot;을 참조하십시오. 업데이트를 위해 노력하고 있으며 리브랜딩이 곧 CRM에 반영됩니다.

아래에서는 을 시작하기 위해 필요한 Dynamics 스키마를 찾을 수 있습니다 [!DNL Marketo Measure]. 필요한 읽기 및/또는 쓰기 액세스와 함께 모든 개체 및 필드가 나열됩니다.

## 구매자 터치포인트 {#buyer-touchpoints}

구매자 터치포인트는 [!DNL Marketo Measure] 연락처 및 리드에 대한 마케팅 상호 작용을 캡슐화할 사용자 지정 엔티티입니다.

## 구매자 접점 관계 {#buyer-touchpoint-relationships}

이 다이어그램은 Dynamics Stock 엔티티와 구매자 터치포인트 간의 관계를 보여주는 높은 수준의 시각화입니다.

## 구매자 터치포인트 {#buyer-touchpoint}

<table> 
 <tbody> 
  <tr> 
   <th><p>스키마 이름</p></th> 
   <th><p>표준/사용자 지정</p></th> 
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
   <td><p>bizible2_Referrer_Page_Raw</p></td> 
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

## 구매자 기여도 분석 터치포인트 {#buyer-attribution-touchpoint}

구매자 기여도 분석 터치포인트는 [!DNL Marketo Measure] Opportunity에 대한 마케팅의 영향을 캡슐화하는 사용자 지정 항목입니다.

## 구매자 속성 터치포인트 관계 {#buyer-attribution-touchpoint-relationships}

이 다이어그램은 Dynamics Stock 엔티티와 구매자 속성 터치포인트 간의 관계에 대한 높은 수준의 시각화입니다.

## 구매자 기여도 분석 터치포인트 {#buyer-attribution-touchpoints}

<table> 
 <tbody> 
  <tr> 
   <th><p>스키마 이름</p></th> 
   <th><p>표준/사용자 지정</p></th> 
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
   <td><p>bizible2_Referrer_Page_Raw</p></td> 
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
   <th><p>표준/사용자 지정</p></th> 
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
   <th><p>표준/사용자 지정</p></th> 
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

## [!DNL Marketo Measure] 내역 {#marketo-measure-history}

<table> 
 <tbody> 
  <tr> 
   <th><p>스키마 이름</p></th> 
   <th><p>표준/사용자 지정</p></th> 
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

## Dynamics 표준 엔터티 {#dynamics-standard-entities}

이 목록은 [!DNL Marketo Measure] 는 이러한 엔티티에 추가하는 사용자 지정 필드뿐만 아니라 과 상호 작용합니다.

**리드**

<table> 
 <tbody> 
  <tr> 
   <th><p>스키마 이름</p></th> 
   <th><p>표준/사용자 지정</p></th> 
   <th><p>읽기</p></th> 
   <th><p>쓰기</p></th> 
  </tr> 
  <tr> 
   <td><p>리드</p></td> 
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
   <td><p>statecode</p></td> 
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
   <td><p>수정 사항</p></td> 
   <td><p>표준</p></td> 
   <td><p>x</p></td> 
   <td> </td> 
  </tr> 
  <tr> 
   <td><p>컨텍스트</p></td> 
   <td><p>표준</p></td> 
   <td><p>x</p></td> 
   <td> </td> 
  </tr> 
  <tr> 
   <td><p>자격 증명 기회id</p></td> 
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
   <th><p>표준/사용자 지정</p></th> 
   <th><p>읽기</p></th> 
   <th><p>쓰기</p></th> 
  </tr> 
  <tr> 
   <td><p>컨텍스트</p></td> 
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
   <td><p>수정 사항</p></td> 
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
   <th><p>표준/사용자 지정</p></th> 
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
   <td><p>수정 사항</p></td> 
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

**기회**

<table> 
 <tbody> 
  <tr> 
   <th><p>스키마 이름</p></th> 
   <th><p>표준/사용자 지정</p></th> 
   <th><p>읽기</p></th> 
   <th><p>쓰기</p></th> 
  </tr> 
  <tr> 
   <td><p>visitor id</p></td> 
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
   <td><p>수정 사항</p></td> 
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
   <td><p>견적:종료 날짜</p></td> 
   <td><p>표준</p></td> 
   <td><p>x</p></td> 
   <td> </td> 
  </tr> 
  <tr> 
   <td><p>액츄에이트 값</p></td> 
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
   <th><p>표준/사용자 지정</p></th> 
   <th><p>읽기</p></th> 
   <th><p>쓰기</p></th> 
  </tr> 
  <tr> 
   <td><p>campaign id</p></td> 
   <td><p>표준</p></td> 
   <td><p>x</p></td> 
   <td> </td> 
  </tr> 
  <tr> 
   <td><p>유형 코드</p></td> 
   <td><p>표준</p></td> 
   <td><p>x</p></td> 
   <td> </td> 
  </tr> 
  <tr> 
   <td><p>typencodename</p></td> 
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
   <td><p>수정 사항</p></td> 
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
   <th><p>표준/사용자 지정</p></th> 
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
   <td><p>activitytypename</p></td> 
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
   <td><p>수정 사항</p></td> 
   <td><p>표준</p></td> 
   <td><p>x</p></td> 
   <td> </td> 
  </tr> 
  <tr> 
   <td><p>responsecode</p></td> 
   <td><p>표준</p></td> 
   <td><p>x</p></td> 
   <td> </td> 
  </tr> 
  <tr> 
   <td><p>responsecodename</p></td> 
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
   <td><p>관련 정보</p></td> 
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
   <th><p>표준/사용자 지정</p></th> 
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
   <td><p>수정 사항</p></td> 
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
   <th><p>표준/사용자 지정</p></th> 
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
   <td><p>listmember id</p></td> 
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
   <td><p>수정 사항</p></td> 
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
   <th><p>표준/사용자 지정</p></th> 
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
   <td><p>activitytypename</p></td> 
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
   <td><p>수정 사항</p></td> 
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
   <td><p>관련 정보</p></td> 
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
