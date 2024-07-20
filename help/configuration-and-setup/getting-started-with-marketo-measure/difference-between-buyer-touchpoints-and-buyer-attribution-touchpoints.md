---
unique-page-id: 18874646
description: 구매자 접점 및 구매자 속성 접점 간의 차이 - [!DNL Marketo Measure]
title: 구매자 접점 및 구매자 속성 접점 간의 차이
exl-id: 19109271-7b59-44c0-b1ff-e3b0bba9f5ce
feature: Touchpoints
source-git-commit: 915e9c5a968ffd9de713b4308cadb91768613fc5
workflow-type: tm+mt
source-wordcount: '392'
ht-degree: 0%

---

# 구매자 접점 및 구매자 속성 접점 간의 차이 {#difference-between-buyer-touchpoints-and-buyer-attribution-touchpoints}

Buyer Touchpoint(BT) 및 Buyer Attribution Touchpoint(BAT)를 정의하는 내용, 둘 간의 차이점 및 자주 묻는 질문에 대한 답변을 알아봅니다.

구매자 터치포인트와 구매자 속성 터치포인트를 구분하는 중요한 요소는 [!DNL Salesforce] 오브젝트와의 관계입니다. BT은 Lead, Contact 및 Case 객체에 관련되지만 Opportunity 객체에는 관련되지 않습니다. 즉, 구매자 터치포인트와 관련된 매출이 없습니다.

Buyer Attribution Touchpoint 오브젝트는 연락처, 계정 및 기회 오브젝트와 관련되지만 리드 오브젝트는 관련되지 않습니다. 구매자 속성 터치포인트는 리드에 연결되지 않습니다. BAT 개체는 특정 마케팅 상호 작용과 관련된 매출을 보게 됩니다.

BT과 BAT의 차이점:

<table> 
 <colgroup> 
  <col> 
  <col> 
 </colgroup> 
 <tbody> 
  <tr> 
   <td>Buyer Touchpoint (BT)</td> 
   <td>Buyer Attribution Touchpoint (BAT)</td> 
  </tr> 
  <tr> 
   <td> 
    <ul> 
     <li>잠재 고객, 연락처 및 케이스 오브젝트와 관련이 있습니다.</li> 
     <li>Opportunity Object 와 관련 없음</li> 
     <li>매출이 Buyer Touchpoint에 연결되지 않음</li> 
    </ul></td> 
   <td> 
    <ul> 
     <li>연락처, 계정 및 영업 기회 개체와 관련이 있습니다</li> 
     <li>리드 오브젝트와 관련이 없음</li> 
     <li>Buyer Attribution Touchpoint은 Opportunity에 연결되어 있으므로 모든 BAT에 연결된 수익이 있습니다.</li> 
    </ul></td> 
  </tr> 
 </tbody> 
</table>

## FAQ {#faq}

**Buyer Touchpoint이 Buyer Attribution Touchpoint이 되는 경우는 언제입니까?**

이 BT가 관련 Opportunity 가 있는 Contact에 연결되면 BAT BT 가 됩니다. 이해해야 할 한 가지 중요한 것은 하나의 구체적인 마케팅 상호 작용이 BT과 BAT일 수 있다는 것이다.

**Buyer Touchpoint에 OC(영업 기회 창출)의 터치포인트 위치가 있을 수 있습니까?**

Buyer Touchpoint에는 첫 번째 터치(FT), 리드 만들기(LC) 또는 양식 제출(중간 터치포인트)의 터치포인트 위치만 있습니다. BT은 Opportunities와 관련이 없으므로 BT에 Opportunity Creation 또는 Closed 터치포인트 Position을 지정할 수 없습니다.

**Buyer Touchpoint 데이터는 어떻게 사용됩니까?**

일반적으로 고객은 Buyer Touchpoint 데이터를 사용하여 단계 상단 및 단계 중간 참여를 이해합니다. 즉, [!DNL Marketo Measure]명의 사용자가 양식을 제출하는 사용자, 사이트를 보는 사용자, 성과가 좋은 블로그 게시물, 전환으로 이어지는 AdWords 광고 등을 알고 있습니다. Buyer Touchpoint 데이터는 리드 및 연락처의 참여를 이해하는 데 유용합니다.

**Salesforce에서 Buyer Touchpoint은 어떻게 생겼습니까?**

다음은 [!DNL Salesforce]의 BT 스크린샷입니다.

![](assets/1.png)

**Salesforce에서 Buyer Attribution Touchpoint은 어떻게 생겼습니까?**

다음은 [!DNL Salesforce]의 BAT 스크린샷입니다.

![](assets/2.png)
