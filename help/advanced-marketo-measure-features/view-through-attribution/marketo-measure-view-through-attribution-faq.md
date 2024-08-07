---
unique-page-id: 18874652
description: "[!DNL Marketo Measure] 속성 FAQ를 통한 보기 - [!DNL Marketo Measure]"
title: "[!DNL Marketo Measure] 속성 FAQ를 통해 보기"
exl-id: d20e88f3-3ff8-4381-a4b8-6862798caa74
feature: Attribution
source-git-commit: 48962b999fdd16fe96d18708ec301e64a39bc76e
workflow-type: tm+mt
source-wordcount: '486'
ht-degree: 1%

---

# [!DNL Marketo Measure] 속성 FAQ를 통해 보기 {#marketo-measure-view-through-attribution-faq}

## 속성을 통한 보기란 무엇입니까? {#what-is-view-through-attribution}

[!DNL Marketo Measure] [!UICONTROL View Through Attribution] 기능에 속성 모델에 광고 노출 횟수를 포함하는 기능이 포함되어 있습니다.

>[!IMPORTANT]
>
>개인 정보 보호 문제로 인해 서드파티 쿠키가 출시되고 있습니다. Google Chrome이 발표한 2024년 3분기 타사 쿠키의 사용 중단을 통해 이러한 형식의 추적이 종료되었음을 효과적으로 알 수 있습니다. 그 결과 Adobe은 타사 쿠키에 의존하는 Marketo Measure 기능을 더 이상 사용하지 않습니다. 특히, Google/DoubleClick 노출 쿠키를 사용하는 도메인 간 추적 및 뷰스루 속성. Marketo Measure의 다른 기능은 영향을 받지 않습니다. 자사 쿠키 사용도 영향을 받지 않습니다. Google의 일정에 비추어 볼 때 위의 두 기능에 대한 예상 사용 중단 날짜는 2024년 6월 1일입니다. 이 날짜 이전에 수집된 관련 데이터는 Adobe 고객이 계속 사용할 수 있습니다.

## [!UICONTROL View Through Attribution]이(가) 중요한 이유 {#why-is-view-through-attribution-important}

지금까지 리타겟팅 또는 노출 광고는 마케터가 속성 분석에서 고려하기 어려웠습니다. 잠재 고객은 시간이 지날수록 타겟팅 다시 광고에 노출될 수 있지만, 실제로 이러한 광고 중 하나를 클릭하고 동일한 세션 내에서 양식을 작성할 가능성은 거의 없습니다. 이제 기여도 분석을 통한 보기 솔루션에는 누군가 노출 광고에 노출되었는지 여부를 추적할 수 있는 기능이 있습니다. 이 접점은 개별 기록에 추가되며 잠재 고객이 고객이 될 때까지 계속 진행됩니다. 이러한 정보를 통해 마케터는 이제 리타겟팅 광고의 성능에 대한 더 나은 통찰력을 얻을 수 있습니다.

## 이를 설정하는 데 관련된 사항은 무엇입니까? {#what-is-involved-in-setting-this-up}

[!DNL Marketo Measure]에서 광고 노출 횟수를 측정하려면 Doubleclick Campaign Manager에 표시해야 하는 노출 태그가 있습니다. 태그가 구현되면 노출 수가 로그에 저장되고 나머지는 우리가 처리합니다. 속성을 통해 보기를 측정하려면 Success Manager에게 문의하십시오.

## 지원되는 광고 플랫폼은 무엇입니까? {#which-ad-platforms-are-supported}

현재 [!DNL Doubleclick] 캠페인 관리자를 지원합니다.

## 속성은 어떻게 계산됩니까? {#how-is-the-attribution-calculated}

노출 데이터와 모든 단계 및 마케팅 채널에서 전환에 미치는 영향에 대한 몇 가지 주의 깊은 분석을 실행했습니다. 분포는 아래 표에서 볼 수 있듯이 모델에 따라 달라집니다.

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
   <th>잠재 고객 생성</th> 
   <th>U자형</th> 
   <th>W자형</th> 
   <th>전체 경로</th> 
   <th>사용자 지정 모델</th> 
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
   <td><strong>종료됨</strong></td> 
   <td>0%</td> 
   <td>0%</td> 
   <td>0%</td> 
   <td>0%</td> 
   <td>20%</td> 
   <td>맞춤형</td> 
  </tr> 
  <tr> 
   <td><strong>가운데</strong></td> 
   <td>0%</td> 
   <td>0%</td> 
   <td>20%</td> 
   <td>10%</td> 
   <td>10%</td> 
   <td>맞춤형</td> 
  </tr> 
 </tbody> 
</table>

## [!DNL Salesforce?]에서 표시 형식 {#what-will-this-look-like-in-salesforce}

[!DNL Marketo Measure]은(는) 디스플레이 광고에 노출된 모든 리드에 단일 노출 터치포인트를 만듭니다. 사용자가 웹 사이트(FT)에 처음 와서 양식(LC)을 작성한 후에도 사용자를 매핑할 수 있습니다. 터치 포인트에는 광고 캠페인 이름/ID, 광고 ID, 광고 컨텐츠, 사이트 이름/ID, 배치 이름/ID, 마케팅 채널, 지역, 레퍼러 페이지 등의 광고 정보가 포함됩니다.

뷰스루 속성 모델은 클라이언트와 데이터에 따라 다릅니다.
