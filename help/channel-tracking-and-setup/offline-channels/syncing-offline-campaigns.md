---
unique-page-id: 18874600
description: 오프라인 캠페인 동기화 - [!DNL Marketo Measure] - 제품 설명서
title: 오프라인 캠페인 동기화
exl-id: a6f9e217-ff6e-474d-9f14-c6f6238c9e84
source-git-commit: 02f686645e942089df92800d8d14c76215ae558f
workflow-type: tm+mt
source-wordcount: '701'
ht-degree: 0%

---

# 오프라인 캠페인 동기화 {#syncing-offline-campaigns}

오프라인 캠페인을 정확하게 추적하고 이 캠페인이 디지털 마케팅 활동과 어떻게 비교되는지를 이해하는 것은 어려울 수 있습니다. [!DNL Marketo Measure] 터치포인트를 추적하여 오프라인 캠페인에 표시할 수 있도록 합니다. [!DNL Salesforce]와 같은 상황에서 [!DNL Salesforce] 캠페인이 이벤트 후 몇 주가 지날 때까지 만들어지지 않습니다.

## 동기화하기 전에 {#before-you-sync}

다음은 효율적인 동기화 프로세스를 위한 팁입니다.

* 오프라인 캠페인은 온라인에서 발생하지 않는 마케팅 상호 작용을 의미합니다. 여기에는 이벤트, 웨비나 및 트레이드쇼와 같은 마케팅 채널이 포함됩니다. 오프라인 마케팅 캠페인만 포함합니다.
* 설치 전에 온라인 활동을 추적한 캠페인을 포함하려는 경우 [!DNL Marketo Measure]를 설정하는 경우 JavaScript가 사이트에 배포된 날짜로 터치 포인트 종료 날짜를 설정해야 합니다.
* 이렇게 하면 [!DNL Marketo Measure] 앱을 오프라인 채널 페이지에서 열어 터치포인트를 구성하는 마케팅 채널과 함께 다양한 캠페인 유형을 쉽게 식별할 수 있습니다.

* &quot;[!UICONTROL Save]&quot; 버튼을 클릭합니다.

## 벌크 업데이트 터치 포인트 날짜 {#bulk-update-touchpoint-date}

in [!DNL Salesforce], 캠페인 구성원 개체의 만든 날짜 필드는 캠페인 구성원이 캠페인에 추가된 날짜를 기록합니다. 동기화 프로세스가 원활하게 작동하려면 구매자 터치 포인트 날짜 필드가 Salesforce 캠페인 구성원 개체의 날짜와 동일한 날짜를 갖는지 확인하십시오. 이 단계는 &quot;[!UICONTROL Bulk Update Touchpoint Date button],&quot; _이전_ 을(를) 선택합니다. [!UICONTROL picklist] 구매자 터치포인트 사용 필드의 옵션.

이것이 중요한 이유는 무엇입니까? 당신의 회사가 1월에 있을 회의에서 부스를 후원했다고 잠시 상상해 보십시오. 컨퍼런스에서 100명의 개인은 제품에 관심을 보이며 이메일 업데이트를 받기 위해 연락 정보를 제공했습니다. 3주 후, 마침내 캠페인을 만들었습니다 [!DNL Salesforce] 회의 결과를 추적하다.

업로드 날짜는 회의 날짜보다 3주 후입니다. 이 차이를 해결하려면 [!UICONTROL Bulk Update Touchpoint Date] 버튼을 사용하여 적절한 날짜를 설정할 수 있습니다. 버튼은 아래 이미지에 나와 있습니다.

![](assets/1-3.png)

이 경우 업로드 날짜를 3주 단위로 채우기 시작합니다. 이 단계는 &quot;[!UICONTROL Enable Buyer Touchpoints]&quot; 필드를 생성할 수 있습니다.

요약하면 [!UICONTROL Bulk Update Touchpoint Date] 단추를 누르고 터치 포인트 날짜를 이벤트 날짜로 변경합니다. [!DNL Marketo Measure] 은 업로드의 날짜가 아니라 이벤트의 실제 날짜에 대한 터치포인트를 생성합니다.

기존 캠페인의 모든 캠페인 구성원에 대한 날짜를 업데이트할 수도 있습니다. 이 작업을 수행할 때 터치 포인트의 날짜가 구성원의 상호 작용 날짜인지 확인하십시오. 구매자 일괄 업데이트 터치포인트 날짜를 클릭하고 캠페인 구성원 목록을 적절하게 필터링한 후 &quot;[!UICONTROL Select Date]캠페인 구성원 목록 위에 있는 옵션을 사용하면 이벤트가 발생한 날짜와 동일한 날짜를 추가합니다.

>[!CAUTION]
>
>터치 포인트 날짜를 업데이트해야 합니다 _이전_ 모든 캠페인 구성원에 대해 터치포인트를 활성화합니다.

![](assets/2-3.png)

## 캠페인 및 동기화 구매자 터치포인트를 만드는 방법 {#how-to-create-a-campaign-and-sync-buyer-touchpoints}

에서 캠페인을 만들려면 [!DNL Salesforce]로 이동합니다. [!UICONTROL Campaigns] 탭을 선택하고[!UICONTROL New]&#39; 는 아래 이미지에 표시되어 있습니다. 사용자 [!DNL Salesforce] 설정을 사용하려면 더하기(+) 아이콘을 클릭하여 맨 위 막대에 캠페인을 추가해야 할 수 있습니다.

![](assets/3-3.png)

이 캠페인을 만들 때 &quot;[!UICONTROL Enable Buyer Touchpoints]&quot; 필드를 선택하고 선택목록에서 다음 옵션 중 하나를 선택합니다.

![](assets/4-3.png)

* **모든 캠페인 구성원 포함**
   * 이 옵션을 사용하면 [!DNL Marketo Measure] 터치포인트를 각 캠페인 구성요소에 연결하도록 했습니다.

* **응답한 캠페인 구성원을 포함합니다.**
   * 이 옵션은 &quot;응답함&quot; 상태가 있는 캠페인 구성원에게 터치포인트를 적용합니다.

* **모든 캠페인 구성원을 제외합니다.**
   * 이 선택 사항은 터치포인트를 캠페인의 어떤 구성요소에도 기여하지 않으며 캠페인이 의도적으로 제외시킨 플래그로 작동합니다 [!DNL Marketo Measure]. 우연히 구매자 터치포인트와 캠페인을 동기화하면 상태를 &quot;모든 캠페인 구성원 제외&quot;로 변경할 수 있으며 터치포인트가 제거됩니다.

이 선택 중 하나가 선택되면 [!DNL Marketo Measure] 해당되는 경우 각 캠페인 구성원에게 터치포인트를 할당할 수 있습니다. 캠페인에 추가된 리드 또는 연락처 _반드시_ 자신의 레코드에 연결된 이메일 주소를 [!DNL Marketo Measure] 터치 포인트를 만들려면 이메일 주소가 없으면, [!DNL Marketo Measure] 터치 포인트를 캠페인 구성원에게 할당하지 않습니다.

>[!MORELIKETHIS]
>
>[[!DNL Marketo Measure] 대학: 오프라인 채널 매핑](https://universityonline.marketo.com/courses/bizible-fundamentals-channel-management/#/page/5c630eca34d9f0367662b77f)
>
>[[!DNL Marketo Measure] 대학: 캠페인 개체 필드](https://universityonline.marketo.com/courses/bizible-fundamentals-channel-management/#/page/5c63007334d9f0367662b758)
