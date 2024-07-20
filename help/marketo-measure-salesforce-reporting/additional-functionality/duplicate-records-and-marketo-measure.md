---
unique-page-id: 18874572
description: 중복 레코드 및  [!DNL Marketo Measure] - [!DNL Marketo Measure]
title: 중복 레코드 및  [!DNL Marketo Measure]
exl-id: e340100c-120a-4771-946d-336a1458da4e
feature: Tracking
source-git-commit: 9e672d0c568ee0b889461bb8ba6fc6333edf31ce
workflow-type: tm+mt
source-wordcount: '278'
ht-degree: 0%

---

# 중복 레코드 및 [!DNL Marketo Measure] {#duplicate-records-and-marketo-measure}

>[!NOTE]
>
>설명서에 &quot;[!DNL Marketo Measure]&quot;을(를) 지정하는 지침이 표시될 수 있지만 CRM에는 &quot;Bizible&quot;이 표시됩니다. 이를 업데이트하고 리브랜딩이 곧 CRM에 반영되도록 노력하고 있습니다.

[!DNL Marketo Measure]은(는) CRM의 관련 잠재 고객 또는 연락처와 데이터를 일치시킬 때 전자 메일 주소를 고유 식별자로 사용합니다. [!DNL Marketo Measure]이(가) 전자 메일 주소가 같은 여러 개의 잠재 고객 또는 연락처를 찾으면 모든 레코드에 동일한 데이터가 표시됩니다. 이에 대한 영향은 [!DNL Marketo Measure]과(와)의 리드 또는 연락처에 대해 보고할 때 발생하며, 구매자 터치포인트를 보유한 고유한 사람 수를 잘못 부풀릴 수 있습니다.

[!DNL Marketo Measure] 보고에서는 어떻게 보이나요?

_예제 보고서: [!DNL Marketo Measure] 구매자 터치포인트가 있는 사람_

![](assets/1-1.png)

kelsey@adobe.com 의 [!DNL Marketo Measure] 개인 ID에 대해 해당 이메일 주소에 있는 잠재 고객과 연락처가 모두 있음을 확인할 수 있습니다. 이 보고서에는 두 개의 첫 번째 터치, 두 개의 리드 생성 터치 및 두 개의 PostLC 상호 작용이 보고됩니다. 이러한 중복 기록은 접점 날짜 및 접점 정보를 공유하므로 동일한 사람임에도 불구하고 두 명의 다른 사람이라는 결론을 도출할 수 있습니다.

**권장 사항**

* 보고서에서 반환을 극대화하려면 CRM 내에서 중복 제거 도구를 사용하여 새로운 고유 레코드만 만들 수 있도록 하는 것이 좋습니다. 이 작업은 Marketing Automation 도구 또는 CRM 내에 설치된 별도의 소프트웨어를 사용하여 수행할 수 있습니다. [!DNL Marketo Measure]은(는) 레코드를 자동으로 중복 제거하지 않으며 소프트웨어를 통해 이 서비스를 제공하지 않습니다.
* 중복 항목을 식별할 때 레코드를 수동으로 병합하는 방법도 있습니다. 이 프로세스는 시간이 많이 소요되고 지루할 수 있지만, 정확한 보고 결과를 도출하는 것은 시간 투자할 가치가 있습니다.
