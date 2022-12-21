---
description: 온라인 채널에 대한 우수 사례 - [!DNL Marketo Measure] - 제품 설명서
title: 온라인 채널에 대한 우수 사례
exl-id: 766cb01c-98b3-492d-bb35-e0a78b76333a
source-git-commit: 02f686645e942089df92800d8d14c76215ae558f
workflow-type: tm+mt
source-wordcount: '612'
ht-degree: 0%

---

# 온라인 채널에 대한 우수 사례 {#best-practices-for-online-channels}

## 개요 {#overview}

정확하려면 [!DNL Marketo Measure] 보고 시 마케팅 채널을 올바로 설정해야 합니다. 마케팅 채널 필드에는 터치포인트가 속할 수 있는 가장 높은 수준의 마케팅 활동 그룹(예: 유료 검색, 직접, 소셜 등)이 표시됩니다.

마케팅 채널 설정에는 두 가지 측면이 있습니다. 온라인 및 오프라인. 이 문서는 [!DNL Marketo Measure] 온라인 채널 설정 및 유지 관리를 위한 우수 사례 권장 사항.

온라인 채널 규칙은 [!DNL Marketo Measure] 디지털 터치포인트를 매핑합니다. 즉, 을 통해 추적되고 생성된 모든 터치포인트를 매핑합니다 [!DNL Marketo Measure] 사이트에 있는 JS. 이러한 규칙이 종합적이지 않거나 올바르게 정렬되지 않으면 터치포인트가 잘못된 채널에 귀속될 수 있으므로 보고의 정확도가 낮아집니다. 온라인 채널 규칙이 정확한지 그리고 최신 상태인지 확인하면 디지털 데이터가 사용자의 [!DNL Marketo Measure] 보고.

## 우수 사례 {#best-practice}

규칙을 처음 설정하든 아니면 정확성을 확인하기 위해 규칙을 검토하든 간에 다음 모범 사례를 기억하십시오.

마케팅 캠페인의 구성과 마케팅 캠페인이 [!DNL Marketo Measure] 프레임워크. 온라인 채널에서 나타낼 채널과 하위 채널을 결정하고, 캠페인, UTM 매개 변수 또는 참조 웹 사이트는 이러한 채널을 서로 구별합니다.

주의 사항:

* 모든 디지털 채널과 하위 채널은 하나 이상의 규칙으로 표시되어야 합니다
   * 채널이 사람들을 사이트로 유도하지 않으면 온라인 채널이 아닙니다
* 하나의 채널/하위 채널에 대해 여러 규칙을 사용할 수 있습니다
   * 여러 규칙을 &quot;더 넓은 네트 캐스팅하기&quot;로 간주하여 각 터치 포인트가 올바르게 매핑되도록 할 수 있습니다. 종종 매개 변수를 잘못 추가하거나 완전히 누락할 수 있으므로 채널/하위 채널을 캡처하는 여러 규칙을 사용하는 것이 매핑 정확성을 보장하는 좋은 방법입니다.
* [!DNL Marketo Measure] 논리는 스프레드시트의 맨 위 행으로 시작하고 다음을 하향식으로 터치 포인트 매핑에 우선 순위를 둡니다
   * [!DNL Marketo Measure] 는 true 및 first fit를 찾아 각 규칙(행)을 읽습니다. 그런 다음 터치 포인트가 해당 채널/하위 채널에 매핑됩니다
   * 이 경우 논리 규칙이 방해되므로 시트를 알파벳순으로 정렬하지 마십시오.
* 대괄호로 묶은 규칙을 유지 관리하고, 대괄호로 묶은 규칙을 편집하거나, 규칙에 추가하지 마십시오(예: [AdWords 유료 검색] 또는 [Facebook 유료] )
   * 이것들은 즉시 사용 가능합니다 [!DNL Marketo Measure] 로직이 내장된 규칙이며 [!DNL Marketo Measure] 통합. 이 규칙들을 채널/하위 채널 섹션에 대해 우선 순위를 지정하여 [!DNL Marketo Measure] 통합은 설계된 대로 작동할 수 있습니다.
* 파일이 업로드되면 7일 동안 규칙을 변경할 수 없습니다
   * [!DNL Marketo Measure] 은 이 시간을 사용하여 터치포인트를 처리하고 업데이트하므로 업로드하기 전에 규칙을 다시 확인하십시오.

## 유지 관리를 위한 우수 사례 {#best-practice-for-maintenace}

저장 및 처리되면 온라인 채널 규칙은 계속해서 디지털 터치포인트를 버킷합니다. 그러나 특정 변경 사항이나 시나리오가 있으면 온라인 채널 설정을 검토하려고 합니다. [!DNL Marketo Measure] 는 6개월마다 한 번씩 온라인 채널 규칙을 검토할 것을 권장합니다. 이렇게 하면 [!DNL Marketo Measure] 데이터는 온라인 채널/하위 채널의 내부 정의 및 UTM 사용과 일치합니다.

팀에서 온라인 채널 유지 관리를 수행하도록 트리거할 수 있는 기타 항목은 다음과 같습니다..

* 새로운 디지털 채널/하위 채널이 시작됩니다
* UTM 매개 변수가 업데이트되거나 변경됩니다
* 채널 조직 또는 이름 지정 규칙 변경
* 마케팅 팀의 이직률

귀하의 팀이 최근에 이러한 경험을 보유한 경우 [!DNL Marketo Measure] 에서는 온라인 채널 규칙을 검토하고 적절하게 변경할 것을 권장합니다.

>[!MORELIKETHIS]
>
>* [온라인 채널 설정](/help/channel-tracking-and-setup/online-channels/online-custom-channel-setup.md)
>* [UTM 매개 변수](/help/channel-tracking-and-setup/online-channels/utm-parameters.md)
>* [마케팅 채널 및 하위 채널](/help/channel-tracking-and-setup/online-channels/marketing-channels-and-subchannels.md)
>* [UTM 우수 사례](/help/channel-tracking-and-setup/online-channels/best-practices-for-setting-up-utm-parameters.md)

