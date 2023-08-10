---
unique-page-id: 18874600
description: 오프라인 캠페인 동기화 - [!DNL Marketo Measure] - 제품 설명서
title: 오프라인 캠페인 동기화
exl-id: a6f9e217-ff6e-474d-9f14-c6f6238c9e84
feature: Channels
source-git-commit: 8ac315e7c4110d14811e77ef0586bd663ea1f8ab
workflow-type: tm+mt
source-wordcount: '701'
ht-degree: 0%

---

# 오프라인 캠페인 동기화 {#syncing-offline-campaigns}

오프라인 캠페인을 정확하게 추적하고 이러한 캠페인이 디지털 마케팅 활동과 어떻게 다른지 이해하는 것은 어려울 수 있습니다. [!DNL Marketo Measure] 에서 오프라인 캠페인에 터치포인트를 추적하고 지정할 수 있습니다. [!DNL Salesforce], 다음과 같은 상황에서도 [!DNL Salesforce] 캠페인은 이벤트 후 몇 주가 지나야 만들어집니다.

## 동기화하기 전에 {#before-you-sync}

다음은 효율적인 동기화 프로세스를 위한 몇 가지 팁입니다.

* 오프라인 캠페인은 온라인에서 발생하지 않는 마케팅 상호 작용을 의미합니다. 여기에는 이벤트, 웨비나 및 트레이드쇼와 같은 마케팅 채널이 포함됩니다. 오프라인 마케팅 캠페인만 포함합니다.
* 를 설치하기 전에 온라인 활동을 추적한 캠페인을 포함하려는 경우 [!DNL Marketo Measure], 터치포인트 종료 날짜를 JavaScript가 사이트에 배포된 날짜로 설정해야 합니다.
* 다음을 유지하는 것이 좋습니다. [!DNL Marketo Measure] 앱이 오프라인 채널 페이지에서 열리므로 터치포인트가 그룹화되는 마케팅 채널과 함께 다양한 캠페인 유형을 쉽게 식별할 수 있습니다.

* &quot; &quot;를 누르기 전에 모든 항목을 다시 확인하십시오.[!UICONTROL Save]&quot; 단추!

## 접점 날짜 벌크 업데이트 {#bulk-update-touchpoint-date}

위치 [!DNL Salesforce]캠페인 멤버 개체의 만든 날짜 필드는 캠페인 멤버가 캠페인에 추가된 날짜를 기록합니다. 동기화 프로세스가 원활하게 진행되도록 하려면 구매자 접점 날짜 필드에 Salesforce 캠페인 멤버 개체의 날짜와 동일한 날짜가 있는지 확인하십시오. 이 단계는 &quot;[!UICONTROL Bulk Update Touchpoint Date button],&quot; _다음 이전_ 다음을 선택합니다. [!UICONTROL picklist] 구매자 접점 활성화 필드의 옵션

이것이 중요한 이유는 무엇입니까? 1월에 있을 컨퍼런스에서 귀사가 부스를 후원한다고 잠시 상상해 보세요. 컨퍼런스에서 100명의 개인이 제품에 관심을 보였고 이메일 업데이트를 받기 위해 연락처 정보를 제공했습니다. 3주 후, 드디어 캠페인이 생성되었습니다. [!DNL Salesforce] 회의의 결과를 추적하다.

업로드 날짜는 회의 날짜보다 3주 늦습니다. 이 차이를 해결하려면 [!UICONTROL Bulk Update Touchpoint Date] 버튼을 사용하여 적절한 날짜를 설정할 수 있습니다. 버튼은 아래 이미지에 나와 있습니다.

![](assets/1-3.png)

이 경우 업로드 날짜가 3주 채워집니다. 이 단계는 를 설정하기 전에 수행해야 합니다.[!UICONTROL Enable Buyer Touchpoints]&quot; 필드.

요약하자면, 다음을 사용하는 경우 [!UICONTROL Bulk Update Touchpoint Date] 버튼을 클릭하고 터치포인트 날짜를 이벤트 날짜로 변경합니다. [!DNL Marketo Measure] 은 업로드 날짜가 아닌 실제 이벤트 날짜에 대한 터치포인트를 생성합니다.

기존 캠페인의 모든 캠페인 멤버에 대한 날짜를 업데이트할 수도 있습니다. 이 작업을 수행할 때는 터치포인트의 날짜가 구성원의 상호 작용 날짜인지 확인해야 합니다. 간단히 대량 업데이트 구매자 접점 날짜 를 클릭하고 캠페인 멤버 목록을 적절하게 필터링한 다음 &quot;[!UICONTROL Select Date]캠페인 멤버 목록 위에 &quot;옵션을 놓고 이벤트가 발생한 날짜와 동일한 날짜를 추가합니다.

>[!CAUTION]
>
>터치포인트 날짜를 업데이트했는지 확인하십시오 _다음 이전_ 모든 캠페인 멤버에 대해 터치포인트를 활성화합니다.

![](assets/2-3.png)

## Campaign을 만들고 구매자 터치포인트를 동기화하는 방법 {#how-to-create-a-campaign-and-sync-buyer-touchpoints}

에서 캠페인을 만들려면 [!DNL Salesforce]로 이동한 다음 [!UICONTROL Campaigns] 탭을 클릭하고 &#39;[!UICONTROL New]아래 이미지에 표시된 대로 &#39;. 다음에 따라 [!DNL Salesforce] 설정에서는 더하기(+) 아이콘을 클릭하여 상단 표시줄에 캠페인을 추가해야 할 수 있습니다.

![](assets/3-3.png)

이 캠페인을 만들 때 &quot;[!UICONTROL Enable Buyer Touchpoints]&quot;필드를 선택하고 선택 목록에서 다음 옵션 중 하나를 선택합니다.

![](assets/4-3.png)

* **모든 캠페인 멤버 포함**
   * 이 옵션을 사용하면 [!DNL Marketo Measure] 터치포인트를 각 캠페인 멤버에 연결합니다.

* **&quot;응답한&quot; 캠페인 구성원을 포함합니다.**
   * 이 옵션은 &quot;응답됨&quot; 상태인 캠페인 멤버에게 터치포인트를 적용합니다.

* **모든 캠페인 구성원을 제외합니다.**
   * 이 옵션은 터치포인트를 캠페인의 멤버에게 기여하지 않으며 캠페인이 의도적으로 제외된 플래그 역할을 합니다 [!DNL Marketo Measure]. 우연히 구매자 터치포인트와 캠페인을 동기화하는 경우 상태를 &quot;모든 캠페인 멤버 제외&quot;로 변경할 수 있으며 터치포인트가 제거됩니다.

이 선택 항목 중 하나를 선택하면 [!DNL Marketo Measure] 해당하는 경우 각 캠페인 멤버에게 터치포인트를 할당합니다. 캠페인에 추가된 잠재 고객 또는 연락처 _필수_ 다음 순서에 따라 레코드에 연결된 이메일 주소가 있습니다. [!DNL Marketo Measure] 터치포인트를 만듭니다. 이메일 주소가 없으면, [!DNL Marketo Measure] 은(는) 캠페인 멤버에게 터치포인트를 할당하지 않습니다.

>[!MORELIKETHIS]
>
>[[!DNL Marketo Measure] 대학교: 오프라인 채널 매핑](https://universityonline.marketo.com/courses/bizible-fundamentals-channel-management/#/page/5c630eca34d9f0367662b77f)
>
>[[!DNL Marketo Measure] 대학교: 캠페인 오브젝트 필드](https://universityonline.marketo.com/courses/bizible-fundamentals-channel-management/#/page/5c63007334d9f0367662b758)
