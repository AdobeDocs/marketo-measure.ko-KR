---
unique-page-id: 18874572
description: 중복 레코드 및 [!DNL Marketo Measure] - [!DNL Marketo Measure]
title: 중복 레코드 및 [!DNL Marketo Measure]
exl-id: e340100c-120a-4771-946d-336a1458da4e
feature: Tracking
source-git-commit: 915e9c5a968ffd9de713b4308cadb91768613fc5
workflow-type: tm+mt
source-wordcount: '288'
ht-degree: 0%

---

# 중복 레코드 및 [!DNL Marketo Measure] {#duplicate-records-and-marketo-measure}

>[!NOTE]
>
>&quot; &quot;을 지정하는 지침이 표시될 수 있습니다.[!DNL Marketo Measure]설명서에는 &quot;가 있지만 CRM에는 &quot;Bizible&quot;이 표시됩니다. 이를 업데이트하고 리브랜딩이 곧 CRM에 반영되도록 노력하고 있습니다.

[!DNL Marketo Measure] crm에서 관련 잠재 고객 또는 연락처와 데이터를 일치시킬 때 이메일 주소를 고유 식별자로 사용합니다. 날짜 [!DNL Marketo Measure] 이메일 주소가 동일한 여러 잠재 고객 또는 연락처를 찾습니다. 모든 레코드에 동일한 데이터가 표시됩니다. 의 영향은 다음으로 잠재 고객 또는 연락처에 대해 보고할 때 발생합니다. [!DNL Marketo Measure] 및 은 구매자 터치포인트가 있는 고유한 사람의 수를 잘못 부풀릴 수 있습니다.

이것은 어떻게 생겼습니까 [!DNL Marketo Measure] 보고?

_예제 보고서: [!DNL Marketo Measure] 구매자 터치포인트가 있는 사람._

![](assets/1-1.png)

다음을 확인할 수 있습니다. [!DNL Marketo Measure] 해당 이메일 주소에 있는 잠재 고객과 연락처가 모두 있는 kelsey@adobe.com의 개인 ID입니다. 이 보고서에는 보고된 두 개의 첫 번째 터치, 보고된 두 개의 리드 생성 터치 및 보고된 두 개의 PostLC 상호 작용이 있습니다. 이러한 중복 기록은 동일한 접점 날짜 및 접점 정보를 공유하므로, 동일한 사람임에도 불구하고 서로 다른 두 사람이라는 결론을 도출할 수 있습니다.

**추천**

* 보고서에서 반환을 극대화하려면 CRM 내의 중복 제거 도구를 활용하여 새로운 고유 레코드만 만들 수 있도록 하는 것이 좋습니다. 이 작업은 Marketing Automation 도구 또는 CRM 내에 설치된 별도의 소프트웨어를 사용하여 수행할 수 있습니다. [!DNL Marketo Measure] 는 레코드를 자동으로 중복 제거하지 않으며 당사의 소프트웨어를 통해 이 서비스를 제공하지 않습니다.
* 중복 항목을 식별할 때 레코드를 수동으로 병합하는 방법도 있습니다. 이 프로세스는 시간이 많이 소요되고 지루할 수 있지만 정확한 보고 결과를 도출하는 것은 시간 투자할 가치가 있습니다.
