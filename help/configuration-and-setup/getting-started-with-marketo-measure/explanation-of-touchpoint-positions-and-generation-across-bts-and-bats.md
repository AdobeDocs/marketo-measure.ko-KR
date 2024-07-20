---
description: BT 및 BAT 간 접점 위치 및 생성에 대한 설명 - [!DNL Marketo Measure]
title: BT 및  [!DNL BATs]의 접점 위치 및 생성에 대한 설명
exl-id: 4903f917-a366-4767-a126-5216d2377399
feature: Touchpoints
source-git-commit: cd5597a681f388a5b5c743dadd38bf3127811bff
workflow-type: tm+mt
source-wordcount: '761'
ht-degree: 0%

---

# BT 및 [!DNL BATs]의 접점 위치 및 생성에 대한 설명 {#explanation-of-touchpoint-positions-and-generation-across-bts-and-bats}

**구매자 여정을 통한 접점 위치 및 흐름 생성**

Buyer Touchpoint 위치와 이러한 위치가 트리거되는 방법을 이해하는 것은 [!DNL Marketo Measure] 데이터를 사용하여 성공적으로 보고하는 데 중요합니다. 잠재 고객이 구매자의 여정을 통해 이동했을 때 수행한 작업과 터치포인트 데이터에서 볼 수 있는 내용을 명확히 이해하려고 합니다. 이 항목에 대한 자세한 내용은 [[!UICONTROL Touchpoint Generation & Mapping]](/help/configuration-and-setup/getting-started-with-marketo-measure/touchpoint-generation-and-mapping.md) 문서를 검토하는 것이 좋습니다.

[!DNL Marketo Measure]에는 구매자 여정의 다양한 단계에 의해 트리거되는 다양한 접점 위치가 있습니다. [!DNL Marketo Measure] 데이터에 대해 보고할 때 두 세트의 터치포인트 데이터, 구매자 터치포인트(BT) 및 구매자 속성 터치포인트(BAT)가 있습니다. 이러한 데이터 집합은 서로 다른 오브젝트와 관련이 있을 때 위치가 약간 다를 수 있습니다. 이 주제에 대한 자세한 내용은 [구매자 접점(BT) 및 구매자 속성 접점(BAT) 간의 차이](/help/configuration-and-setup/getting-started-with-marketo-measure/difference-between-buyer-touchpoints-and-buyer-attribution-touchpoints.md) 문서를 검토하는 것이 좋습니다.

**구매자 접점(BT)**: 개별 사용자와 해당 여정에 연결된 접점이며 해당 개인에게 고유합니다. 다음의 기본 보고서는 Buyer Touchpoint 데이터를 기반으로 만들어집니다.

* [!DNL Marketo Measure] 101: ID별 잠재 고객
* [!DNL Marketo Measure] 101: 채널별 잠재 고객
* [!DNL Marketo Measure] 101: ID별 잠재 고객/연락처
* [!DNL Marketo Measure] 101: 채널별 리드/연락처

다음은 개인이 여정 내에서 어떤 위치에 있고 해당 위치를 얻기 위해 수행한 작업을 설명하는 Buyer Touchpoint 직책에 대해 간략히 설명합니다.

<table> 
 <tbody>
  <tr>
   <th>Buyer Touchpoint(BT) 위치</th> 
   <th>접점 유형(터치포인트를 트리거할 수 있는 작업)</th> 
   <th>접점 설명</th> 
  </tr>
  <tr>
   <td>첫 번째 터치(FT)</td> 
   <td>웹 방문</td> 
   <td>개인이 브랜드와 갖는 첫 번째 마케팅 상호 작용</td> 
  </tr>
  <tr>
   <td>리드 생성(LC)</td> 
   <td>양식 채우기 <strong>OR</strong> 캠페인/프로그램 포함</td> 
   <td>개인에게 필요한 첫 번째 양식은 (일반적으로 양식 제출이지만 캠페인/프로그램 포함일 수도 있음) 입니다</td> 
  </tr>
  <tr>
   <td>LC 이후</td> 
   <td>양식 채우기 <strong>OR</strong> 캠페인/프로그램 포함</td> 
   <td>LC(또는 후속 캠페인/프로그램 포함) 후에 개인이 완료하는 모든 양식</td> 
  </tr>
 </tbody>
</table>

**구매자 속성 접점(BAT)**: 영업 기회 및 해당 여정에 연결된 접점입니다. 이러한 접점은 Opportunity 및 해당 Contact에 연결되므로 매출에 연결됩니다. 다음의 기본 보고서는 Buyer Attribution Touchpoint 데이터를 기반으로 만들어집니다.

* [!DNL Marketo Measure] 101: ID별 기회
* [!DNL Marketo Measure] 101: ID 채널별 기회

<table> 
 <tbody>
  <tr>
   <th>Buyer Attribution Touchpoint(BAT) 위치</th> 
   <th>접점 유형(터치포인트를 트리거할 수 있는 작업)</th> 
   <th>접점 설명</th> 
  </tr>
  <tr>
   <td>첫 번째 터치(FT)</td> 
   <td>웹 방문</td> 
   <td>연락처가 브랜드와 벌인 첫 번째 마케팅 상호 작용</td> 
  </tr>
  <tr>
   <td>리드 생성(LC)</td> 
   <td>양식 채우기 <strong>OR</strong> 캠페인/프로그램 포함</td> 
   <td>연락처에 포함된 첫 번째 양식 채우기(일반적으로 양식 제출이지만 캠페인/프로그램 포함일 수도 있음)</td> 
  </tr>
  <tr>
   <td>영업 기회 생성</td> 
   <td>양식 채우기 <strong>OR</strong> 웹 방문 <strong>OR</strong> 캠페인/프로그램 포함</td> 
   <td>Opp 생성 시 가장 가까운 마케팅 상호 작용</td> 
  </tr> 
  <tr>
   <td>원화/상실 마감</td> 
   <td>양식 채우기 <strong>OR</strong> 웹 방문 <strong>OR</strong> 캠페인/프로그램 포함</td> 
   <td>Opp가 마감된 시기(성사 또는 상실)에 가장 가까운 마케팅 상호 작용</td> 
  </tr>
  <tr>
   <td>가운데 터치</td> 
   <td>양식 채우기 <strong>OR</strong> 캠페인/프로그램 포함</td> 
   <td>연락처가 온라인 양식을 작성할 때 마일스톤 터치포인트와 일치하지 않습니다</td> 
  </tr>
 </tbody>
</table>

[!DNL Marketo Measure]은(는) 개별 사용자의 여정 및 기회를 명확하게 이해하기 위해 이 두 세트의 터치포인트 데이터를 가지고 있습니다. 이 두 접점 데이터 세트는 단계 상단에서 단계 하단으로 발생한 일에 대한 명확한 맵을 제공합니다.

다음 예는 구매자 접점(BT)에서 구매자 속성 접점(BAT)으로의 데이터 흐름을 보여줍니다. 이 예에서 개인 A와 개인 B는 모두 생성된 일자가 2020년 3월 7일이고 마감 일자가 2020년 5월 6일인 동일한 영업 기회의 일부입니다.

**개인 A** Buyer Touchpoint 데이터 집합

* 첫 번째 터치(FT) - 유료 Search.AdWords - 2019년 9월 1일
* 잠재 고객 생성(LC) - Organic Search.Google - 11/20/2019
* Post LC(양식 채우기) - 웨비나 - 2020년 3월 4일

**개인 B** Buyer Touchpoint 데이터 집합

* 첫 번째 터치(FT) - 유료 Social.Facebook - 2019년 8월 26일
* 잠재 고객 생성(LC) - Organic Search.Yahoo - 2020년 2월 20일
* LC 게시(양식 채우기) - 이메일 - 2020년 5월 1일

**기회** Buyer Attribution Touchpoint 데이터는 다음과 같이 읽힙니다.

* 첫 번째 터치(FT) - 유료 Social.Facebook - 2019년 8월 26일
   * (계정/Opp에 대해 **사용자 B**&#x200B;의 실제 _첫 번째 터치_&#x200B;가 있으므로)
* 잠재 고객 생성(LC) - Organic Search.Google - 11/20/2019
   * (계정/Opp에 대한 실제 _잠재 고객 생성_&#x200B;이 있으므로 **사용자 A**&#x200B;부터)
* OC(Opportunity Creation) - 웨비나 - 2020년 3월 4일
   * (2020년 3월 7일에 만들어지는 Opportunity에 대한 가장 최근 상호 작용이었으므로 **개인 A**&#x200B;의 Post LC 터치 포인트는 _OC 터치 포인트_&#x200B;가 됩니다.)
* 마감일 - 이메일 - 2020년 5월 1일
   * (2020년 5월 6일에 마감된 Opportunity에 대한 가장 최근 상호 작용이므로 **개인 B**&#x200B;의 Post LC 터치포인트는 _마감된 완료 터치포인트_&#x200B;가 됩니다.)
