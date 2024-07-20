---
description: 온라인 채널 모범 사례 - [!DNL Marketo Measure]
title: 온라인 채널에 대한 우수 사례
exl-id: 766cb01c-98b3-492d-bb35-e0a78b76333a
feature: Channels
source-git-commit: 9e672d0c568ee0b889461bb8ba6fc6333edf31ce
workflow-type: tm+mt
source-wordcount: '611'
ht-degree: 0%

---

# 온라인 채널에 대한 우수 사례 {#best-practices-for-online-channels}

## 개요 {#overview}

정확한 [!DNL Marketo Measure] 보고를 받으려면 마케팅 채널을 올바르게 설정해야 합니다. 마케팅 채널 필드에는 터치포인트가 속할 수 있는 최상위 수준의 마케팅 활동 그룹(예: 유료 검색, 직접, 소셜 등)이 표시됩니다.

마케팅 채널을 설정하는 방법에는 온라인과 오프라인의 두 가지 측면이 있습니다. 이 문서는 온라인 채널 설정 및 유지 관리를 위한 [!DNL Marketo Measure] 모범 사례 권장 사항에 중점을 두고 있습니다.

온라인 채널 규칙은 [!DNL Marketo Measure]이(가) 사이트에서 [!DNL Marketo Measure] JS를 통해 추적 및 생성된 디지털 터치포인트를 매핑하는 방법에 대한 지침입니다. 이러한 규칙이 포괄적이지 않거나 올바르게 순서가 지정되지 않으면 터치포인트가 잘못된 채널로 할당될 수 있으므로 보고의 정확도가 줄어듭니다. 온라인 채널 규칙이 정확하고 최신 버전인지 확인하면 디지털 데이터가 [!DNL Marketo Measure] 보고에서 올바른 채널 및 하위 채널로 귀속됩니다.

## 우수 사례 {#best-practice}

규칙을 처음 설정하든 단순히 검토하여 정확성을 확인하든 관계없이 다음 모범 사례를 염두에 두십시오.

마케팅 캠페인의 구성과 [!DNL Marketo Measure] 프레임워크에 어떻게 적합한지 생각해 보십시오. 온라인 채널에 표시해야 하는 채널과 하위 채널, 그리고 이러한 채널을 서로 구별하는 캠페인, UTM 매개 변수 또는 참조 웹 사이트를 결정합니다.

명심해야 할 사항:

* 모든 디지털 채널과 하위 채널은 하나 이상의 규칙으로 표시되어야 합니다
   * 채널이 사람들을 사이트로 유도하지 않는 경우 온라인 채널이 아닙니다
* 하나의 채널/하위 채널에 여러 개의 규칙이 있어도 됩니다.
   * 여러 규칙을 &quot;더 넓은 네트 주조&quot;로 간주하여 각 터치포인트가 올바르게 매핑되도록 할 수 있습니다. 종종 매개 변수가 잘못 추가되거나 완전히 누락될 수 있으므로 매핑 정확성을 보장하기 위해 채널/하위 채널을 캡처하는 여러 규칙을 사용하는 것이 좋습니다.
* [!DNL Marketo Measure] 논리는 스프레드시트의 맨 위 행부터 시작하여 아래로 내려가는 내림차순으로 터치포인트 매핑의 우선 순위를 지정합니다.
   * [!DNL Marketo Measure]은(는) 각 규칙(행)을 읽고 true와 first fit을 찾습니다. 그런 다음 터치포인트가 해당 채널/하위 채널에 매핑됩니다
   * 시트가 논리 규칙을 방해하므로 시트를 알파벳순으로 정렬하지 마십시오.
* 대괄호로 묶인 규칙을 유지하고 대괄호로 묶인 규칙을 편집하거나 추가하지 마십시오(예: [AdWords 유료 검색] 또는 [Facebook 유료 검색] ).
   * 기본 제공 논리가 있으며 [!DNL Marketo Measure] 통합과 연결된 기본 제공 [!DNL Marketo Measure] 규칙이 있습니다. [!DNL Marketo Measure] 통합이 설계된 대로 작동할 수 있도록 하려면 해당 채널/하위 채널 섹션에 대해 이러한 규칙을 최우선으로 적용하십시오.
* 파일이 업로드되면 7일 동안 규칙을 변경할 수 없습니다
   * [!DNL Marketo Measure]은(는) 이 시간을 사용하여 터치포인트를 처리하고 업데이트하므로 업로드하기 전에 규칙을 다시 확인하십시오.

## 유지 관리에 대한 우수 사례 {#best-practice-for-maintenace}

온라인 채널 규칙이 저장되고 처리된 후 디지털 터치포인트를 버킷화하기 위해 지속적으로 작업합니다. 그러나 특정 변경 또는 시나리오로 인해 온라인 채널 설정을 검토해야 합니다. [!DNL Marketo Measure]에서는 6개월에 한 번 온라인 채널 규칙을 검토할 것을 권장합니다. 이렇게 하면 [!DNL Marketo Measure] 데이터가 온라인 채널/하위 채널의 내부 정의 및 UTM 사용에 맞게 조정됩니다.

팀이 온라인 채널 유지 관리를 수행하도록 트리거할 수 있는 기타 항목은 다음과 같습니다....

* 새 디지털 채널/하위 채널이 시작되었습니다.
* UTM 매개 변수가 업데이트되거나 변경됩니다.
* 채널 조직 또는 이름 지정 규칙 변경
* 마케팅 팀에서의 이직률

팀에서 최근 [!DNL Marketo Measure]을(를) 경험한 적이 있는 경우 온라인 채널 규칙을 검토하고 적절하게 변경할 것을 권장합니다.

>[!MORELIKETHIS]
>
>* [온라인 채널 설정](/help/channel-tracking-and-setup/online-channels/online-custom-channel-setup.md)
>* [UTM 매개 변수](/help/channel-tracking-and-setup/online-channels/utm-parameters.md)
>* [마케팅 채널 및 하위 채널](/help/channel-tracking-and-setup/online-channels/marketing-channels-and-subchannels.md)
>* [UTM 모범 사례](/help/channel-tracking-and-setup/online-channels/best-practices-for-setting-up-utm-parameters.md)
