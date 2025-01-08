---
description: Data Warehouse 액세스 - Reader 계정 - 제품 설명서
title: Data Warehouse 액세스 - Reader 계정
exl-id: 2aa73c41-47ab-4f11-96d8-dafb642308fc
feature: Data Warehouse
source-git-commit: e9861f8032475d3e60a3bb3ebf67dfee520bbb75
workflow-type: tm+mt
source-wordcount: '479'
ht-degree: 0%

---

# Data Warehouse 액세스 - Reader 계정 {#data-warehouse-access-reader-account}

## Snowflake 액세스 링크 {#snowflake-access-link}

Snowflake Data Warehouse에 액세스하려면 Snowflake 계정의 특정 URL로 이동해야 합니다. [!DNL Marketo Measure]에 로그인한 다음 아래 단계에 따라 Data Warehouse 정보 페이지로 이동하여 이 액세스 링크를 찾을 수 있습니다.

1. [!DNL Marketo Measure]의 페이지 맨 위에서 **[!UICONTROL My Account]** > **[!UICONTROL Settings]**&#x200B;을(를) 클릭합니다.

   ![](assets/data-warehouse-access-reader-account-1.png)

1. 왼쪽 메뉴에서 보안 아래의 **[!UICONTROL Data Warehouse]**&#x200B;을(를) 클릭합니다.

   ![](assets/data-warehouse-access-reader-account-2.png)

1. 이 페이지에는 Snowflake Data Warehouse 및 사용자 이름에 대한 링크가 있습니다.

   ![](assets/data-warehouse-access-reader-account-3.png)

   >[!NOTE]
   >
   >이는 개별 사용자가 아닌 조직에서 사용할 수 있는 읽기 전용 계정입니다. 조직 내에서 [!DNL Marketo Measure]에 액세스할 수 있는 모든 사용자는 이 계정을 사용하여 Snowflake Data Warehouse 판독기 계정에 로그인할 수 있습니다.

1. Snowflake URL에 제공된 링크를 클릭하면 사용자 이름과 암호를 입력하는 Snowflake 로그인 페이지로 이동합니다. _암호가 없는 경우 아래 단계를 참조하여 암호를 재설정하십시오_.

   ![](assets/data-warehouse-access-reader-account-4.png)

1. 로그인하고 나면 페이지 상단의 **[!UICONTROL Worksheets]**&#x200B;을(를) 클릭합니다.

   ![](assets/data-warehouse-access-reader-account-5.png)

1. BIZIBLE_ROI_V3 데이터베이스 개체는 화면 왼쪽에 있습니다. 쿼리 창 상단의 드롭다운 옵션에서 웨어하우스, 데이터베이스 및 스키마를 입력합니다. 각 옵션에는 하나만 있어야 합니다. 이제 Snowflake 쿼리 편집기 내에서 쿼리를 실행할 준비가 되었습니다.

   ![](assets/data-warehouse-access-reader-account-6.png)

## 암호 재설정 {#reset-your-password}

[!DNL Marketo Measure]은(는) Snowflake 로그인 암호에 액세스할 수 없습니다. 암호를 다시 설정해야 하는 경우 Data Warehouse 정보 페이지에서 [!UICONTROL Reset Password] 단추를 클릭하고 지침을 따릅니다. 임시 암호가 UI에 즉시 표시됩니다. 다음 Data Warehouse 로그인 시 암호를 만들라는 메시지가 표시됩니다.

>[!NOTE]
>
>* 암호를 재설정하면 현재 로그인한 사용자뿐만 아니라 조직의 모든 [!DNL Marketo Measure] 사용자에 대해 재설정됩니다.
>* UI에는 임시 암호만 표시됩니다. 이메일이 전송되지 않습니다.

![](assets/data-warehouse-access-reader-account-7.png)

![](assets/data-warehouse-access-reader-account-8.png)

## 서드파티 도구를 통해 Snowflake에 연결 {#connecting-to-snowflake-via-third-party-tools}

Snowflake 데이터 웨어하우스를 서드파티 도구에 연결하려면 몇 가지 정보를 입력해야 합니다.

>[!NOTE]
>
>각 도구에는 서로 다른 연결 요구 사항이 있습니다. 연결하려는 특정 도구에 대한 설명서를 참조하는 것이 좋습니다.

* **URI**(항상 필요)
   * Snowflake 계정의 도메인 이름입니다. Snowflake 로그인 링크의 일부에 포함되어 있습니다.
* **사용자 이름**(항상 필요)
   * [!DNL Marketo Measure]의 Data Warehouse 정보 페이지에 사용자 이름이 나열됩니다.
* **암호**(항상 필요)
   * Snowflake 계정에 처음 로그인할 때 설정한 암호입니다. 암호를 재설정하려면 위에 설명된 단계를 참조하십시오.
* **데이터베이스 이름**(항상 필요한 것은 아님)
   * 데이터베이스는 Snowflake에 데이터를 저장하는 것입니다. 스토리지 리소스입니다. 데이터베이스 이름이 [!DNL Marketo Measure]의 Data Warehouse 정보 페이지에 나열됩니다.
* **웨어하우스 이름**(항상 필요한 것은 아님)
   * 웨어하우스는 Snowflake에서 쿼리를 실행합니다. 계산된 리소스입니다. 웨어하우스 이름이 [!DNL Marketo Measure]의 Data Warehouse 정보 페이지에 나열됩니다.

  ![](assets/data-warehouse-access-reader-account-9.png)
