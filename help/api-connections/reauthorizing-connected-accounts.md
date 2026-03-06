---
description: Marketo Measure 사용자를 위한 연결된 계정 재인증 지침
title: 연결된 계정 재인증
exl-id: 7abd1d67-5bed-45bb-844f-0ffd23c3d7f8
feature: APIs, Integration
hidefromtoc: true
source-git-commit: 7a4661c8d42214d32e5360dc45d6d880b08ef37c
workflow-type: tm+mt
source-wordcount: '204'
ht-degree: 0%

---

# 연결된 계정 재인증 {#reauthorizing-connected-accounts}

[!DNL Marketo Measure] 계정에서 계정 연결이 끊기면 플랫폼의 상태가 &#39;인증 필요&#39;로 변경되고 빨간색 키 아이콘이 표시됩니다.

광고 플랫폼의 연결이 끊기면 [!DNL Marketo Measure]에서 비용 데이터를 다운로드할 수 없거나 자동 태그 지정이 활성화된 경우 [!DNL Marketo Measure] UTM 매개 변수를 새로 만든 광고에 추가합니다. [!DNL Marketo Measure] 는 계정 연결이 끊어진 동안 광고 플랫폼에서 생성된 터치포인트에 UTM 매개 변수를 소급하여 추가할 수 없습니다.

CRM 플랫폼의 연결이 끊기면 [!DNL Marketo Measure]에서 [!DNL Marketo Measure] 데이터를 업데이트하거나 새 터치포인트를 조직에 푸시할 수 없습니다. CRM 연결이 다시 설정되면 [!DNL Marketo Measure]에서 계정 연결이 끊어진 동안 누락된 모든 데이터를 푸시합니다.

![CRM 플랫폼의 연결이 끊기면 Marketo Measure은 &#x200B;](assets/utilizing-connections-7.png)이 되지 않습니다.

## 연결이 끊어진 계정 다시 인증 {#re-authorizing-disconnected-accounts}

1. [experience.adobe.com/marketo-measure](https://experience.adobe.com/marketo-measure){target="_blank"}(으)로 이동하여 로그인합니다.
1. 왼쪽 상단 모서리의 [!UICONTROL My Account] 탭에서 **[!UICONTROL Settings]**&#x200B;을(를) 선택합니다.
1. 왼쪽의 통합 섹션을 찾아 **[!UICONTROL Connections]**&#x200B;을(를) 클릭합니다.
1. 다시 연결해야 하는 계정 옆의 빨간색 키 기호를 선택합니다.
1. 계정에 대한 로그인 세부 정보를 입력하라는 팝업 창이 나타납니다.
