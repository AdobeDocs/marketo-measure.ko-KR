---
description: "[!DNL Marketo Measure] Adobe Analytics과의 통합 - [!DNL Marketo Measure] - 제품 설명서"
title: "[!DNL Marketo Measure] 통합 [!DNL Adobe Analytics]"
exl-id: 3a125a15-eb74-454a-afb3-75746a1dfac6
source-git-commit: 54337a0a65b79d80ebeae6531f5e92f4f48721a7
workflow-type: tm+mt
source-wordcount: '985'
ht-degree: 0%

---

# [!DNL Marketo Measure] Adobe Analytics과 통합 {#marketo-measure-integrations-with-adobe-analytics}

B2B 고객 속성 통합을 통해 [!DNL Marketo Measure] 그리고 Adobe Analytics은 [!DNL Adobe Analytics] 사용자 프로필에서 파생된 중요한 메타데이터가 있는 사용자 프로필 [!DNL Marketo Measure] 속성 엔진 및 CRM과의 동기화 기능을 통해 속성 엔진([!DNL Microsoft Dynamics] 및 [!DNL Salesforce]). 모든 고객이 무료로 이용할 수 있습니다 [!DNL Adobe Analytics] 및 [!DNL Marketo Measure].

>[!PREREQUISITES]
>
>두 가지 모두에 대한 활성 구독이 있어야 합니다 [!DNL Marketo Measure] 및 [!DNL Adobe Analytics].

## 통합 구성 {#configuring-the-integration}

1. 먼저 Experience Cloud 콘솔에서 새 고객 속성 데이터 소스를 만듭니다. 자세한 지침 [여기에서 찾을 수 있습니다.](https://docs.adobe.com/content/help/en/core-services/interface/customer-attributes/t-crs-usecase.html).

   프로세스의 이후 단계 중 일부에 필요한 경우 다음 정보를 기록하십시오.

   * 원하는 값일 수 있는 별칭 ID. &quot;marketomeasure_id&quot;를 권장합니다

   * FTP 서버 호스트 이름 및 자격 증명(사용자 이름 및 암호)

1. 고객 속성 데이터 소스가 생성되면 다음 위치로 이동하여 구성 프로세스를 계속 진행합니다 **[!UICONTROL Integrations]** > **[!UICONTROL Connections]** 의 화면 [!DNL Marketo Measure] 관리 메뉴.

1. 을(를) 클릭합니다. **[!UICONTROL Set Up New Customer Attributes Connection]** 버튼을 클릭하고 지침에 따라 고객 속성 통합을 구성합니다. UI에서 핵심 서비스 콘솔에서 고객 속성 소스를 만들 때 획득한 별칭 ID 및 FTP 연결 정보를 확인하고, 여기에 동기화할 계정 속성 세트를 선택하라는 메시지를 표시합니다 [!DNL Adobe Analytics] 계정이 필요합니다.

   Adobe IMS 조직 ID도 입력해야 합니다. 이 ID는 Adobe Experience Cloud Admin Console의 오른쪽 아래 모서리에 표시됩니다. 이 ID를 찾는 데 도움이 필요하면 고객 성공 관리자에게 문의하십시오.

1. 에서 연결 만들기를 완료하면 [!DNL Marketo Measure] account: Experience Cloud 콘솔으로 돌아가야 합니다 [스키마 유효성 검사](https://docs.adobe.com/content/help/en/core-services/interface/customer-attributes/validate-schema.html). FTP 파일 업로드에 대해 걱정할 필요가 없습니다. [!DNL Marketo Measure] 는 자동으로 해당 부분을 제공합니다. 1단계에서 만든 고객 속성 소스에 대한 &quot;보기/편집&quot; 스키마 화면으로 이동하여 해당 속성에 대해 데이터 유형이 무엇인지 Adobe에 알려면 됩니다 [!DNL Marketo Measure] 를 대신 업로드했습니다. 원하는 경우 업로드한 속성에 대해 새 디스플레이 친숙한 이름을 생성할 수도 있습니다.

   CRM 계정 개체의 특성을 동기화하도록 선택한 경우 다음과 같이 새 표시 이름을 선택하는 것이 좋습니다 [!DNL Marketo Measure] 는 이러한 속성에 대한 API 수준 이름만 채우며, 일반적으로 보고에 익숙하지 않습니다.

1. 마지막 단계는 의 속성을 사용할 Experience Cloud 애플리케이션에 대한 속성 가입을 구성하는 것입니다.  에 대한 구독을 구성할 수 있습니다 [!DNL Adobe Analytics] 또는 [!DNL Adobe Target].  방법 추가 정보 [여기에서 찾을 수 있습니다.](https://docs.adobe.com/content/help/en/core-services/interface/customer-attributes/subscription.html).

## 속성 설명 {#attribute-descriptions}

새 B2B 고객 속성 연결을 만들면 [!DNL Marketo Measure] 는 자동으로 표준 B2B 고객 속성 세트를 만듭니다. 이러한 속성은 아래 표에 설명되어 있습니다.

아래 나열된 속성 외에도 CRM에서 계정 개체에 첨부된 모든 속성을 업로드할 수 있습니다. 지정된 사용자에게 둘 이상의 계정이 연결된 경우 [!DNL Marketo Measure] 은(는) 세미콜론으로 구분된 목록에 일치하는 모든 계정 속성 값을 채웁니다.

<table> 
 <colgroup> 
  <col> 
  <col> 
 </colgroup> 
 <tbody> 
  <tr> 
   <td><b>속성 이름</b></td> 
   <td><b>설명</b></td>
  </tr> 
  <tr> 
   <td>Account.Name</td> 
   <td>주어진 웹 방문자와 연관된 계정 이름입니다. 지정된 사용자에게 둘 이상의 계정이 연결된 경우 [!DNL Marketo Measure] 세미콜론으로 구분된 목록에서 일치하는 모든 계정 이름을 채웁니다.<br/>
   <strong>참고:</strong> account.name은 계정 개체에 있는 이름 속성에 대한 Salesforce-API 수준 이름입니다. 통합 구성(4단계)의 스키마 유효성 검사 단계에서 이 속성에 대해 더 나은 표시 이름(예: "회사")을 선택할 수 있습니다.</td>
  </tr>
  <tr> 
   <td>귀속 수익 - ? 모델</td> 
   <td>CRM에서 계산된 대로, CRM에서 닫힌 원 기회와 연결되어 이 고객에게 할당된 수익입니다 [!DNL Marketo Measure] 속성 엔진.<br/>
   사용자의 [!DNL Marketo Measure] 가입은 을 허용합니다(예: "속성 수입 - 전체 경로").</td>
  </tr>
  <tr> 
   <td>가장 깊은 단계 단계 단계</td> 
   <td>주어진 사용자와 연관된 오픈 기회의 가장 깊은 단계 단계입니다.</td>
  </tr>
  <tr> 
   <td>기회 열기</td> 
   <td>주어진 사용자가 CRM 데이터에 따라 연결되는 영업 기회 ID의 세미콜론으로 구분된 목록입니다.</td>
  </tr> 
 </tbody> 
</table>

**속성 제한에 대한 참고 사항**

이 통합을 통해 표면화된 속성은 여전히 [!DNL Adobe Analytics] 및 [!DNL Adobe Target]. 속성 가입(의 5단계)을 통해 나타나는 특성만 [통합 구성](#configuring-the-integration))은 구독한 애플리케이션의 제한에 대해 계산됩니다.

## FAQ {#faqs}

**이 통합을 통해 공유할 속성 세트를 변경하려면 어떻게 해야 합니까?**

에서 공유하는 속성의 경우 [!DNL Marketo Measure] 에서 보고 사용할 수 있도록 이 통합을 통해 Adobe IMS 조직에 연결 [!DNL Adobe Analytics]를 채울 때는 핵심 서비스 콘솔에 구성된 속성 구독을 통해 표시해야 합니다. 따라서 속성이 더 이상 표시되지 않도록 속성을 제거하려면 [!DNL Adobe Analytics]를 설정하는 경우 속성 가입을 삭제하기만 하면 됩니다.

B2B 고객 속성 연결은에서 삭제할 수도 있습니다 [!DNL Marketo Measure] 더 이상 연결 구성에서 제외되지 않을 속성으로 다시 만듭니다. 마찬가지로 속성에 속성을 추가하려면 기존 연결을 삭제하고 원하는 속성이 구성에 추가된 새 연결을 만들어야 합니다.

위의 경우, 처음으로 속성 연결을 구성할 때 속성을 선택할 때 가능한 한 포함할 것을 권장합니다.

**이 통합에 대한 몇 가지 사용 사례는 무엇입니까?**

1. 계정 기반 트래픽 지표: 계정 이름 속성을 사용하여 Adobe Analytics에서 하나 이상의 대상 계정의 세그먼트를 만들고, 대상 계정에서 시작된 트래픽의 하위 세트에 대해서만 사이트 트래픽 지표를 분석할 수 있습니다.
1. 컨텐츠 분석: 매출 지표를 사용하여 궁극적으로 제품이나 서비스를 구매하는 고객 또는 특정 관심 단계 단계에 도달하는 고객에게 가장 매력적인 사이트 콘텐츠를 분석합니다.
1. 라이브 거래 지원: CRM에서 특정 영업 기회와 연관된 사용자의 사이트 동작을 분석하여 영업 팀에 조치 가능한 통찰력을 제공합니다.
