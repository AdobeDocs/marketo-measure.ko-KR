---
unique-page-id: 18874698
description: ' [!DNL Marketo Measure] 프로필 만들기 - [!DNL Marketo Measure]'
title: ' [!DNL Marketo Measure] 프로필 만들기'
exl-id: dab2e2cb-fbd3-464a-9bd7-e9bf153d9848
feature: Salesforce
source-git-commit: 915e9c5a968ffd9de713b4308cadb91768613fc5
workflow-type: tm+mt
source-wordcount: '176'
ht-degree: 0%

---

# [!DNL Marketo Measure] 프로필 만들기 {#creating-a-marketo-measure-profile}

[!DNL Marketo Measure] 프로필을 만드는 방법을 알아봅니다. [!DNL Marketo Measure] 프로필을 만들면 CRM으로 데이터를 푸시할 때 유효성 검사 오류가 발생하지 않습니다.

1. 특정 [!DNL Marketo Measure] 프로필 만들기:

   * [!DNL Marketo Measure] 관리자 권한 집합 할당
   * 전환된 리드를 보고 편집할 수 있는 권한 활성화

   >[!NOTE]
   >
   >이 프로필은 [!DNL System Admin] 프로필의 복제일 수 있습니다.

1. 전용 [!DNL Marketo Measure] 사용자를 만들었습니다.

   * 해당 사용자에게 새 [!DNL Marketo Measure] 프로필 할당
   * 사용자 수준 권한으로 &quot;마케팅 사용자&quot;를 활성화합니다.

1. 모든 트리거, 워크플로우 및 프로세스에서 이 프로필을 제외합니다.
1. [!DNL Marketo Measure] 계정에 로그인하고 새 사용자와의 [!DNL Salesforce] 연결을 다시 승인합니다.

   * [experience.adobe.com/marketo-measure](https://experience.adobe.com/marketo-measure){target="_blank"}(으)로 이동하여 새 사용자 프로덕션 Salesforce 자격 증명으로 로그인합니다.
   * &quot;[!UICONTROL My Account]&quot; 드롭다운 내에서 &quot;[!UICONTROL Settings]&quot; 선택
   * &quot;[!UICONTROL Integrations]&quot; 그룹화 내에서 &quot;[!UICONTROL Connections]&quot; 선택
   * 현재 연결된 [!DNL Salesforce] 연결 오른쪽에 있는 키 아이콘을 클릭하고 프로덕션으로 재인증하도록 선택합니다. 그런 다음 메시지가 표시되면 새 사용자 자격 증명으로 다시 로그인합니다

   완료!

   전용 [!DNL Marketo Measure] 프로필 만들기에 대한 질문이 있는 경우 Adobe 계정 팀(계정 관리자) 또는 [Marketo 지원](https://nation.marketo.com/t5/support/ct-p/Support){target="_blank"}에 문의하세요.
