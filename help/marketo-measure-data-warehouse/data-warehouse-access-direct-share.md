---
description: Data Warehouse 액세스 - 직접 공유 - 제품 설명서
title: Data Warehouse 액세스 - 직접 공유
exl-id: 940c3316-5f94-4aa2-a656-aec5eb7b7450
feature: Data Warehouse
source-git-commit: bff10626589aba8c3dfe995dabde6eac1fc7809f
workflow-type: tm+mt
source-wordcount: '280'
ht-degree: 0%

---

# Data Warehouse 액세스 - 직접 공유 {#data-warehouse-access-direct-share}

## 요구 사항 {#requirements}

[!DNL Marketo Measure]이(가) 데이터 웨어하우스에 대한 직접 공유를 설정하려면 다음 요구 사항을 충족해야 합니다.

* 고유한 Snowflake 인스턴스가 있습니다.
* Snowflake 인스턴스는 Azure East US 2 Snowflake 지역에 있습니다.
* [!DNL Marketo Measure]에게 Snowflake 계정 ID를 제공합니다.

## 제한 사항 {#limitations}

[!DNL Marketo Measure]은(는) Azure East US 2에 있는 계정으로 Snowflake Direct 공유를 설정할 수 있습니다(Marketo Measure의 제한 사항이며 Snowflake의 제한 사항은 아님). 다른 Snowflake 지역에서 데이터를 사용할 수 있도록 해야 하는 경우 미국 동부 2에 있는 Snowflake 계정에서 데이터 복사본을 만들고 [Snowflake 데이터베이스 복제](https://docs.snowflake.com/en/user-guide/database-replication-intro.html){target="_blank"} 기능을 사용하여 선택한 Snowflake 지역/계정에서 데이터를 복사하는 것이 좋습니다.

## Snowflake 계정 ID 입력 {#enter-snowflake-account-id}

Marketo Measure 앱에서 **설정** 섹션을 열고 **Data Warehouse** 페이지로 이동합니다. **직접 공유** 섹션에서 제공된 상자에 [Snowflake 계정 ID](https://docs.snowflake.com/en/user-guide/admin-account-identifier.html){target="_blank"}를 입력하고 **연결**&#x200B;을 클릭합니다.

![](assets/data-warehouse-access-direct-share-1.png)

## 공유 액세스 {#accessing-the-share}

제공된 계정 ID에 대한 공유를 만든 후에는 Snowflake 인스턴스 내에서 [설정 단계](https://docs.snowflake.com/en/user-guide/data-share-consumers.html){target="_blank"}를 완료해야 데이터에 액세스할 수 있습니다.

>[!NOTE]
>
>원하는 데이터베이스 이름을 선택할 수 있습니다. Snowflake 인스턴스에 존재하는 한 선택한 모든 역할에 권한을 할당할 수 있습니다.

* 계정 관리자 역할 사용

```
USE ROLE ACCOUNTADMIN
```

* 사용 가능한 공유 보기(부여된 공유 이름 표시)

```
SHOW SHARES
```

* 공유에 대한 데이터베이스 만들기

```
CREATE DATABASE <database_name> FROM SHARE <provider_account>.<share_name>
```

* 공유 데이터베이스에 대한 권한 부여

```
GRANT IMPORTED PRIVILEGES ON DATABASE <database_name> TO ROLE <role_name>
GRANT IMPORTED PRIVILEGES ON ALL SCHEMAS IN DATABASE <database_name> TO ROLE <role_name>
```

Snowflake UI에서 이러한 단계를 수행하는 자세한 지침 및 단계는 [Snowflake 설명서를 직접](https://docs.snowflake.com/en/user-guide/data-share-consumers.html){target="_blank"}참조하십시오.
