---
unique-page-id: 18874694
description: Salesforce Sandbox에서 Production으로 마이그레이션 - [!DNL Marketo Measure] - 제품 설명서
title: Salesforce Sandbox에서 프로덕션 마이그레이션으로 마이그레이션
exl-id: b2b71c4a-f192-43ce-a27e-cbd0ec3cf008
source-git-commit: b59c79236d3e324e8c8b07c5a6d68bd8176fc8a9
workflow-type: tm+mt
source-wordcount: '329'
ht-degree: 0%

---

# Salesforce Sandbox에서 프로덕션 마이그레이션으로 마이그레이션 {#salesforce-sandbox-to-production-migration}

테스트를 선택한 경우 [!DNL Marketo Measure] 에서 [!DNL Salesforce] 샌드박스 환경을 사용하려면 다음 지침에 따라 준비가 되면 프로덕션으로 마이그레이션하십시오. 다음 지침은 를 이미 다운로드했다고 가정합니다. [!DNL Marketo Measure] 를 Sandbox 조직에 패키지로 만들고, 필요한 테스트를 수행하며, 푸시할 준비가 되었습니다. [!DNL Marketo Measure] 프로덕션에 추가할 수 있습니다.

## 1단계: 설치 [!DNL Marketo Measure] 프로덕션에 패키지 [!DNL Salesforce] 인스턴스 {#install-marketo-measure-packages-into-your-production-salesforce-instance}

* 두 개 설치 [!DNL Marketo Measure] 는 &quot;[!UICONTROL All Users]&quot; 설정

   * [기본 패키지](https://appexchange.salesforce.com/appxListingDetail?listingId=a0N3000000B3KLuEAN){target=&quot;_blank&quot;}
   * [대시보드 확장 패키지](https://login.salesforce.com/packaging/installPackage.apexp?p0=04t610000001jI6){target=&quot;_blank&quot;}

* 에 대한 자세한 정보 [!DNL Marketo Measure] 관계 [!DNL Salesforce]를 살펴보고 [이 문서](/help/configuration-and-setup/marketo-measure-and-salesforce/how-marketo-measure-and-salesforce-interact.md)
* 약간 [!DNL Salesforce] 구성이 필요합니다. 특정 작업 항목은 아래에 요약되어 있습니다. [아래의 4단계](#salesforce-configuration)

## 2단계: 에서 현재 샌드박스 CRM 연결 삭제 [!DNL Marketo Measure] 앱 {#delete-the-current-sandbox-crm-connection-in-marketo-measure-app}

* 에 로그인합니다. [!DNL Marketo Measure] experience.adobe.com/marketo-measure
* 내 계정 >[!UICONTROL Settings] >[!UICONTROL Connections]
* 삭제할 SFDC 연결 옆에 있는 휴지통 아이콘을 클릭합니다
* 삭제를 확인하는 메시지가 표시됩니다. 메시지를 주의 깊게 읽고 삭제의 결과를 이해하십시오

   ![](assets/salesforce-sandbox-to-production-migration-1.png)

   * 확인 모델에 나타나는 비즈니스 이름을 입력하고 &quot;I understanding the result, delete this connection&quot;을 클릭합니다.
* 이렇게 하면 삭제 프로세스가 트리거되며 완료하는 데 시간이 소요됩니다

## 3단계: 에서 프로덕션 CRM 인스턴스 연결 [!DNL Marketo Measure] 앱 {#connect-the-production-crm-instance-in-marketo-measure-app}

* 에 로그인합니다. [!DNL Marketo Measure] experience.adobe.com/marketo-measure
* 다음으로 이동 [!UICONTROL My Account] >[!UICONTROL Settings] > [!UICONTROL Connections]
* 샌드박스 연결이 성공적으로 삭제되면 연결이 페이지에서 사라집니다. 그렇지 않으면 연결이 &quot;삭제 진행 중&quot; 상태로 계속 표시됩니다
* 클릭 &quot;[!UICONTROL Set up New CRM connection]&quot;
* 에서[!UICONTROL Select CRM Connection]&quot; 모달 대화 상자에서 &quot;[!UICONTROL Connect]&quot; 작업 [!DNL Salesforce] 플랫폼, &quot;[!UICONTROL Production]&quot; 옵션
* 자격 증명을 입력하라는 메시지가 표시되면 프로덕션 로그인 세부 정보를 입력해야 합니다

## 4단계: Salesforce 구성 {#salesforce-configuration}

[페이지 레이아웃](/help/configuration-and-setup/marketo-measure-and-salesforce/page-layout-instructions.md)

[권한 집합](/help/configuration-and-setup/marketo-measure-and-salesforce/marketo-measure-permission-sets.md)

[보고서 공유](https://help.salesforce.com/articleView?id=analytics_share_folder.htm&amp;type=0){target=&quot;_blank&quot;}

[불필요한 보고서 유형 숨기기](/help/configuration-and-setup/marketo-measure-and-salesforce/hiding-unnecessary-report-types.md)

[해당되는 경우 사용자 지정 워크플로우](/help/advanced-marketo-measure-features/custom-revenue-amount/using-a-custom-revenue-amount-field.md)
