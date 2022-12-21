---
unique-page-id: 37356395
description: "[!DNL Marketo Engage] 사용자 통합 - [!DNL Marketo Measure] - 제품 설명서"
title: "[!DNL Marketo Engage] 사용자 통합"
exl-id: 51930e84-4ff8-4e35-9d44-ea017c24b051
source-git-commit: 54337a0a65b79d80ebeae6531f5e92f4f48721a7
workflow-type: tm+mt
source-wordcount: '878'
ht-degree: 0%

---

# [!DNL Marketo Engage] 사용자 통합 {#marketo-engage-people-integration}

Marketo 사람 통합은 [!DNL Marketo Measure] Marketo에서 사용자 다운로드를 시작하고 추적한 세션을 개인에게 연결하고 터치포인트를 참여에 매핑하기 시작합니다. 역사적으로, [!DNL Marketo Measure] 는 CRM에서 사람에게 터치포인트를 매핑할 수만 있으므로 마케터가 스테이지를 기다리거나 CRM에 동기화하도록 트리거하는 대신 마케팅 활동을 더 빨리 측정할 수 있습니다.

## 요구 사항 {#requirements}

* 프로덕션 Marketo 인스턴스
* 프로덕션 [!DNL Salesforce] 또는 [!DNL Microsoft Dynamics] 인스턴스
* 모든 유료 [!DNL Marketo Measure] 구독
* SOLR이 활성화되었습니다. [Marketo 지원](https://nation.marketo.com/t5/Support/ct-p/Support) 이 기능이 활성화됨)

## 작동 방법 {#how-it-works}

현재 고객으로서 [!DNL Marketo Measure] 이(가) 이미 CRM에서 사용자를 다운로드하는 중입니다. 표준 프로세스는 다음과 같습니다 [!DNL Marketo Measure] 사용자를 다운로드하고 bizible.js를 통해 추적한 웹 세션에 이메일 주소를 매핑합니다.

Marketo 사용자 다운로드가 소개되면서, [!DNL Marketo Measure] 이제 CRM과 동기화되지 않은 대규모 개인 풀에 웹 세션을 매핑할 수 있습니다. 일반적으로 사람들이 CRM에 푸시되기 전에 특정 상태에 도달할 때까지 대기하는 내부 프로세스 때문에 이를 볼 수 있습니다.

When [!DNL Marketo Measure] Marketo 사용자를 웹 세션에 성공적으로 매핑하면 처리 시 그에 대한 모든 관련 터치포인트를 생성하며 이것은 궁극적으로 [!DNL Marketo Measure Discover]. 해당 Marketo 사람이 CRM에 푸시되면, [!DNL Marketo Measure] 은(는) 중복 시나리오를 처리하고 CRM 사용자를 위한 터치포인트를 다시 만들고 초기 세트를 &quot;복제&quot;로 표시합니다.

이러한 중복 항목을 검색하려면 [!DNL Marketo-Salesforce] 또는 [!DNL Marketo-Dynamics] 동기화가 Marketo Person에서 리드 및 연락처 ID를 채우는 중입니다. ID가 제대로 동기화된 경우 다음과 같이 개인 레코드에 CRM ID를 볼 수 있습니다.

![](assets/5a.png)

![](assets/5b.png)

고객은 의 내부에 있는 Marketo 사람 및 CRM 사람 전체 세트를 보고할 수 있습니다 [!DNL Marketo Measure] 검색. CRM 사람에 대한 보고에만 관심이 있는 경우 세그먼트를 만들어 필터링하는 것이 좋습니다.

## [!DNL Marketo Measure Discover] {#marketo-measure-discover}

의 리드(사람)에 대해 보고할 때 [!DNL Marketo Measure Discover]로 설정되면 총 Marketo 및 CRM 리드 수가 표시됩니다. Marketo 사용자만 또는 CRM 리드에만 보고하려면 소스에 대한 세그먼트 카테고리를 만든 다음 &quot;소스 시스템&quot; 필드를 사용하여 Marketo 및 CRM에 대한 세그먼트 규칙을 만들어 규칙을 정의합니다. 세그먼트가 만들어지면 세그먼트를 통해 필터링할 수 있는 소스 카테고리가 표시됩니다 [!DNL Marketo Measure Discover] 대시보드 .

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
   <th><p><strong>biz_leads</strong></p></th> 
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
   <td><p>계정 Id(L2A)</p></td> 
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

*Marketo 회사 엔티티의 필드가 개인의 updateAt 값에 영향을 주지 않으므로 웹 사이트 또는 회사와 같은 관련 필드가 업데이트된 경우, [!DNL Marketo Measure] updatedAt 날짜/시간 값이 업데이트되지 않으므로 이러한 값이 수정되는 것을 알 수 없습니다. 이는 리드에 대한 계정을 해결할 새 데이터가 없는 ABM 기능에 영향을 줍니다. 지금은 해결 방법이 없지만 나중에 이것을 해결할 계획이 있습니다.

## FAQ {#faq}

**CRM과 내 리드 카운트가 다른 이유는 무엇입니까? [!DNL Marketo Measure Discover]?**

이 통합을 통해 Marketo에서 직접 가져온 리드에 대한 터치포인트를 만들 수 있으므로, CRM에 동기화되지 않은 리드가 있을 수 있으므로 CRM 리드에 대해서만 터치포인트를 푸시하므로 Discover 내의 카운트가 CRM보다 더 클 수 있습니다.

**이렇게 하면 데이터가 어떻게 대체됩니까?**

이 통합은 실제로 현재 내의 데이터 세트를 병합합니다 [!DNL Marketo Measure] 예를 들어 아무것도 대체되지 않습니다. 현재 CRM에서 기대하는 것은 2년 가치의 Marketo 리드를 다운로드할 때 Marketo 리드와 일치도 있다는 것을 보여주기 위해 해당 리드 레코드를 업데이트한다는 것입니다. 모든 것이 백엔드에서 발생하고 터치 포인트가 동일하게 유지되어야 합니다. 또한 자격이 있는 Marketo 리드 때문에 더 많은 터치포인트를 볼 수 있을 것으로 예상됩니다. 해당 Marketo 사용자와 일치하는 웹 세션을 찾을 수 있으면 에서 카운트되는 터치포인트를 볼 수 있습니다. [!DNL Marketo Measure].

**Marketo에서 다운로드한 사용자만 CRM 연결을 끊게 할 수 있습니까?**

지금은 안 돼 미래에는 이 옵션이 제공될 예정이지만, 프로그램, 기회 및 거래를 Marketo에서 로 연결할 수 있도록 이 Marketo 통합의 다른 단계를 구축해야 합니다 [!DNL Marketo Measure].

**내 Marketo 사람들을 모두 가져오나요?**

현재, 가장 빨리 사람을 가져올 수 있는 방법은 최소 2년의 데이터를 가져올 수 있도록 1/1/2018에서 가져온 것입니다. 이는 CRM 다운로드에서 적용하는 것과 동일한 동작입니다. Marketo 연결이 설정되면 롤링 2년 기간을 다운로드하는 향상된 동작을 구현합니다.

또한 사람 유형을 필터링하지 않으므로 2년 창 내의 모든 사용자는 가져올 수 있고 터치포인트를 사용할 수 있습니다.

**SOLR이란 무엇이며 이 기능을 사용하기 위해 SOLR을 활성화해야 하는 이유는 무엇입니까?**

Marketo 인스턴스에 대한 SOLR 활성화는 구독에서 다음을 사용할 수 있도록 Marketo의 하드웨어 공간을 여는 간단한 단계입니다 [!DNL Marketo Measure] 통합. SOLR이 활성화되어 있지 않으면 Marketo 인스턴스에서 적절한 사람을 다운로드할 수 있는 특정 호출에 액세스할 수 없습니다.
