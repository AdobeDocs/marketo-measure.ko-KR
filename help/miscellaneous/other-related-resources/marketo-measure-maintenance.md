---
unique-page-id: 18874556
description: "[!DNL Marketo Measure] 유지 관리 - [!DNL Marketo Measure]"
title: "[!DNL Marketo Measure] 유지 관리"
exl-id: 4e1d53bb-0af8-4774-9f69-6a95516b3d11
feature: Tracking
source-git-commit: fca2db86611d16f4e74467405521a89dd5d825ab
workflow-type: tm+mt
source-wordcount: '623'
ht-degree: 0%

---

# [!DNL Marketo Measure] 유지 관리 {#marketo-measure-maintenance}

[!DNL Marketo Measure]은(는) 매일 CRM에서 필요한 거의 모든 것을 가져오지만, [!DNL Marketo Measure]을(를) 계속 최신 상태로 유지하고 가능한 가장 정확한 정보를 출력하는 데 정기적으로 예약해야 하는 몇 가지 유지 관리 작업이 있습니다.

**새 오프라인 캠페인에 대한 구매자 터치포인트 동기화(2x/월)**

온보딩 중에 학습한 대로 [!DNL Marketo Measure]은(는) CRM의 캠페인과 동기화하여 오프라인 마케팅 활동에 대한 정보를 얻습니다. 조직에서 새 캠페인을 시작할 때 각 캠페인에 대한 구매자 터치포인트를 적절하게 활성화해야 합니다.

**모든 채널에 대한 지출 업로드(1x/월)**

[!DNL Marketo Measure]의 전체 매출과 ROI 보고 기능을 활용하려면 [!DNL Marketo Measure]에 각 마케팅 채널과 하위 채널에서 지출하는 비용을 알려야 합니다. 각 채널/하위 채널의 소유자를 지정하고 이러한 사람이 매월 새 비용 정보를 업로드할 단일 당사자에게 지출을 보고하도록 합니다.

[이 문서](/help/marketing-spend/spend-management/marketing-channel-costs.md)를 읽고 비용 정보를 업로드하는 방법에 대한 기억을 새로 고치십시오.

**추적할 도메인 목록 업데이트(1x/월)**

Marketo Measure은 Javascript가 활성화된 모든 페이지와 하위 도메인을 추적하지만, 알고 있는 도메인에 대해서만 추적합니다. 최근에 새 도메인을 데뷔했거나, 국제적으로 확장했거나, 기본 도메인을 변경한 경우 [Marketo 지원 센터](https://nation.marketo.com/t5/support/ct-p/Support){target="_blank"}에 연락하여 계정을 적절하게 업데이트하십시오.

**정확성에 대한 사용자 지정 채널 매핑 검토(1x/월)**

온보딩 중에 온라인 및 오프라인 마케팅 활동에 대한 사용자 지정 채널 매핑을 설정합니다. 마케팅 전략과 Marketo Measure의 사용이 발전함에 따라 모든 터치포인트가 적절하게 분류될 수 있도록 해당 매핑 논리를 주시해야 합니다.

[!DNL Marketo Measure]은(는) 매핑 논리를 편집할 때 데이터를 재처리하므로 7일마다 두 번 이상 이러한 규칙을 변경할 수 없습니다.

온라인 설정에 대해서는 [이 문서](/help/channel-tracking-and-setup/online-channels/online-custom-channel-setup.md)를 참조하고, 오프라인 설정에 대해서는 [이 문서](/help/channel-tracking-and-setup/offline-channels/offline-custom-channel-setup.md)을(를) 참조하며, 고객으로부터 선별된 모범 사례 목록은 다음과 같습니다.

* 현재 &quot;기타&quot; 또는 &quot;NULL&quot; 채널에 속하는 터치포인트를 검토합니다. 해당되는 경우 매핑 논리를 업데이트하여 해당 터치포인트를 더 정확한 채널로 다시 분류합니다.
* 현재 직접 채널에 속하는 터치포인트를 검토합니다. 이메일 마케팅 캠페인이나 기타 활동 중 일부에 UTM 매개 변수가 없는 경우 트래픽이 직접 채널에 부적절하게 그룹화될 가능성이 있습니다. 참조 소스를 캡처하려면 UTM 매개 변수를 업데이트하는 것이 좋습니다.

**접점 비표시 설정 평가(1x/분기)**

속성 스토리(예: [!DNL Login] 또는 [!DNL Unsubscribe forms], 경력 페이지 또는 내부 앱)에서 고려하지 않는 터치포인트가 많이 표시되는 경우 기존 터치포인트 억제 설정을 평가할 수 있습니다. 분기별로 한 번, 불필요한 노이즈를 만드는 터치포인트 그룹을 정확히 파악하고 억제 논리를 적절하게 업데이트합니다. [사용 방법에 대한 유용한 문서](/help/advanced-marketo-measure-features/touchpoint-settings/touchpoint-removal-and-touchpoint-suppression.md)입니다.

**정확성에 대한 사용자 지정 단계 매핑 검토(해당되는 경우 1x/분기)**

사용자 지정 [!UICONTROL Lead], [!UICONTROL Contact] 또는 [!UICONTROL Opportunities] 단계를 사용하는 경우 해당 단계가 매핑되는 파이프라인의 일부 및 해당 단계가 사용자 지정 속성 모델에 포함되는지 여부도 사용자 지정했을 수 있습니다. 분기별로 한 번, [이 문서](/help/advanced-marketo-measure-features/custom-attribution-models/custom-attribution-model-and-setup.md)를 방문하여 사용자 지정 단계 매핑에 대한 메모리를 새로 고치고 사용자 지정 단계를 정확하게 추적하고 있는지 확인하십시오.

**기계 학습 모델과 사용자 지정 모델 가중치 비교(1x/분기)(해당되는 경우)**

[!DNL Marketo Measure] 사용자 지정 모델에 대해 라이선스가 부여된 경우 [!UICONTROL Settings] > [!UICONTROL Attribution Settings]의 MLM(Machine Learning Model)에서 사용 가능한 데이터도 있습니다. MLM은 계정의 접점 데이터를 사용하여 각 단계의 중요도를 계산하며, 사용자 지정 모델에서 속성 가중치를 할당하는 방법을 결정하는 데 도움이 될 수 있습니다. 분기별로 한 번 MLM을 사용자 지정 모델과 비교하고 사용자 지정 모델에 대한 잠재적 변경 사항의 영향을 SM과 논의하는 것이 좋습니다.

[!DNL Marketo Measure] 기계 학습 모델에 대한 자세한 내용은 [이 문서](/help/advanced-marketo-measure-features/custom-attribution-models/machine-learning-model-faq.md)를 참조하세요.
