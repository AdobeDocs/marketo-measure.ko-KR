---
unique-page-id: 18874706
description: 보안 세션 제한 - IP 주소 허용 목록 - Marketo Measure - 제품 설명서
title: 보안 세션 제한 - IP 주소 허용 목록
exl-id: aaf5190f-893c-4872-8d03-93f516e70a59
feature: Tracking
TQID: https://experienceleague.adobe.com/Ka7ff5qarBVEm4JdSGCbaUM3Mrug0r3ZOPSKPrnc3Zo
product_v2: id: e6fc4016-a972-4f36-8c30-a6a5f82ad0c8
topic_v2: id: d095671a-1355-40aa-8b5f-06c33c68080bid: eddd9b14-83bd-4ff4-9072-54a4a484abb7
source-git-commit: 9ceb54139bfa9b6ce7c2c5fbb4e25e649f5708a3
workflow-type: tm+mt
source-wordcount: 76
ht-degree: 0%

---

# 보안 세션 제한: IP 주소 허용 목록 {#security-session-restrictions-ip-addresses-to-allowlist}

특정 IP 주소가 데이터를 [!DNL Salesforce] 인스턴스로 푸시하거나 가져오지 못하게 하는 [세션 보안 설정](https://help.salesforce.com/articleView?id=admin_sessions.htm&type=0){target="_blank"}이 있는 경우 [!DNL Marketo Measure]에서 데이터를 [!DNL Salesforce]으로 푸시할 수 있도록 하려면 다음 IP 범위를 허용 목록에추가된으로 설정해야 합니다.

* 52.162.84.192 - 52.162.84.207
* 23.100.229.112 - 23.100.229.127
* 20.186.163.0 - 20.186.163.15

Salesforce에서 [!DNL Marketo Measure]개의 IP를 신뢰할 수 있는 IP 범위에 추가하려면 **[!UICONTROL Setup]** > **[!UICONTROL Administration Setup]** > **[!UICONTROL Security Controls]** > **[!UICONTROL Network Access]** > **[!UICONTROL New]**&#x200B;을(를) 클릭합니다.

![](assets/1.png)
