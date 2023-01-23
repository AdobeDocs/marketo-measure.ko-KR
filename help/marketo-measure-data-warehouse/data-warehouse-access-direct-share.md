---
description: Data Warehouse 액세스 - 직접 공유 - 제품 설명서
title: Data Warehouse 액세스 - 직접 공유
exl-id: 940c3316-5f94-4aa2-a656-aec5eb7b7450
source-git-commit: 36ee02b2dfc2651987f72fc7f02fe629717f02a0
workflow-type: tm+mt
source-wordcount: '298'
ht-degree: 0%

---

# Data Warehouse 액세스 - 직접 공유 {#data-warehouse-access-direct-share}

## 요구 사항 {#requirements}

대상 [!DNL Marketo Measure] data warehouse에 대한 직접 공유를 설정하려면 다음 요구 사항을 충족해야 합니다.

* 자체 Snowflake 인스턴스가 있습니다.
* Snowflake 인스턴스가 Azure East US 2 Snowflake 영역에 있습니다.
* 다음을 제공합니다 [!DNL Marketo Measure] Snowflake 계정 id와 함께 사용할 수 있습니다.

## 제한 사항 {#limitations}

[!DNL Marketo Measure] 은(는) 현재 Snowflake 직접 공유 제한 사항으로 인해 Azure 동부 미국 2에 있는 계정의 Snowflake 직접 공유만 설정할 수 있습니다. 데이터를 다른 Snowflake 지역에서 사용할 수 있도록 해야 하는 경우 Azure 동부 미국 2에 있는 Snowflake 계정에서 데이터 사본을 만들고 [Snowflake 데이터베이스 복제](https://docs.snowflake.com/en/user-guide/database-replication-intro.html){target="_blank"} 선택한 Snowflake 지역/계정에서 데이터를 복사하는 기능입니다.

## Snowflake 계정 ID 입력 {#enter-snowflake-account-id}

를 엽니다. **설정** Marketo 측정 앱의 섹션을 찾아 **Data Warehouse** 페이지. 에서 **직접 공유** 섹션에서 [Snowflake 계정 id](https://docs.snowflake.com/en/user-guide/admin-account-identifier.html){target="_blank"} 제공된 상자에서 를 클릭하고 **Connect**.

![](assets/data-warehouse-access-direct-share-1.png)

## 공유 액세스 {#accessing-the-share}

제공된 계정 ID에 대한 공유가 생성되면, 다음을 완료해야 합니다 [설정 단계](https://docs.snowflake.com/en/user-guide/data-share-consumers.html){target="_blank"} Snowflake 인스턴스 내에서 데이터를 액세스할 수 있습니다.

>[!NOTE]
>
>원하는 데이터베이스 이름을 선택할 수 있습니다. Snowflake 인스턴스에 있는 한 선택한 롤에 권한을 할당할 수 있습니다.

* 계정 관리자 역할 사용

```
USE ROLE ACCOUNTADMIN
```

* 사용 가능한 공유 보기(부여된 공유 이름이 표시됨)

```
SHOW SHARES
```

* 공유를 위한 데이터베이스 만들기

```
CREATE DATABASE <database_name> FROM SHARE <provider_account>.<share_name>
```

* 공유 데이터베이스에 대한 권한 부여

```
GRANT IMPORTED PRIVILEGES ON DATABASE <database_name> TO ROLE <role_name>
GRANT IMPORTED PRIVILEGES ON ALL SCHEMAS IN DATABASE <database_name> TO ROLE <role_name>
```

Snowflake UI에서 이러한 단계를 수행하는 자세한 지침 및 단계는 다음을 참조하십시오 [Snowflake 설명서 직접](https://docs.snowflake.com/en/user-guide/data-share-consumers.html){target="_blank"}.
