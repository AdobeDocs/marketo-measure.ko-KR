---
unique-page-id: 18874646
description: 구매자 접점 및 구매자 속성 접점 간의 차이 - [!DNL Marketo Measure] - 제품 설명서
title: 구매자 접점 및 구매자 속성 접점 간의 차이
exl-id: 19109271-7b59-44c0-b1ff-e3b0bba9f5ce
feature: Touchpoints
source-git-commit: 8ac315e7c4110d14811e77ef0586bd663ea1f8ab
workflow-type: tm+mt
source-wordcount: '392'
ht-degree: 0%

---

# 구매자 접점 및 구매자 속성 접점 간의 차이 {#difference-between-buyer-touchpoints-and-buyer-attribution-touchpoints}

구매자 접점(BT) 및 구매자 속성 접점(BAT)을 정의하는 내용, 둘 사이의 차이점을 알아보고 자주 묻는 질문에 답합니다.

구매자 터치포인트와 구매자 속성 터치포인트 간의 주요 차이점은 와의 관계입니다. [!DNL Salesforce] 개체. BT는 Lead, Contact 및 Case Object에 관련되지만 Opportunity Object에 관련되지 않습니다. 즉, 구매자 터치포인트와 관련된 매출이 절대 발생하지 않습니다.

구매자 속성 접점 객체는 연락처, 계정 및 기회 객체와 관련되지만 리드 객체는 관련되지 않습니다. 즉, 리드에 연결된 구매자 속성 터치포인트가 절대 없습니다. BAT 오브젝트는 특정 마케팅 상호 작용과 관련된 매출을 볼 수 있습니다.

BT와 BAT의 차이점:

<table> 
 <colgroup> 
  <col> 
  <col> 
 </colgroup> 
 <tbody> 
  <tr> 
   <td>구매자 접점(BT)</td> 
   <td>구매자 속성 접점(BAT)</td> 
  </tr> 
  <tr> 
   <td> 
    <ul> 
     <li>잠재 고객, 연락처 및 케이스 오브젝트와 관련이 있습니다.</li> 
     <li>Opportunity Object 와 관련 없음</li> 
     <li>매출은 구매자 접점과 연관되지 않음</li> 
    </ul></td> 
   <td> 
    <ul> 
     <li>연락처, 계정 및 영업 기회 개체와 관련이 있습니다</li> 
     <li>리드 오브젝트와 관련이 없음</li> 
     <li>구매자 속성 접점 이 Opportunity에 연결되어 있으므로 모든 BAT에 관련 매출이 있습니다.</li> 
    </ul></td> 
  </tr> 
 </tbody> 
</table>

## FAQ {#faq}

**언제 구매자 터치포인트가 구매자 속성 터치포인트가 됩니까?**

이 BT가 관련 영업 기회가 있는 연락처에 연결되면 BT는 BAT가 됩니다. 이해하는 데 매우 중요한 한 가지는 하나의 구체적인 마케팅 상호 작용이 BT와 BAT가 될 수 있다는 점이다.

**구매자 터치포인트에 기회 생성(OC)의 터치포인트 위치가 있을 수 있습니까?**

구매자 터치포인트에는 첫 번째 터치(FT), 리드 생성(LC) 또는 양식 제출(중간 터치포인트)의 터치포인트 위치만 있습니다. BT는 Opportunities와 관련이 없으므로 BT에게 Opportunity Creation 또는 Closed라는 터치포인트 Position을 부여할 수는 없습니다.

**구매자 접점 데이터는 어떻게 활용됩니까?**

일반적으로 고객은 구매자 접점 데이터를 활용하여 단계 상단 및 단계 중간 참여를 이해합니다. 의미 [!DNL Marketo Measure] 사용자는 누가 양식을 제출하고 있는지, 누가 사이트를 보고 있는지, 어떤 블로그 게시물이 좋은 성과를 내고 있는지, 어떤 AdWords 광고가 전환을 유도하는지 등을 알고 있습니다. 구매자 접점 데이터는 리드 및 연락처의 참여를 이해하는 데 유용합니다.

**Salesforce의 바이어 접점은 어떻게 생겼습니까?**

다음은 BT의 스크린샷입니다 [!DNL Salesforce]:

![](assets/1.png)

**Salesforce에서 구매자 속성 터치포인트는 어떻게 생겼습니까?**

여기 BAT 스크린샷이 있습니다. [!DNL Salesforce]:

![](assets/2.png)
