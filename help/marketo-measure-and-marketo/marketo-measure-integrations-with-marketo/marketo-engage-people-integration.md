---
unique-page-id: 37356395
description: '[!DNL Marketo Engage]명의 사용자 통합 - [!DNL Marketo Measure]'
title: '[!DNL Marketo Engage]명의 사용자 통합'
exl-id: 51930e84-4ff8-4e35-9d44-ea017c24b051
feature: Integration
source-git-commit: de366de2d1df3d4dc9fc33e5fd0dab225b6af081
workflow-type: tm+mt
source-wordcount: '868'
ht-degree: 1%

---

# [!DNL Marketo Engage]명의 사용자 통합 {#marketo-engage-people-integration}

Marketo 사용자 통합을 사용하면 [!DNL Marketo Measure]이(가) Marketo에서 사용자를 다운로드하고 추적된 세션을 개인에게 연결하고 접점을 참여에 매핑할 수 있습니다. 이전에는 [!DNL Marketo Measure]에서 터치포인트를 CRM의 사용자에게 매핑할 수만 있었지만, 이렇게 하면 마케터가 단계나 트리거를 기다리지 않고 마케팅 노력을 더 빨리 측정하여 CRM에 동기화할 수 있습니다.

## 요구 사항 {#requirements}

* 프로덕션 Marketo 인스턴스
* 프로덕션 [!DNL Salesforce] 또는 [!DNL Microsoft Dynamics] 인스턴스
* 모든 유료 [!DNL Marketo Measure] 구독
* SOLR이 활성화되었습니다(활성화하려면 [Marketo 지원](https://nation.marketo.com/t5/Support/ct-p/Support){target="_blank"}에 연결).

## 작동 방법 {#how-it-works}

현재 고객인 [!DNL Marketo Measure]이(가) 이미 CRM에서 사람을 다운로드하고 있습니다. 표준 프로세스는 [!DNL Marketo Measure]이(가) 사용자를 다운로드하고 전자 메일 주소를 bizible.js를 통해 추적한 웹 세션에 매핑하는 것입니다.

Marketo 사용자 다운로드를 도입하면서 [!DNL Marketo Measure]은(는) 이제 CRM과 동기화되지 않은 더 큰 개인 풀에 웹 세션을 매핑할 수 있습니다. 일반적으로 이러한 현상은 사람들이 CRM으로 푸시되기 전에 특정 상태에 도달할 때까지 대기하는 내부 프로세스 때문에 발생합니다.

[!DNL Marketo Measure]이(가) Marketo 사용자를 웹 세션에 성공적으로 매핑하면 처리가 관련 터치포인트를 생성하며, 이는 궁극적으로 [!DNL Marketo Measure Discover]에서 보고할 수 있습니다. 해당 Marketo 사용자가 CRM으로 푸시되면 [!DNL Marketo Measure]에서 중복 시나리오를 처리하고 CRM 사용자에 대한 터치포인트를 다시 만들고 초기 설정을 &quot;복제&quot;로 표시합니다.

이러한 중복을 탐지하려면 [!DNL Marketo-Salesforce] 또는 [!DNL Marketo-Dynamics] 동기화가 Marketo 사용자에 대한 잠재 고객 및 연락처 ID를 채우고 있는지 확인하십시오. ID가 제대로 동기화되지 않으면 다음과 같이 개인 레코드에서 CRM ID를 볼 수 있습니다.

![](assets/5a.png)

![](assets/5b.png)

고객은 [!DNL Marketo Measure] Discover 내의 전체 Marketo 사용자 및 CRM 사용자 집합을 보고할 수 있습니다. CRM 직원에만 보고하려면 세그먼트를 만들어 필터링하는 것이 좋습니다.

## [!DNL Marketo Measure Discover] {#marketo-measure-discover}

[!DNL Marketo Measure Discover]의 리드(사람)에 대해 보고할 때 총 Marketo 및 CRM 리드가 표시됩니다. Marketo 직원만 보고하거나 CRM 리드만 보고하려면 소스에 대한 세그먼트 범주를 만든 다음 &quot;Source 시스템&quot; 필드를 사용하여 Marketo 및 CRM에 대한 세그먼트 규칙을 만들어 규칙을 정의합니다. 세그먼트가 만들어지면 [!DNL Marketo Measure Discover] 대시보드에서 필터링할 수 있는 Source 범주가 표시됩니다.

![](assets/bizible-discover-1.png)

![](assets/bizible-discover-2.png)

## 필드 매핑 {#field-mappings}

<table> 
 <colgroup> 
  <col> 
  <col> 
 </colgroup> 
 <tbody> 
  <tr> 
   <th><p><strong>biz_lead</strong></p></th> 
   <th><p><strong>Marketo</strong></p></th> 
  </tr> 
  <tr> 
   <td><p>ID</p></td> 
   <td><p>ID</p></td> 
  </tr> 
  <tr> 
   <td><p>MODIFIED_DATE</p></td> 
   <td><p>updatedAt<strong>*</strong></p></td> 
  </tr> 
  <tr> 
   <td><p>CREATED_DATE</p></td> 
   <td><p>createdAt</p></td> 
  </tr> 
  <tr> 
   <td><p>이메일</p></td> 
   <td><p>이메일</p></td> 
  </tr> 
  <tr> 
   <td><p>WEB_SITE</p></td> 
   <td><p>웹 사이트</p></td> 
  </tr> 
  <tr> 
   <td><p>회사</p></td> 
   <td><p>회사</p></td> 
  </tr> 
  <tr> 
   <td><p>IS_CONVERTED</p></td> 
   <td><p>해당 사항 없음</p></td> 
  </tr> 
  <tr> 
   <td><p>ACCOUNT_ID</p></td> 
   <td><p>계정 ID(L2A)</p></td> 
  </tr> 
  <tr> 
   <td><p>BIZIBLE_STAGE</p></td> 
   <td><p>상태</p></td> 
  </tr> 
  <tr> 
   <td><p>IS_DELETED</p></td> 
   <td><p>true/false</p></td> 
  </tr> 
 </tbody> 
</table>

*Marketo 회사 엔터티의 필드가 개인의 updatedAt 값에 영향을 주지 않는 알려진 동작 문제가 있으므로 웹 사이트 또는 회사와 같은 관련 필드가 업데이트되면 updatedAt 날짜/시간 값이 업데이트되지 않으므로 [!DNL Marketo Measure]에서 해당 값이 수정되었음을 알 수 없습니다. 이는 잠재 고객에 대한 계정을 해결할 새로운 데이터가 없는 ABM 기능에 영향을 줍니다. 현재로서는 해결 방법이 없지만, 향후 이를 해결할 계획이 있다.

## FAQ {#faq}

**내 CRM과 [!DNL Marketo Measure Discover] 사이의 리드 개수가 다른 이유는 무엇입니까?**

이 통합을 통해 Marketo에서 직접 가져온 리드에 대한 터치포인트를 만들 수 있으므로, CRM에 동기화되지 않은 리드가 있을 수 있으므로 터치포인트가 CRM 리드에 대해서만 푸시되므로 Discover 내의 카운트는 CRM보다 높을 수 있습니다.

**이 작업으로 인해 내 데이터가 어떻게 대체됩니까?**

이 통합은 현재 [!DNL Marketo Measure] 인스턴스 내의 데이터 집합을 실제로 병합하므로 아무것도 대체되지 않습니다. 현재 CRM 잠재 고객에게서 기대하는 것은 2년 분량의 Marketo 잠재 고객을 다운로드할 때 Marketo 잠재 고객과도 일치했음을 나타내기 위해 해당 잠재 고객 레코드를 업데이트한다는 것입니다. 모든 작업은 백엔드에서 이루어지며 터치포인트는 동일하게 유지되어야 합니다. 또한 자격이 되는 Marketo 리드로 인해 더 많은 터치포인트를 볼 수 있을 것으로 예상됩니다. 해당 Marketo 사용자와 일치하는 웹 세션을 찾을 수 있는 경우 [!DNL Marketo Measure]에서 터치포인트를 계산합니다.

**내 직원만 Marketo에서 다운로드하고 CRM 연결을 끊을 수 있습니까?**

지금은 아닙니다. 이 옵션은 나중에 사용할 수 있지만 프로그램, 영업 기회 및 거래를 Marketo에서 [!DNL Marketo Measure]에 연결할 수 있도록 이 Marketo 통합의 다른 단계를 빌드해야 합니다.

**내 Marketo 직원을 모두 가져오시겠습니까?**

현재, 가장 빠른 시일 내에 사람을 가져올 수 있는 시간은 2018년 1월 1일이며, 따라서 최소 2년의 데이터가 확보되며, 이는 CRM 다운로드에서 적용하는 동작과 동일합니다. Marketo 연결이 설정되면 롤링 2년 기간을 다운로드하도록 개선된 비헤이비어를 구현합니다.

또한 사람 유형에 대해 필터링하지 않으므로 2년 기간 내에 있는 모든 사람은 가져오기되며 터치포인트에 적용됩니다.

**SOLR이란 무엇이며 이 기능을 사용하려면 SOLR을 활성화해야 하는 이유는 무엇입니까?**

Marketo 인스턴스에 대해 SOLR을 사용하도록 설정하는 것은 구독이 [!DNL Marketo Measure] 통합을 활용할 수 있도록 Marketo에서 하드웨어 공간을 여는 간단한 단계입니다. SOLR을 활성화하지 않으면 Marketo 인스턴스에서 적절한 사용자를 다운로드할 수 있는 특정 호출에 액세스할 수 없습니다.
