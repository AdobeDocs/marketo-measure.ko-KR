---
unique-page-id: 18874610
description: Dynamics 캠페인 및 마케팅 목록 - [!DNL Marketo Measure] - 제품 설명서
title: Dynamics 캠페인 및 마케팅 목록
exl-id: 7b3d4032-5edf-489d-b86b-1e2a5755b258
source-git-commit: 54337a0a65b79d80ebeae6531f5e92f4f48721a7
workflow-type: tm+mt
source-wordcount: '825'
ht-degree: 0%

---

# Dynamics 캠페인 및 마케팅 목록 {#dynamics-campaigns-and-marketing-lists}

>[!NOTE]
>
>&quot;[!DNL Marketo Measure]&quot;은 설명서이지만 CRM에서 &quot;Bizible&quot;을 참조하십시오. 업데이트를 위해 노력하고 있으며 리브랜딩이 곧 CRM에 반영됩니다.

## 캠페인 {#campaigns}

Dynamics Campaigns는 오프라인 마케팅 활동을 추적하여 옴니채널 여정에 포함하는 데 유용합니다. Campaign은 Lead 또는 Contacts와 관계가 있어야 하며 Campaign Response 또는 Marketing List를 통해 Campaign으로 롤업할 수 있습니다.

## 캠페인 응답 {#campaign-responses}

Lead 또는 Contact 가 Campaign에 직접 추가되면 Campaign Response 레코드로 입력됩니다.

![](assets/1.png)

## 터치포인트 활성화 {#enable-touchpoints}

터치 포인트 여정에 이러한 레코드를 포함하려면, 동기화할 캠페인 응답 유형에 대한 몇 가지 옵션이 있습니다. Campaign 레코드에는 설치된 솔루션의 사용자 지정 필드가 &quot;[!UICONTROL Enable Buyer Touchpoints].&quot; 표시되지 않는 경우 양식 편집기를 통해 필드를 추가해야 합니다.

![](assets/2.png)

캠페인에 캠페인 응답이 있는 모든 레코드를 포함하도록 선택하거나, &quot;관심 있는&quot; 응답이 있는 레코드만 포함하도록 선택하거나, 기본적으로 캠페인 응답을 포함할 수 없습니다. 필드를 비워 두거나 명시적으로 제외하도록 선택할 수 있습니다.

[!DNL Marketo Measure] 은 사용자 지정 응답 값을 지원하지 않습니다.

![](assets/3.png)

다음은 Campaign 응답에 대한 주식 응답 값입니다.

![](assets/4.png)

선택한 내용에 따라 이러한 레코드는 이제 Lead, Contact 또는 Opportunity 여정에서 터치포인트에 적합합니다. 자격이 있는 경우 &quot;Dynamics Campaign&quot; 터치포인트가 여정에 표시됩니다.

캠페인 응답이 표시되지 않을 수 있는 한 가지 이유는 첫 번째 터치 및/또는 리드 생성 터치 활동이 리드/연락처에 대해 이미 기록되었으며 &quot;PostLC&quot; 기능이 비활성화되어 있거나 최대 터치포인트 수에 도달했기 때문입니다.

## 터치 포인트 날짜 {#touchpoint-date}

캠페인에 대한 터치포인트 날짜는 일반적으로 캠페인 응답이 캠페인에 추가된 날짜입니다. 설치된 솔루션 &quot;구매자 터치 포인트 날짜&quot;라는 레이블이 지정된 사용자 지정 필드가 채워지면 이 필드를 대체할 수 있습니다. 표시되지 않는 경우 양식 편집기를 통해 필드를 추가해야 합니다.

이 필드를 사용하는 한 가지 일반적인 예는 이벤트가 발생한 후 CRM에 이벤트의 배지 스캔 목록이 추가되어 사용자가 실제로 구매자 터치 포인트 날짜를 이벤트가 발생한 날짜로 변경할 수 있는 이벤트에 대한 것입니다.

![](assets/5.png)

## 마케팅 목록 {#marketing-lists}

마케팅 목록은 리드 또는 연락처를 마케팅 여정에 포함하는 또 다른 방법입니다. 마케팅 목록은 가망 고객 또는 연락처 그룹에 대해 고유합니다. 즉, 사용자가 해당 목록이 리드 집합인지 또는 연락처 세트인지를 선택해야 합니다.

[!DNL Marketo Measure] 에서는 정적 마케팅 목록만 지원합니다. Adobe에서는 동적 마케팅 목록을 지원하지 않습니다. 왜냐하면 처리를 수행하려면 레코드의 수정 날짜를 확인해야 하지만, 동적 목록이 자주 변경되므로 여기에 대한 수정 날짜가 없습니다 [!DNL Marketo Measure] 확인. 이렇게 하려면 하루 종일 전체 데이터 세트를 계속 다운로드해야 합니다.

![](assets/6.png)

위의 스크린샷은 리드에 대한 마케팅 목록입니다. 마케팅 목록은 캠페인과 연결되어 있으며 여러 캠페인에 연결할 수 있습니다. 하나의 캠페인에 대해 하나의 마케팅 목록만 만들지 않는 한, [!DNL Marketo Measure] 고객은 마케팅 목록을 사용하여 캠페인을 추적하는 것이 좋습니다. 동일한 리드/연락처 목록이 여러 캠페인에서 터치포인트에 적격일 가능성이 없습니다.

## 터치포인트 활성화 {#enable-touchpoints-1}

터치포인트에 대한 마케팅 목록을 활성화하려면, 캠페인 레코드에 &quot;[!UICONTROL Sync Marketing Lists],&quot;는 단순한 예/아니요 스위치입니다. 표시되지 않는 경우 양식 편집기를 통해 필드를 추가해야 합니다. 캠페인 레코드에서는 캠페인과 관련된 마케팅 목록을 확인할 수 있으므로 활성화한 목록 수를 알 수 있습니다.

![](assets/7.png)

## 터치 포인트 날짜 {#touchpoint-date-1}

마케팅 목록에 대한 터치포인트 날짜는 일반적으로 ListMember 생성 날짜이므로 리드 또는 연락처가 마케팅 목록에 추가된 날짜입니다. 설치된 솔루션 &quot;구매자 터치 포인트 날짜&quot;라는 레이블이 지정된 사용자 지정 필드가 채워지면 이 필드를 대체할 수 있습니다. 표시되지 않는 경우 양식 편집기를 통해 필드를 추가해야 합니다.

![](assets/8.png)

## 채널 매핑 {#channel-mapping}

Dynamics 캠페인은 캠페인 유형 필드를 사용하여 사용자 지정 마케팅 채널에서 버킷됩니다. Dynamics 사용자 지정 메뉴에서 변경할 수 있습니다.

캠페인 유형 메뉴의 값이 [!DNL Marketo Measure] 애플리케이션. **[!UICONTROL My Account]** > **[!UICONTROL Settings]** > **[!UICONTROL Offline Channels]**.

각 캠페인 유형에 대해 채널 및 하위 채널 조합에 매핑될 수 있으므로 Campaign에서 파생되는 각 터치 포인트에 올바른 매핑된 채널 및 하위 채널이 있도록 합니다.

![](assets/9.png)

![](assets/10.png)

## 캠페인 동기화 날짜 {#campaign-sync-date}

Dynamics 고객은 이 기능을 사용할 수 없습니다

## FAQ {#faq}

**마케팅 목록에서 터치포인트를 활성화하거나 Dynamics의 캠페인만 활성화할 수 있습니까?**

마케팅 목록을 활성화할 수 있지만, 마케팅 목록을 동기화하는 옵션이 캠페인에 있으므로 캠페인과 관련이 있어야 합니다.

**캠페인에서 캠페인 응답 및 마케팅 목록을 사용할 수 있습니까?**

예.
