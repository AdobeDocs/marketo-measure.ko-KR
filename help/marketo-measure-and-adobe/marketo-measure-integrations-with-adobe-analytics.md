---
description: "[!DNL Marketo Measure] Adobe Analytics과 통합 - [!DNL Marketo Measure] - 제품 설명서"
title: "[!DNL Marketo Measure] 와 통합 [!DNL Adobe Analytics]"
exl-id: 3a125a15-eb74-454a-afb3-75746a1dfac6
feature: Integration
source-git-commit: 8ac315e7c4110d14811e77ef0586bd663ea1f8ab
workflow-type: tm+mt
source-wordcount: '988'
ht-degree: 0%

---

# [!DNL Marketo Measure] Adobe Analytics과 통합 {#marketo-measure-integrations-with-adobe-analytics}

B2B 고객 속성 통합을 통해 [!DNL Marketo Measure] 및 Adobe Analytics을 통해 [!DNL Adobe Analytics] 에서 파생된 중요한 메타데이터가 있는 사용자 프로필 [!DNL Marketo Measure] 기여도 분석 엔진 및 CRM과의 동기화 기능([!DNL Microsoft Dynamics] 및 [!DNL Salesforce]). 이용하는 모든 고객에게 무료로 제공됩니다 [!DNL Adobe Analytics] 및 [!DNL Marketo Measure].

>[!PREREQUISITES]
>
>두 항목 모두에 대해 활성 구독이 있어야 합니다. [!DNL Marketo Measure] 및 [!DNL Adobe Analytics].

## 통합 구성 {#configuring-the-integration}

1. Experience Cloud 콘솔에서 새 고객 속성 데이터 소스를 만들어 시작합니다. 자세한 지침 [은(는) 여기에서 찾을 수 있음](https://docs.adobe.com/content/help/en/core-services/interface/customer-attributes/t-crs-usecase.html).

   이 프로세스의 이후 단계 중 일부에 필요하므로 다음 정보를 참고하십시오.

   * 원하는 값이 될 수 있는 별칭 ID입니다. &quot;marketomeasure_id&quot;를 권장합니다.

   * FTP 서버 호스트 이름 및 자격 증명(사용자 이름 및 암호)

1. 고객 속성 데이터 소스가 만들어지면 로 이동하여 구성 프로세스를 계속합니다. **[!UICONTROL Integrations]** > **[!UICONTROL Connections]** 의 화면 [!DNL Marketo Measure] 관리 메뉴.

1. 을(를) 클릭합니다 **[!UICONTROL Set Up New Customer Attributes Connection]** 버튼을 클릭하고 지침에 따라 고객 속성 통합을 구성합니다. UI는 핵심 서비스 콘솔에서 고객 속성 소스를 만들 때 얻은 별칭 ID 및 FTP 연결 정보를 확인하고, 와 동기화하려는 계정 속성 세트를 선택합니다 [!DNL Adobe Analytics] 계정입니다.

   Adobe IMS 조직 ID도 입력해야 합니다. 이 ID는 Adobe Experience Cloud Admin Console의 오른쪽 아래 모서리에 표시됩니다. 이 ID를 찾는 데 대한 자세한 내용은 Adobe 계정 팀(계정 관리자)에 문의하십시오.

1. 에서 연결 생성을 완료하면 [!DNL Marketo Measure] 계정, 다음을 수행하려면 Experience Cloud 콘솔로 돌아가야 합니다. [스키마 유효성 검사](https://docs.adobe.com/content/help/en/core-services/interface/customer-attributes/validate-schema.html). FTP 파일 업로드에 대해서는 걱정할 필요가 없습니다. [!DNL Marketo Measure] 이(가) 해당 부분을 자동화했습니다. 1단계에서 만든 고객 속성 소스에 대한 &quot;보기/편집&quot; 스키마 화면으로 이동하여 다음과 같은 각 속성에 대한 데이터 유형을 Adobe에게 알려주면 됩니다 [!DNL Marketo Measure] 이(가) 귀하를 대신하여 업로드했습니다. 원하는 경우 업로드한 속성에 대해 새로운 표시용 이름을 만들 수도 있습니다.

   CRM 계정 개체에서 특성을 동기화하도록 선택한 경우에는 과 같이 해당 특성에 대한 새 표시 이름을 선택하는 것이 좋습니다 [!DNL Marketo Measure] 는 일반적으로 보고에 익숙하지 않은 이러한 속성에 대한 API 수준 이름만 채웁니다.

1. 마지막 단계는 속성을 사용할 Experience Cloud 응용 프로그램에 대해 속성 구독을 구성하는 것입니다.  다음에 대한 구독을 구성할 수 있습니다. [!DNL Adobe Analytics] 또는 [!DNL Adobe Target].  이 작업을 수행하는 방법에 대한 자세한 정보 [은(는) 여기에서 찾을 수 있음](https://docs.adobe.com/content/help/en/core-services/interface/customer-attributes/subscription.html).

## 속성 설명 {#attribute-descriptions}

새 B2B 고객 속성 연결을 만들 때 [!DNL Marketo Measure] 에서는 자동으로 표준 B2B 고객 속성 세트를 만듭니다. 이러한 속성은 아래 표에 설명되어 있습니다.

아래 나열된 속성 외에도 CRM의 계정 개체에 첨부된 속성을 업로드할 수도 있습니다. 지정된 사용자에 연결된 계정이 두 개 이상인 경우 [!DNL Marketo Measure] 는 세미콜론으로 구분된 목록에서 일치하는 모든 계정 속성 값을 채웁니다.

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
   <td>지정된 웹 방문자와 연결된 계정 이름. 지정된 사용자에 연결된 계정이 두 개 이상인 경우 [!DNL Marketo Measure] 는 세미콜론으로 구분된 목록에서 일치하는 모든 계정 이름을 채웁니다.<br/>
   <strong>참고:</strong> account.name은 계정 객체의 name 속성에 대한 Salesforce-API 수준 이름입니다. 통합 구성의 스키마 유효성 검사 단계(4단계) 동안 이 속성에 대해 더 나은 표시 이름(예: "회사")을 선택할 수 있습니다.</td>
  </tr>
  <tr> 
   <td>속성 수익 - ‹모델›</td> 
   <td>CRM에서 비공개 기회와 연결하여 이 고객에게 발생한 매출은 다음을 통해 계산됩니다. [!DNL Marketo Measure] 속성 엔진입니다.<br/>
   다음과 같은 각 속성 모델에 대해 다음 속성 중 하나가 있습니다. [!DNL Marketo Measure] 구독은에 대해 허용됩니다(예: "속성 수익 - 전체 경로").</td>
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

**속성 제한에 대한 참고 사항**

이 통합을 통해 표면화된 속성은 여전히 의 계약상 속성 제한에 포함됩니다. [!DNL Adobe Analytics] 및 [!DNL Adobe Target]. 속성 가입(의 5단계)을 통해 표시되는 속성만 [통합 구성](#configuring-the-integration))은 구독한 애플리케이션의 제한에 따라 계산됩니다.

## FAQ {#faqs}

**이 통합을 통해 공유할 속성 세트를 변경하려면 어떻게 해야 합니까?**

속성이에 의해 공유됨 [!DNL Marketo Measure] 이 통합을 통해 Adobe IMS 조직에 연결하여에서 보고 사용할 수 있습니다. [!DNL Adobe Analytics]핵심 서비스 콘솔에 구성된 속성 구독을 통해 표시되어야 합니다. 따라서 속성이 더 이상 표시되지 않도록 제거하려면 [!DNL Adobe Analytics], 속성 구독을 삭제하면 이를 간단히 수행할 수 있습니다.

에서 B2B 고객 속성 연결을 삭제할 수도 있습니다. [!DNL Marketo Measure] 더 이상 공유하지 않을 속성을 연결 구성에서 제외된 상태로 다시 만듭니다. 마찬가지로, 통합에 속성을 추가하려면 기존 연결을 삭제하고 구성에 원하는 속성이 추가된 새 연결을 만들어야 합니다.

위의 경우, 속성 연결을 처음으로 구성할 때 속성을 선택할 때 가능한 한 포함하는 것이 좋습니다.

**이 통합에 대한 몇 가지 사용 사례는 무엇입니까?**

1. 계정 기반 트래픽 지표: 계정 이름 속성을 사용하여 Adobe Analytics에서 하나 이상의 대상 계정의 세그먼트를 만들고 대상 계정에서 시작된 트래픽의 하위 집합에 대한 사이트 트래픽 지표를 분석할 수 있습니다.
1. 콘텐츠 분석: 매출 지표를 사용하여 제품이나 서비스를 최종적으로 구매하는 고객 또는 특정 단계 관심 단계에 도달한 고객에게 가장 매력적인 사이트 콘텐츠를 분석합니다.
1. 라이브 거래 지원: CRM의 특정 진행 중 기회와 연관된 사용자의 사이트 동작을 분석하여 영업 팀에 실행 가능한 통찰력을 제공합니다.
