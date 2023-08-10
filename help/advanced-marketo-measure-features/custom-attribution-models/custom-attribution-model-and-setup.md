---
unique-page-id: 18874779
description: 사용자 지정 속성 모델 및 설정 - [!DNL Marketo Measure] - 제품 설명서
title: 사용자 지정 속성 모델 및 설정
exl-id: 7b156db2-9ac6-4d32-ac67-06c0aa15d651
feature: Attribution, Custom Models
source-git-commit: a2a7657e8377fd5c556d38f6eb815e39d2b8d15e
workflow-type: tm+mt
source-wordcount: '820'
ht-degree: 0%

---

# 사용자 지정 속성 모델 및 설정 {#custom-attribution-model-and-setup}

에 대한 개요는 아래를 참조하십시오. [!DNL Marketo Measure] 사용자 지정 속성 모델 및 설정 방법.

## 사용자 지정 속성 모델 {#custom-attribution-model}

다음 [!DNL Marketo Measure] 사용자 지정 속성 모델을 사용하면 모델에 포함할 터치포인트 또는 사용자 지정 단계를 선택할 수 있습니다. 사용자는 이러한 접점 및 단계에 귀속되는 매출 크레딧의 백분율을 제어하거나, [!DNL Marketo Measure] 머신 러닝 모델.

## 사용자 지정 속성 모델을 설정하는 방법 {#how-to-set-up-your-custom-attribution-model}

1. 사용자 지정 모델에 포함할 단계를 결정합니다.

   사용자 지정 속성 모델 구축을 시작하려면 마케팅 팀에 중요한 단계를 선택해야 합니다. 이외에도 [!DNL Marketo Measure] 마일스톤 단계(FT, LC, OC, 마감됨) 사용자 정의 모델에서 최대 6개의 추가 리드/연락처 상태 또는 영업 기회 단계를 추가할 수 있습니다. 예를 들어 MQL 단계가 사용자 정의 모델에 포함되는 것이 일반적입니다. 마케팅 팀은 종종 어떤 노력이나 채널이 MQL 단계로 전환을 유도하는지 알고 싶어합니다.

   로그인 대상 [experience.adobe.com/marketo-measure](https://experience.adobe.com/marketo-measure){target="_blank"}. 다음으로 이동 [!UICONTROL My Account] > [!UICONTROL Settings] > 및 CRM 섹션에서 다음을 선택합니다. **[!UICONTROL Stage Mapping]**.

   여기에서 다음을 선택하여 포함할 잠재 고객/연락처 및 영업 기회 단계를 선택해야 합니다. **[!UICONTROL Include in Model]** 상자.

   >[!NOTE]
   >
   >최대 6개의 사용자 정의 단계(기본값 포함 안 함: FT, LC, OC, Closed)가 허용됩니다.

   ![](assets/1-1.png)

   >[!NOTE]
   >
   >_모두_ 단계가 비활성 상태이거나 더 이상 사용되지 않는 경우에도 Lead/Contacts 및 Opportunity 단계가 여기에 표시됩니다. [!DNL Salesforce]. 이러한 단계를 제거하려면 다음에서 하드 삭제해야 합니다. [!DNL Salesforce].

   단계를 선택했으면 다음을 클릭하십시오. **[!UICONTROL Save & Process]** 페이지 하단에 있는 단추입니다. 이제 단계에 다음이 표시됩니다. **[!UICONTROL Attribution Settings]** 탭하면 각 단계에 속성 백분율을 할당할 수 있습니다. 사용자 지정 단계는 마케팅 성능 세트에 수요 폭포 내의 잠재 고객 또는 기회 단계로도 표시됩니다.

   모델에 포함할 다른 단계가 있지만 에는 없는 경우 [!UICONTROL Lead/Contact Status] 또는 [!UICONTROL Opportunity Stage] 목록에서는 CRM의 필드를 기반으로 사용자 지정 단계를 정의할 수 있습니다.

   아래 예에서는 날짜 필드를 사용하여 사용자 정의 &quot;MQL&quot; 단계를 정의합니다. 규칙은 단순히 MQL 날짜 필드가 비어 있지 않은 경우 MQL로 간주해야 하고 사용자 지정 모델에 포함되어야 한다고 명시합니다. 맞춤형 단계가 생성되면 판매 주기의 진행에 따라 정렬하는 것도 중요합니다.

   ![](assets/2-1.png)

   >[!CAUTION]
   >
   >사용자 정의 필드에 대한 내역 추적을 활성화하는 것을 잊지 마십시오.

사용자 지정 모델에서 사용자 지정 필드를 사용하는 경우 CRM에서 필드 기록 추적을 활성화해야 합니다. 필드 내역 추적을 활성화하는 방법에 대한 지침은 [여기를 클릭하십시오.](/help/advanced-marketo-measure-features/custom-attribution-models/custom-model-setup-enable-field-history-tracking.md).

1. 사용자 지정 모델의 속성 비율을 결정합니다.

   로 이동 **[!UICONTROL Attribution Settings]** 위치: [!DNL Marketo Measure] 앱: 사용자 지정 단계는 여기에 속성 테이블에 표시됩니다. 속성 테이블에는 모든 [!DNL Marketo Measure] 기여도 분석 모델 및 각 모델의 기여도 분석 가중치 처음 5개 모델의 기여도 분석 비율은 고정되며 변경할 수 없습니다.

   맨 오른쪽 열에 &quot;&quot;라는 레이블이 지정됨&#x200B;**[!UICONTROL Custom]**,&quot; 사용자 지정 속성 모델에서 각 단계에 대한 백분율 가중치를 설정할 수 있습니다. 사용자 지정 열 아래에 각 단계의 값을 입력하기만 하면 됩니다. 그러면 **[!UICONTROL Save and Reprocess]** 완료되면

   &quot;사용자 지정&quot; 열 왼쪽에는 **[!DNL Marketo Measure]머신 러닝 모델**. 머신 러닝 모델은 각 사용자 지정 단계에서 발생한 사항에 따라 거래 승인에 대한 상대적 중요도에 따라 속성 가중치를 계산합니다. 머신 러닝 모델에 대한 자세한 내용은 [여기를 클릭하십시오.](/help/advanced-marketo-measure-features/custom-attribution-models/machine-learning-model-faq.md).

   ![](assets/3.png)

## 접점 위치 {#touchpoint-positions}

속성 백분율이 저장되고 처리되면 터치포인트가 업데이트되어 새 단계 및 위치를 수신하게 됩니다. 단계 전환 전에 가장 최근에 발생한 접점은 해당 단계에 대한 크레딧을 받습니다(아래 참조). 사용자 정의 가중치 및 매출도 재분배됩니다.

![](assets/4.png)

## 단계 단계와 사용자 정의 모델 단계 간의 차이 {#the-difference-between-funnel-stages-and-custom-model-stages}

이제 사용자 지정 모델을 활성화하지 않았더라도 마케팅 단계에서 사용자 지정 단계를 볼 수 있습니다. 단계 단계 기능을 사용하면 됩니다. 단계 이제 단계에 단계를 추가할 수 있지만 단계에 대한 속성은 볼 수 없습니다.

단계 단계는 여전히 터치 포인트로 추적되며 CRM에서 터치 포인트 위치로 표시됩니다. 사용자 지정 모델이 없어도 양식 채우기가 있는 경우 이러한 터치포인트는 여전히 중간 터치 속성을 받을 수 있지만(중간 터치는 10%), 웹 방문만 있는 경우 속성 크레딧이 0입니다.

아래에서 볼 수 있듯이 Diligence 단계는 단계 단계와 별도로 포함되었습니다. 즉, 위치에 Diligence가 포함된 터치포인트가 있지만 해당 터치포인트는 사용자 지정 모델이 활성화되어 있지 않은 경우(최대 10%) 중간 터치 속성 크레딧만 받습니다.

![](assets/5.png)

>[!NOTE]
>
>BAT 사용자 정의 모델의 비헤이비어는 중간 터치가 없는 경우 사용자 정의 모델 중간 터치 비율을 다른 단계에서 균등하게 나누는 것입니다.
