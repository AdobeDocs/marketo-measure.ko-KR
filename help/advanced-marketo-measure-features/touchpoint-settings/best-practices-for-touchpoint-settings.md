---
description: 터치포인트 설정에 대한 우수 사례 - [!DNL Marketo Measure]
title: 접점 설정에 대한 우수 사례
exl-id: 01e314a6-e33d-45cd-aaa3-c212afec07d1
feature: Touchpoints
source-git-commit: 9e672d0c568ee0b889461bb8ba6fc6333edf31ce
workflow-type: tm+mt
source-wordcount: '651'
ht-degree: 0%

---

# 접점 설정에 대한 우수 사례 {#best-practices-for-touchpoint-settings}

## 개요 {#overview}

[!DNL Marketo Measure] 앱의 [!UICONTROL Touchpoint Settings] 섹션에서 [!DNL Marketo Measure] 데이터 및 관련 시스템의 터치포인트를 표시하지 않거나 제거하는 규칙을 설정할 수 있습니다. 이러한 규칙을 사용하면 구매자 접점 데이터에 표시할 필요가 없거나 추적 및 데이터 수집을 방해하지 않고 속성 크레딧을 받고 싶지 않은 특정 데이터 세트를 분리하는 데 도움이 될 수 있습니다.

**접점 제거**&#x200B;는 [!DNL Marketo Measure]이(가) 규칙 기준에 맞는 CRM의 모든 접점을 제거(즉, 제거)함을 의미합니다. 데이터는 [!DNL Marketo Measure] ROI 대시보드(검색) 내에서 보고할 수 있지만 CRM에는 표시되지 않습니다. CRM 내에서 데이터 스토리지 제한에 대한 스트레스를 완화하는 데 일반적으로 사용됩니다.

**접점 억제**&#x200B;는 접점 제거와 유사하지만 ROI 대시보드 내에서 데이터를 보고할 수 없습니다. 억제된 터치포인트는 CRM 또는 Discover에서 액세스할 수 없습니다. 비표시 를 통해 CRM 데이터와 검색 데이터가 일치하게 됩니다. 일반적으로 속성 크레딧을 받을 접점 데이터를 미세 조정하고 추가로 지정하는 데 사용됩니다.

[!DNL Marketo Measure] 앱에서 [!UICONTROL Touchpoint Settings] 섹션은 네 개의 주요 섹션으로 나뉩니다. 각 섹션은 서로 다른 데이터 세트를 억제하거나 제거합니다. 아래 키를 사용하여 규칙이 원하는 터치포인트를 억제 또는 제거하는지 확인하십시오.

* CRM에서 구매자 터치포인트 제거
   * **CRM**&#x200B;에서 **Buyer Touchpoint 데이터**(기회가 아닌 개인에 연결된 터치포인트)를 제거하는 규칙을 만들려면 이 섹션을 사용하십시오.
* CRM에서 구매자 터치포인트 제외
   * **CRM** 및 **검색**&#x200B;에서 **Buyer Touchpoint 데이터**(기회가 아닌 개인과 연결된 터치포인트)를 제거하는 규칙을 만들려면 이 섹션을 사용하십시오.
* CRM에서 구매자 속성 터치포인트 제거
   * **CRM**&#x200B;에서 **Buyer Attribution Touchpoint** 데이터(영업 기회 및 매출에 연결된 터치포인트)를 제거하는 규칙을 만들려면 이 섹션을 사용하십시오
* CRM에서 구매자 속성 터치포인트 제외
   * **CRM** 및 **검색**&#x200B;에서 **Buyer Attribution Touchpoint** 데이터(영업 기회 및 매출에 연결된 터치포인트)를 제거하는 규칙을 만들려면 이 섹션을 사용하십시오.

## 우수 사례 {#best-practice}

접점 설정 규칙을 처음 설정하든 아니면 단순히 규칙을 검토하여 정확성을 확인하든 관계없이 다음 모범 사례를 염두에 두십시오.

* 규칙을 만들기 전에 제외하거나 제거할 데이터 목록을 설정합니다
* 설정하는 규칙을 명확하게 나타내는 필드를 정확하게 식별합니다
* 규칙에 올바른 연산자를 지정했는지 확인하십시오
* 위의 키를 사용하여 규칙이 터치포인트 설정의 올바른 섹션에 지정되었는지 확인하십시오
* CRM의 구매자 접점 보고서에 규칙 로직을 복제하여 규칙을 구현하기 전에 규칙을 테스트하여 원하는 데이터를 억제하거나 제거하는지 확인하십시오

## 유지 관리에 대한 우수 사례 {#best-practice-for-maintenance}

올바르게 정의되지 않은 경우 데이터를 크게 변경할 수 있으므로 [!UICONTROL Touchpoint Settings]을(를) 검토하는 것이 중요합니다. 우수 사례로서, 1년에 두 번 이상 터치포인트 설정을 검토하는 것이 좋습니다. [!DNL Marketo Measure] 앱의 터치포인트 설정 섹션에서 설정된 규칙을 시각적으로 간단하게 검토합니다. 이 검토를 통해 터치포인트 설정이 최신 상태이고 그에 따라 모든 변경 사항을 적용할 수 있다고 확신할 수 있습니다.

[!UICONTROL Touchpoint] 설정을 검토하는 이유는 다음과 같습니다.

* 마케팅 팀에서의 이직률
* 웹 사이트 구조에 대한 주요 업데이트
* 더 이상 유용하지 않은 접점 데이터 식별
   * 속성 크레딧을 받지 않아야 한다고 생각하는 터치포인트 데이터를 발견할 때마다 [!DNL touchpoint suppression] 규칙은 데이터를 가능한 한 깨끗하고 정확하게 유지하는 기능입니다.
* 제외 또는 제거 규칙을 정의하는 데 사용되는 필드 변경 사항

>[!MORELIKETHIS]
>
>* [접점 제거 및 제외 개요](/help/advanced-marketo-measure-features/touchpoint-settings/touchpoint-removal-and-touchpoint-suppression.md)
>* [터치포인트를 삭제하지 않는 이유](/help/advanced-marketo-measure-features/touchpoint-settings/why-you-should-never-delete-touchpoints.md)
>* [구매자 접점(BT) 대 구매자 속성 접점(BAT)](/help/configuration-and-setup/getting-started-with-marketo-measure/difference-between-buyer-touchpoints-and-buyer-attribution-touchpoints.md)

