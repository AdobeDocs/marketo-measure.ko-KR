---
description: 통합 권한 개요 - [!DNL Marketo Measure] - 제품 설명서
title: 통합 권한 개요
hide: true
hidefromtoc: true
feature: APIs, Integration
source-git-commit: 1c3cd5ac9999550003765a9e1ed8d538224fe8a9
workflow-type: tm+mt
source-wordcount: '239'
ht-degree: 3%

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
    <td></td>
    <td></td>
    <td></td>
    <td></td>
  </tr>
  <tr>
    <td></td>
    <td></td>
    <td></td>
    <td></td>
  </tr>
  <tr>
    <td></td>
    <td></td>
    <td></td>
    <td></td>
  </tr>
  <tr>
    <td></td>
    <td></td>
    <td></td>
    <td></td>
  </tr>
  <tr>
    <td></td>
    <td></td>
    <td></td>
    <td></td>
  </tr>
  <tr>
    <td></td>
    <td></td>
    <td></td>
    <td></td>
  </tr>
  <tr>
    <td></td>
    <td></td>
    <td></td>
    <td></td>
  </tr>
  <tr>
    <td></td>
    <td></td>
    <td></td>
    <td></td>
  </tr>
  <tr>
    <td></td>
    <td></td>
    <td></td>
    <td></td>
  </tr>
</tbody>
</table>
