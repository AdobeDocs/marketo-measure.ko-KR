---
description: 최신 릴리스 정보 - [!DNL Marketo Measure] - 제품 설명서
title: 최신 릴리스 정보
exl-id: e93ff03e-ea21-41f4-abb8-32313ee74c0c
feature: Release Notes
source-git-commit: 40cd00c8edeb04c1939db9402d537d4c0e7a3406
workflow-type: tm+mt
source-wordcount: '926'
ht-degree: 0%

---

# 릴리스 노트: 2023 {#release-notes-2023}

아래에는 2023년 릴리스의 모든 새로운 기능과 업데이트된 기능이 있습니다.

## 4분기 릴리스 {#q4-release}

<p>

**웹 트래픽 대시보드**

새롭게 디자인된 [웹 트래픽 대시보드](/help/marketo-measure-discover-ui/dashboards/web-traffic-dashboard.md){target="_blank"} 이제 모든 고객이 액세스할 수 있습니다. 이 대시보드는 웹 사이트의 방문자 상호 작용에 대한 전체 개요를 제공합니다. 특정 양식 URL 또는 랜딩 페이지에서 URL당 고유 방문자 수, 전체 방문, 페이지 보기 수, 양식 제출과 같은 지표를 분석할 수 있습니다. 월별 트래픽 트렌드를 추적하고 성과가 좋은 유료 미디어를 식별할 수도 있으므로 최적의 수익 생성을 위한 전략을 구체화하는 데 도움이 됩니다.

새로운 사전 설치된 대시보드 세트는 올해 말 이전에 완료되어 파동으로 도입될 예정입니다.

>[!NOTE]
>
>현재 대시보드는 2024년 1월 중순까지 사용 중단되지만, 그때까지 두 버전을 모두 활용하여 원활하게 전환할 수 있습니다.

**IP 주소 데이터 제거**

데이터 개인 정보 보호 규정 준수를 보장하기 위해 장기 저장소에서 IP 주소 데이터를 제거하고 있습니다. 현재 다음 Snowflake 테이블 및 뷰에는 IP 주소가 포함되어 있으며 이 데이터를 제거하고 새 지리적 위치 정보를 추가할 계획입니다.

<table style="width:400px">
<thead>
  <tr>
    <th style="width:50%">태블릿</th>
    <th>보기</th>
  </tr>
</thead>
<tbody>
  <tr>
    <td>CUSTOMER_AB_TESTS</td>
    <td>BIZ_CUSTOMER_AB_TESTS</td>
  </tr>
  <tr>
    <td>CUSTOMER_EVENTS</td>
    <td>BIZ_CUSTOMER_EVENTS</td>
  </tr>
  <tr>
    <td>FORM_SUBMISSES</td>
    <td>BIZ_FORM_SUBMITTS</td>
  </tr>
  <tr>
    <td>노출 횟수</td>
    <td>BIZ_IMPTIONS</td>
  </tr>
  <tr>
    <td>PAGE_VIEWS</td>
    <td>BIZ_PAGE_VIEWS</td>
  </tr>
  <tr>
    <td>세션</td>
    <td>BIZ_SESSIONS</td>
  </tr>
  <tr>
    <td>웹 호스트 매핑</td>
    <td>BIZ_WEB_HOST_MAPPING</td>
  </tr>
</tbody>
</table>

* 이제부터 국가 이름, 도시 이름 및 지역 이름 대신 국가 코드, 도시 이름 및 지역 코드를 다운로드합니다.
* 모든 이력 웹 활동의 처리 동안, 레코드 전반에 걸쳐 위치 정보의 불일치가 발생할 수 있다. 이러한 불일치에는 지리적 위치 세부 정보가 없는 IP 주소 존재, IP 주소가 없는 업데이트된 지리적 위치 정보 또는 국가 또는 지역 이름과 코드의 혼합이 포함될 수 있습니다.
* _**이러한 혼재된 데이터 기간은 2023/01/04~2023/02/29 사이에 발생할 것으로 예상된다.**_

**URL 테이블의 페이지 제목 데이터**

의 URL 테이블 [data warehouse](/help/marketo-measure-data-warehouse/data-warehouse-schema.md){target="_blank"} 이제 웹 데이터 테이블 외에 페이지 제목 필드가 포함됩니다.

URL 테이블의 페이지 제목이 다른 웹 테이블의 페이지 제목과 항상 일치하지 않을 수 있습니다. URL 테이블에는 가장 최근의 페이지 제목이 있습니다. 웹 활동이 발생한 후 URL에 대한 제목을 변경한 경우 URL 표의 내용과 일치하지 않습니다.

**대시보드 재디자인 살펴보기**

모든 Marketo Measure 사용자는 향상된 유용성과 부가 가치를 결합한 새로운 디자인의 인앱 대시보드를 경험하게 됩니다. 또한 B2B Go-to-Markets에서 마케팅 투자와 구매 간의 일반적인 지연을 고려한 &quot;실현된 ROI&quot;와 같은 새로운 지표를 소개합니다.

10월 첫째 주에 시작하여 올해 말 이전에 마무리되는 새로운 사전 설치된 대시보드 세트는 물결에 도입될 예정입니다. 이러한 새 대시보드는 제품 내 정보 및 설명서에 대한 링크와 함께 인스턴스에 자동으로 표시됩니다.

* [새로운 Discover Dashboard 안내서](/help/marketo-measure-discover-ui/dashboards/new-discover-dashboard-guide.md){target="_blank"}
* [대시보드 기본 사항 살펴보기](/help/marketo-measure-discover-ui/dashboards/discover-dashboard-basics.md){target="_blank"}
* [수익 개요 대시보드](/help/marketo-measure-discover-ui/dashboards/revenue-overview-dashboard.md){target="_blank"}
* [속성 수익 대시보드](/help/marketo-measure-discover-ui/dashboards/attributed-revenue-dashboard.md){target="_blank"}
* [ROI 대시보드](/help/marketo-measure-discover-ui/dashboards/roi-dashboard.md){target="_blank"}
* [Passport 대시보드](/help/marketo-measure-discover-ui/dashboards/passport-dashboard.md){target="_blank"}

>[!NOTE]
>
>현재 대시보드는 2024년 1월 중순까지 사용 중단되지만, 그때까지 두 버전을 모두 활용하여 원활하게 전환할 수 있습니다.

### 사용 중단 {#deprecations}

<p>

* **Salesforce 필드 사용 중단**

통합을 단순화하고 Salesforce 표준 개체로 내보낼 필요가 없도록 리드/연락처 개체로의 내보내기 작업을 단계적으로 수행할 예정입니다. 고객이 터치포인트 오브젝트에서 동일한 데이터를 얻을 수 있으므로 아래 나열된 비정규화된 필드도 더 이상 사용되지 않습니다. _**사용 중단 기한은 2024년 6월입니다.**_

<table style="width:300px">
<tbody>
  <tr>
    <td>bizible2__Ad_Campaign_Name_FT__c</td>
  </tr>
  <tr>
    <td>bizible2__Ad_Campaign_Name_LC__c</td>
  </tr>
  <tr>
    <td>bizible2__Landing_Page_FT__c</td>
  </tr>
  <tr>
    <td>bizible2__Landing_Page_LC__c</td>
  </tr>
  <tr>
    <td>bizible2__Touchpoint_Date_FT__c</td>
  </tr>
  <tr>
    <td>bizible2__Touchpoint_Date_LC__c</td>
  </tr>
  <tr>
    <td>bizible2__Touchpoint_Source_FT__c</td>
  </tr>
  <tr>
    <td>bizible2__Touchpoint_Source_LC__c</td>
  </tr>
  <tr>
    <td>bizible2__Marketing_Channel_FT__c</td>
  </tr>
  <tr>
    <td>bizible2__Marketing_Channel_LC__c</td>
  </tr>
</tbody>
</table>

* **Dynamics 패키지 관련**

   * Dynamics에 계속 연결하려면 최신 패키지 버전인 v6.12를 설치하십시오. 이전 버전 `(<v6.12)` 은(는) 더 이상 지원되지 않습니다. 이 업데이트는 기록 레코드 생성을 최적화하여 스토리지 사용을 줄입니다.

   * RefreshToken을 사용하는 OAuth의 오래된 메서드는 더 이상 사용되지 않습니다. 다음을 참조하십시오. [이 안내서](/help/marketo-measure-and-dynamics/getting-started-with-marketo-measure-and-dynamics/oauth-with-azure-active-directory-for-dynamics-crm.md){target="_blank"} Microsoft의 ClientSecret 사용 모범 사례를 준수하도록 자격 증명을 업데이트할 수 있습니다.

* **&quot;custom_properties&quot; 필드**

Data Warehouse에서 &quot;custom_properties&quot; 필드는 고정 스키마에서 다루지 않는 추가 데이터 포인트를 위한 저장소 역할을 했습니다. JSON 형식으로 저장된 이 필드는 사용이 제한되고 SQL 쿼리와의 통합이 복잡하여 성능에 영향을 줄 수 있습니다. 이러한 요소들을 고려하여, 우리는 이 분야를 더 이상 사용하지 않기로 결정했다. 이 변경 사항은 주로 Azure 테이블 저장소 내의 데이터 처리 계층 및 데이터 웨어하우스로 내보낸 데이터에 영향을 줍니다.

### 뭐가 오는데? {#q4-whats-coming}

<p>

**인앱 사용자 지정 보고**

Marketo Measure 고객은 처음으로 앱에서 바로 보고서를 만들고 저장할 수 있습니다. 이는 2024년 초에 사전 설치된 대시보드의 릴리스를 따릅니다.

<br>

## 2분기 릴리스 {#q2-release}

<p>

* **Salesforce 패키지 통합**

향상된 사용자 경험과 간소화된 사용을 위해 모든 Salesforce 패키지를 포괄적인 단일 패키지로 병합하고 있습니다. V1, V2_EXT 및 보고 패키지가 다음 분기에 중단됩니다. 새로운 패키지는 이전의 모든 기능을 결합하므로 보다 효율적인 추적을 수행하고 보다 심층적인 고객 통찰력을 얻을 수 있습니다.

이미 V2 패키지를 설치한 고객은 이 패키지를 새로운 통합 버전으로 업데이트해야 합니다.

보고 기능을 향상시키기 위해 두 개의 새 필드가 추가되었습니다.

* form_name: 이제 BT/BAT 객체에서 사용할 수 있으며, 이 필드를 통해 사용자는 양식 이름을 기반으로 보고서를 작성할 수 있습니다.
* user_touchpoint_id: 이 필드를 사용하면 사용자가 고유한 사용자 터치포인트 카운트로 보고서를 만들 수 있습니다.

[이 문서](/help/configuration-and-setup/marketo-measure-and-salesforce/salesforce-package-consolidation.md){target="_blank"} 기존 보고 패키지에서 보고서 및 대시보드를 다시 만드는 방법에 대한 안내서를 포함합니다.

* **Salesforce API 버전 업데이트**

UserActivityContext 클래스를 비롯한 Apex 클래스의 모든 Salesforce API 버전이 지원되는 버전으로 업데이트됩니다. (31.0~57.0)

* **새 패키지 설치**

새로운 통합 패키지 설치 링크 [은(는) 여기에서 찾을 수 있음](https://login.salesforce.com/packaging/installPackage.apexp?p0=04t1P000000VY6Z){target="_blank"}

### 뭐가 오는데? {#q2-whats-coming}

<p>

**IP 주소 스토리지 변경**

개인 정보 보호 고려 사항에 따라 시스템에 더 이상 IP 주소를 저장하지 않습니다. IP 주소의 지리적 위치를 계속 식별하고 저장하지만 형식이 변경됩니다(예: &quot;미국&quot;에서 &quot;미국&quot;으로 변경).
