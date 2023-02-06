---
unique-page-id: 18874556
description: "[!DNL Marketo Measure] 유지 관리 - [!DNL Marketo Measure] - 제품 설명서"
title: "[!DNL Marketo Measure] 유지 관리"
exl-id: 4e1d53bb-0af8-4774-9f69-6a95516b3d11
source-git-commit: 09ffdbb0b1baeed870a3145268997e63a3707c97
workflow-type: tm+mt
source-wordcount: '638'
ht-degree: 0%

---

# [!DNL Marketo Measure] 유지 관리 {#marketo-measure-maintenance}

[!DNL Marketo Measure] 매일 CRM에서 필요한 거의 모든 것을 가져오지만 정기적으로 유지 관리를 예약하려는 몇 가지 유지 관리 작업이 있습니다 [!DNL Marketo Measure] 흥얼거리고 가능한 가장 정확한 정보를 출력한다.

**새로운 오프라인 캠페인을 위해 구매자 터치포인트 동기화(월 2회)**

온보딩 중에 배운 대로 [!DNL Marketo Measure] crm의 캠페인과 동기화하여 오프라인 마케팅 활동에 대한 정보를 가져옵니다. 조직이 새로운 캠페인을 시작할 때 각 캠페인에 대해 구매자 터치포인트를 적절히 사용하도록 설정해야 합니다. 체크 아웃 [이 문서](/help/channel-tracking-and-setup/offline-channels/syncing-offline-campaigns.md)추가 정보.

**모든 채널에 대한 비용 업로드(1x/월)**

에 대한 전체 매출 및 ROI 보고 기능을 활용하려면[!DNL Marketo Measure]에 대해 [!DNL Marketo Measure] 각 마케팅 채널 및 하위 채널에 지출하는 금액입니다. 각 채널/하위 채널의 소유자를 지정하고 이러한 사람들이 매달 새로운 비용 정보를 업로드하는 데 필요한 비용을 한 개인에게 보고하도록 하는 것이 좋습니다.

읽기 방식으로 비용 정보를 업로드하는 방법에 대한 메모리를 새로 고칩니다. [이 문서](/help/marketing-spend/spend-management/marketing-channel-costs.md).

**추적할 도메인 목록 업데이트(월 1일)**

Marketo Measure은 Javascript가 활성화된 모든 페이지 및 하위 도메인을 추적하지만, 우리가 알고 있는 도메인에 대해서만 추적합니다. 최근 새 도메인을 처음 만들었거나, 국제적으로 확장했거나, 주 도메인을 변경한 경우 [Marketo 지원](https://nation.marketo.com/t5/support/ct-p/Support){target="_blank"} Adobe에서 귀하의 계정을 적절하게 업데이트하도록 하십시오.

**정확성을 위한 사용자 지정 채널 매핑 검토(월 1회)**

온보딩 중에 온라인 및 오프라인 마케팅 활동에 대한 사용자 지정 채널 매핑을 설정합니다. 마케팅 전략 및 Marketo Measure 사용이 발전함에 따라 모든 터치포인트가 적절하게 분류되도록 해당 매핑 로직을 주시해야 합니다.

기억해 [!DNL Marketo Measure] 매핑 논리를 편집할 때 데이터를 재처리하므로 7일에 한 번 이상 이러한 규칙을 변경할 수 없습니다.

참조 [이 문서](/help/channel-tracking-and-setup/online-channels/online-custom-channel-setup.md) 온라인 설정의 경우, [이 문서](/help/channel-tracking-and-setup/offline-channels/offline-custom-channel-setup.md) 오프라인 설정을 사용하고, 이 우수 사례 목록이 고객으로부터 제공됩니다.

* 현재 설정했을 수 있는 &quot;기타&quot; 또는 &quot;NULL&quot; 채널에 속하는 터치포인트를 검토합니다. 적절한 경우 매핑 논리를 업데이트하여 해당 터치포인트를 더 정확한 채널로 다시 분류하십시오.
* 현재 직접 채널에 속하는 터치포인트를 검토합니다. 이메일 마케팅 캠페인이나 기타 활동 중 일부가 UTM 매개 변수를 누락된 경우 트래픽이 직접 채널로 잘못 그룹화할 가능성이 높습니다. 참조 소스를 캡처하려면 UTM 매개 변수 업데이트를 고려하십시오.

**터치 포인트 억제 설정 평가(1x/분기)**

기여도 분석 스토리에서 고려되지 않는 것을 선호하는 많은 터치포인트를 보고 있는 경우 [!DNL Login] 또는 [!DNL Unsubscribe forms], 경력 페이지 또는 내부 앱(예: )을 사용할 때 기존 터치 포인트 억제 설정을 평가할 수 있습니다. 한 분기에 한 번, 불필요한 노이즈를 만드는 터치 포인트 그룹을 정확히 파악하고 억제 논리를 적절하게 업데이트합니다. [여기 유용한 기사가 있습니다](/help/advanced-marketo-measure-features/touchpoint-settings/touchpoint-removal-and-touchpoint-suppression.md)  방법 사용.

**정확도를 위한 사용자 지정 단계 매핑 검토(해당하는 경우)**

사용자 지정 항목을 사용하는 경우 [!UICONTROL Lead], [!UICONTROL Contact], 또는 [!UICONTROL Opportunities] 스테이지는 해당 단계가 매핑되는 파이프라인의 일부 및 해당 단계가 사용자 지정 속성 모델에 포함되는지 여부를 사용자 지정할 수도 있습니다. 분기별로 한 번, 방문 [이 문서](/help/advanced-marketo-measure-features/custom-attribution-models/custom-attribution-model-and-setup.md) 를 클릭하여 사용자 지정 단계 매핑에서 메모리를 새로 고치고 사용자 지정 단계를 정확하게 추적하는지 확인합니다.

**기계 학습 모델과 사용자 지정 모델 가중치(1x/분기) 비교(해당되는 경우)**

에 대한 라이센스가 있는 경우 [!DNL Marketo Measure] 사용자 정의 모델에는 의 MLM(기계 학습 모델)에서 데이터를 사용할 수 있습니다. [!UICONTROL Settings] > [!UICONTROL Attribution Settings]. MLM은 계정의 터치포인트 데이터를 사용하여 각 단계의 중요도를 계산하고 사용자 지정 모델에 속성 가중치를 할당하는 방법을 결정하는 데 도움이 될 수 있습니다. MLM을 분기별로 한 번 사용자 지정 모델과 비교하고 사용자 지정 모델에 대한 잠재적 변경 사항에 대한 의미와 SM을 논의할 것을 권장합니다.

에 대한 자세한 정보 [!DNL Marketo Measure] 기계 학습 모델, 체크 아웃 [이 문서](/help/advanced-marketo-measure-features/custom-attribution-models/machine-learning-model-faq.md).
