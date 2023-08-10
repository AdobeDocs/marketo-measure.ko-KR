---
unique-page-id: 18874610
description: Dynamics 캠페인 및 마케팅 목록 - [!DNL Marketo Measure] - 제품 설명서
title: Dynamics 캠페인 및 마케팅 목록
exl-id: 7b3d4032-5edf-489d-b86b-1e2a5755b258
feature: Microsoft Dynamics
source-git-commit: 8ac315e7c4110d14811e77ef0586bd663ea1f8ab
workflow-type: tm+mt
source-wordcount: '825'
ht-degree: 0%

---

# Dynamics 캠페인 및 마케팅 목록 {#dynamics-campaigns-and-marketing-lists}

>[!NOTE]
>
>&quot; &quot;을 지정하는 지침이 표시될 수 있습니다.[!DNL Marketo Measure]설명서에는 &quot;가 있지만 CRM에는 &quot;Bizible&quot;이 표시됩니다. 이를 업데이트하고 리브랜딩이 곧 CRM에 반영되도록 노력하고 있습니다.

## 캠페인 {#campaigns}

Dynamics Campaign은 오프라인 마케팅 활동을 추적하고 이를 옴니채널 여정에 포함하는 데 유용합니다. 캠페인은 리드 또는 연락처와 관련되어야 하며 캠페인 응답 또는 마케팅 목록을 통해 캠페인에 롤업할 수 있습니다.

## 캠페인 응답 {#campaign-responses}

잠재 고객 또는 연락처가 Campaign에 직접 추가되면 캠페인 응답 레코드로 입력됩니다.

![](assets/1.png)

## 접점 활성화 {#enable-touchpoints}

접점 여정에 이러한 레코드를 포함하려면 캠페인 응답 유형을 동기화하는 몇 가지 옵션이 있습니다. Campaign 레코드에는 &quot; &quot;(으)로 레이블이 지정된 설치된 솔루션의 사용자 정의 필드가 있어야 합니다.[!UICONTROL Enable Buyer Touchpoints].&quot; 표시되지 않으면 양식 편집기를 통해 필드를 추가해야 합니다.

![](assets/2.png)

캠페인 응답이 캠페인에 있는 모든 레코드 또는 &quot;관심있는&quot; 응답이 있는 레코드만 포함하도록 선택할 수 있습니다. 또는 기본적으로 캠페인 응답은 전혀 포함할 수 없습니다. 필드를 비워 두거나 명시적으로 제외하도록 선택할 수 있습니다.

[!DNL Marketo Measure] 은(는) 사용자 지정 응답 값을 지원하지 않습니다.

![](assets/3.png)

캠페인 응답에 대한 재고 응답 값은 다음과 같습니다.

![](assets/4.png)

선택한 항목에 따라 이러한 레코드는 이제 Lead, Contact 또는 Opportunity 여정에서 터치포인트에 사용할 수 있습니다. 적합한 경우 &quot;Dynamics Campaign&quot; 터치포인트가 여정에 표시됩니다.

캠페인 응답이 표시되지 않을 수 있는 한 가지 이유는 리드/연락처에 대해 첫 번째 터치 및/또는 리드 만들기 터치 활동이 이미 기록되어 있고 &quot;PostLC&quot; 기능이 비활성화되었거나 최대 터치포인트 수에 도달했기 때문입니다.

## 접점 날짜 {#touchpoint-date}

캠페인에 대한 터치포인트 날짜는 일반적으로 캠페인 응답이 캠페인에 추가된 날짜입니다. 레이블이 &quot;구매자 터치포인트 날짜&quot;로 지정된 설치된 솔루션의 사용자 지정 필드가 채워지는 경우 재정의할 수 있습니다. 표시되지 않으면 양식 편집기를 통해 필드를 추가해야 합니다.

이 필드를 사용하는 일반적인 예 중 하나는 이벤트가 발생한 후 며칠 후에 이벤트의 배지 스캔 목록이 CRM에 추가되는 이벤트에 대한 것입니다. 따라서 사용자는 실제로 구매자 터치포인트 날짜를 이벤트가 발생한 시점으로 변경할 수 있습니다.

![](assets/5.png)

## 마케팅 목록 {#marketing-lists}

마케팅 목록은 잠재 고객 또는 연락처를 마케팅 여정에 포함하는 또 다른 방법입니다. 마케팅 목록은 리드 또는 연락처 그룹에 대해 고유합니다. 즉, 해당 목록이 리드 집합인지 아니면 연락처 집합인지 선택해야 합니다.

[!DNL Marketo Measure] 는 정적 마케팅 목록만 지원합니다. 처리에서는 레코드의 수정 날짜를 확인해야 하지만 동적 목록이 자주 변경되기 때문에 동적 마케팅 목록은 지원되지 않습니다. [!DNL Marketo Measure] 확인할 대상. 이렇게 하려면 하루 종일 전체 데이터 세트를 일정하게 다운로드해야 합니다.

![](assets/6.png)

위의 스크린샷은 리드에 대한 마케팅 목록입니다. 마케팅 목록은 캠페인에 연결되며, 여러 캠페인에 연결될 수 있습니다. 하나의 캠페인에 대해 하나의 마케팅 목록만 만들지 않으면 [!DNL Marketo Measure] 는 고객이 마케팅 목록을 사용하여 캠페인을 추적할 수 있도록 권장하지 않습니다. 동일한 정확한 리드/연락처 목록이 여러 캠페인에서 터치포인트에 적합하지 않을 가능성이 높습니다.

## 접점 활성화 {#enable-touchpoints-1}

접점에 대한 마케팅 목록을 활성화하려면 캠페인 레코드에 &quot;&quot;라는 별도의 설정이 있습니다.[!UICONTROL Sync Marketing Lists],&quot; 는 간단한 예/아니요 스위치입니다. 표시되지 않으면 양식 편집기를 통해 필드를 추가해야 합니다. Campaign 레코드에서 Campaign과 관련된 마케팅 목록을 볼 수 있으므로 활성화 중인 목록 수를 알 수 있습니다.

![](assets/7.png)

## 접점 날짜 {#touchpoint-date-1}

마케팅 목록에 대한 접점 날짜는 일반적으로 ListMember 생성 날짜이므로 리드 또는 연락처가 마케팅 목록에 추가된 날짜입니다. 레이블이 &quot;구매자 터치포인트 날짜&quot;로 지정된 설치된 솔루션의 사용자 지정 필드가 채워지는 경우 재정의할 수 있습니다. 표시되지 않으면 양식 편집기를 통해 필드를 추가해야 합니다.

![](assets/8.png)

## 채널 매핑 {#channel-mapping}

Dynamics 캠페인은 캠페인 유형 필드를 사용하여 사용자 지정 마케팅 채널에 그룹화됩니다. 이러한 변경 내용은 Dynamics 사용자 지정 메뉴에서 변경할 수 있습니다.

캠페인 유형 메뉴의 값은 [!DNL Marketo Measure] 애플리케이션. **[!UICONTROL My Account]** > **[!UICONTROL Settings]** > **[!UICONTROL Offline Channels]**.

각 캠페인 유형에 대해 채널 및 하위 채널 조합에 매핑하여 캠페인에서 파생되는 각 터치포인트가 올바르게 매핑된 채널 및 하위 채널을 갖도록 할 수 있습니다.

![](assets/9.png)

![](assets/10.png)

## Campaign 동기화 날짜 {#campaign-sync-date}

Dynamics 고객은 사용할 수 없습니다.

## FAQ {#faq}

**마케팅 목록에서 터치포인트를 활성화하거나 Dynamics에서 캠페인만 활성화할 수 있습니까?**

마케팅 목록을 활성화할 수 있지만 마케팅 목록 동기화 옵션이 캠페인에 있기 때문에 캠페인과 관련되어야 합니다.

**캠페인에서 캠페인 응답 및 마케팅 목록을 사용할 수 있습니까?**

예.
