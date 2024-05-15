---
unique-page-id: 18874604
description: 사용자 정의 세분화 - [!DNL Marketo Measure]
title: 사용자 정의 세분화
exl-id: c20a2add-250e-45ff-97a6-1b1c03351b6a
feature: Segmentation
source-git-commit: e1ad563aac12ceb6bea6c28621ebd1cb7ec0a923
workflow-type: tm+mt
source-wordcount: '733'
ht-degree: 0%

---

# 사용자 정의 세분화 {#custom-segmentation}

세그먼트는 의 데이터를 필터링하는 기능을 제공합니다. [!DNL Marketo Measure] 특정 데이터 세트에 대해 추가로 드릴다운할 수 있는 ROI 대시보드 . 예를 들어 세그먼트는 지리적 영역 또는 등급 지정 시스템에 의해 정의될 수 있습니다.

**사용자 정의 세그먼테이션의 이유**

사용자 지정 세그멘테이션을 사용하면 카테고리(필터 이름) 및 규칙(필터 값)별로 터치포인트를 필터링할 수 있습니다. Tier 1 고객은 하나의 세그먼트를, Tier 2 고객은 10 개의 세그먼트를 갖게 됩니다. ROI 대시가 가리키는 개체(리드 또는 연락처)에 따라 리드/연락처 개체에 있는 필드를 기반으로 세그먼트를 만들 수 있습니다. 또한 Opportunity 객체에 있는 모든 필드를 기반으로 세그먼트를 생성할 수 있습니다.

**사용자 정의 세분화 기능은 언제 유용합니까?**

사용자 정의 세그먼테이션을 사용하여 특정 레코드 유형의 데이터를 볼 수 있습니다. 필터 논리를 매핑하면 [!DNL Marketo Measure] 대시보드의 Demand Waterfall 보기—CRM에서 볼 수 있는 것과 동일한 데이터입니다.

**어떻게 설정해야 합니까?**

>[!NOTE]
>
>세그먼트 규칙을 업데이트하면 내역 데이터가 다시 처리됩니다.

1단계 - 보려는 정보를 결정합니다.

이 기능을 사용하기 전에 필터링할 터치포인트 정보를 파악합니다. 레코드 종류에 대해 CRM의 정확한 값을 사용해야 합니다. 설정은 마케팅 단계의 맨 위에서 맨 아래로 터치포인트를 필터링합니다.

2단계 - 로그인하고 [!UICONTROL Segments] 기능.

* 다음으로 이동 [experience.adobe.com/marketo-measure](https://experience.adobe.com/marketo-measure){target="_blank"} 및 로그인
* 아래 [!UICONTROL My Account] 탭, 선택 [!UICONTROL Settings]
* 선택 [!UICONTROL Segments] 사이드바의 옵션에서 왼쪽, [!UICONTROL Reporting] 섹션

3단계 - 구성 요소를 이해합니다.

* 이 범례를 사용하여 이 페이지에 있는 다양한 아이콘을 이해합니다

![](assets/1.png)

4단계 - 필터 규칙을 추가합니다.

* 먼저 범주 이름을 입력합니다. [!UICONTROL Business Type] 예. 완료되면 확인 표시를 클릭합니다. 세그먼트를 추가하려면 먼저 카테고리 이름을 입력해야 합니다.
* 더하기 기호를 클릭하여 세그먼트를 추가합니다.
* 세그먼트 이름을 입력합니다. 예를 들어 신규 비즈니스, 파트너, 갱신 또는 상향 판매를 위한 하나의 세그먼트가 있을 수 있습니다

![](assets/2.png)

* 더하기 아이콘을 클릭하여 규칙 입력 필드를 표시합니다. 필드 선택 목록의 옵션은 CRM에서 직접 필드를 가져옵니다

![](assets/3.png)

>[!NOTE]
>
>공식 필드는 규칙 내에서 사용할 수 없으며 선택 목록에 표시되지 않습니다. 수식은 백그라운드에서 계산되며 레코드를 수정하지 않으므로 [!DNL Marketo Measure] 레코드가 규칙에 맞는지 여부를 감지할 수 없습니다.

* 다음 [!UICONTROL Value] 옵션은 드롭다운이 아니며 값을 수동으로 입력해야 합니다. Salesforce 조직의 값을 확인하십시오.
* Opportunities 세그먼트 규칙에 대해 이 프로세스를 반복합니다
* 기타 카테고리는 정의되지 않은 터치포인트를 캡처하는 기본 세그먼트입니다. 기본 세그먼트의 이름을 변경할 수 있습니다
* 전체 범주 또는 범주 내의 개별 규칙을 삭제하려면 휴지통 아이콘을 클릭합니다. 또는 연필 아이콘을 클릭하여 범주 또는 규칙을 편집합니다
* 이(가) 있습니다.[!UICONTROL Save]&quot;버튼 및 &quot;저장 및 처리&quot; 버튼. 저장 버튼을 사용하여 작업 및 시간 경과에 따른 변경 사항을 저장합니다. 다음을 확인한 경우에만 저장 및 처리 단추를 사용합니다.

   * 매핑이 정확합니다
   * 범주 내에 추적할 모든 세그먼트를 추가했습니다.
   * 저장 및 프로세스 버튼이 트리거됩니다. [!DNL Marketo Measure] 모든 터치포인트를 동기화하고 추가한 새 정보를 적용합니다. 이 프로세스는 7일이 소요되며 이 기간 동안 규칙을 변경할 수 없습니다.

**_추가 참고 사항:_**

Lead/Contacts 와 Opportunity 모두에 대해 규칙이 설정되지 않은 경우 데이터의 일부만 표시됩니다. 다시 말해, Opportunities 규칙을 설정하지 않으면 관련된 Opportunities 가 없는 Lead/Contact 데이터만 표시됩니다. Lead/Contact에 대한 규칙을 설정하지 않은 경우에도 마찬가지입니다. 연관된 Lead/Contact 가 없는 Opportunity 만 표시됩니다.

완료되면 다음을 클릭합니다. [!UICONTROL Save] 먼저 모든 항목을 두 번 확인한 다음 [!UICONTROL Save and Process]. 다음 이유로 저장 및 처리한 후 7일 동안 설정을 편집할 수 없습니다. [!DNL Marketo Measure] 은(는) 이 시간 동안 데이터의 서식을 다시 지정합니다.

Marketo Measure Ultimate 고객이고 기본 대시보드 개체를 연락처로 설정한 경우 잠재 고객용 아래 두 필드를 사용하지 마십시오([자세히 알아보기](/help/marketo-measure-ultimate/data-integrity-requirement.md){target="_blank"}).

* b2b.personStatus
* b2b.isConverted

**생성된 보고서는 어떻게 저장합니까?**

생성된 보고서를 사용자 인터페이스에 직접 저장할 수 없습니다. 그러나 [!DNL Marketo Measure] 페이지를 책갈피로 지정하여 각 보고서를 기록할 수 있도록 세그먼트 이름을 URL에 저장합니다.
