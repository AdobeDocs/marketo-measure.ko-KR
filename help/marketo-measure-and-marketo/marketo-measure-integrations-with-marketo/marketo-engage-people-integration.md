---
unique-page-id: 37356395
description: "[!DNL Marketo Engage] 사용자 통합 - [!DNL Marketo Measure] - 제품 설명서"
title: "[!DNL Marketo Engage] 사용자 통합"
exl-id: 51930e84-4ff8-4e35-9d44-ea017c24b051
feature: Integration
source-git-commit: 8ac315e7c4110d14811e77ef0586bd663ea1f8ab
workflow-type: tm+mt
source-wordcount: '878'
ht-degree: 0%

---

# [!DNL Marketo Engage] 사용자 통합 {#marketo-engage-people-integration}

Marketo 사용자 통합을 통해 [!DNL Marketo Measure] Marketo에서 사람들을 다운로드하기 시작하고 추적된 세션을 개인에게 연결하고 터치포인트를 참여에 매핑합니다. 지금까지, [!DNL Marketo Measure] 은 CRM의 개인에게만 터치포인트를 매핑할 수 있으므로 마케터가 스테이지를 기다리거나 트리거하여 CRM에 동기화하지 않고 마케팅 노력을 더 빨리 측정하는 데 도움이 됩니다.

## 요구 사항 {#requirements}

* 프로덕션 Marketo 인스턴스
* 프로덕션 [!DNL Salesforce] 또는 [!DNL Microsoft Dynamics] 인스턴스
* 유료 항목 [!DNL Marketo Measure] 구독
* SOLR이 활성화되었습니다( 다음 대상에게 문의하십시오.) [Marketo 지원](https://nation.marketo.com/t5/Support/ct-p/Support) 활성화하려면)

## 작동 방법 {#how-it-works}

현재 고객으로서, [!DNL Marketo Measure] 은(는) 이미 CRM에서 사람을 다운로드하고 있습니다. 표준 프로세스는 다음과 같습니다 [!DNL Marketo Measure] 는 사용자를 다운로드하고 이메일 주소를 bizible.js를 통해 추적한 웹 세션에 매핑합니다.

Marketo 사람 다운로드의 도입으로 [!DNL Marketo Measure] 이제 CRM과 동기화되지 않은 더 큰 개인 풀에 웹 세션을 매핑할 수 있습니다. 일반적으로 이러한 현상은 사람들이 CRM으로 푸시되기 전에 특정 상태에 도달할 때까지 대기하는 내부 프로세스 때문에 발생합니다.

날짜 [!DNL Marketo Measure] Marketo 사용자를 웹 세션에 성공적으로 매핑하면 처리에서 궁극적으로 보고 가능한 관련 터치포인트가 생성됩니다. [!DNL Marketo Measure Discover]. 해당 Marketo 사용자가 CRM에 푸시되면 [!DNL Marketo Measure] 은 중복 시나리오를 처리하고 CRM 사용자에 대한 터치포인트를 다시 만들고 초기 세트를 &quot;복제&quot;로 표시합니다.

이러한 중복을 탐지하려면 다음을 확인하십시오 [!DNL Marketo-Salesforce] 또는 [!DNL Marketo-Dynamics] Marketo 사용자에 대한 잠재 고객 및 연락처 ID를 동기화하는 중입니다. ID가 제대로 동기화되지 않으면 다음과 같이 개인 레코드에서 CRM ID를 볼 수 있습니다.

![](assets/5a.png)

![](assets/5b.png)

고객은 전체 Marketo 사용자 및 CRM 사용자 세트를 [!DNL Marketo Measure] 발견. CRM 직원만 보고하려면 세그먼트를 만들어 필터링하는 것이 좋습니다.

## [!DNL Marketo Measure Discover] {#marketo-measure-discover}

에서 리드(사람)에 대해 보고할 때 [!DNL Marketo Measure Discover], 총 Marketo 및 CRM 잠재 고객 수가 표시됩니다. Marketo 직원만 보고하거나 CRM 리드만 보고하려면 소스에 대한 세그먼트 범주를 만든 다음 &quot;소스 시스템&quot; 필드를 사용하여 Marketo 및 CRM에 대한 세그먼트 규칙을 만들어 규칙을 정의합니다. 세그먼트가 만들어지면에서 필터링할 수 있는 소스 카테고리가 표시됩니다. [!DNL Marketo Measure Discover] 대시보드.

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

*Marketo 회사 엔티티의 필드가 개인의 updatedAt 값에 영향을 주지 않는 알려진 비헤이비어 문제가 있으므로 웹 사이트 또는 회사와 같은 관련 필드가 업데이트될 경우 [!DNL Marketo Measure] updatedAt date/time 값이 업데이트되지 않으므로 해당 값이 수정되는지 알 수 없습니다. 이는 잠재 고객에 대한 계정을 해결할 새로운 데이터가 없는 ABM 기능에 영향을 줍니다. 현재로서는 해결 방법이 없지만, 향후 이를 해결할 계획이 있다.

## FAQ {#faq}

**내 CRM과 의 리드 카운트가 다른 이유 [!DNL Marketo Measure Discover]?**

이 통합을 통해 Marketo에서 직접 가져온 리드에 대한 터치포인트를 만들 수 있으므로, CRM에 동기화되지 않은 리드가 있을 수 있으므로 터치포인트가 CRM 리드에 대해서만 푸시되므로 Discover 내의 카운트는 CRM보다 높을 수 있습니다.

**이렇게 하면 데이터가 어떻게 대체됩니까?**

이 통합은 현재 내의 데이터 세트를 실제로 병합합니다 [!DNL Marketo Measure] 인스턴스를 사용하므로 아무것도 교체되지 않습니다. 현재 CRM 잠재 고객에게서 기대하는 것은 2년 분량의 Marketo 잠재 고객을 다운로드할 때 Marketo 잠재 고객과도 일치했음을 나타내기 위해 해당 잠재 고객 레코드를 업데이트한다는 것입니다. 모든 작업은 백엔드에서 이루어지며 터치포인트는 동일하게 유지되어야 합니다. 또한 자격이 되는 Marketo 리드로 인해 더 많은 터치포인트를 볼 수 있을 것으로 예상됩니다. 해당 Marketo 사용자와 일치하는 웹 세션을 찾을 수 있는 경우, 카운트된 터치포인트를 볼 수 있습니다. [!DNL Marketo Measure].

**Marketo에서 내 직원만 다운로드하고 CRM 연결을 끊을 수 있습니까?**

지금은 아닙니다. 향후 이 옵션이 제공될 예정이지만 Marketo에서 프로그램, 기회 및 거래를 다음으로 연결할 수 있도록 이 Marketo 통합의 다른 단계를 빌드해야 합니다. [!DNL Marketo Measure].

**내 Marketo 사람들을 모두 가져오시겠습니까?**

현재, 가장 빠른 시일 내에 사람을 가져올 수 있는 시간은 2018년 1월 1일이며, 따라서 최소 2년의 데이터가 확보되며, 이는 CRM 다운로드에서 적용하는 동작과 동일합니다. Marketo 연결이 설정되면 롤링 2년 기간을 다운로드하도록 개선된 비헤이비어를 구현합니다.

또한 사람 유형에 대해 필터링하지 않으므로 2년 기간 내에 있는 모든 사람은 가져오기되며 터치포인트에 적용됩니다.

**SOLR이란 무엇이며 이 기능을 사용하기 위해 SOLR을 활성화해야 하는 이유는 무엇입니까?**

Marketo 인스턴스에 대해 SOLR을 활성화하는 것은 구독이 를 활용할 수 있도록 Marketo에서 하드웨어 공간을 여는 간단한 단계입니다. [!DNL Marketo Measure] 통합. SOLR을 활성화하지 않으면 Marketo 인스턴스에서 적절한 사용자를 다운로드할 수 있는 특정 호출에 액세스할 수 없습니다.
