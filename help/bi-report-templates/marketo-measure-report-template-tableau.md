---
description: "[!DNL Marketo Measure] 보고서 템플릿 - 타블로 - [!DNL Marketo Measure] - 제품 설명서"
title: "[!DNL Marketo Measure] 보고서 템플릿 - 타블로"
exl-id: 18963be9-5c6e-4454-8244-b50460e2bed5
source-git-commit: 1b0d043e9015f2f8e2f6a3a2a49849bb792c7f21
workflow-type: tm+mt
source-wordcount: '2296'
ht-degree: 0%

---

# [!DNL Marketo Measure] 보고서 템플릿 - 타블로 {#marketo-measure-report-template-tableau}

## 시작하기 {#getting-started}

에 액세스할 수 있습니다 [!DNL Tableau] 보고서 템플릿 [여기](https://github.com/adobe/Marketo-Measure-BI-Templates){target="_blank"}.

를 엽니다. [!DNL Adobe Marketo Measure] 보고 템플릿 타블로 통합 문서 파일입니다.

기존 연결 데이터를 특정 Snowflake 연결 정보로 업데이트해야 합니다. 을(를) 클릭합니다. [!UICONTROL Edit Connection] 버튼을 클릭하고 [[!UICONTROL Data Connection]](#data-connection) 섹션을 참조하십시오.

![](assets/marketo-measure-report-template-tableau-1.png)

## 데이터 연결 {#data-connection}

Snowflake 인스턴스에 데이터 연결을 설정해야 합니다. 이렇게 하려면 사용자 이름 및 암호와 함께 서버 이름이 필요합니다. 이 정보를 찾고 암호를 재설정할 위치에 대한 자세한 내용은 문서화되어 있습니다 [여기](/help/marketo-measure-data-warehouse/data-warehouse-access-reader-account.md){target="_blank"}.

![](assets/marketo-measure-report-template-tableau-2.png)

또한 초기 SQL 명령을 입력해야 합니다. 이 데이터 모델에서는 사용자 지정 쿼리 사용을 지원합니다. 입력할 명령은 &quot;스키마 사용&quot;입니다. `<your schema name>`&quot;. 에서 스키마 이름을 찾을 수 있습니다 [!UICONTROL data warehouse connections] 페이지를 보려면 위에서 참조한 설명서를 참조하십시오.

![](assets/marketo-measure-report-template-tableau-3.png)

### 사용자 지정 SQL 쿼리 {#custom-sql-queries}

왜냐면 [!DNL Tableau] 필터를 설정한 개별 테이블이 아닌 전체 쿼리에 데이터 소스 필터를 적용하여 모델의 각 테이블에 대해 사용자 정의 SQL을 사용하도록 선택했습니다. 이렇게 하면 모델이 테이블 수준에서 삭제된 행과 중복 행을 필터링할 수 있습니다. 예를 들어 데이터 소스 필터로 적용할 경우 세션입니다._deleted_date is null 은 쿼리의 where 절에 추가되어 다음 쿼리가 수행됩니다.

**데이터 소스에 추가된 필터**

```
--A deleted session removes this row completely and the touchpoint data is lost. Select *
   From Touchpoint    tp
      join Session sn
      on tp.session_id = sn.session_id 
 Where tp._deleted_date is null
    and sn._deleted_date is null
```

하지만 세션이 삭제되었지만 해당 터치포인트가 삭제되지 않은 경우 데이터 세트에서 터치 포인트 데이터가 제거된다는 점에서 올바르지 않습니다. 터치 포인트가 삭제되지 않았으므로 데이터 세트에 터치 포인트 데이터가 있기를 바랍니다. 사용자 지정 SQL을 추가하면 필터 기준이 테이블 수준에서 적용되어 다음 쿼리가 수행됩니다.

**사용자 지정 SQL을 통해 적용된 필터**

```
--A deleted session only removes the session related data, and the touchpoint data is preserved. Select *
   From Touchpoint       tp
      join Session sn
      on tp.session_id          = sn.session_id 
      and sn._deleted_date      is null
  Where tp._deleted_date is null
```

## 데이터 변환 {#data-transformations}

몇 가지 변형이 의 데이터에 적용되었습니다 [!DNL Tableau] Snowflake의 원래 상태에서 이러한 변환 대부분은 사용자 정의 SQL 쿼리에 적용되어 [!DNL Tableau] 모델. 테이블을 생성하는 데 사용되는 사용자 정의 SQL을 보려면 테이블 이름을 마우스 오른쪽 단추로 클릭하고 &quot;사용자 정의 SQL 쿼리 편집&quot;을 선택합니다. 특정 변형 중 일부는 아래에 요약되어 있습니다.

![](assets/marketo-measure-report-template-tableau-4.png)

![](assets/marketo-measure-report-template-tableau-5.png)

### 제거된 열 {#removed-columns}

데이터 모델을 단순화하고 중복 및 불필요한 데이터를 제거하기 위해 원래 Snowflake 테이블에서 타블로 로 로 가져온 열 수를 줄였습니다. 제거된 열에는 불필요한 외래 키, 모델의 다른 테이블, 감사 열 및 내부용으로 사용되는 필드에 대한 관계를 통해 더 잘 활용되는 비정규화된 차원 데이터가 포함됩니다 [!DNL Marketo Measure] 처리 중입니다. 사용자 지정 SQL의 선택 섹션에서 가져온 열 목록을 편집하여 비즈니스 요구 사항에 맞게 열을 추가하거나 제거할 수 있습니다.

>[!NOTE]
>
>Data Warehouse의 대부분의 테이블에는 비정규화된 차원 데이터가 포함됩니다. 우리는 모델을 정규화하고 정리하기 위해 노력했다 [!DNL Tableau] 성능 및 데이터 정확도를 향상시킬 수 있습니다. 따라서 팩트 테이블에 추가로 비정규화된 필드를 포함할 때 주의하십시오. 이 경우 테이블 간의 차원 필터링이 중단되며 부정확한 보고가 발생할 수도 있습니다.

### 이름이 변경된 열 {#renamed-columns}

테이블 및 열의 이름을 사용자 친화적으로 변경하고 이름 지정 규칙을 표준화했습니다. 열 이름 변경 사항을 보려면 테이블을 생성하는 사용자 정의 SQL 문을 참조합니다.

### 추가된 행 {#rows-added}

모델의 계산에 통화 변환 기능을 추가하기 위해 Opportunity 및 Cost 테이블에 회사 변환율 및 Target 변환율 열을 추가했습니다. 이러한 열의 값은 행 수준에서 추가되며, 날짜 및 통화 ID에서 변환율 테이블에 결합하여 평가됩니다. 타블로는 팩트 테이블이 두 개 이상의 차원 테이블을 공유할 수 없으므로 이를 사용하는 테이블에 직접 전환율이 추가되었습니다. 이 모델에서 통화 전환이 작동하는 방식에 대한 자세한 내용은 [통화 전환](#currency-conversion) 섹션을 참조하십시오.

![](assets/marketo-measure-report-template-tableau-6.png)

두 자리가 있는 곳이 몇 군데 있습니다 [!DNL Snowflake] 에서 한 개의 테이블을 만들기 위해 결합과 결합되었습니다 [!DNL Tableau] 데이터 모델. 이러한 경우, &quot;유형&quot; 열이 추가되어 어떤 열이 [!DNL Snowflake] 테이블에서 가져오고 행이 나타내는 엔터티를 지정합니다. 결합된 표에 대한 자세한 내용은 이 설명서의 관계 및 데이터 흐름 섹션을 참조하십시오.

![](assets/marketo-measure-report-template-tableau-7.png)

### 세그먼트 이름 {#segment-names}

세그먼트 이름은 사용자 지정할 수 있으므로 Snowflake 데이터 웨어하우스에 일반 열 이름이 있습니다. [!DNL BIZ_SEGMENT_NAMES] 는 매핑의 세그먼트 섹션에 정의된 대로 매핑되는 사용자 지정된 세그먼트 이름과 함께 일반 세그먼트 이름을 나열하는 매핑 테이블입니다 [!DNL Marketo Measure] UI. 사용자 지정 세그먼트 이름을 사용하고 [!DNL Tableau] 모델을 통합하는 경우 이 테이블을 사용하고 타블로 모델 내의 열 이름을 수동으로 바꾸십시오. 세그먼트 열은 리드 및 속성 터치포인트 테이블에 있으며 이름을 한 번만 변경하면 됩니다.

다음 [!UICONTROL CATEGORY] 열에는 카테고리 번호가 나열되며 SEGMENT_NAME 열에는 매핑되는 사용자 지정된 세그먼트 이름이 있습니다.

![](assets/marketo-measure-report-template-tableau-8.png)

이름은 두 가지 방법으로 업데이트할 수 있습니다. 첫 번째 옵션은 사용자 지정 SQL을 업데이트하는 것입니다. 이 예에서 카테고리 1-6은 세그먼트 이름 테이블의 매핑을 기반으로 이름이 변경되었습니다.

![](assets/marketo-measure-report-template-tableau-9.png)

다른 옵션은 에서 직접 열 이름을 바꾸는 것입니다 [!DNL Tableau] 테이블.

![](assets/marketo-measure-report-template-tableau-10.png)

## 데이터 모델 {#data-model}

전체 크기 버전을 보려면 아래 이미지를 클릭하십시오.

[![](assets/marketo-measure-report-template-tableau-11.png)](/help/bi-report-templates/assets/tableau-data-model.png){target="_blank"}

### 관계 및 데이터 흐름 {#relationships-and-data-flow}

터치포인트를 만드는 데 사용되는 이벤트 데이터는 [!UICONTROL Session], [!UICONTROL Task], [!UICONTROL Event], [!UICONTROL Activity], 및 [!UICONTROL Campaign Member] 표. 이러한 이벤트 테이블은 해당 ID를 통해 터치포인트 테이블에 결합하고, 이벤트가 터치포인트를 일으킨 경우 세부 사항이 터치포인트 테이블에 저장됩니다.

리드 접점 및 속성 접점은 터치포인트 테이블에 대한 링크와 함께 이 모델의 한 테이블로 결합됩니다. 터치 포인트 유형 열이 행이 리드인지 속성 터치포인트인지를 지정하기 위해 추가되었습니다. 리드 및 기여도 분석 접점에 대한 대부분의 차원 데이터는 해당 접점으로의 링크에서 소싱됩니다.

Opportunity Stage Transitions와 Lead Stage Transitions는 이 모델의 한 테이블로 결합되며 [!UICONTROL Lead and Attribution] 터치포인트 테이블. 행이 Opportunity 또는 Lead 단계 전환인 경우 Transition Type 열이 추가되었습니다.

비용과 터치포인트 데이터 모두 채널과 캠페인 차원을 공유합니다. 그러나 타블로는 팩트 테이블 간에 공유 차원을 모델링하는 능력이 제한되어 있습니다. 하나의 공유 차원 테이블만 제한되므로 채널 및 캠페인 데이터가 하나의 테이블에 결합되었습니다. 두 차원의 교차 조인을 사용하여 Tableau의 한 테이블로 결합됩니다. 채널 및 캠페인. 고유 ID는 채널과 캠페인 ID를 연결하여 생성됩니다. 이 동일한 id 값이 터치포인트 및 비용 테이블 모두에 추가되어 이 결합된 차원 테이블에 대한 관계를 만듭니다.

![](assets/marketo-measure-report-template-tableau-12.png)

이 모델에서 Campaign 및 채널 차원은 터치 포인트에 연결되어 있으므로 이러한 차원에 대한 모든 보고는 이 링크를 통해 수행되며, 이벤트 데이터에 대한 차원 보고가 불완전할 수 있습니다. 이것은 많은 이벤트가 터치 포인트로 처리된 후에 이러한 차원에 대한 링크가 없기 때문입니다.

>[!NOTE]
>
>세션 과 같은 일부 이벤트에는 캠페인 및 채널 차원에 대한 직접 링크가 있습니다. 이러한 차원에 대한 세션 수준에서 보고가 필요한 경우, 이를 위해 별도의 데이터 모델을 만드는 것이 좋습니다.

비용 데이터는 Snowflake Data Warehouse 비용 테이블 내의 서로 다른 총괄 레벨에 저장됩니다. 모든 광고 공급자에 대해 캠페인 수준 데이터를 채널 수준으로 롤업할 수 있습니다. 이러한 이유로 이 모델은 &quot;campaign_is_aggregatable_cost&quot; 플래그를 기반으로 비용 데이터를 가져옵니다. 자체 보고된 비용은 채널 수준에서만 제출할 수 있으며 Campaign 데이터가 필요하지 않습니다. 가장 정확한 원가 보고를 제공하기 위해 &quot;channel_is_aggregatable_cost&quot; 플래그를 기반으로 자동 보고된 비용을 가져옵니다. 비용 데이터를 가져오는 쿼리는 다음 논리를 사용하여 작성됩니다. ad_provider = &quot;SelfReported&quot;일 경우 channel_is_aggregatable_cost = true, else campaign_is_aggregatable_cost = true입니다.

이 모델의 컨텍스트 내에서, Lead, [!UICONTROL Contact], [!UICONTROL Account], 및 [!UICONTROL Opportunity] 데이터는 차원 데이터로 간주되며, 리드 및 속성 터치포인트 테이블에 직접 연결됩니다.

### 통화 전환 {#currency-conversion}

변환율 테이블의 환율은 법인 통화에서 금액을 변환하는 데 필요한 값을 나타냅니다. 모든 통화로 전환하려면 먼저 원래 통화에서 법인 통화로 전환한 다음 회사 통화에서 선택한 통화로 이중 전환이 필요합니다. 모델의 이 체인의 첫 번째 단계에서는 변환 비율이 있는 두 개의 열을 금액, 기회 및 비용이 있는 테이블에 추가합니다. 이러한 단계는 이 문서의 추가된 행 섹션에 자세히 설명되어 있습니다. 전환율은 정적이 아니어야 하며, 지정된 날짜 범위에 따라 변경할 수 있으므로 모든 통화 변환 계산은 행 수준에서 수행해야 합니다. 원래 통화에서 회사 통화로 변환하는 작업은 값을 회사 전환율로 나눈 다음 대상 전환율을 곱하여 구성합니다. 대상 전환율은 선택한 통화 매개변수 값에 의해 결정됩니다.

* 원래 값을 법인 통화 값/회사 전환율 = 법인 통화로 변환합니다.
* 법인 통화에서 선택한 통화 값으로 값을 변환합니다 `*` 선택한 통화의 전환율 = 선택한 통화로 표시된 값

![](assets/marketo-measure-report-template-tableau-13.png)

이 모델의 통화 변환 측정은 변환율을 식별할 수 없는 경우 환율을 1.0으로 바꿉니다. 측정값에 대한 통화 값을 표시하기 위해 별도의 측정값이 생성되었으며, 계산에 둘 이상의 통화 값이 포함되어 있는 경우(즉, 값을 선택한 통화로 변환할 수 없음) 경고가 표시됩니다. 비용 통화 및 수익 통화와 같은 측정 단위는 원가 또는 수익 데이터를 표시하는 시각에서 도구 설명에 포함됩니다.

![](assets/marketo-measure-report-template-tableau-14.png)

## 데이터 정의 {#data-definitions}

정의가 [!DNL Tableau model] 매개 변수, 사용자 지정 열 및 측정값에 대해 설명합니다.

![](assets/marketo-measure-report-template-tableau-15.png)

에서 바로 오는 열에 대한 정의를 보려면 [!DNL Snowflake]를 보려면 [data warehouse 설명서](/help/marketo-measure-data-warehouse/data-warehouse-schema.md){target="_blank"}.

## 템플릿과 검색 간의 불일치 {#discrepancies-between-templates-and-discover}

### 귀속 수입 {#attributed-revenue}

리드 터치포인트 및 속성 터치포인트는 원래 터치포인트에서 차원 데이터를 상속합니다. 보고 템플릿 모델은 관계에서 터치 포인트에 대해 상속된 모든 차원 데이터를 제공하는 반면, 검색 모델에서 차원 데이터는 리드 및 속성 터치 포인트 레코드에 정규화됩니다. 전체 예상 매출액 또는 특성 파이프라인 수익 값은 두 보고서 간에 정렬되어야 합니다. 하지만 매출이 차원 데이터(채널, 하위 채널 또는 캠페인)로 분류되거나 필터링되면 불일치를 관찰할 수 있습니다. 차원 매출 금액이 템플릿과 검색 간에 일치하지 않는 경우 템플릿 보고서 데이터 세트에 터치 포인트 레코드가 누락될 수 있습니다. 이 문제는 리드 또는 속성 터치 포인트 레코드가 있지만 보고서로 가져온 데이터 세트 내의 터치 포인트 테이블에 해당 레코드가 없을 때 발생합니다. 이러한 표는 수정된 날짜로 필터링되므로 리드/기여도 분석 터치포인트 레코드가 터치포인트 레코드보다 더 최근에 수정되었을 수 있으며, 따라서 리드/기여도 분석 터치포인트를 원래 터치포인트 레코드가 아닌 데이터 세트로 가져올 수 있습니다. 이 문제를 해결하려면 터치 포인트 테이블의 필터링된 날짜 범위를 확장하거나 날짜 제한을 모두 함께 제거하는 것이 좋습니다.

>[!NOTE]
>
>Touchpoint는 큰 테이블이므로 더 완전한 데이터 세트와 가져와야 하는 데이터의 양을 고려해 보십시오.

### 비용 {#cost}

템플릿의 비용 보고는 캠페인 및 채널 수준에서만 사용할 수 있지만, Discover에서는 일부 광고 공급자(예: 광고, 키워드, 광고 그룹 등)에 대해 더 낮은 수준의 세부기간 보고를 제공합니다. 템플릿에서 비용 데이터를 모델링하는 방법에 대한 자세한 내용은 [!UICONTROL Data Model] 섹션을 참조하십시오. 차원 필터인 경우 [!UICONTROL Discover] 가 채널 또는 캠페인으로 설정되면, 채널, 하위 채널 및 캠페인 수준의 비용이 Discover와 보고서 템플릿 간에 연결되어야 합니다.

### ROI {#roi}

ROI는 속성 수익과 비용으로 계산되므로, 해당 섹션에서 설명한 바와 같이 ROI와 동일한 이유로 인해 이러한 계산에서 발생할 수 있는 동일한 불일치가 발생할 수 있습니다.

### 터치포인트 {#touchpoints}

보고 템플릿에 표시된 대로 이러한 지표는 Discover에서 미러링되지 않습니다. 현재 그 둘 사이에는 직접적인 비교가 없다.

### 웹 트래픽 {#web-traffic}

보고 템플릿 데이터 모델은 세션과 터치포인트 간의 관계를 통해 채널, 하위 채널 및 캠페인 차원 데이터를 표준화합니다. 이 차원은 세션으로 비정규화하는 Discover 데이터 모델과 다릅니다. 이러한 차이로 인해 방문 및 방문자에 대한 전체 카운트는 Discover와 보고 템플릿 간에 일치해야 하지만, 차원별로 표시되거나 필터링되면 이러한 숫자가 일치하지 않을 수 있습니다. 템플릿의 차원 데이터는 터치포인트를 초래한 웹 이벤트(즉, 익명의 이벤트가 아닌 이벤트)에만 사용할 수 있기 때문입니다. 자세한 내용은 [데이터 모델](#data-model) 섹션을 참조하십시오.

총 사이트 양식 수 간에 불일치가 약간 있을 수 있습니다 [!DNL Discover] 및 템플릿을 선택합니다. 보고 템플릿의 데이터 모델이 세션 및 터치 포인트에 대한 관계를 통해 사이트 양식에 대한 차원 데이터를 가져오기 때문입니다. 사이트 양식 데이터에 상관 관계가 있는 세션이 없는 인스턴스가 몇 개 있습니다.

### 리드 및 계정 {#leads-and-accounts}

터치된 계정에 대한 차원 보고는 약간 다를 수 있습니다 [!DNL Discover] 터치 포인트와 리드 터치 포인트 또는 속성 터치 포인트 간의 관계에서 나오는 차원 모델링 때문에 다시 발생합니다. 자세한 내용은 특성 매출 섹션에 설명된 세부 사항을 참조하십시오.

모든 리드는 [!UICONTROL Discover] 는 리드 카운트로 분류되며, 보고 템플릿에서 지표는 [!UICONTROL leads] 만지고 따라서 이 측정값에 대한 두 보고서 간에는 직접적인 비교가 없습니다.

### 참여 경로 {#engagement-path}

와 는 직접적인 비교가 없다 [!UICONTROL Engagement Path] 보고서 위치 [!DNL Discover] 및 템플릿을 선택합니다. 의 보고서 [!DNL Discover] 은 터치 포인트를 모델링하고 템플릿의 보고서는 속성 터치 포인트를 모델링합니다. 템플릿은 모든 터치 포인트 데이터를 표시하는 대신 기회와 관련 터치 포인트에 중점을 둡니다.

### 거래 속도 {#deal-velocity}

템플릿의 이 보고서와 Discover의 Velocity 대시보드의 Deal Velocity 타일 간에 차이가 없어야 합니다.
