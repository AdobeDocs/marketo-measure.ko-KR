---
unique-page-id: 18874767
description: 부메랑 단계 설정 - [!DNL Marketo Measure] - 제품 설명서
title: 부메랑 단계 설정
exl-id: 00dd2826-27a3-462e-a70e-4cec90d07f92
source-git-commit: b59c79236d3e324e8c8b07c5a6d68bd8176fc8a9
workflow-type: tm+mt
source-wordcount: '281'
ht-degree: 0%

---

# 부메랑 단계 설정 {#setting-up-boomerang-stages}

활성화하려면 [!UICONTROL Boomerang] 계정의 단계는 계정 관리자여야 합니다. 또는 및에 연락하여 활성화할 수 있습니다 [Marketo 지원](https://nation.marketo.com/t5/support/ct-p/Support){target="_blank"}. 기능이 활성화되면 다음 지침에 따라 설정하십시오.

## 부메랑 스테이지 설정 {#boomerang-stage-setup}

1. 이동 [!UICONTROL Stage Mapping]. 열 아래에 &quot;[!UICONTROL Boomerang]추적하려는 단계 옆에 있는 상자를 선택합니다.

   ![](assets/1-2.png)

1. 로 이동합니다. [!UICONTROL Attribution Settings] 탭하여 확인할 각 스테이지의 터치포인트 수를 입력합니다. 최대 10개까지 가능합니다 기본값은 1로 설정되어 있습니다.

   ![](assets/2-2.png)

1. 클릭 **[!UICONTROL Save]**.

   >[!NOTE]
   >
   >이러한 변경 사항에 따라 데이터를 다시 처리하는 데 24-48시간이 소요됩니다.

## 사용자 지정 모델 속성을 사용한 부메랑 스테이지 설정 {#boomerang-stage-setup-with-custom-model-attribution}

1. 이동 [!UICONTROL Stage Mapping]. 열 아래에 &quot;[!UICONTROL Boomerang]추적하려는 단계 옆에 있는 상자를 선택합니다.

   ![](assets/3-1.png)

1. 사용자 지정 모델에 이 부메랑 단계도 포함시키고 속성 크레딧을 받으려면 &quot;[!UICONTROL Custom Model]&quot; 열이 포함되어 있습니다.

   ![](assets/4-1.png)

1. 로 이동합니다. [!UICONTROL Attribution Settings] 탭. 부메랑 단계에 대한 기여도 분석에 가중치를 부여할 방법을 결정합니다. 옵션은 첫 번째 발생 또는 마지막 발생 횟수에서 속성에 가중치를 적용하거나 모든 발생 횟수에서 균일하게 분할하는 것입니다.

   ![](assets/5-1.png)

1. 표시할 각 단계의 발생 횟수를 입력합니다. 최대 10개까지 가능합니다 기본값은 1로 설정되어 있습니다.

   ![](assets/6-1.png)

1. 사용자 지정 모델에 포함시킨 부메랑 단계에 할당할 속성 비율을 설정합니다. 모든 단계에 대한 총 속성이 최대 100%까지 추가되는지 확인하십시오. 클릭 **[!UICONTROL Save and Process]**.

   ![](assets/7-1.png)

   >[!NOTE]
   >
   >이러한 변경 사항에 따라 데이터를 다시 처리하는 데 24-48시간이 소요됩니다.
