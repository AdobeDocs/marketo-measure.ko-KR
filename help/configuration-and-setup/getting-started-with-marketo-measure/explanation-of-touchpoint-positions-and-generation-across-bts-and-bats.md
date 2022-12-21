---
description: BT와 BAT에서 터치 포인트 위치 및 생성 설명 - [!DNL Marketo Measure] - 제품 설명서
title: BT에 대한 접점 위치 및 생성 설명 [!DNL BATs]
exl-id: 4903f917-a366-4767-a126-5216d2377399
source-git-commit: b910e5aedb9e178058f7af9a6907a1039458ce7a
workflow-type: tm+mt
source-wordcount: '749'
ht-degree: 0%

---

# BT에 대한 접점 위치 및 생성 설명 [!DNL BATs] {#explanation-of-touchpoint-positions-and-generation-across-bts-and-bats}

**구매자 여정을 통한 터치포인트 위치 및 흐름 생성**

구매자 터치포인트 위치와 터치포인트 위치가 트리거되는 방식을 이해하는 것은 을 사용하여 성공적으로 보고하는 데 중요합니다 [!DNL Marketo Measure] 데이터. 구매자의 여정을 통해 이동할 때 잠재 고객이 수행한 작업과 터치포인트 데이터에서 어떤 모습인지에 대한 명확한 이해를 얻을 수 있습니다. 이 항목에 대한 자세한 내용을 보려면 [[!UICONTROL Touchpoint Generation & Mapping]](/help/configuration-and-setup/getting-started-with-marketo-measure/touchpoint-generation-and-mapping.md) 문서.

[!DNL Marketo Measure] 는 구매자의 여정에서 다양한 단계에 의해 트리거되는 다양한 터치 포인트 위치를 갖습니다. 보고 시 [!DNL Marketo Measure] 데이터에는 터치포인트 데이터, 구매자 터치포인트(BT) 및 구매자 기여도 분석 터치포인트(BAT) 세트가 있습니다. 이러한 데이터 집합은 서로 다른 객체와 관련될 때 위치가 약간 다릅니다. 이 항목에 대한 자세한 내용을 보려면 [구매자 터치포인트(BT) 및 구매자 기여도 분석 터치포인트(BAT) 간의 차이](/help/configuration-and-setup/getting-started-with-marketo-measure/difference-between-buyer-touchpoints-and-buyer-attribution-touchpoints.md) 문서.

**구매자 터치포인트(BT)**: 이것은 개별 개인 및 해당 여정에 연결된 터치포인트이며 해당 개인에게 고유합니다. 즉시 제공되는 보고서에서는 Buyer Touchpoint 데이터가 작성됩니다.

* [!DNL Marketo Measure] 101: Id별 리드
* [!DNL Marketo Measure] 101: 채널별 리드
* [!DNL Marketo Measure] 101: ID별 리드/연락처
* [!DNL Marketo Measure] 101: 채널별 리드/연락처

다음은 개인이 여정에서 어디에 있는지, 어떤 조치를 취했는지를 설명하는 구매자 터치포인트 포지션에 대한 개요입니다.

<table> 
 <tbody>
  <tr>
   <th>구매자 터치 포인트(BT) 위치</th> 
   <th>터치포인트 유형(터치포인트를 트리거할 수 있는 작업)</th> 
   <th>터치 포인트에 대한 설명</th> 
  </tr>
  <tr>
   <td>첫 번째 터치(FT)</td> 
   <td>웹 방문</td> 
   <td>개인이 브랜드와 함께 갖는 가장 첫 번째 마케팅 상호 작용</td> 
  </tr>
  <tr>
   <td>리드 생성(LC)</td> 
   <td>양식 채우기 <strong>또는</strong> 캠페인/프로그램 포함</td> 
   <td>개인이 갖는 첫 번째 양식 채우기에 대한 것입니다(일반적으로 양식 제출이지만 캠페인/프로그램 포함일 수도 있음)</td> 
  </tr>
  <tr>
   <td>LC 게시</td> 
   <td>양식 채우기 <strong>또는</strong> 캠페인/프로그램 포함</td> 
   <td>LC(또는 후속 캠페인/프로그램 포함) 후에 개별 양식을 작성합니다</td> 
  </tr>
 </tbody>
</table>

**구매자 속성 터치포인트(BAT)**: Opportunity 및 Opportunity 여정 와 관련된 터치포인트입니다. 이러한 터치포인트는 Opportunity 및 Contact 와 연결되므로 매출과 연결됩니다. 즉시 사용 가능한 보고서는 Buyer Attribution Touchpoint 데이터로 작성됩니다.

* [!DNL Marketo Measure] 101: ID별 기회
* [!DNL Marketo Measure] 101: ID 채널별 기회

<table> 
 <tbody>
  <tr>
   <th>구매자 속성 터치포인트(BAT) 위치</th> 
   <th>터치포인트 유형(터치포인트를 트리거할 수 있는 작업)</th> 
   <th>터치 포인트에 대한 설명</th> 
  </tr>
  <tr>
   <td>첫 번째 터치(FT)</td> 
   <td>웹 방문</td> 
   <td>연락처가 브랜드와 가졌던 첫 번째 마케팅 상호 작용</td> 
  </tr>
  <tr>
   <td>리드 생성(LC)</td> 
   <td>양식 채우기 <strong>또는</strong> 캠페인/프로그램 포함</td> 
   <td>연락처가 보유한 첫 번째 양식(일반적으로 양식 제출이지만 캠페인/프로그램 포함일 수도 있음)입니다</td> 
  </tr>
  <tr>
   <td>기회 생성</td> 
   <td>양식 채우기 <strong>또는</strong> 웹 방문 <strong>또는</strong> 캠페인/프로그램 포함</td> 
   <td>Opp 생성 시 가장 가까운 마케팅 상호 작용</td> 
  </tr> 
  <tr>
   <td>마감 원/분실</td> 
   <td>양식 채우기 <strong>또는</strong> 웹 방문 <strong>또는</strong> 캠페인/프로그램 포함</td> 
   <td>Opp가 닫힐 때(원 또는 분실)에 가장 가까운 마케팅 상호 작용</td> 
  </tr>
  <tr>
   <td>중간 터치</td> 
   <td>양식 채우기 <strong>또는</strong> 캠페인/프로그램 포함</td> 
   <td>연락처가 온라인 양식을 작성하고 마일스톤 터치 포인트와 일치하지 않는 경우</td> 
  </tr>
 </tbody>
</table>

[!DNL Marketo Measure] 는 Opportunity 뿐만 아니라 개인의 여정에 대한 명확한 이해를 만들기 위해 이 두 개의 Touchpoint 데이터 세트를 포함합니다. 이 두 터치 포인트 데이터 세트는 단계 맨 위에서 단계 맨 아래로 발생한 사항에 대한 명확한 맵을 제공합니다.

다음 예는 구매자 터치포인트(BT)에서 구매자 속성 터치포인트(BAT)로의 데이터 흐름을 보여줍니다. 이 예에서 개인 A와 개인 B는 모두 생성 일자가 3/7/2020이고 마감 일자가 5/6/2020 동일한 기회의입니다.

**개인 A** 구매자 터치포인트 데이터 세트

* 첫 번째 터치(FT) - 유료 Search.AdWords - 9/1/2019
* 리드 생성(LC) - 유기 검색.Google - 11/20/2019
* 게시물 LC(양식 채우기) - 웨비나 - 3/4/2020

**개인 B** 구매자 터치포인트 데이터 세트

* 첫 번째 터치(FT) - 유료 Social.Facebook - 8/26/2019
* 리드 생성(LC) - 유기 검색.Yahoo - 2/20/2020
* 게시물 LC(양식 채우기) - 이메일 - 5/1/2020

**기회** 구매자 속성 터치포인트 데이터는 다음과 같이 읽습니다...

* 첫 번째 터치(FT) - 유료 Social.Facebook - 8/26/2019
   * (부터) **개인 B** 왜냐하면 그들은 진실하고 _첫 번째 터치_ ( 계정/Opp)
* 리드 생성(LC) - 유기 검색.Google - 11/20/2019
   * (부터) **개인 A** 왜냐하면 그들은 진실하고 _리드 만들기_ ( 계정/Opp)
* 영업 기회 생성(OC) - 웨비나 - 3/4/2020
   * (LC 터치포인트 게시 위치 **개인 A** 이 경우 _OC 터치포인트_ Opportunity에 대한 가장 최근 상호 작용이 3/7/2020)
* 마감 원 - 이메일 - 5/1/2020
   * (LC 터치포인트 게시 위치 **개인 B** 이 경우 _마감 원화 터치포인트_ Opportunity가 5/6/2020에 종료되는 가장 최근의 상호 작용이므로)
