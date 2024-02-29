---
description: 오류 알림 - [!DNL Marketo Measure]
title: 오류 알림
feature: Fundamentals
source-git-commit: 915e9c5a968ffd9de713b4308cadb91768613fc5
workflow-type: tm+mt
source-wordcount: '607'
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
      <td>에서 다음 Salesforce 설명서를 참조하십시오. <a href="https://help.salesforce.com/s/articleView?id=sf.branded_apps_commun_api_permset.htm&amp;type=5">api 액세스를 활성화하는 방법</a>.</td>
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
      <td>INVALID_ANALYTICS_ADOBE</td>
      <td>AdobeAnalytics 내보내기 중 오류 발생: INVALID_UPLOAD_ANALYTICS_CONFIGURATION : 오류: ADOBE이 허용되지 않습니다. 업로드하기 전에 데이터 소스 스키마를 확인합니다. 데이터 소스 Id:1234</td>
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
      <td>알림에 표시된 소스 시스템(Ad, Crm, Marketo)에서 레코드와 연결된 통화에 지원되고 유효한 통화가 있는지 확인합니다. 지원되는 통화는 ISO 통화 표준에서 파생됩니다.</td>
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
      <td>NULL_EMPTY_CURRENCY_ISO_CODE</td>
      <td>
        <p>
          Crm 가져오기 중 오류 발생: NULL_EMPTY_CURRENCY_ISO_CODE: RecordId 1234에 대해 MultiCurrency가 활성화된 경우 통화 ISO 코드가 NULL이거나 비어 있습니다.
      </td>
      <td>통화는 지원되는 ISO 통화 코드여야 합니다.</td>
      <td>알림에 표시된 소스 시스템(Ad, Crm, Marketo)에서 레코드와 연결된 통화에 지원되고 유효한 통화가 있는지 확인합니다. 지원되는 통화는 ISO 통화 표준에서 파생됩니다.</td>
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
