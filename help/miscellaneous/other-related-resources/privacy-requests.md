---
description: 개인 정보 보호 요청 - [!DNL Marketo Measure]
title: 개인 정보 보호 요청
exl-id: 883e475f-9868-412a-b505-230556f38484
feature: APIs, Tracking
source-git-commit: 4787f765348da71bc149c997470ce678ba498772
workflow-type: tm+mt
source-wordcount: '249'
ht-degree: 0%

---

# 개인 정보 보호 요청 {#privacy-requests}

이 문서는에 보낼 수 있는 개별 데이터 개인 정보 보호 요청 관리에 대한 개요를 제공합니다 [!DNL Marketo Measure] 다음을 통해 [!DNL Privacy Service] UI 및 **[!DNL Privacy Service]API**.

에서 소비자 데이터에 액세스하고 삭제하기 위한 개별 요청을 제출할 수 있습니다. [!DNL Marketo Measure] 두 가지 방법으로:

* 다음을 통해 [[!DNL Privacy Service] UI](https://experienceleague.adobe.com/docs/experience-platform/privacy/ui/overview.html){target="_blank"}.
* 다음을 통해 **[!DNL Privacy Service]API**. 설명서 참조 [여기](https://experienceleague.adobe.com/docs/experience-platform/privacy/api/overview.html){target="_blank"} and the API reference [here](https://developer.adobe.com/experience-platform-apis/references/privacy-service/){target="_blank"}.

다음 [Privacy Service](https://experienceleague.adobe.com/docs/experience-platform/privacy/home.html){target="_blank"} 는 데이터 액세스 요청과 데이터 삭제, 이렇게 두 가지 유형의 요청을 지원합니다.

액세스 및 삭제 요청을 만드는 방법을 살펴보겠습니다.

## Marketo Measure에 대한 요청을 전송하기 위한 필수 설정 {#required-setup-to-send-requests-for-marketo-measure}

다음에 대한 데이터 액세스 및 삭제를 요청하려면 [!DNL Marketo Measure], 다음을 수행해야 합니다.

1. 다음을 확인하십시오.

   a. IMS 조직 ID

   b. 조치를 취하고자 하는 사람의 이메일 주소

   IMS 조직 ID는 @AdobeOrg이 추가된 24자 영숫자 문자열입니다. 마케팅 팀이나 내부 Adobe 시스템 관리자가 조직의 IMS 조직 ID를 모르는 경우에는 Adobe 고객 지원 센터(gdprsupport@adobe.com)에 문의하십시오. Privacy API에 요청을 제출하려면 IMS 조직 ID가 필요합니다.

1. 위치 [!DNL Privacy Service]에 액세스 및 삭제 요청을 제출할 수 있습니다. [!DNL Marketo Measure]을 클릭하고 기존 요청의 상태를 확인합니다.

## 의 필수 필드 값 [!DNL Marketo Measure] JSON 요청 {#required-field-values-in-marketo-measure-json-requests}

&quot;companyContexts&quot;:

* &quot;네임스페이스&quot;: **imsOrgID**
* &quot;value&quot;: `<Your IMS Org ID Value>`

&quot;users&quot;:

* &quot;action&quot;: 다음 중 하나 [!UICONTROL access] 또는 삭제
* &quot;userIDs&quot;:
   * &quot;namespace&quot;: 이메일
   * &quot;type&quot;: standard
   * &quot;value&quot;: `<Data Subject's Email Address>`

&quot;include&quot;:

* **marketoMeasure** (요청에 적용되는 Adobe 제품)

&quot;regulation&quot;:

* **gdpr**, **ccpa**, **pdpa**, **lgpd_bra**, 또는 **nzpa_nzl** (요청에 적용되는 개인정보 보호 규정)

## 예 1: GDPR 삭제 요청 {#gdpr-delete-request}

JSON 요청

```text
{
  "companyContexts": [
    {
      "namespace": "imsOrgID",
      "value": "1231659F56A68A8B7F000101@AdobeOrg"
    }
  ],
  "users": [
    {
      "action": [
        "delete"
      ],
      "userIDs": [
        {
          "namespace": "email",
          "type": "standard",
          "value": "john.doe@adobe.com"
        }
      ]
    }
  ],
  "include": [
    "marketoMeasure"
  ],
  "regulation": "gdpr",
}
```

JSON 응답

```text
{
  "requestId": "16331241037112570RX-245",
  "totalRecords": 1,
  "jobs": [
    {
      "jobId": "997b01e3-9568-402c-904b-b4e60a437875",
      "customer": {
        "user": {
          "action": [
            "delete"
          ],
          "userIDs": [
            {
              "namespace": "email",
              "value": "john.doe@adobe.com",
              "type": "standard",
              "namespaceId": 6,
              "isDeletedClientSide": false
            }
          ]
        }
      }
    }
  ]
}
```

## 예제 2: CCPA 액세스 요청 {#ccpa-access-request}

JSON 요청

```text
{
  "companyContexts": [
    {
      "namespace": "imsOrgID",
      "value": "1231659F56A68A8B7F000101@AdobeOrg"
    }
  ],
  "users": [
    {
      "action": [
        "access"
      ],
      "userIDs": [
        {
          "namespace": "email",
          "type": "standard",
          "value": "john.doe@adobe.com"
        }
      ]
    }
  ],
  "include": [
    "marketoMeasure"
  ],
  "regulation": "ccpa",
}
```

JSON 응답

```text
{
  "requestId": "16329573462631890RX-207",
  "totalRecords": 1,
  "jobs": [
    {
      "jobId": "3115e42d-011b-47ab-a2b0-ed4356af4d3e",
      "customer": {
        "user": {
          "action": [
            "access"
          ],
          "userIDs": [
            {
              "namespace": "email",
              "value": "john.doe@adobe.com",
              "type": "standard",
              "namespaceId": 6,
              "isDeletedClientSide": false
            }
          ]
        }
      }
    }
  ]
}
```
