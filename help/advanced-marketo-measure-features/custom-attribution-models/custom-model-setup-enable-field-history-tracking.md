---
unique-page-id: 18874777
description: 사용자 지정 모델 설정 - 필드 내역 추적 활성화 - [!DNL Marketo Measure] - 제품 설명서
title: 사용자 지정 모델 설정 - 필드 내역 추적 활성화
exl-id: 70328e67-051b-4864-891b-b251e49859c2
source-git-commit: b59c79236d3e324e8c8b07c5a6d68bd8176fc8a9
workflow-type: tm+mt
source-wordcount: '310'
ht-degree: 0%

---

# 사용자 지정 모델 설정: 필드 기록 추적 활성화 {#custom-model-setup-enable-field-history-tracking}

## 필드 기록 추적을 활성화하는 이유 및 시기 {#why-and-when-to-enable-field-history-tracking}

사용자 지정 필드를 사용자 지정 속성 모델의 스테이지로 포함하기로 결정하는 경우 필드 내역 추적 **를 사용해야 합니다.** 참조하십시오. 필드 기록 추적을 활성화하면 [!DNL Salesforce] 작업 내역 추적 테이블에서 레코드를 만들어 사용자 지정 필드가 편집될 때마다 추적하려면 [!DNL Marketo Measure] 해당 테이블을 다운로드하고 이 정보를 사용하여 &quot;전환&quot;이 발생한 시간과 일을 측정할 수 있습니다. 필드 기록 추적 없이 [!DNL Marketo Measure] 이(가) 이 필드와 관련된 변경 사항을 추적할 수 없습니다.

다음의 경우에만 [!UICONTROL Lead Status] 또는 Opportunity Stage는 사용자 지정 모델에서 사용되며 Stage 전환으로 자동으로 추적되므로 Field History 추적을 설정할 필요가 없습니다.

필드 기록 추적을 활성화하려면 아래 지침을 따르십시오.

## 필드 기록 추적 활성화 {#enable-field-history-tracking}

>[!NOTE]
>
>Lead/Contact/Opportunity 객체의 필드를 변경하려면 시스템 관리자가 되어야 합니다.

1. 사용자 지정 필드가 있는 개체로 이동하고 **[!UICONTROL Set History Tracking]** 버튼을 클릭합니다.

   ![](assets/1.png)

1. 변경 사항을 추적할 필드를 선택합니다.

   ![](assets/2.png)

[!DNL Marketo Measure] 레코드가 최근에 수정된 것으로 보이는 경우에만 레코드를 다시 가져올 수 있습니다. 공식 필드는 백그라운드에서 계산을 수행하므로 변경 시 기본적으로 레코드를 수정하지 않습니다. 규칙이 건너뛸 때 [!DNL Marketo Measure] 레코드가 변경되지 않았으므로 **규칙 정의에 수식 필드를 사용하지 않습니다.**. 해결 방법은 텍스트 필드를 만들고 워크플로우를 사용하여 레코드가 편집되거나 기준에 맞을 때마다 해당 필드를 적절한 값 또는 계산으로 채우는 것입니다. 이렇게 하려면 워크플로우가 이전 레코드에서 소급하여 작동할 수 있도록 모든 레코드를 편집해야 합니다.
