---
description: "[!DNL Marketo Measure] Adobe Analytics과 통합 - [!DNL Marketo Measure]"
title: " [!DNL Adobe Analytics]과(와) [!DNL Marketo Measure]개의 통합"
exl-id: 3a125a15-eb74-454a-afb3-75746a1dfac6
feature: Integration
source-git-commit: 1a274c83814f4d729053bb36548ee544b973dff5
workflow-type: tm+mt
source-wordcount: '914'
ht-degree: 0%

---

# Adobe Analytics과 [!DNL Marketo Measure] 통합 {#marketo-measure-integrations-with-adobe-analytics}

B2B 고객 특성 통합을 통해 [!DNL Marketo Measure] 및 Adobe Analytics의 상호 사용자가 [!DNL Marketo Measure] 속성 엔진에서 파생된 중요한 메타데이터와 CRM([!DNL Microsoft Dynamics] 및 [!DNL Salesforce])과의 동기화 기능을 통해 [!DNL Adobe Analytics] 사용자 프로필을 보강할 수 있습니다. [!DNL Adobe Analytics] 및 [!DNL Marketo Measure]을(를) 사용하는 모든 고객에게 무료로 제공됩니다.

>[!PREREQUISITES]
>
>[!DNL Marketo Measure]과(와) [!DNL Adobe Analytics] 모두에 대해 활성 구독이 있어야 합니다.

## 통합 구성 {#configuring-the-integration}

1. Experience Cloud 콘솔에서 새 고객 속성 데이터 Source을 만듭니다. 자세한 지침 [은(는) 여기에서 찾을 수 있습니다](https://experienceleague.adobe.com/docs/core-services/interface/services/customer-attributes/t-crs-usecase.html?lang=ko).

   이후 단계에서 필요한 다음 정보를 참고하십시오.

   * 원하는 값이 될 수 있는 별칭 ID입니다. &quot;marketomeasure_id&quot;를 권장합니다.

   * FTP 서버 호스트 이름 및 자격 증명(사용자 이름 및 암호)

1. 고객 특성 데이터 Source이 만들어지면 [!DNL Marketo Measure] 관리 메뉴의 **[!UICONTROL Integrations]** > **[!UICONTROL Connections]** 화면으로 이동하여 구성 프로세스를 계속합니다.

1. **[!UICONTROL Set Up New Customer Attributes Connection]** 단추를 클릭하고 지침에 따라 고객 특성 통합을 구성하십시오. 핵심 서비스 콘솔에서 고객 속성 Source을 만들 때 얻은 별칭 ID 및 FTP 연결 정보를 묻는 UI의 메시지가 표시됩니다. [!DNL Adobe Analytics] 계정과 동기화할 계정 특성 집합을 선택하십시오.

   Adobe IMS 조직 ID를 입력합니다. 이 ID는 Adobe Experience Cloud Admin Console의 오른쪽 아래 모서리에 표시됩니다. 이 ID를 찾는 데 대한 자세한 내용은 Adobe 계정 팀(계정 관리자)에 문의하십시오.

1. [!DNL Marketo Measure] 계정에서 연결을 만든 후에는 Experience Cloud 콘솔로 돌아가서 [스키마를 확인](https://experienceleague.adobe.com/docs/core-services/interface/services/customer-attributes/validate-schema.html?lang=ko)해야 합니다. FTP 파일 업로드에 대해 걱정할 필요가 없습니다. [!DNL Marketo Measure]에서 해당 부분을 자동화했습니다. 1단계에서 만든 고객 특성 Source에 대한 &quot;보기/편집&quot; 스키마 화면으로 이동하여 [!DNL Marketo Measure]이(가) 대신 업로드한 각 특성에 대한 데이터 형식을 Adobe에게 알려 줍니다. 원하는 경우 업로드한 속성에 대해 새로운 표시용 이름을 만들 수도 있습니다.

   CRM 계정 개체의 특성을 동기화하도록 선택한 경우 [!DNL Marketo Measure]이(가) 일반적으로 보고에 적합하지 않은 해당 특성에 대한 API 수준 이름만 채우므로 이 특성에 대해 새 표시 이름을 선택하는 것이 좋습니다.

1. 마지막 단계는 속성을 사용할 Experience Cloud 응용 프로그램에 대해 속성 구독을 구성하는 것입니다. [!DNL Adobe Analytics] 또는 [!DNL Adobe Target]에 대한 구독을 구성할 수 있습니다.  [하는 방법에 대한 자세한 내용은 여기](https://experienceleague.adobe.com/docs/core-services/interface/services/customer-attributes/subscription.html?lang=ko)에서 확인할 수 있습니다.

## 속성 설명 {#attribute-descriptions}

B2B 고객 특성 연결을 만들면 [!DNL Marketo Measure]에서 자동으로 표준 B2B 고객 특성 집합을 만듭니다. 이러한 속성은 아래 표에 설명되어 있습니다.

아래 나열된 속성 외에도 CRM의 계정 개체에 첨부된 속성을 업로드할 수도 있습니다. 지정된 사용자에 연결된 계정이 두 개 이상인 경우 [!DNL Marketo Measure]은(는) 세미콜론으로 구분된 목록에 일치하는 모든 계정 특성 값을 채웁니다.

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
   <td>지정된 웹 방문자와 연결된 계정 이름. 지정된 사용자에 연결된 계정이 두 개 이상인 경우 [!DNL Marketo Measure]은(는) 세미콜론으로 구분된 목록에 일치하는 모든 계정 이름을 채웁니다.<br/>
   <strong>참고:</strong> account.name은 계정 개체에 있는 이름 특성에 대한 Salesforce-API 수준 이름입니다. 통합 구성의 스키마 유효성 검사 단계(4단계) 동안 이 속성에 대해 더 나은 표시 이름(예: "회사")을 선택할 수 있습니다.</td>
  </tr>
  <tr> 
   <td>속성 수익 - ‹모델›</td> 
   <td>[!DNL Marketo Measure] 속성 엔진에서 계산한 CRM의 비공개 기회와의 연결을 통해 이 고객에게 발생한 매출입니다.<br/>
   [!DNL Marketo Measure] 구독이 허용하는 각 속성 모델에 대해 이러한 특성 중 하나가 있습니다(예: "속성 수익 - 전체 경로").</td>
  </tr>
  <tr> 
   <td>가장 깊은 단계</td> 
   <td>주어진 사용자와 연계된 열린 영업 기회의 가장 깊은 단계.</td>
  </tr>
  <tr> 
   <td>영업 기회 열기</td> 
   <td>CRM 데이터에 따라 해당 사용자가 연결되어 있는 영업 기회 ID의 세미콜론으로 구분된 목록입니다.</td>
  </tr> 
 </tbody> 
</table>

**특성 제한에 대한 참고 사항**

[!DNL Adobe Analytics] 및 [!DNL Adobe Target]의 계약상 특성 제한에 대해 이 통합을 통해 표면화된 특성입니다. 특성 구독([통합 구성](#configuring-the-integration)의 5단계)을 통해 표시되는 특성만 구독한 응용 프로그램에 대한 제한에 대해 계산됩니다.

## FAQ {#faqs}

**이 통합을 통해 공유할 특성 집합을 변경하려면 어떻게 해야 합니까?**

[!DNL Marketo Measure]이(가) 이 통합을 통해 Adobe IMS 조직에 공유하는 특성을 보고 [!DNL Adobe Analytics]에서 사용하려면 핵심 서비스 콘솔에 구성된 특성 구독을 통해 특성이 표시되어야 합니다. 따라서 [!DNL Adobe Analytics]에 더 이상 나타나지 않도록 특성을 제거하려면 특성 구독을 삭제하면 됩니다.

[!DNL Marketo Measure]에서 B2B 고객 특성 연결을 삭제하고 더 이상 공유하지 않으려는 특성을 사용하여 연결 구성에서 제외된 연결을 다시 만들 수도 있습니다. 마찬가지로 통합에 속성을 추가하려면 기존 연결을 삭제하고 구성에 원하는 속성이 추가된 새 연결을 만들어야 합니다.

위의 경우, 속성 연결을 처음으로 구성할 때 속성을 선택할 때 가능한 한 포함하는 것이 좋습니다.

**이 통합에 대한 사용 사례는 무엇입니까?**

1. 계정 기반 트래픽 지표: 계정 이름 속성을 사용하여 Adobe Analytics에서 하나 이상의 대상 계정의 세그먼트를 만들고 대상 계정에서 시작된 트래픽의 하위 집합에 대한 사이트 트래픽 지표를 분석할 수 있습니다.
1. 콘텐츠 분석: 매출 지표를 사용하여 제품이나 서비스를 최종적으로 구매하는 고객 또는 특정 단계 관심 단계에 도달한 고객에게 가장 매력적인 사이트 콘텐츠를 분석합니다.
1. 라이브 거래 지원: CRM의 특정 진행 중 기회와 연관된 사용자의 사이트 동작을 분석하여 영업 팀에 실행 가능한 통찰력을 제공합니다.
