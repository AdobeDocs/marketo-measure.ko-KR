---
description: 통합 권한 개요 - [!DNL Marketo Measure] - 제품 설명서
title: 통합 권한 개요
hide: true
hidefromtoc: true
feature: APIs, Integration
source-git-commit: d7ded9075f7f5831314d59294327f1e4928baf8a
workflow-type: tm+mt
source-wordcount: '636'
ht-degree: 2%

---

# 통합 권한 개요 {#integration-permissions-overview}

이 안내서에서는 각 통합이 문제 없이 효과적으로 작동할 수 있도록 Marketo Measure과의 원활한 통합에 필요한 권한을 간략하게 설명합니다.

<table>
<thead>
  <tr>
    <th style="width:10%">통합</th>
    <th style="width:20%">데이터 유형
    <li>웹 인터랙션 데이터</li>
    <li>B2B 시스템 데이터</li>
    <li>광고 플랫폼 데이터</li></th>
    <th style="width:30%">추적 항목</th>
    <th style="width:40%">권한 요구 사항</th>
  </tr>
</thead>
<tbody>
  <tr>
    <td>Salesforce</td>
    <td>B2B 시스템 데이터    
</td>
    <td>Marketo Measure이 추적 중:
    <p>
    <li>계정</li>
    <li>Campaign</li>
    <li>CampaignMember</li>
    <li>연락처</li>
    <li>CurrencyConversionRange</li>
    <li>통화 상태</li>
    <li>이벤트</li>
    <li>FieldHistory(Lead, Contact 및 Opportunity)</li>
    <li>리드</li>
    <li>기회</li>
    <li>영업 기회 연락처 역할</li>
    <li>영업 기회 내역</li>
    <li>작업</li>
<p>
만들어진 터치포인트와 기타 데이터는 계정, 캠페인, 캠페인 멤버, 사례, 연락처, 잠재 고객 및 기회에 대한 사용자 지정 bizible 필드에 작성됩니다.</td>
    <td><b>Salesforce 연결된 사용자 권한(필수)</b>
    <p>
    <b>전용 사용자에 대한 Marketo Measure 관리자 권한 집합:</b> SFDC 관리자가 marketo 측정 개체에 대해 CRUD 작업을 수행할 수 있도록 허용합니다.
    <br>
    <b>전환된 잠재 고객 사용 권한 집합 보기 및 편집:</b> 이렇게 하면 Marketo Measure은 잠재 고객을 연락처로 전환한 후 데코레이트할 수 있습니다.
    <br>
    <b>Salesforce 마케팅 사용자 확인란:</b> 마케팅 사용자 확인란을 통해 캠페인을 만들고 캠페인 가져오기 마법사를 사용할 수 있습니다.
    <br>
    <b>Marketo Measure Standard 사용자:</b> 사용자에게 Marketo Measure 오브젝트에서 레코드를 읽을 수 있는 기능을 제공합니다.
    <p>
    <b>Salesforce Standard 필드 권한</b>
    <a href="/help/configuration-and-setup/marketo-measure-and-salesforce/how-marketo-measure-and-salesforce-interact.md">Salesforce 표준 개체 및 액세스</a>
    <p>
    <b>Salesforce 사용자 지정 필드 권한</b>
    <br>
    고객이 사용할 수 있는 사용자 정의 Salesforce 필드를 보관할 수 있는 기능 설정을 제공합니다. 이러한 기능 설정이 정의된 경우 기능 설정에 저장된 각 Salesforce 필드에 대한 읽기 액세스 권한이 필요합니다(예: CustomLeadSourceField 설정 값이 "LeadSource__c"와 동일한 경우 이 필드에 대한 읽기 액세스 권한이 필요합니다).
    </td>
  </tr>
  <tr>
    <td>Dynamics</td>
    <td>B2B 시스템 데이터</td>
    <td>Marketo Measure이 추적 중:
    <p>
    <li>계정
<li>활동 파티
<li>활동 포인터
<li>Campaign
<li>CampaignItem(시스템의 CampaignList)
<li>CampaignResponse(시스템 내 CampaignMember)
<li>연락처
<li>리드
<li>목록(시스템의 MarketingList)
<li>ListMember(시스템의 MarketingListMember)
<li>기회
<li>조직
<li>TransactionCurrency(시스템의 CurrencyConversionRange 및 CurrencyStatus)
<li>약속, CampaignActivity, 이메일, 팩스, 문제 해결, 편지, 전화 통화, RecurringAppointmentMaster, ServiceAppointment, 작업
<li>bizible2_bizible_abtest
<li>bizible2_bizible_attribution_touchpoint
<li>bizible2_bizible_event
<li>bizible2_bizible_history
<li>bizible2_bizible_touchpoint
<p>
만들어진 터치포인트 및 기타 데이터는 계정, 캠페인, 캠페인, 캠페인 응답, 연락처, 잠재 고객, 목록, 영업 기회 및 전화의 사용자 지정 bizible 필드에 기록됩니다</td>
    <td><b>Marketo Measure 사용자 권한</b>
<p>
CRM의 다른 사용자와 관련된 문제를 방지하기 위해 Dynamics 내에서 를 통해 데이터를 내보내고 가져올 수 있는 전용 Marketo Measure 사용자를 만드는 것이 좋습니다. Marketo Measure 계정을 만들 때 사용할 사용자 이름 및 암호와 끝점 URL을 참고하십시오.
<p>
<b>보안 역할</b>
<p>
조직에서 Dynamics 보안 역할을 사용하는 경우 연결된 사용자 또는 전용 Marketo Measure 사용자에게 필요한 엔티티에 대한 충분한 읽기/쓰기 권한이 있는지 확인하십시오.
<br>
보안 역할은 설정 &gt; 보안 &gt; 보안 역할에 있습니다.
<br>
Marketo Measure 사용자 지정 엔터티의 경우 모든 엔터티에 대해 전체 권한이 필요합니다.
<p>
<b>Dynamics Standard 필드 권한</b>
<br>
<a href="/help/marketo-measure-and-dynamics/getting-started-with-marketo-measure-and-dynamics/marketo-measure-dynamics-schema.md">Marketo Measure Dynamics 스키마</a>
<p>
<b>Dynamics 사용자 지정 필드 권한</b>
<br>
고객이 터치 포인트 설정 규칙의 사용자 지정 억제/제거에 사용하려는 잠재 고객 또는 연락처 엔터티의 모든 필드에 대한 읽기 액세스 권한이 필요합니다.
<br>
고객이 세그먼트 규칙 또는 단계 매핑에 사용하려는 Lead 또는 Opportunity 엔티티의 모든 필드에 대한 읽기 액세스 권한이 필요합니다.
<br>
고객이 Campaign/MarketingList 구성원을 동기화하는 데 사용하려는 Campaign, CampaignResponse 및 List 엔터티의 모든 필드에 대한 읽기 액세스 권한이 필요합니다.
</td>
  </tr>
  <tr>
    <td>Facebook</td>
    <td>광고 플랫폼 데이터</td>
    <td>facebook과 통합하여 다음과 같은 작업을 수행합니다.
<p>
<li>고객 광고 데이터 가져오기</li>
<li>고객 광고 비용 데이터 가져오기</li>
<li>URL 매개 변수를 추가하여 클라이언트의 광고 업데이트</li>
<p>
Marketo Measure은 계정, 캠페인, 광고 그룹, 광고, 필터 ID 및 URL을 추적하고 있습니다.</td>
    <td><li>캠페인을 만들거나 광고를 관리하거나 광고 지표를 가져오려면 ads_management 권한이 필요합니다.</li>
<li>이메일 권한은 사용자가 Facebook 이메일에 로그인할 수 있도록 하기 위해 필요합니다.</li>
<p>
<b>범위</b>
<p>
<a href="https://developers.facebook.com/docs/permissions/reference/ads_management/">ads_management</a>
<br>
<li>프로그래밍 방식으로 캠페인을 만들고, 광고를 관리하고, 지표를 가져옵니다.</li>
<li>광고주를 위한 혁신적인 솔루션과 차별화된 가치를 제공하는 광고 관리 도구를 구축할 수 있습니다.</li>
<p>
<a href="https://developers.facebook.com/docs/permissions/reference/email">이메일</a>
<br>
<li>다른 사용자와 통신하고 해당 Facebook 프로필과 연결된 이메일 주소로 앱에 로그인할 수 있도록 합니다.</li></td>
  </tr>
  <tr>
    <td>LinkedIn</td>
    <td></td>
    <td></td>
    <td></td>
  </tr>
  <tr>
    <td>더블 클릭</td>
    <td></td>
    <td></td>
    <td></td>
  </tr>
  <tr>
    <td>AdWords</td>
    <td></td>
    <td></td>
    <td></td>
  </tr>
  <tr>
    <td>빙</td>
    <td></td>
    <td></td>
    <td></td>
  </tr>
  <tr>
    <td>Marketo Engage</td>
    <td></td>
    <td></td>
    <td></td>
  </tr>
  <tr>
    <td>Adobe Analytics</td>
    <td></td>
    <td></td>
    <td></td>
  </tr>
  <tr>
    <td>Bizible Javascript</td>
    <td></td>
    <td></td>
    <td></td>
  </tr>
</tbody>
</table>
