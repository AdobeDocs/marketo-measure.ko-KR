---
unique-page-id: 18874604
description: 사용자 지정 세그멘테이션 - [!DNL Marketo Measure] - 제품 설명서
title: 사용자 지정 세그멘테이션
exl-id: c20a2add-250e-45ff-97a6-1b1c03351b6a
source-git-commit: b59c79236d3e324e8c8b07c5a6d68bd8176fc8a9
workflow-type: tm+mt
source-wordcount: '693'
ht-degree: 0%

---

# 사용자 지정 세그멘테이션 {#custom-segmentation}

세그먼트는 [!DNL Marketo Measure] 특정 데이터 세트에 대해 추가로 드릴다운하려면 ROI 대시보드 를 참조하십시오. 예를 들어, 세그먼트는 지역 또는 채점 시스템에 의해 정의될 수 있습니다.

**사용자 지정 세그먼테이션의 이유**

사용자 지정 세그먼테이션 기능을 사용하면 터치포인트를 하나의 카테고리와 최대 5개의 세그먼트로 필터링할 수 있습니다. ROI 대시가 가리키는 개체(리드 또는 연락처)에 따라 리드/연락처 개체에 있는 필드를 기반으로 세그먼트를 만들 수 있습니다. 또한 Opportunity Object 의 필드를 기반으로 세그먼트를 만들 수도 있습니다.

**사용자 지정 세그먼테이션 기능은 언제 유용합니까?**

사용자 지정 세그먼테이션을 사용하여 특정 레코드 유형에 대한 데이터를 볼 수 있습니다. 필터 논리를 매핑하면 [!DNL Marketo Measure] CRM에 표시되는 것과 동일한 대시보드 수요 워터폴 보기.

**어떻게 설정합니까?**

1단계 - 보려는 정보를 결정합니다.

이 기능을 사용하기 전에 필터링할 터치 포인트 정보를 파악합니다. CRM에서 레코드 유형에 정확한 값을 사용해야 합니다. 터치 포인트를 마케팅 단계의 맨 위에서 맨 아래로 필터링합니다.

2단계 - 로그인하고 세그먼트 기능을 찾습니다.

* 이동 [experience.adobe.com/marketo-measure](https://experience.adobe.com/marketo-measure){target=&quot;_blank&quot;} 및 로그인
* 아래에 [!UICONTROL My Account] 탭, 선택 [!UICONTROL Settings]
* 선택 [!UICONTROL Segments] 사이드바의 옵션(왼쪽, 아래)에서 [!UICONTROL Reporting] 섹션

3단계 - 구성 요소를 이해합니다.

* 이 범례를 사용하여 이 페이지에 있는 다양한 아이콘을 이해할 수 있습니다

![](assets/1.png)

4단계 - 필터 규칙 추가.

* 먼저 범주 이름을 입력합니다. 비즈니스 유형이 예입니다. 완료되면 확인 표시를 클릭합니다. 세그먼트를 추가하려면 먼저 카테고리 이름을 입력해야 합니다
* 더하기 기호를 클릭하여 세그먼트를 추가합니다
* 세그먼트 이름을 입력합니다. 예를 들어 신규 비즈니스, 파트너, 갱신 또는 업셀용 세그먼트가 한 개 있을 수 있습니다

![](assets/2.png)

* 더하기 아이콘을 클릭하여 규칙 입력 필드를 표시합니다. 필드 선택 목록의 옵션은 CRM에서 직접 필드를 가져옵니다

![](assets/3.png)

>[!NOTE]
>
>공식 필드는 규칙 내에서 사용할 수 없으며 선택 목록에 표시되지 않습니다. 수식은 백그라운드에서 계산되며 레코드를 수정하지 않으므로 [!DNL Marketo Measure] 레코드가 규칙에 적합한지 여부를 감지할 수 없습니다.

* 값 옵션은 드롭다운이 아니며 해당 값을 수동으로 입력해야 합니다. Salesforce 조직의 값을 확인해야 합니다
* Opportunity 세그먼트 규칙에 대해 이 프로세스를 반복합니다
* 기타 카테고리는 정의되지 않은 터치포인트를 캡처하는 기본 세그먼트입니다. 기본 세그먼트 이름을 변경할 수 있습니다
* 휴지통 아이콘을 클릭하여 전체 카테고리 또는 카테고리 내의 개별 규칙을 삭제합니다. 또는 연필 아이콘을 클릭하여 카테고리 또는 규칙을 편집합니다
* &quot;저장&quot; 단추와 &quot;저장 및 프로세스&quot; 단추가 있습니다. 저장 단추를 사용하여 시간 경과에 따라 작업 및 변경 사항을 저장합니다. 저장 및 프로세스 단추를 사용할 때는 다음을 확인합니다.

   * 매핑이 정확합니다
   * 카테고리 내에서 추적할 모든 세그먼트를 추가했습니다
   * 저장 및 프로세스 단추가 트리거됩니다 [!DNL Marketo Measure] 모든 터치포인트를 동기화하고 추가한 새 정보를 적용하려면 이 프로세스는 7일이 걸리고 이 기간 동안 규칙을 변경할 수 없습니다

**_추가 참고 사항:_**

리드/연락처 및 기회 둘 다에 대해 규칙이 설정되지 않은 경우 데이터의 일부만 표시됩니다. 자세히 설명하자면, Opportunity 규칙을 설정하지 않으면 Opportunity 와 연관된 Opportunity 가 없는 Lead/Contact 데이터만 표시됩니다. Lead/Contact에 대한 규칙을 설정하지 않으면 Opportunity만 표시됩니다. Lead/Contact가 없는 Opportunity만 표시됩니다.

완료되면 을(를) 클릭합니다. [!UICONTROL Save] 먼저 모든 항목을 다시 확인한 다음 [!UICONTROL Save and Process]. 처럼 저장하고 처리할 때 7일 동안 설정을 편집할 수 없습니다 [!DNL Marketo Measure] 는 이 시간 동안 데이터를 다시 포맷합니다.

**생성된 보고서를 어떻게 저장합니까?**

생성된 보고서를 사용자 인터페이스에 직접 저장할 수 없습니다. 하지만, [!DNL Marketo Measure] 페이지를 책갈피로 지정하여 각 보고서의 레코드를 유지할 수 있도록 세그먼트 이름을 URL에 저장합니다.