---
unique-page-id: 18874562
description: PostLC 접점 및 리드 참여 - Marketo Measure - 제품 설명서
title: PostLC 접점 및 리드 참여
exl-id: 3ee5c571-195e-46c7-b150-fedcbc3614cb
feature: Touchpoints
source-git-commit: 9e672d0c568ee0b889461bb8ba6fc6333edf31ce
workflow-type: tm+mt
source-wordcount: '378'
ht-degree: 0%

---

# PostLC 접점 및 리드 참여 {#postlc-touchpoints-and-lead-engagement}

[!DNL Marketo Measure] PostLC(Post-Lead Creation) 터치포인트는 멀티 터치 속성 모델(W자형 이상)을 사용하는 고객에게 제공됩니다. 잠재 고객 또는 연락처가 웹 사이트로 돌아가 양식을 계속 작성하면 이러한 양식 제출이 PostLC 터치포인트로 등록됩니다. 이러한 터치포인트를 사용하면 리드가 첫 번째 전환 후 한참 동안 사이트에 계속 참여하도록 유도하는 콘텐츠를 확인할 수 있습니다. PostLC 터치포인트는 Opportunity 내의 모든 중개 터치포인트와 속성 크레딧을 공유합니다. 10% 속성 크레딧은 중개 터치포인트에 할당되며 모든 터치 간에 균등하게 분배됩니다.

![](assets/1.png)

[!DNL SFDC]에 표시되는 PostLC 터치포인트의 수를 조정할 수 있습니다. 일반적으로 PostLC 터치포인트를 최대 5개까지 푸시하는 것이 좋습니다. 각 터치포인트는 [!DNL SFDC]에서 1KB씩 소요됩니다.

>[!NOTE]
>
>PostLC 터치포인트 설정을 조정하는 방법에 대한 지침은 이 문서의 끝에 있습니다.

PostLC 터치포인트는 동적입니다. 리드 또는 연락처가 PostLC 양식을 계속 제출하면 [!DNL Marketo Measure]에서 CRM의 PostLC 터치포인트를 업데이트하여 최신 양식 제출을 표시합니다. 특히 5개의 PostLC 터치포인트 제한을 설정한 경우 [!DNL Marketo Measure]은(는) 항상 5개의 _가장 최근_ 터치포인트를 CRM에 푸시합니다.  이 예에서는 이 계정이 PostLC 제한을 4개의 터치포인트로 설정했습니다. 이 리드는 이미 CRM에 포함할 수 있는 PostLC 터치포인트의 최대 수에 도달했습니다. 마지막 PostLC 터치는 2018년 2월 6일이었습니다. 이 사용자가 다음 날 다른 양식을 작성해야 하는 경우 [!DNL Marketo Measure]이(가) 2017년 11월 9일에 첫 번째 PostLC 접점을 제거하여 2018년 2월 7일에 최신 접점을 추가합니다.

![](assets/2.png)

>[!NOTE]
>
>[!DNL Marketo Measure]은(는) 잠재 고객 또는 연락처의 PostLC 터치포인트만 업데이트하며 기회의 PostLC 속성 터치포인트는 업데이트하지 않습니다. 연락처의 모든 관련 PostLC 접점은 Opportunity에 포함됩니다.

## PostLC 터치포인트 설정을 변경하는 방법 {#how-to-change-postlc-touchpoint-settings}

리드 또는 연락처에 대한 PostLC 터치포인트 설정을 조정하려면 아래 지침을 따르십시오.

**리드**

1. [!DNL Marketo Measure] 계정([experience.adobe.com/marketo-measure](https://experience.adobe.com/marketo-measure){target="_blank"})에 로그인하고 [!UICONTROL Settings](으)로 이동합니다.

1. CRM에서 **[!UICONTROL Leads]**&#x200B;을(를) 선택합니다.

1. 리드에 푸시할 postLC 터치포인트 수를 입력하고 **[!UICONTROL Save]**&#x200B;을(를) 클릭합니다.

   ![](assets/3.png)

**연락처**

1. [!DNL Marketo Measure] 계정([experience.adobe.com/marketo-measure](https://experience.adobe.com/marketo-measure){target="_blank"})에 로그인하고 [!UICONTROL Settings](으)로 이동합니다.

1. CRM에서 **[!UICONTROL Contacts]**&#x200B;을(를) 선택합니다.

1. 연락처에 푸시할 postLC 터치포인트의 수를 입력하고 **[!UICONTROL Save]**&#x200B;을(를) 클릭합니다.

   ![](assets/4.png)
