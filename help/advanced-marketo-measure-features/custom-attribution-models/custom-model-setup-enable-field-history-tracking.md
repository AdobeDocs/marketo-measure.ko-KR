---
unique-page-id: 18874777
description: 사용자 지정 모델 설정 - 필드 내역 추적 활성화 - [!DNL Marketo Measure]
title: 사용자 지정 모델 설정 - 필드 내역 추적 활성화
exl-id: 70328e67-051b-4864-891b-b251e49859c2
feature: Custom Models
source-git-commit: 915e9c5a968ffd9de713b4308cadb91768613fc5
workflow-type: tm+mt
source-wordcount: '307'
ht-degree: 0%

---

# 사용자 지정 모델 설정: 필드 내역 추적 활성화 {#custom-model-setup-enable-field-history-tracking}

## 필드 내역 추적을 활성화해야 하는 이유 및 시기 {#why-and-when-to-enable-field-history-tracking}

사용자 지정 속성 모델에 사용자 지정 필드를 단계로 포함하기로 결정하는 경우 필드 내역 추적 **은(는) 활성화되어야 합니다.** 이 필드에 대해 선택합니다. 필드 내역 추적을 활성화하면 [!DNL Salesforce] 기록 추적 테이블에서 기록을 생성하여 사용자 정의 필드를 편집할 때마다 추적합니다. [!DNL Marketo Measure] 은 해당 테이블을 다운로드하고 이 정보를 사용하여 &quot;전환&quot;이 발생한 시간 및 일을 측정할 수 있습니다. 필드 내역 추적 없이, [!DNL Marketo Measure] 이 필드와 관련된 변경 사항을 추적할 수 없습니다.

If only [!UICONTROL Lead Status] 또는 Opportunity Stage 가 사용자 정의 모델에 사용되면 Field History Tracking 이 Stage Transition으로 자동 추적되므로 On 할 필요가 없습니다.

필드 내역 추적을 활성화하려면 아래 지침을 따르십시오.

## 필드 내역 추적 활성화 {#enable-field-history-tracking}

>[!NOTE]
>
>Lead/Contact/Opportunity 객체의 필드를 변경하려면 시스템 관리자여야 합니다.

1. 사용자 지정 필드가 있는 개체로 이동하여 **[!UICONTROL Set History Tracking]** 단추를 클릭합니다.

   ![](assets/1.png)

1. 변경 사항을 추적할 필드를 선택합니다.

   ![](assets/2.png)

[!DNL Marketo Measure] 는 레코드가 최근에 수정된 경우에만 레코드를 다시 가져올 수 있습니다. 수식 필드는 백그라운드에서 계산을 수행하므로 레코드가 변경될 때 기술적으로 수정되지 않습니다. 다음 이유로 규칙이 생략되는 문제가 발견되었습니다. [!DNL Marketo Measure] 이(가) 레코드 변경을 보지 못했으므로 다음을 수행하는 것이 좋습니다. **규칙 정의에 공식 필드를 사용하지 않음**. 해결 방법은 텍스트 필드를 만들고 워크플로우를 사용하여 레코드가 편집되거나 기준에 맞을 때마다 적절한 값 또는 계산으로 해당 필드를 채우는 것입니다. 이를 위해서는 워크플로가 이전 레코드에서 소급하여 작업할 수 있도록 모든 레코드가 편집되어야 합니다.
