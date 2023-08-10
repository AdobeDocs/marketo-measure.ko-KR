---
description: Data Warehouse 액세스 - 직접 공유 - 제품 설명서
title: Data Warehouse 액세스 - 직접 공유
exl-id: 940c3316-5f94-4aa2-a656-aec5eb7b7450
feature: Data Warehouse
source-git-commit: 8ac315e7c4110d14811e77ef0586bd663ea1f8ab
workflow-type: tm+mt
source-wordcount: '298'
ht-degree: 0%

---

# Data Warehouse 액세스 - 직접 공유 {#data-warehouse-access-direct-share}

## 요구 사항 {#requirements}

주문 [!DNL Marketo Measure] data warehouse에 대한 직접 공유를 설정하려면 다음 요구 사항을 충족해야 합니다.

* 고유한 Snowflake 인스턴스가 있습니다.
* Snowflake 인스턴스는 Azure East US 2 Snowflake 영역에 있습니다.
* 다음을 제공합니다. [!DNL Marketo Measure] (Snowflake 계정 id 포함)

## 제한 사항 {#limitations}

[!DNL Marketo Measure] 은(는) 현재 Snowflake 직접 공유 제한 사항으로 인해 Azure East US 2에 있는 계정과 Snowflake 직접 공유만 설정할 수 있습니다. 다른 Snowflake 지역에서 데이터를 사용할 수 있도록 해야 하는 경우 Azure East US 2에 있는 Snowflake 계정에서 데이터 복사본을 만들고 을 활용하는 것이 좋습니다. [Snowflake 데이터베이스 복제](https://docs.snowflake.com/en/user-guide/database-replication-intro.html){target="_blank"} 선택한 Snowflake 영역/계정에서 데이터를 복사하는 기능입니다.

## Snowflake 계정 ID 입력 {#enter-snowflake-account-id}

를 엽니다. **설정** 섹션으로 이동하여 Marketo Measure 앱 **Data Warehouse** 페이지를 가리키도록 업데이트하는 중입니다. 다음에서 **직접 공유** 섹션, 다음을 입력합니다. [Snowflake 계정 id](https://docs.snowflake.com/en/user-guide/admin-account-identifier.html){target="_blank"} 입력란에 표시하고 **연결**.

![](assets/data-warehouse-access-direct-share-1.png)

## 공유 액세스 {#accessing-the-share}

제공된 계정 ID에 대해 공유가 생성되면 다음을 완료해야 합니다. [설정 단계](https://docs.snowflake.com/en/user-guide/data-share-consumers.html){target="_blank"} 데이터에 액세스하기 위해 Snowflake 인스턴스 내에서

>[!NOTE]
>
>원하는 데이터베이스 이름을 선택할 수 있습니다. Snowflake 인스턴스에 존재하는 한 선택한 모든 롤에 권한을 지정할 수 있습니다.

* 계정 관리자 역할 사용

```
USE ROLE ACCOUNTADMIN
```

* 사용 가능한 공유 보기(부여된 공유 이름이 표시됨)

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

Snowflake UI에서 이러한 단계를 수행하는 자세한 지침 및 단계는 를 참조하십시오. [Snowflake 설명서 직접](https://docs.snowflake.com/en/user-guide/data-share-consumers.html){target="_blank"}.
