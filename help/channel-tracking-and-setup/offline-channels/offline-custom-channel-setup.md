---
unique-page-id: 18874598
description: 오프라인 사용자 지정 채널 설정 - [!DNL Marketo Measure] - 제품 설명서
title: 오프라인 사용자 지정 채널 설정
exl-id: c5697714-1a79-40bd-8b7c-e10768f4ef67
source-git-commit: 02f686645e942089df92800d8d14c76215ae558f
workflow-type: tm+mt
source-wordcount: '880'
ht-degree: 0%

---

# 오프라인 사용자 지정 채널 설정 {#offline-custom-channel-setup}

## 시작하기 {#getting-started}

방법 비교 [!DNL Marketo Measure] 온라인 채널 규칙을 처리합니다. 오프라인 채널 규칙은 스프레드시트를 사용하지 않아도 됩니다. 그러나 오프라인 채널을 구성하는 방법을 통해 이해하는 데 도움이 될 수 있으므로 구현 계획에 아직 시트가 제공됩니다.

스프레드시트에는 세 개의 열이 있습니다.

![](assets/1-2.png)

**[!UICONTROL Salesforce]캠페인 유형** - 에서 식별된 캠페인 유형 추가 [!DNL Salesforce] 여기

* 예를 들어, 이것은 이메일, 웨비나, 전화 회의 또는 터치포인트를 지정할 이 필드에 대해 만든 모든 값일 수 있습니다.

**[!UICONTROL Channel]** - 여기에 다양한 마케팅 채널을 추가합니다.

**[!UICONTROL Subchannel]** - 여기에 해당 하위 채널 추가

## 오프라인 채널 논리 {#offline-channel-logic}

[!DNL Marketo Measure] 오프라인 채널 로직은 Campaign 개체, 특히 [!DNL Salesforce] 캠페인 유형. 각 오프라인 작업에는 [!DNL Salesforce] Campaign Type(예: 디너 또는 트레이드쇼), [!DNL Marketo Measure] 매핑할 채널과 하위 채널을 이해하려면 이 필드를 사용합니다.

SFDC 캠페인 유형은 오프라인 채널의 탭에 다음 아래에 나열됩니다 [!DNL Salesforce] 캠페인 유형. 주의하십시오 [!DNL Marketo Measure] 는 구매자 터치포인트가 연결된 캠페인에 대해서만 SFDC 캠페인 유형을 가져올 수 있습니다.

![](assets/2-2.png)

여기서 에서 채널/하위 채널 매핑을 만들 수 있습니다 [!DNL Marketo Measure] 앱. 여기에는 [!DNL Marketo Measure] 앱의 채널 만들기 섹션에서 수행되는 작업은 아래 이미지에 표시됩니다. 에 대해 새 채널 및 하위 채널을 만들어야 합니다 [!DNL Marketo Measure] 터치포인트를 푸시할 위치를 이해합니다. 캠페인 유형을 매핑하는 방법을 결정할 수 있습니다.

![](assets/3-2.png)

## 채널 매핑 예 {#channel-mapping-example}

예를 들어, 두 사람이 참석한다고 상상해 보세요 [!DNL Salesforce] 1년 회의. 하지만 각 컨퍼런스는 매우 다르며 고유한 타겟 대상자를 갖습니다. 둘 중 어느 것이 더 많은 가치를 가져올지 알고 싶을 것이다. 사용자 [!DNL Salesforce] 환경을 사용하면 1월 이벤트에 캠페인 유형 &quot;회의&quot;를 지정하고 채널의 이름을 &quot;[!DNL Salesforce], 및 하위 채널 &quot;1월 회의&quot;를 참조하십시오.

이제 당신은 6월 컨퍼런스를 위해 같은 일을 하기를 원합니다. 이 컨퍼런스도 같은 캠페인이므로 이 경우 &quot;회의&quot;와 같은 캠페인 유형도 지정할 수 있습니다. 채널은 똑같고 [!DNL Salesforce]그리고 이 두 번째 컨퍼런스의 하위 채널은 &quot;6월 회의&quot;입니다. 조직적 관점에서 보면 이해가 간다. 하지만, 그것은 [!DNL Marketo Measure] 두 캠페인 모두에 동일한 캠페인 유형이 있으므로 이러한 규칙을 읽고 적용하는 논리입니다. [!DNL Marketo Measure] 스크립트는 한 유형의 데이터를 두 개의 다른 하위 채널에 매핑할 수 없습니다. 즉, 각 하위 채널에 대해 새 캠페인 유형을 만들어야 하지만 하위 채널에는 동일한 채널이 있을 수 있습니다.

아래는 [!DNL Marketo Measure] 다음을 읽을 수 없습니다.

![](assets/4-2.png)

위의 시나리오에서는 동일한 캠페인 유형을 두 개의 다른 하위 채널에 매핑할 수 없으므로 고유한 캠페인 유형을 만들어야 합니다. 대신 다음과 같은 고유한 유형을 설정할 수 있습니다.

![](assets/5-2.png)

기존 캠페인 유형은 채널 맵에 포함해야 하며 &quot;NULL&quot;을 채널로 추가해야 합니다.

시간을 내서 안으로 들어가세요 [!DNL Salesforce] 를 추가하여 기존 레코드 유형의 개수, 성격 및 위의 정보를 기반으로 추가 캠페인을 만들어야 하는지 여부를 결정합니다. 필요한 정보를 모두 입력했으면 업로드할 준비가 되었습니다.

추가 정보 [오프라인 동기화 [!DNL Salesforce] 캠페인 [!DNL Marketo Measure]](/help/channel-tracking-and-setup/offline-channels/syncing-offline-campaigns.md).

## 온라인 마케팅 활동을 위한 SFDC 캠페인 처리 {#handling-sfdc-campaigns-for-online-marketing-efforts}

마케팅 팀에서 만드는 것은 일반적입니다 [!DNL Salesforce] 다양한 디지털 마케팅 활동을 추적할 캠페인. 이 방법에는 아무런 문제가 없습니다. 그러나 이러한 캠페인을 DM 또는 컨퍼런스와 같은 진정한 오프라인 캠페인과 다르게 처리하는 것이 중요합니다. 디지털 이벤트와 관련된 캠페인(웹 사이트에서 발생하는 상호 작용)은 [!DNL Marketo Measure]. 이러한 캠페인을 동기화하면 [!DNL Marketo Measure] JavaScript가 이미 온라인 노력을 추적하고 있습니다.

온라인 활동을 위한 캠페인을 처리하기 위한 또 다른 팁은 [!DNL Salesforce] 캠페인 유형을 NULL로 변환. 이렇게 하려면 먼저 [!DNL Marketo Measure] 아래 이미지에 나와 있는 대로 NULL이라는 앱이 게시되었습니다. 이 함수는 [!DNL Marketo Measure] 아래의 앱 **채널 만들기** 섹션을 참조하십시오. 이 기능은 동기화하지 말아야 하는 캠페인이 실수로 동기화되는 경우에 유용합니다. NULL에서 버킷된 모든 항목을 확인하면 캠페인을 쉽게 찾고 동기화 상태를 수정할 수 있습니다.

![](assets/6-2.png)

## 앱에 오프라인 채널 규칙 입력 {#entering-your-offline-channel-rules-to-the-app}

사용자 지정 규칙을 사용하여 스프레드시트를 편집하고 업데이트했다면 다음 단계는 의 [!DNL Marketo Measure] 앱 - 오프라인 채널용 스프레드시트를 실제로 업로드하지 않습니다. 대신 아래 이미지에 표시된 대로 선택 목록 상자에 정보를 입력합니다. 다음 아이콘을 클릭하여 찾습니다 **[!UICONTROL Offline Channels]** 아래에 **[!UICONTROL Channels]** 섹션을 참조하십시오.

![](assets/7-2.png)

>[!TIP]
>
>확인 _when_ a [!DNL Salesforce] 캠페인 유형을 [!DNL Marketo Measure] 채널 매핑? 로 이동합니다. **[!UICONTROL Setup]** > **[!UICONTROL Campaigns]** > **[!UICONTROL Fields]** > **[!UICONTROL Type]**. 그러면 선택 목록에 있는 값과 비활성 값을 확인할 수 있습니다. 비활성 항목은 &quot;[!UICONTROL Offline Channels]&quot; 섹션을 참조하십시오. 참고로, 이 프로세스는 몇 분에서 48시간 정도 걸릴 수 있습니다.

클릭 **[!UICONTROL Save]** 끝나고 나면 [!DNL Marketo Measure] 이 변경 사항을 업로드하고 데이터를 다시 처리합니다.

>[!MORELIKETHIS]
>
>* [[!DNL Marketo Measure] 대학: 오프라인 채널 매핑](https://universityonline.marketo.com/courses/bizible-fundamentals-channel-management/#/page/5c630eca34d9f0367662b77f)
>
>* [[!DNL Marketo Measure] 대학: 오프라인 캠페인 동기화](https://universityonline.marketo.com/courses/bizible-fundamentals-channel-management/#/page/5c63286e34d9f0367662b78b)
>
>* [Marketo Engage 프로그램 통합](/help/marketo-measure-and-marketo/marketo-measure-integrations-with-marketo/marketo-engage-programs-integration.md#channel-mapping)

