---
description: 오류 알림 - [!DNL Marketo Measure]
title: 오류 알림
feature: Fundamentals
exl-id: ed07eed6-ddeb-4856-a1ac-ea3d571283f6
source-git-commit: 2b13a518d1be768a5c312ea4abdf2039aa22cf08
workflow-type: tm+mt
source-wordcount: '1675'
ht-degree: 0%

---

# 오류 알림 {#error-notifications}

다음은 인앱 알림 또는 이메일을 통해 받을 수 있는 오류 목록입니다. 이러한 메시지가 표시되면 각각의 문제 해결 단계를 따르십시오. 이러한 단계로 문제가 해결되지 않으면 다음 연락처에 문의하십시오. [Marketo 지원](https://nation.marketo.com/t5/support/ct-p/Support).

<table>
  <tbody>
    <tr>
      <th style="width:31%">오류 코드</th>
      <th style="width:23%">알림 예</th>
      <th style="width:23%">설명</th>
      <th style="width:23%">문제 해결 단계</th>
    </tr>
    <tr>
      <td>API 비활성화(_D)</td>
      <td>CRM 가져오기 중 오류 발생 : API_DISABLED : 이 사용자에 대해 API 호출이 비활성화되었습니다.</td>
      <td>Marketo Measure 사용자에 대해 API 권한이 비활성화되었습니다.</td>
      <td>에서 다음 Salesforce 설명서를 참조하십시오. <a href="https://help.salesforce.com/s/articleView?language=en_US&amp;id=sf.branded_apps_commun_api_permset.htm&amp;type=5">api 액세스를 활성화하는 방법</a>.</td>
    </tr>
    <tr>
      <td>API_LIMIT_EXCEEDED</td>
      <td>CRM 내보내기 중 오류 발생: PI_LIMIT_EXCEEDED</td>
      <td>CRM의 API 제한이 초과되었습니다(24시간).</td>
      <td>API 크레딧 할당을 조정하는 데 도움이 필요하면 CRM에 대한 다음 설명서를 참조하십시오.</p>
          <ul>
            <li><a href="https://learn.microsoft.com/en-us/dynamics365/fin-ops-core/dev-itpro/data-entities/service-protection-monitoring">Dynamics</a>
            </li>
            <li><a href="https://developer.salesforce.com/docs/atlas.en-us.salesforce_app_limits_cheatsheet.meta/salesforce_app_limits_cheatsheet/salesforce_app_limits_platform_api.htm">Salesforce</a>
            </li>
          </ul>
          <p>아래 단계에 따라 Marketo Measure에서 사용하는 CRM 크레딧을 조정할 수도 있습니다.</p>
          <ul>
            <li>다음으로 이동 <b>설정</b> &gt; <b>CRM</b> &gt; <b>일반</b></li>
            <li>일별 CRM API 제한 업데이트<br/>
              <ul>
                <li><b>참고: 기본값은 100,000입니다</b></li>
              </ul>
            </li>
          </ul>
          <p>
           <img src="assets/error-notifications-1.png">
          </p>
      </td>
    </tr>
    <tr>
      <td>CANNOT_EXECUTE_FLOW_TRIGGER</td>
      <td>Crm 내보내기 중 오류 발생: CANNOT_EXECUTE_FLOW_TRIGGER : 엔티티 유형 'Contact' Salesforce 관리자에게 자세한 내용을 제공합니다.
제한 초과됨 사용자 또는 사용자 조직이 이 기능의 최대 제한을 초과했습니다. 오류 ID: 123456</td>
      <td>레코드가 Salesforce 조직에 설정된 트리거 흐름 규칙을 충족하지 않으므로 저장할 수 없습니다.</td>
      <td>알림 메시지의 전체 세부 정보를 검토하고 Salesforce 조직의 흐름 트리거를 검토하십시오.
흐름 트리거에 대한 Salesforce 설명서 <a href="https://admin.salesforce.com/blog/2023/what-is-a-record-triggered-flow#:~:text=A%20record%2Dtriggered%20flow%20allows,is%20created%20and%2For%20updated">은(는) 여기에서 찾을 수 있음</a>.
      </td>
    </tr>
    <tr>
      <td>CANNOT_INSERT_UPDATE_ACTIVATE_ENTITY</td>
      <td>CRM 내보내기 중 오류 발생: CANNOT_INSERT_UPDATE_ACTIVATE_ENTITY : 엔티티 유형 'Lead': CRM ErrorCode: CANNOT_INSERT_UPDATE_ACTIVATE_ENTITY, CRM ErrorMessage: System.LimitException: Apex CPU 시간 제한 초과, RecordId: 0123456
      <p>
      CRM 내보내기 중 오류 발생: CANNOT_INSERT_UPDATE_ACTIVATE_ENTITY : 엔티티 유형 '계정': CRM 오류 코드: CANNOT_INSERT_UPDATE_ACTIVATE_ENTITY, CRM 오류 메시지: 엔티티 유형을 업데이트할 수 없음: 계정, 레코드 ID: 0123456</td>
      <td>트리거로 인해 개체를 업데이트하거나 삽입할 수 없습니다.
      <p>
      또는
      <p>
      오브젝트에 대한 권한이 없습니다.</td>
      <td>삽입/업데이트 실패의 원인이 되는 트리거 코드를 검토합니다. 트리거에 대한 자세한 내용은 다음 Salesforce 설명서를 참조하십시오.
        <ul>
          <li><a href="https://help.salesforce.com/s/articleView?id=sf.code_manage_triggers.htm&amp;type=5">Apex 트리거</a>
          </li>
          <li><a href="https://admin.salesforce.com/blog/2023/what-is-a-record-triggered-flow#:~:text=A%20record%2Dtriggered%20flow%20allows,is%20created%20and%2For%20updated">흐름 트리거</a>
          </li>
        </ul>
        <p>
        에 필요한 모든 권한을 제공합니다. <a href="/help/configuration-and-setup/marketo-measure-and-salesforce/how-marketo-measure-and-salesforce-interact.md">Marketo Measure 사용자</a>.
      </td>
    </tr>
    <tr>
      <td>DUPLICATES_DETECTED</td>
      <td>CRM 내보내기 중 오류 발생: DUPLICATES_DETECTED : 엔티티 유형 'Contact': CRM ErrorCode: DUPLICATES_DETECTED, CRM ErrorMessage: 중복 레코드를 만들고 있습니다. 대신 기존 레코드를 사용하는 것이 좋습니다. 레코드 ID: 0123456</td>
      <td>Salesforce 조직으로 가져오는 레코드가 이미 있습니다.</td>
      <td>
        <ul>
          <li><a href="https://help.salesforce.com/s/articleView?id=000390009&amp;type=1">"중복 규칙" 설정 비활성화</a> 복제를 허용합니다.
          </li>
          <li>에서 Marketo Measure 전용 사용자 제외 <a href="https://trailhead.salesforce.com/content/learn/modules/validation-rules/bypass-your-validation-rules">사용자 지정 유효성 검사 규칙</a>.
          </li>
        </ul>
      </td>
    </tr>
    <tr>
      <td>DUPLEX_VALUE</td>
      <td>CRM 내보내기 중 오류 발생: DUPLICATE_VALUE : 엔티티 유형 'Lead': CRM 오류 코드: DUPLICATE_VALUE, CRM 오류 메시지: 중복 값 발견: Email_Unique__c 중복 값 (ID: 123, RecordId: 456)</td>
      <td>Salesforce 조직으로 가져오는 필드에서 중복 값을 허용하지 않습니다.</td>
      <td>
        <ul>
          <li>선택 취소 <a href="https://help.salesforce.com/s/articleView?id=000390009&amp;type=1">"고유 확인란"</a> Salesforce.
          </li>
          <li>에서 Marketo Measure 전용 사용자 제외 <a href="https://trailhead.salesforce.com/content/learn/modules/validation-rules/bypass-your-validation-rules">사용자 지정 유효성 검사 규칙</a>.
          </li>
        </ul>
      </td>
    </tr>
    <tr>
      <td>ENTITY_IS_LOCKED</td>
      <td>CRM 내보내기 중 오류 발생: ENTITY_IS_LOCKED : 엔티티 유형 'Account': CRM 오류 코드: ENTITY_IS_LOCKED, CRM 오류 메시지: 이 레코드가 잠겨 있습니다. 편집해야 하는 경우 관리자에게 문의하십시오., 레코드 ID: 0123456</td>
      <td>레코드가 승인 프로세스에 있고 현재 승인자나 시스템 관리자가 아닌 사용자가 레코드를 편집하려고 할 때</td>
      <td>
        <ul>
          <li>Salesforce 조직의 해당 레코드에 대해 보류 중인 승인 프로세스를 해결합니다.</li>
          <li>에서 Marketo Measure 전용 사용자 제외 <a href="https://trailhead.salesforce.com/content/learn/modules/validation-rules/bypass-your-validation-rules">사용자 지정 유효성 검사 규칙</a>.
          </li>
        </ul>
      </td>
    </tr>
    <tr>
      <td>FIELD_FILTER_VALIDATION_EXCEPTION</td>
      <td>CRM 내보내기 중 오류 발생: FIELD_FILTER_VALIDATION_EXCEPTION : 엔티티 유형 'Lead': CRM 오류 코드: FIELD_FILTER_VALIDATION_EXCEPTION, 필드: User__C, CRM 오류 메시지: 값이 없거나 필터 조건과 일치하지 않습니다. "계정 담당자, Inside Sales" 역할을 가진 사용자를 선택하십시오. 레코드 ID: 0123456</td>
      <td>수정된 레코드가 개체에 정의된 조회 필터를 더 이상 충족하지 않습니다.</td>
      <td>Marketo Measure이 수정하려는 개체에서 필터를 확인합니다. 다음을 참조하십시오 <a href="https://help.salesforce.com/s/articleView?id=000384756&amp;type=1">이 Salesforce 문서</a> 개체에서 필터를 확인하는 방법을 알아봅니다.</td>
    </tr>
    <tr>
      <td>FIELD_INTEGRITY_EXCEPTION</td>
      <td>CRM 내보내기 중 오류 발생: FIELD_INTEGRITY_EXCEPTION : 엔티티 유형 'Lead': CRM 오류 코드: FIELD_INTEGRITY_EXCEPTION, 필드: 국가, CRM 오류 메시지: 이 국가에 문제가 있습니다. 올바른 것처럼 보일 수 있습니다. 유효한 국가 목록에서 국가/지역을 선택하십시오.: 국가, RecordId: 0123456</td>
      <td>레코드의 예상 유형이 일치하지 않습니다.</td>
      <td>가장 일반적인 사례는 주/국가 필드가 특정 선택 목록 값만 수락하도록 표준화되었기 때문에 Salesforce 조직에 설정된 주/국가 이름 지정 표준을 따르지 않는 것입니다. 이 문제를 해결하려면 다음을 수행할 수 있습니다.
        <ul>
          <li>레코드를 업데이트하여 해당 필드에 대해 조직에서 수락한 값을 따릅니다. SFDC 관리자에게 문의하여 허용되는 값 목록을 받으십시오.</li>
          <li><a href="https://help.salesforce.com/s/articleView?id=sf.admin_state_country_picklist_enable.htm&amp;type=5">국가/시/도 선택 목록 비활성화</a>.
          </li>
        </ul>
      </td>
    </tr>
    <tr>
      <td>INACTIVE_OWNER_OR_USER</td>
      <td>CRM 내보내기 중 오류 발생: INACTIVE_OWNER_OR_USER : 엔티티 유형 'Contact': CRM 오류 코드: INACTIVE_OWNER_OR_USER, CRM 오류 메시지: 비활성 사용자 [1234]을(를) 연락처 소유자로 사용하여 수행된 작업, 레코드 ID: 0123456</td>
      <td>Marketo Measure에 "비활성 소유자로 레코드 업데이트" 권한이 없습니다.</td>
      <td>Marketo Measure에 " 권한 부여<a href="https://help.salesforce.com/s/articleView?id=000386699&amp;type=1">비활성 소유자로 레코드 업데이트</a>"권한.</td>
    </tr>
    <tr>
      <td>INSUFFICIENT_ACCESS_OR_READONLY</td>
      <td>CRM 내보내기 중 오류 발생: INSUFFICIENT_ACCESS_OR_READONLY : 엔티티 유형 'Account': CRM ErrorCode: INSUFFICIENT_ACCESS_OR_READONLY, CRM ErrorMessage: 오브젝트 ID에 대한 액세스 권한 부족: [123], RecordId: 456</td>
      <td>Marketo Measure에 오브젝트/필드에 대한 권한이 없거나 오브젝트가 읽기 전용입니다.</td>
      <td>다음을 참조하십시오 <a href="/help/configuration-and-setup/marketo-measure-and-salesforce/how-marketo-measure-and-salesforce-interact.md">Experience League 문서</a> Marketo Measure에 필요한 권한에 대한 지침을 보려면.</td>
    </tr>
    <tr>
      <td>INVALID_ANALYTICS_ADOBE</td>
      <td>Adobe Analytics 내보내기 중 오류 발생: INVALID_UPLOAD_ANALYTICS_CONFIGURATION : 오류: ADOBE이 허용되지 않습니다. 업로드하기 전에 데이터 소스 스키마를 확인합니다. 데이터 소스 Id:1234</td>
      <td>Adobe Analytics 통합이 올바르게 구성되지 않았습니다.</td>
      <td>올바른 구성을 위해 다음 도움말 문서를 참조하십시오.
        <ul>
          <li>
            <a href="/help/marketo-measure-and-adobe/marketo-measure-integrations-with-adobe-analytics.md">Adobe Analytics과 Marketo Measure 통합</a>
          </li>
          <li>
            <a href="https://experienceleague.adobe.com/docs/core-services/interface/services/customer-attributes/t-crs-usecase.html">고객 속성 소스를 만들고 데이터 파일 업로드</a>
          </li>
        </ul>
      </td>
    </tr>
    <tr>
      <td>INVALID_CURRENCY_ISO_CODE</td>
      <td>광고 가져오기 중 오류 발생: INVALID_CURRENCY_ISO_CODE: 통화 XXX는 Marketo Measure에서 지원되지 않습니다.
      <p>
      광고 가져오기 중 오류 발생: INVALID_CURRENCY_ISO_CODE : 1234 계정의 통화 XXX는 Marketo Measure에서 지원되지 않습니다.</td>
      <td>지원되지 않는 통화가 발견되었습니다.</td>
      <td>알림에 표시된 소스 시스템(광고, Crm, Marketo)에서 레코드와 연결된 통화에 지원되는 유효한 통화가 있는지 확인합니다. 지원되는 통화는 ISO 통화 표준에서 파생됩니다.</td>
    </tr>
    <tr>
      <td>MISSING_BIZIBLE_CUSTOM_FIELDS_PERMISSIONS</td>
      <td>CRM 내보내기 중 오류 발생: MISSING_BIZIBLE_CUSTOM_FIELDS_PERMISSIONS : 엔티티 유형 'Campaign': CRM 오류 코드: INVALID_FIELD_FOR_INSERT_UPDATE, 필드: bizible2__UniqueId__c, CRM 오류 메시지: 필드를 만들거나 업데이트할 수 없음: bizible2__UniqueId__c. 이 필드의 보안 설정을 확인하고 프로필 또는 권한 집합에 대해 읽기/쓰기가 수행되는지 확인하십시오.</td>
      <td>Marketo Measure에 bizible 필드에 대한 권한이 없습니다.</td>
      <td>접두사가 "bizible2__"인 모든 필드에 대한 읽기 및 쓰기 권한이 필요합니다. 이러한 필드의 전체 목록을 찾을 수 있습니다 <a href="/help/configuration-and-setup/marketo-measure-and-salesforce/how-marketo-measure-and-salesforce-interact.md">이 문서에서</a>.</td>
    </tr>
    <tr>
      <td>MISSING_CONVERTED_LEAD_PERMISSION</td>
      <td>CRM 내보내기 중 오류 발생: MISSING_CONVERTED_LEAD_PERMISSION</td>
      <td>Marketo Measure에 전환된 리드 보기/편집 권한이 없습니다.</td>
      <td>CRM에서 이 권한을 활성화하는 데 도움이 필요하면 다음 Experience League 문서를 참조하십시오<br/>
          <a href="/help/marketo-measure-salesforce-reporting/additional-functionality/enabling-the-permission-to-edit-converted-leads.md">전환된 리드를 편집할 수 있는 권한 활성화</a></td>
    </tr>
    <tr>
      <td>MISSING_FIELD_READ_PERMISSION</td>
      <td>CRM 가져오기 중 오류 발생: MISSING_FIELD_READ_PERMISSION : 엔티티 유형 'Event': INVALID_FIELD:<br/>
    SystemModstamp,IsDeleted,WhoId,bizible2__Bizible_Touchpoint_Date__c</td>
      <td>Marketo Measure에 필수 필드에 대한 읽기 권한이 없습니다.</td>
      <td>Marketo Measure에 필요한 권한에 대한 지침은 다음 도움말 문서를 참조하십시오.
        <ul>
          <li><a href="/help/marketo-measure-and-dynamics/getting-started-with-marketo-measure-and-dynamics/marketo-measure-dynamics-schema.md">Dynamics</a>
          </li>
          <li><a href="/help/configuration-and-setup/marketo-measure-and-salesforce/how-marketo-measure-and-salesforce-interact.md">Salesforce</a>
          </li>
        </ul>
      </td>
    </tr>
    <tr>
      <td>MISSING_ISREPLICATABLE_PERMISSION</td>
      <td>Crm 가져오기 중 오류 발생: MISSING_ISREPLICATABLE_PERMISSION : Campaign에 IsReplicatable 권한이 없습니다.</td>
      <td>Marketo Measure과 Salesforce의 동기화를 유지하려면 Salesforce 개체에 이 권한이 필요합니다.</td>
      <td>개체에 대한 복제 가능 권한 설정에 대한 자세한 내용은 Salesforce 지원에 문의하십시오.</td>
    </tr>
    <tr>
      <td>MISSING_OBJECT_READ_PERMISSION</td>
      <td>Crm 가져오기 중 오류 발생: MISSING_OBJECT_READ_PERMISSION : Entity type Campaign': CRM 오류 코드: MISSING_PERMISSION</td>
      <td>Marketo Measure에 필수 개체에 대한 읽기 권한이 없습니다.</td>
      <td rowspan="2">Marketo Measure에 필요한 권한에 대한 지침은 다음 도움말 문서를 참조하십시오.
          <ul>
            <li><a href="/help/marketo-measure-and-dynamics/getting-started-with-marketo-measure-and-dynamics/marketo-measure-dynamics-schema.md">Dynamics</a>
            </li>
            <li><a href="/help/configuration-and-setup/marketo-measure-and-salesforce/how-marketo-measure-and-salesforce-interact.md">Salesforce</a>
            </li>
          </ul>
      </td>
    </tr>
    <tr>
      <td>MISSING_OBJECT_WRITE_PERMISSION</td>
      <td>CRM 내보내기 중 오류 발생: MISSING_OBJECT_WRITE_PERMISSION : 엔티티 유형 'bizible2_Bizible_Attribution_Touchpoint': CRM 오류 코드: MISSING_PERMISSION</td>
      <td>Marketo Measure에 필수 개체에 대한 쓰기 권한이 없습니다.</td>
    </tr>
    <tr>
      <td>MISSING_RECORD_OBJECT_PERMISSIONS</td>
      <td>CRM 내보내기 중 오류 발생: MISSING_RECORD_OBJECT_PERMISSIONS : 엔티티 유형 'bizible2__Bizible_Touchpoint__c': CRM 오류 코드: INSUFFICIENT_ACCESS_ON_CROSS_REFERENCE_ENTITY, 필드: 계정, CRM 오류 메시지: 상호 참조 ID에 대한 액세스 권한 부족: 0123456</td>
      <td>Marketo Measure에 권한이 없습니다.</td>
      <td>이 오류에는 Salesforce 조직에만 해당되는 몇 가지 이유가 있습니다. 다음은 이 문제를 해결할 수 있는 몇 가지 일반적인 문제 해결 단계입니다.
        <ul>
          <li>각각에 대해 필요한 모든 권한 검토 <a href="/help/configuration-and-setup/marketo-measure-and-salesforce/how-marketo-measure-and-salesforce-interact.md">오브젝트 및 필드</a>.</li>
          <li>에서 Marketo Measure 전용 사용자 제외 <a href="https://trailhead.salesforce.com/content/learn/modules/validation-rules/bypass-your-validation-rules">사용자 지정 유효성 검사 규칙</a>.</li>
          <li>Marketo Measure 부여 "<a href="https://developer.salesforce.com/docs/atlas.en-us.securityImplGuide.meta/securityImplGuide/users_profiles_view_all_mod_all.htm">모두 수정</a>"권한.</li>
        </ul>
      </td>
    </tr>
    <tr>
      <td>NULL_EMPTY_CURRENCY_ISO_CODE</td>
      <td>
        <p>
          Crm 가져오기 중 오류 발생: NULL_EMPTY_CURRENCY_ISO_CODE: RecordId 1234에 대해 MultiCurrency가 활성화된 경우 통화 ISO 코드가 NULL이거나 비어 있습니다.
      </td>
      <td>통화는 지원되는 ISO 통화 코드여야 합니다.</td>
      <td>알림에 표시된 소스 시스템(광고, Crm, Marketo)에서 레코드와 연결된 통화에 지원되는 유효한 통화가 있는지 확인합니다. 지원되는 통화는 ISO 통화 표준에서 파생됩니다.</td>
    </tr>
    <tr>
      <td>OPERATION_TO_LARGE</td>
      <td>CRM 가져오기 중 오류 발생: OPERATION_TOO_LARGE : 활동을 성공적으로 쿼리하려면 '모든 데이터 보기' 권한이 필요합니다.</td>
      <td>CRM 설정으로 인해 Marketo Measure에서 충분히 큰 데이터 세트를 쿼리할 수 없습니다.</td>
      <td>지정된 개체에 대해 Marketo Measure '모든 데이터 보기' 권한을 부여합니다.
      <p>
      '모든 데이터 보기' 권한에 대한 추가 정보 <a href="https://developer.salesforce.com/docs/atlas.en-us.securityImplGuide.meta/securityImplGuide/users_profiles_view_all_mod_all.htm">은(는) 여기에서 찾을 수 있음</a>.</td>
    </tr>
    <tr>
      <td>RECORD_NONCOMPLIANT_WITH_VALIDATION_RULES</td>
      <td>Crm 내보내기 중 오류 발생: RECORD_NONCOMPLIANT_WITH_VALIDATION_RULES : 엔티티 유형 'Lead': CRM 오류 코드: FIELD_CUSTOM_VALIDATION_EXCEPTION, 필드: Lead_Status_Reason__c, CRM 오류 메시지: Lead 상태 이유, RecordId: 0123456을 선택해야 합니다.</td>
      <td>업데이트하는 레코드가 Salesforce 조직에 설정된 유효성 검사 규칙을 충족하지 않습니다.</td>
      <td>에서 Marketo Measure 전용 사용자 제외 <a href="https://trailhead.salesforce.com/content/learn/modules/validation-rules/bypass-your-validation-rules">사용자 지정 유효성 검사 규칙</a>.
      <p>
      업데이트 <a href="https://help.salesforce.com/s/articleView?id=sf.fields_about_field_validation.htm&amp;type=5">유효성 검사 규칙</a>.</td>
    </tr>
    <tr>
      <td>RESTRICT_PICKLIST_VALUES_ENABLED</td>
      <td>CRM 내보내기 중 오류 발생: RESTRICT_PICKLIST_VALUES_ENABLED : 엔티티 유형 '캠페인': CRM 오류 코드: INVALID_OR_NULL_FOR_RESTRICTED_PICKLIST, 필드: Areas_of_Interest__c, CRM 오류 메시지: 제한된 picklist 필드에 대한 잘못된 값: 알 수 없음</td>
      <td>선택 목록 필드의 설정에서 '값 집합에 정의된 값으로 선택 목록 제한'을 활성화한 경우 또는 필드에 삽입되는 값을 개체의 레코드 유형에서 사용할 수 없는 경우입니다.</td>
      <td>Salesforce 조직에서 선택 목록 제한 설정을 비활성화합니다.
          <p>
          에서 Marketo Measure 전용 사용자 제외 <a href="https://trailhead.salesforce.com/content/learn/modules/validation-rules/bypass-your-validation-rules">사용자 지정 유효성 검사 규칙</a>.
      </td>
    </tr>
    <tr>
      <td>REQUIRED_FIELD_MISSING</td>
      <td>CRM 내보내기 중 오류 발생: MISSING_REQUIRED_FIELD : 엔티티 유형 'Lead': CRM 오류 코드: REQUIRED_FIELD_MISSING, 필드: Product_Type__c, CRM 오류 메시지: 필수 필드가 누락됨: [Product_Type__c], RecordId: 0123456</td>
      <td>유효성 검사 규칙에서 개체에 필수 필드를 지정하는 경우.</td>
      <td>에서 Marketo Measure 전용 사용자 제외 <a href="https://trailhead.salesforce.com/content/learn/modules/validation-rules/bypass-your-validation-rules">사용자 지정 유효성 검사 규칙</a>.
      </td>
    </tr>
    <tr>
      <td>알 수 없는 예외_사항</td>
      <td>CRM 내보내기 중 오류 발생: UNKNOWN_EXCEPTION : 엔티티 유형 'Contact': CRM ErrorCode: UNKNOWN_EXCEPTION, CRM ErrorMessage: 포털 사용자는 파트너 계정을 소유할 수 없음, RecordId: 0123456</td>
      <td>Salesforce에서 처리되지 않은 예외가 발생했습니다.</td>
      <td>문제가 지속되면 Salesforce로 사례를 제출하고 오류 메시지의 숫자 값을 복사합니다.</td>
    </tr>
    <tr>
      <td>지원되지 않는 CRM_PACKAGE_VERSION</td>
      <td>CRM 가져오기 중 오류 발생: UNSUPPORTED_CRM_PACKAGE_VERSION : CRM 패키지 업데이트</td>
      <td>감지된 현재 패키지는 더 이상 지원되지 않습니다.</td>
      <td>패키지를 최신 버전으로 업그레이드하십시오.
        <ul>
          <li><a href="/help/configuration-and-setup/marketo-measure-and-salesforce/best-practices-for-marketo-measure-crm-package.md">우수 사례</a>
          </li>
          <li><a href="/help/marketo-measure-and-dynamics/getting-started-with-marketo-measure-and-dynamics/microsoft-dynamics-crm-installation-guide.md">Dynamics</a>
          </li>
          <li><a href="/help/configuration-and-setup/marketo-measure-and-salesforce/marketo-measure-salesforce-package-installation-and-set-up.md">Salesforce</a>
          </li>
        </ul>
      </td>
    </tr>
  </tbody>
</table>
