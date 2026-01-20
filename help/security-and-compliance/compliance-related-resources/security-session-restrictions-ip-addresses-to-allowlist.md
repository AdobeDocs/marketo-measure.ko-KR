---
unique-page-id: 18874706
description: 보안 세션 제한 - IP 주소 허용 목록 - Marketo Measure - 제품 설명서
title: 보안 세션 제한 - IP 주소 허용 목록
exl-id: aaf5190f-893c-4872-8d03-93f516e70a59
feature: Tracking
source-git-commit: 666812e8bf095170d611cd694b5d0ac5151d8fdd
workflow-type: tm+mt
source-wordcount: '70'
ht-degree: 0%

---

# 보안 세션 제한: IP 주소 허용 목록 {#security-session-restrictions-ip-addresses-to-allowlist}

특정 IP 주소가 데이터를 [&#x200B; 인스턴스로 푸시하거나 가져오지 못하게 하는 &#x200B;](https://help.salesforce.com/articleView?id=admin_sessions.htm&type=0){target="_blank"}세션 보안 설정[!DNL Salesforce]이 있는 경우 [!DNL Marketo Measure]에서 데이터를 [!DNL Salesforce]으로 푸시할 수 있도록 하려면 다음 IP 범위를 허용 목록에추가된으로 설정해야 합니다.

* 52.162.84.192 - 52.162.84.207
* 23.100.229.112 - 23.100.229.127
* 20.186.163.0 - 20.186.163.15

Salesforce에서 [!DNL Marketo Measure]개의 IP를 신뢰할 수 있는 IP 범위에 추가하려면 **[!UICONTROL Setup]** > **[!UICONTROL Administration Setup]** > **[!UICONTROL Security Controls]** > **[!UICONTROL Network Access]** > **[!UICONTROL New]**&#x200B;을(를) 클릭합니다.

![](assets/1.png)
