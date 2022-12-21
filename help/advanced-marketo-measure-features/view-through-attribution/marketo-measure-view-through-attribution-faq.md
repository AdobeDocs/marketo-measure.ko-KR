---
unique-page-id: 18874652
description: "[!DNL Marketo Measure] 기여도 분석을 통해 보기 FAQ - [!DNL Marketo Measure] - 제품 설명서"
title: "[!DNL Marketo Measure] 기여도 분석 FAQ 보기"
exl-id: d20e88f3-3ff8-4381-a4b8-6862798caa74
source-git-commit: b59c79236d3e324e8c8b07c5a6d68bd8176fc8a9
workflow-type: tm+mt
source-wordcount: '397'
ht-degree: 9%

---

# [!DNL Marketo Measure] 기여도 분석을 통해 보기 FAQ {#marketo-measure-view-through-attribution-faq}

## 속성을 통한 보기란 무엇입니까? {#what-is-view-through-attribution}

다음 [!DNL Marketo Measure] 뷰스루 속성 기능에는 속성 모델에 광고 노출 횟수를 포함하는 기능이 포함되어 있습니다.

## 속성을 통한 보기가 중요한 이유는 무엇입니까? {#why-is-view-through-attribution-important}

이전에는 마케터가 속성 분석에서 을 고려하기가 어려웠던 재타깃팅 또는 노출 광고입니다. 잠재적 클라이언트는 시간이 지남에 따라 광고를 다시 타겟팅하는 데 노출될 수 있지만 실제로 이러한 광고 중 하나를 클릭하고 동일한 세션 내에 양식을 작성하는 것은 거의 없습니다. 이제 View Through Attribution 솔루션을 통해 누군가 노출 광고에 노출되었는지 여부를 추적할 수 있습니다. 이 터치포인트는 개별 레코드에 추가되며 잠재 고객이 될 때까지 전달됩니다. 이러한 정보를 통해 마케터는 이제 재타깃팅 광고의 성능에 대한 통찰력을 향상시킬 수 있습니다.

## 이 설정과 관련된 것은 무엇입니까? {#what-is-involved-in-setting-this-up}

대상 [!DNL Marketo Measure] 광고 노출 횟수 측정을 시작하려면 Doubleclick Campaign Manager에 배치해야 하는 노출 태그가 있습니다. 태그가 구현되면 노출 수가 로그에 저장되고 나머지 항목은 처리합니다. 속성을 통해 보기를 측정하는 데 관심이 있는 경우 성공 관리자에게 문의하십시오.

## 어떤 광고 플랫폼이 지원됩니까? {#which-ad-platforms-are-supported}

현재 Doubleclick Campaign Manager를 지원합니다.

## 속성은 어떻게 계산됩니까? {#how-is-the-attribution-calculated}

모든 단계 및 마케팅 채널에서 노출 데이터와 해당 데이터가 전환에 미치는 영향에 대한 몇 가지 신중하게 분석했습니다. 배포는 아래 표에서 볼 수 있는 모델에 따라 달라집니다.

<table> 
 <colgroup> 
  <col> 
  <col> 
  <col> 
  <col> 
  <col> 
  <col> 
  <col> 
 </colgroup> 
 <tbody> 
  <tr> 
   <th><br></th> 
   <th>첫 번째 터치</th> 
   <th>리드 만들기</th> 
   <th>U자형</th> 
   <th>W자형</th> 
   <th>전체 경로</th> 
   <th>사용자 정의 모델</th> 
  </tr> 
  <tr> 
   <td><strong>노출 횟수</strong></td> 
   <td>0%</td> 
   <td>0%</td> 
   <td>10%</td> 
   <td>10%</td> 
   <td>10%</td> 
   <td>맞춤형</td> 
  </tr> 
  <tr> 
   <td><strong>FT</strong></td> 
   <td>100%</td> 
   <td>0%</td> 
   <td>35%</td> 
   <td>26.6%</td> 
   <td>20%</td> 
   <td>맞춤형</td> 
  </tr> 
  <tr> 
   <td><strong>LC</strong></td> 
   <td>0%</td> 
   <td>100%</td> 
   <td>35%</td> 
   <td>26.6%</td> 
   <td>20%</td> 
   <td>맞춤형</td> 
  </tr> 
  <tr> 
   <td><strong>OC</strong></td> 
   <td>0%</td> 
   <td>0%</td> 
   <td>0%</td> 
   <td>26.6%</td> 
   <td>20%</td> 
   <td>맞춤형</td> 
  </tr> 
  <tr> 
   <td><strong>닫힘</strong></td> 
   <td>0%</td> 
   <td>0%</td> 
   <td>0%</td> 
   <td>0%</td> 
   <td>20%</td> 
   <td>맞춤형</td> 
  </tr> 
  <tr> 
   <td><strong>중간</strong></td> 
   <td>0%</td> 
   <td>0%</td> 
   <td>20%</td> 
   <td>10%</td> 
   <td>10%</td> 
   <td>맞춤형</td> 
  </tr> 
 </tbody> 
</table>

## Salesforce에서는 어떻게 표시됩니까? {#what-will-this-look-like-in-salesforce}

[!DNL Marketo Measure] 디스플레이 광고에 노출된 모든 리드에 대해 하나의 노출 터치 포인트를 만듭니다. 사용자가 웹 사이트(FT)를 처음 방문하여 양식(LC)을 작성한 후에도 사용자를 매핑할 수 있습니다. 터치포인트에는 광고 캠페인 이름/ID, 광고 ID, 광고 컨텐츠, 사이트 이름/ID, 배치 이름/ID, 마케팅 채널, 지역, 레퍼러 페이지 등의 광고 정보가 포함됩니다.

뷰스루 속성 모델은 클라이언트와 데이터에 따라 다릅니다.
