---
unique-page-id: 18874706
description: 보안 세션 제한 - IP 주소 허용 목록 - Marketo Measure - 제품 설명서
title: 보안 세션 제한 - IP 주소 허용 목록
exl-id: aaf5190f-893c-4872-8d03-93f516e70a59
feature: Tracking
source-git-commit: 8ac315e7c4110d14811e77ef0586bd663ea1f8ab
workflow-type: tm+mt
source-wordcount: '79'
ht-degree: 3%

---

# 보안 세션 제한: IP 주소 허용 목록 {#security-session-restrictions-ip-addresses-to-allowlist}

있는 경우 [세션 보안 설정](https://help.salesforce.com/articleView?id=admin_sessions.htm&amp;type=0){target="_blank"} 특정 IP 주소가 데이터를 로 푸시하거나 가져오는 것을 방지함 [!DNL Salesforce] 예를 들어 다음 IP 범위를 허용 목록에추가된으로 허용해야 합니다. [!DNL Marketo Measure] 데이터를 로 푸시하려면 [!DNL Salesforce]:

* 52.162.84.192 - 52.162.84.207
* 23.100.229.112 - 23.100.229.127
* 20.186.163.0 - 20.186.163.15

추가하려면 [!DNL Marketo Measure] Salesforce에서 신뢰할 수 있는 IP 범위에 대한 IP를 **[!UICONTROL Setup]** > **[!UICONTROL Administration Setup]** > **[!UICONTROL Security Controls]** > **[!UICONTROL Network Access]** > **[!UICONTROL New]**.

![](assets/1.png)
