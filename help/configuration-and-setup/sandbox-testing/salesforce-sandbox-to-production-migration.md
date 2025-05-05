---
unique-page-id: 18874694
description: Salesforce 샌드박스를 프로덕션으로 마이그레이션 - [!DNL Marketo Measure]
title: Salesforce 샌드박스를 프로덕션으로 마이그레이션
exl-id: b2b71c4a-f192-43ce-a27e-cbd0ec3cf008
feature: Salesforce
source-git-commit: 915e9c5a968ffd9de713b4308cadb91768613fc5
workflow-type: tm+mt
source-wordcount: '294'
ht-degree: 0%

---

# Salesforce 샌드박스를 프로덕션으로 마이그레이션 {#salesforce-sandbox-to-production-migration}

[!DNL Salesforce] 샌드박스 환경에서 [!DNL Marketo Measure]을(를) 테스트하도록 선택한 경우 다음 지침에 따라 준비가 되면 프로덕션으로 마이그레이션하십시오. 다음 지침은 이미 [!DNL Marketo Measure] 패키지를 샌드박스 조직에 다운로드하고 필요한 테스트를 수행했으며 [!DNL Marketo Measure]을(를) 프로덕션에 푸시할 준비가 되었다고 가정합니다.

## 1단계: 프로덕션 [!DNL Salesforce] 인스턴스에 [!DNL Marketo Measure] 패키지 설치

* &quot;[!UICONTROL All Users]&quot; 설정으로 프로덕션에 [!DNL Marketo Measure] 패키지 설치

   * [기본 패키지](https://appexchange.salesforce.com/appxListingDetail?listingId=a0N3000000B3KLuEAN){target="_blank"}

* [!DNL Salesforce]과(와)의 [!DNL Marketo Measure] 관계에 대한 자세한 내용은 [이 문서](/help/configuration-and-setup/marketo-measure-and-salesforce/how-marketo-measure-and-salesforce-interact.md)를 참조하세요.
* [!DNL Salesforce] 구성이 필요합니다. 특정 작업 항목은 [아래 4단계](#salesforce-configuration)에서 아래에 요약되어 있습니다.

## 2단계: [!DNL Marketo Measure] 앱에서 현재 샌드박스 CRM 연결 삭제 {#delete-the-current-sandbox-crm-connection-in-marketo-measure-app}

* experience.adobe.com/marketo-measure에서 [!DNL Marketo Measure] 응용 프로그램에 로그인합니다.
* 내 계정 >[!UICONTROL Settings] >[!UICONTROL Connections] (으)로 이동
* SFDC 연결 옆에 있는 휴지통 아이콘을 클릭하여 삭제합니다.
* 삭제를 확인하는 메시지가 표시됩니다. 프롬프트를 주의 깊게 읽고 삭제 결과를 이해해야 합니다.

  ![](assets/salesforce-sandbox-to-production-migration-1.png)

   * 확인 모델에 표시되는 대로 비즈니스 이름을 입력하고 &quot;결과 확인, 이 연결 삭제&quot;를 클릭합니다.
* 이 작업은 삭제 프로세스를 트리거하며 완료하는 데 시간이 소요됩니다

## 3단계: [!DNL Marketo Measure] 앱에서 프로덕션 CRM 인스턴스 연결 {#connect-the-production-crm-instance-in-marketo-measure-app}

* experience.adobe.com/marketo-measure에서 [!DNL Marketo Measure] 응용 프로그램에 로그인합니다.
* [!UICONTROL My Account] >[!UICONTROL Settings] > [!UICONTROL Connections] (으)로 이동
* 샌드박스 연결 삭제가 정상적으로 삭제되면 연결이 페이지에서 사라집니다. 그렇지 않으면 연결이 여전히 &quot;삭제 진행 중&quot; 상태로 표시됩니다.
* &quot;[!UICONTROL Set up New CRM connection]&quot; 클릭
* &quot;[!UICONTROL Select CRM Connection]&quot; 모달 대화 상자에서 [!DNL Salesforce] 플랫폼 옆의 &quot;[!UICONTROL Connect]&quot; 작업을 클릭하고 &quot;[!UICONTROL Production]&quot; 옵션을 선택합니다
* 자격 증명을 입력하라는 메시지가 표시되면 프로덕션 로그인 세부 정보를 입력해야 합니다.

## 4단계: Salesforce 구성 {#salesforce-configuration}

[페이지 레이아웃](/help/configuration-and-setup/marketo-measure-and-salesforce/page-layout-instructions.md)

[사용 권한 집합](/help/configuration-and-setup/marketo-measure-and-salesforce/marketo-measure-permission-sets.md)

[보고서 공유](https://help.salesforce.com/s/articleView?language=en_US&amp;id=analytics_share_folder.htm&amp;type=0){target="_blank"}

[불필요한 보고서 유형 숨기기](/help/configuration-and-setup/marketo-measure-and-salesforce/hiding-unnecessary-report-types.md)

[해당되는 경우 사용자 정의 워크플로](/help/advanced-marketo-measure-features/custom-revenue-amount/using-a-custom-revenue-amount-field.md)
