---
unique-page-id: 18874698
description: 만들기 [!DNL Marketo Measure] 프로필 - [!DNL Marketo Measure] - 제품 설명서
title: 만들기 [!DNL Marketo Measure] 프로필
exl-id: dab2e2cb-fbd3-464a-9bd7-e9bf153d9848
feature: Salesforce
source-git-commit: 8ac315e7c4110d14811e77ef0586bd663ea1f8ab
workflow-type: tm+mt
source-wordcount: '186'
ht-degree: 0%

---

# 만들기 [!DNL Marketo Measure] 프로필 {#creating-a-marketo-measure-profile}

을(를) 만드는 방법 알아보기 [!DNL Marketo Measure] 프로필. 만들기 [!DNL Marketo Measure] 프로필은 데이터를 CRM으로 푸시할 때 유효성 검사 오류가 발생하지 않도록 합니다.

1. 특정 만들기 [!DNL Marketo Measure] 프로필:

   * 할당 [!DNL Marketo Measure] 관리자 권한 집합
   * 전환된 리드를 보고 편집할 수 있는 권한 활성화

   >[!NOTE]
   >
   >이 프로필은 의 복제본일 수 있습니다. [!DNL System Admin] 프로필

1. 전용 을(를) 만들었습니다. [!DNL Marketo Measure] 사용자:

   * 새 항목 할당 [!DNL Marketo Measure] 해당 사용자에 대한 프로필
   * 사용자 수준 권한으로 &quot;마케팅 사용자&quot;를 활성화합니다.

1. 모든 트리거, 워크플로우 및 프로세스에서 이 프로필을 제외합니다.
1. 에 로그인 [!DNL Marketo Measure] 계정 및 재인증 [!DNL Salesforce] 새 사용자와의 연결:

   * 다음으로 이동 [experience.adobe.com/marketo-measure](https://experience.adobe.com/marketo-measure){target="_blank"} 새 사용자 프로덕션 Salesforce 자격 증명으로 로그인
   * 선택[!UICONTROL Settings]&quot; 내의 &quot;[!UICONTROL My Account]&quot; 드롭다운
   * 선택[!UICONTROL Connections]&quot; 내의 &quot;[!UICONTROL Integrations]&quot; 그룹화
   * 현재 연결된 항목 오른쪽에 있는 키 아이콘 을 클릭합니다 [!DNL Salesforce] 를 연결하고 프로덕션으로 재인증하려면 을 선택합니다. 그런 다음 메시지가 표시되면 새 사용자 자격 증명으로 다시 로그인합니다

   완료!

   전용 만들기에 대한 질문이 있는 경우 [!DNL Marketo Measure] 프로필에서 Adobe 계정 팀(계정 관리자) 또는 [Marketo 지원](https://nation.marketo.com/t5/support/ct-p/Support){target="_blank"}.
