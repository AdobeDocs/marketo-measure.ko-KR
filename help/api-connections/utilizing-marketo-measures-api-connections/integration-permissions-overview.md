---
description: 통합 권한 개요 - [!DNL Marketo Measure] - 제품 설명서
title: 통합 권한 개요
feature: APIs, Integration
source-git-commit: e427f5e9f234917c033188116602d4798701118c
workflow-type: tm+mt
source-wordcount: '1286'
ht-degree: 1%

---

# 통합 권한 개요 {#integration-permissions-overview}

이 안내서에서는 각 통합이 문제 없이 효과적으로 작동할 수 있도록 Marketo Measure과의 원활한 통합에 필요한 권한을 간략하게 설명합니다.

<table>
<thead>
  <tr>
    <th style="width:10%">통합</th>
    <th style="width:25%">데이터 유형
    <li>웹 인터랙션 데이터</li>
    <li>B2B 시스템 데이터</li>
    <li>광고 플랫폼 데이터</li></th>
    <th style="width:25%">추적 항목</th>
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
    <br>
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
<br>
CRM의 다른 사용자와 관련된 문제를 방지하기 위해 Dynamics 내에서 를 통해 데이터를 내보내고 가져올 수 있는 전용 Marketo Measure 사용자를 만드는 것이 좋습니다. Marketo Measure 계정을 만들 때 사용할 사용자 이름 및 암호와 끝점 URL을 참고하십시오.
<p>
<b>보안 역할</b>
<br>
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
<br>
<a href="https://developers.facebook.com/docs/permissions/reference/ads_management/">ads_management</a>
<br>
<li>프로그래밍 방식으로 캠페인을 만들고, 광고를 관리하고, 지표를 가져옵니다.</li>
<li>광고주를 위한 혁신적인 솔루션과 차별화된 가치를 제공하는 광고 관리 도구를 구축할 수 있습니다.</li>
<br>
<br>
<a href="https://developers.facebook.com/docs/permissions/reference/email">이메일</a>
<br>
<li>다른 사용자와 통신하고 해당 Facebook 프로필과 연결된 이메일 주소로 앱에 로그인할 수 있도록 합니다.</li></td>
  </tr>
  <tr>
    <td>LinkedIn</td>
    <td>광고 플랫폼 데이터
    <p>
    B2B 시스템 데이터 (CRM 활동으로 분류되는 양식 및 제출을 포함하는 리드 세대 양식 데이터).</td>
    <td>Marketo Measure은 LinkedIn 광고 캠페인, 광고 크리에이티브 및 비용 데이터뿐만 아니라 잠재 고객 Forms 및 응답을 추적하고 있습니다. 가져온 데이터를 기반으로 LinkedIn 터치포인트를 생성하고 리드 양식 응답을 고객의 리드에 연결할 수 있습니다.</td>
    <td><li>Marketo Measure에서 비용 데이터를 다운로드하려면 캠페인 관리자 또는 계정 관리자 역할이 필요합니다. (범위 행 1)</li>
    <br>
    <li>Marketo Measure에서 리드 세대 양식 데이터에 액세스하려면 슈퍼 관리자(페이지 관리자 역할, 범위 행 2) 또는 리드 세대 Forms 관리자(유료 미디어 관리자 역할, 범위 행 3)가 필요합니다</li>
    <br>
    <li>Marketo Measure에서 자동 태그 지정을 조작하려면 수퍼 관리자(페이지 관리자 역할, 범위 행 2) 또는 스폰서드 콘텐츠 포스터(유료 미디어 관리자 역할, 범위 행 3)가 필요합니다</li>
    <p>
    <b>범위</b>
    <br>
    <a href="https://www.linkedin.com/campaignmanager/accounts">포털에서 사용자 역할 설정(LinkedIn 계정에 로그인 필요)</a> - <a href="https://www.linkedin.com/help/lms/answer/a425731/user-roles-and-functions-in-campaign-manager">사용자 역할 개요</a>: 사용자 역할, 사용자 권한 보기 및 관리, 계정 관리자 또는 캠페인 관리자와 같은 역할 할당
    <p>
    <a href="https://www.linkedin.com/help/linkedin/answer/a570172/add-or-remove-admins-on-your-showcase-page?lang=en">페이지 관리자 역할 설정 - <a href="https://www.linkedin.com/help/linkedin/answer/a541981/linkedin-page-admin-roles-overview">페이지 관리자 역할 정의</a>: 원하는 관리 페이지에서 페이지 관리자 역할
    <p>
    <a href="https://www.linkedin.com/help/linkedin/answer/a570172/add-or-remove-admins-on-your-showcase-page?lang=en">유료 미디어 관리자 역할 설정(유료 미디어 관리자 찾기) - <a href="https://www.linkedin.com/help/linkedin/answer/a554540">유료 미디어 관리자 정의</a>: 유료 미디어 관리자 역할</td>
  </tr>
  <tr>
    <td>더블 클릭</td>
    <td>광고 플랫폼 데이터</td>
    <td>Marketo Measure은 계정, 광고주, 캠페인, (사용자 정의) 랜딩 페이지, 광고, 크리에이티브, 배치 및 사이트를 추적합니다.</td>
    <td><li>사용자의 기본 Google 계정 이메일 주소가 필요합니다.</li>
<li>Campaign Manager 360 계정에 액세스하는 데 필요한 Campaign Manager 권한</li>
<ul>
<li>DoubleClick 광고주 보고서 보기 및 관리</li>
<li>DoubleClick 캠페인 관리자를 보고 관리하면 광고 캠페인이 표시됩니다</li>
<p>
    <b>범위</b>
    <br>
    <a href="https://www.googleapis.com/auth/userinfo.email">https://www.googleapis.com/auth/userinfo.email</a>: 기본 Google 계정 이메일 주소 보기
    <p>
     <a href="https://www.googleapis.com/auth/dfareporting">https://www.googleapis.com/auth/dfareporting</a>: 광고주를 위한 DoubleClick 보고서 보기 및 관리
    <p>
     <a href="https://www.googleapis.com/auth/dfatrafficking">https://www.googleapis.com/auth/dfatrafficking</a>: DCM(DoubleClick Campaign Manager)의 디스플레이 광고 캠페인을 보고 관리합니다</td>
  </tr>
  <tr>
    <td>AdWords</td>
    <td>광고 플랫폼 데이터</td>
    <td>AdWords와 통합하여 다음과 같은 작업을 수행합니다.
<p>
<li>고객 광고 데이터 가져오기</li>
<li>고객 광고 비용 데이터 가져오기</li>
<li>URL 매개 변수 추가/URL 추적 템플릿 업데이트를 통해 클라이언트의 광고 업데이트</li>
<p>
Marketo Measure은 캠페인, 광고 그룹, 크리에이티브, 사이트 링크 및 키워드를 추적합니다.</td>
    <td><li>사용자의 기본 Google 계정 이메일 주소가 필요합니다.</li>
<p>
    <b>범위</b>
    <br>
    <a href="https://www.googleapis.com/auth/userinfo.email">https://www.googleapis.com/auth/userinfo.email</a>: 기본 Google 계정 이메일 주소 보기</td>
  </tr>
  <tr>
    <td>빙</td>
    <td>광고 플랫폼 데이터</td>
    <td>Marketo Measure은 계정, 캠페인, 광고 그룹, 크리에이티브 및 키워드를 추적합니다.</td>
    <td><li>사용자는 Microsoft 계정을 통해 "오프라인 액세스"를 부여해야 합니다(로그인하지 않은 경우에도 최종 사용자의 사용자 정보에 대한 Marketo Measure 액세스 권한을 부여함). 다음을 참조하십시오 <a href="https://learn.microsoft.com/en-us/deployoffice/overview-extended-offline-access">Microsoft 페이지</a> 방법을 참조하십시오.</li>
<p>
    <b>범위</b>
    <br>
    <a href="https://learn.microsoft.com/en-us/deployoffice/overview-extended-offline-access">https://learn.microsoft.com/en-us/deployoffice/overview-extended-offline-access</a>: 권한에 대한 액세스 권한을 부여한 데이터에 대한 액세스 권한을 유지합니다.</td>
  </tr>
  <tr>
    <td>Marketo Engage</td>
    <td>B2B 시스템 데이터</td>
    <td>Marketo 통합을 통해 Marketo Measure은 Marketo 활동, 사람, 프로그램 및 프로그램 멤버십을 수집할 수 있습니다. 또한 Marketo Measure은 Marketo 웹 활동을 Marketo Measure 리드 터치포인트에 연결하기 위한 목적으로 Marketo 쿠키(Munchkin ID)를 추적합니다. <a href="/help/marketo-measure-and-marketo/marketo-measure-integrations-with-marketo/marketo-engage-programs-integration.md#cookie-mapping">여기에 기재된 바와 같이</a>:
    <p>
    <i>Marketo과 Marketo Measure 통합의 결과로 Marketo Measure 쿠키 ID도 매핑되고 Marketo Munchkin ID와 동기화됩니다. 이렇게 하면 FT 및 LC 터치를 모두 Marketo 활동에 귀속시키지 않고 간격을 닫아 익명의 첫 번째 터치를 웹 세션에 귀속시킵니다.</i>
    </td>
    <td>고객은 전용 Marketo Engage API 사용자를 만들고 Marketo Measure에 자격 증명을 제공해야 합니다. 추가적인 권한 구성은 필요하지 않습니다. <a href="/help/marketo-measure-and-marketo/marketo-measure-integrations-with-marketo/set-up-marketo-connection.md#configuring-the-integration">자세히 알아보기</a>.</td>
  </tr>
  <tr>
    <td>Adobe Analytics</td>
    <td>B2B 시스템 데이터</td>
    <td>B2B 고객 속성 통합을 통해 Marketo Measure과 Adobe Analytics의 상호 사용자는 Marketo Measure 속성 엔진에서 파생된 중요한 메타데이터와 CRM(Microsoft Dynamics 및 Salesforce)과의 동기화 기능을 통해 Adobe Analytics 사용자 프로필을 보강할 수 있습니다. <a href="/help/marketo-measure-and-adobe/marketo-measure-integrations-with-adobe-analytics.md">자세히 알아보기</a>.</td>
    <td>고객은 Marketo Measure에 별칭 ID와 FTP 서버 자격 증명을 제공하여 데이터가 Analytics 인스턴스에 업로드될 위치에 있어야 합니다.
    <p>
    이 프로세스의 이후 단계 중 일부에 필요하므로 다음 정보를 참고하십시오.
    <p>
    <li>원하는 값이 될 수 있는 별칭 ID입니다. "marketomeasure_id"를 권장합니다.</li>
    <li>FTP 서버 호스트 이름 및 자격 증명(사용자 이름 및 암호)</li>
    <p>
    <a href="/help/marketo-measure-and-adobe/marketo-measure-integrations-with-adobe-analytics.md#configuring-the-integration">자세히 알아보기</a></td>
  </tr>
  <tr>
    <td>Bizible Javascript</td>
    <td></td>
    <td><a href="/help/marketo-measure-tracking/setting-up-tracking/data-collected-by-javascript.md">bizible.js에서 수집하는 데이터</a>.</td>
    <td></td>
  </tr>
</tbody>
</table>
