---
unique-page-id: 18874708
description: Salesforce 활동 속성 - [!DNL Marketo Measure] - 제품 설명서
title: Salesforce 활동 속성
exl-id: 1dc6f15b-2a45-4ed3-9fa3-5267366d1f45
source-git-commit: b59c79236d3e324e8c8b07c5a6d68bd8176fc8a9
workflow-type: tm+mt
source-wordcount: '682'
ht-degree: 0%

---

# Salesforce 활동 속성 {#salesforce-activities-attribution}

다음 [!DNL Marketo Measure] Salesforce 활동 통합은 특정 작업 및 이벤트 레코드를 속성 모델로 가져옵니다. 크레딧을 받지 못한 판매 이메일이나 판매 전화 통화와 같은 것을 추적하기 시작합니다. 활동 규칙을 구성하려면 다음 위치로 이동해야 합니다 [experience.adobe.com/marketo-measure](https://experience.adobe.com/marketo-measure){target=&quot;_blank&quot;}. 거기에서 다음 위치로 이동합니다. **[!UICONTROL Settings]** 탭을 클릭하고 **[!UICONTROL Activities]** 탭.

영업 팀을 매우 기쁘게 만들 것입니다! 간단한 자습서를 살펴보십시오.

![](assets/1.png)

먼저, 우리는 새로운 개념을 도입했습니다. [!DNL Marketo Measure] 캠페인. 정의한 각 규칙에 대해 레코드를 [!DNL Marketo Measure] 이름을 지정할 수 있는 캠페인. 필요에 따라 여러 캠페인을 추가합니다. 유료 미디어 캠페인 옆에 있는 아웃바운드 판매 캠페인의 효과를 측정해 보십시오!

이걸 쓰실 겁니다 [!DNL Marketo Measure] 캠페인 이름 을 사용하여 매핑해야 하는 채널을 알려줍니다. 여전히 아웃바운드 판매에 대해 생각하고 있다면 모든 아웃바운드 판매 캠페인이 BDR 채널에 참여해야 합니다.

다음 계층에 익숙해지십시오.

* 채널
   * 하위 채널
      * 캠페인
      * 캠페인
   * 하위 채널
      * 캠페인

>[!TIP]
>
>예를 들어 각 영업 대표에 대해 고유한 캠페인을 설정하려면 동적 교체 매개 변수를 사용하여 을 입력합니다 [!DNL Marketo Measure] 캠페인 이름. 동일한 예에서 `"Outbound Sales - {AssignedTo}"` 그리고 우리는 그것을 다음과 같은 것으로 만들어낼 것입니다 `"Outbound Sales - Jill"` 또는 `"Outbound Sales - Jack."` 우리가 얼마나 오래 당신을 구했는지 당신은 몰라요!

![](assets/2.png)

한 번 [!DNL Marketo Measure] 캠페인 이름이 설정되어 있으면 활동 규칙을 설정할 차례입니다.

규칙은 속성 자격이 있는 레코드를 제공하는 필터 역할을 합니다. 유사한 논리를 사용하여 해당 보고서를 생성하는 CRM에서 보고서를 만든다고 가정합니다. 일치, 포함, 다음으로 시작, 다음으로 끝남, 같음 등과 같은 다양한 연산자와 and/or 문의 조합을 사용할 수 있는 유연성이 있습니다. 상자 외부에 있는 박스형 규칙 또는 레이어 &quot;or&quot; 문 내에 &quot;and&quot; 문을 정의합니다.

![](assets/3.png)

>[!NOTE]
>
>공식 필드는 규칙 내에서 사용할 수 없으며 선택 목록에 표시되지 않습니다. 수식은 백그라운드에서 계산되며 레코드를 수정하지 않으므로 [!DNL Marketo Measure] 레코드가 규칙에 적합한지 여부를 감지할 수 없습니다.
>
>CrmEvent.CreatedById와 같은 ID 필드에 올바른 값을 사용해야 합니다. [!DNL Salesforce IDs] 길이는 18자(예: 0054H000007WmrfQAC)입니다.

마지막으로, 구매자 터치포인트 날짜로 사용할 날짜 또는 날짜/시간 필드 중 하나를 선택하겠습니다. 표준 및 사용자 지정 필드를 선택할 수 있습니다.

>[!TIP]
>
>패키지 설치 시 [!DNL Marketo Measure] 활동 레코드에 사용자 지정 구매자 터치포인트 날짜 필드를 포함합니다. 상태가 변경되는 날짜와 같은 동적 날짜를 사용하려면 CRM 워크플로우를 사용하여 &quot;구매자 터치 포인트 날짜&quot;를 설정한 다음 이 단계에서 구매자 터치 포인트 날짜를 선택할 수 있습니다.

![](assets/4.png)

작업 또는 이벤트에 대해 다른 규칙을 설정하는 것을 잊지 마십시오. 영업 팀이 활동을 기록하는 데 사용하는 객체를 알고 있어야 합니다.

![](assets/5.png)

이 새로운 터치포인트를 적절한 위치에 배치해야 할 것입니다 [마케팅 채널](https://experience.adobe.com/#/marketo-measure/MyAccount/Business?busView=false&amp;id=10#/!/MyAccount/Business/Account.Settings.SettingsHome?tab=Channels.Online%20Channels){target=&quot;_blank&quot;}. 이렇게 하려면 방금 만든 새 캠페인 매핑으로 채널을 정의하여 할 수 있습니다. 캠페인이 아웃바운드로 시작되는 BDR 채널에 대해 새 행을 만들 수도 있습니다.

>[!TIP]
>
>채널 정의를 추가할 때 다음과 같이 연산자를 더 쉽게 지정할 수 있도록 와일드카드 값을 사용하십시오.
>
>다음으로 시작(아웃바운드)&#42; )
>
>다음( 포함) &#42;아웃바운드&#42; )
>
>다음으로 끝남( &#42;아웃바운드 )
>
>와일드카드가 기본적으로 &quot;같음&quot;이라는 의미이므로 필요에 따라 사용하십시오.

| **연산자** | **사용 사례** |
|---|---|
| 다음과 같음 | 단일 값 - 정확히 일치 |
| 포함 | 단일 값 - 값 포함 |
| 일치 | 여러 값 - 정확히 일치 |
| 모두 일치(포함) | 여러 값 - &#42;value&#42;, &#42;값, &#42;value&#42; |

![](assets/6.png)

마지막으로, 하지만 가장 중요한 것은, 새 채널에 대한 비용을 입력할 수 있다는 것입니다. Adobe [마케팅 비용 업로드](https://experience.adobe.com/#/marketo-measure/MyAccount/Business?busView=false&amp;id=10#/!/MyAccount/Business/Account.Settings.SettingsHome?tab=Reporting.Marketing%20Spend){target=&quot;_blank&quot;} 채널 수준, 하위 채널 수준 또는 캠페인 수준에서 비용을 입력할 수 있습니다. 새로운 [!DNL Marketo Measure] 캠페인에서 이러한 관련 비용을 월별로 추가한 다음 각 캠페인에 대한 ROI를 확인할 수 있습니다.

![](assets/7.png)

>[!MORELIKETHIS]
>
>[Activity Attribution FAQ](/help/advanced-marketo-measure-features/activities-attribution/activities-attribution-faq.md)
