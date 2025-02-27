---
description: '[!DNL Marketo Measure] Ultimate 데이터 무결성 요구 사항 - [!DNL Marketo Measure]'
title: '[!DNL Marketo Measure] Ultimate 데이터 무결성 요구 사항'
feature: Integration, Tracking, Attribution
exl-id: 8ad001d0-e9fe-46f5-b808-d6203a55a229
source-git-commit: 4f504bd940e2d28603af65b75151d8143cdcbea8
workflow-type: tm+mt
source-wordcount: '1611'
ht-degree: 16%

---

# [!DNL Marketo Measure] Ultimate 데이터 무결성 요구 사항 {#marketo-measure-ultimate-data-integrity-requirement}

[!DNL Marketo Measure]은(는) 들어오는 AEP 데이터 세트의 유효성을 검사하여 데이터가 속성에 대해 충분하고 일관성이 있는지 확인합니다. 데이터 무결성 요구 사항을 충족하지 못하면 [!DNL Marketo Measure] 시스템에서 데이터 세트가 거부됩니다. 이 문서에서는 데이터 무결성 요구 사항에 대해 자세히 설명하고 데이터 검사를 위한 쿼리 예를 제공하며 null 값이 있는 필수 필드에 대한 솔루션을 권장합니다.

## 엔티티 개체 {#entity-object}

<table style="table-layout:auto">
  <tr>
    <th>XDM 클래스</th>
    <th>XDM 필드 그룹</th>
    <th>XDM 경로</th>
    <th>XDM 유형</th>
    <th>데이터 Source 필드</th>
    <th>필수?</th>
    <th>참고</th>
  </tr>
  <tbody>
    <tr>
      <td colspan="7"><strong>계정</strong>(Salesforce 계정, 회사 계정 및/또는 Marketo의 명명된 계정)</td>
    </tr>
    <tr>
      <td rowspan="6">XDM 비즈니스 계정</td>
      <td></td>
      <td>accountKey.sourceKey</td>
      <td>문자열</td>
      <td></td>
      <td>예</td>
      <td>예 - 123@999-abc-888.Marketo</td>
    </tr>
    <tr>
      <td></td>
      <td>accountKey.sourceID</td>
      <td>문자열</td>
      <td>ID</td>
      <td>예</td>
      <td>예: - 123</td>
    </tr>
    <tr>
      <td></td>
      <td>accountKey.sourceInstanceID</td>
      <td>문자열</td>
      <td></td>
      <td>예</td>
      <td>예: - 999-abc-888</td>
    </tr>
    <tr>
      <td></td>
      <td>accountKey.sourceType</td>
      <td>문자열</td>
      <td></td>
      <td>예</td>
      <td>예: - Marketo</td>
    </tr>
    <tr>
      <td></td>
      <td>extSourceSystemAudit.createdDate</td>
      <td>date-time</td>
      <td>CreatedDate</td>
      <td>예</td>
      <td></td>
    </tr>
    <tr>
      <td></td>
      <td>extSourceSystemAudit.lastUpdatedDate</td>
      <td>date-time</td>
      <td>ModifiedDate</td>
      <td>예</td>
      <td></td>
    </tr>
    <tr>
      <td></td>
      <td>XDM 비즈니스 계정 세부 정보</td>
      <td>accountName</td>
      <td>문자열</td>
      <td>이름</td>
      <td>예</td>
      <td></td>
    </tr>
    <tr>
      <td colspan="7"><strong>캠페인</strong>(Salesforce용 캠페인, Marketo용 프로그램)</td>
    </tr>
    <tr>
      <td rowspan="8">XDM 비즈니스 캠페인</td>
      <td></td>
      <td>campaignKey.sourceKey</td>
      <td>문자열</td>
      <td></td>
      <td>예</td>
      <td>예: - 55555@999-abc-888.Marketo</td>
    </tr>
    <tr>
      <td></td>
      <td>campaignKey.sourceID</td>
      <td>문자열</td>
      <td>ID</td>
      <td>예</td>
      <td>예: - 55555</td>
    </tr>
    <tr>
      <td></td>
      <td>campaignKey.sourceInstanceID</td>
      <td>문자열</td>
      <td></td>
      <td>예</td>
      <td>예: - 999-abc-888</td>
    </tr>
    <tr>
      <td></td>
      <td>campaignKey.sourceType</td>
      <td>문자열</td>
      <td></td>
      <td>예</td>
      <td>예: - Marketo</td>
    </tr>
    <tr>
      <td></td>
      <td>extSourceSystemAudit.createdDate</td>
      <td>date-time</td>
      <td>CreatedDate</td>
      <td>예</td>
      <td></td>
    </tr>
    <tr>
      <td></td>
      <td>extSourceSystemAudit.lastUpdatedDate</td>
      <td>date-time</td>
      <td>ModifiedDate</td>
      <td>예</td>
      <td></td>
    </tr>
    <tr>
      <td></td>
      <td>campaignName</td>
      <td>문자열</td>
      <td>이름</td>
      <td>예</td>
      <td></td>
    </tr>
    <tr>
      <td></td>
      <td>캠페인 유형</td>
      <td>문자열</td>
      <td>캠페인 유형</td>
      <td>아니요</td>
      <td>채널 매핑용</td>
    </tr>
    <tr>
      <td></td>
      <td rowspan="5">XDM 비즈니스 캠페인 세부 정보</td>
      <td>channelName</td>
      <td>문자열</td>
      <td>채널 이름</td>
      <td>아니요</td>
      <td>채널 매핑용</td>
    </tr>
    <tr>
      <td></td>
      <td>campaignStartDate</td>
      <td>date-time</td>
      <td>시작 날짜</td>
      <td>아니요</td>
      <td>캠페인 비용</td>
    </tr>
    <tr>
      <td></td>
      <td>캠페인 종료일</td>
      <td>date-time</td>
      <td>종료일</td>
      <td>아니요</td>
      <td>캠페인 비용</td>
    </tr>
    <tr>
      <td></td>
      <td>actualCost.amount</td>
      <td>번호</td>
      <td>비용</td>
      <td>아니요</td>
      <td>캠페인 비용</td>
    </tr>
    <tr>
      <td></td>
      <td>actualCost.currencyCode</td>
      <td>
        <p>문자열</p>
        <p>^[A-Z]{3}$</p>
      </td>
      <td>CurrencyIsoCode</td>
      <td>아니요</td>
      <td>캠페인 비용</td>
    </tr>
    <tr>
      <td colspan="7"><strong>캠페인 멤버</strong>(Salesforce의 캠페인 멤버, Marketo의 프로그램 멤버십)</td>
    </tr>
    <tr>
      <td rowspan="14">XDM 비즈니스 캠페인 멤버</td>
      <td></td>
      <td>campaignMemberKey.sourceKey</td>
      <td>문자열</td>
      <td></td>
      <td>예</td>
      <td>예: - 987654321@999-abc-888.Marketo</td>
    </tr>
    <tr>
      <td></td>
      <td>campaignMemberKey.sourceID</td>
      <td>문자열</td>
      <td>ID</td>
      <td>예</td>
      <td>예: - 987654321</td>
    </tr>
    <tr>
      <td></td>
      <td>campaignMemberKey.sourceInstanceID</td>
      <td>문자열</td>
      <td></td>
      <td>예</td>
      <td>예: - 999-abc-888</td>
    </tr>
    <tr>
      <td></td>
      <td>campaignMemberKey.sourceType</td>
      <td>문자열</td>
      <td></td>
      <td>예</td>
      <td>예: - Marketo</td>
    </tr>
    <tr>
      <td></td>
      <td>extSourceSystemAudit.createdDate</td>
      <td>date-time</td>
      <td>CreatedDate</td>
      <td>예</td>
      <td></td>
    </tr>
    <tr>
      <td></td>
      <td>extSourceSystemAudit.lastUpdatedDate</td>
      <td>date-time</td>
      <td>ModifiedDate</td>
      <td>예</td>
      <td></td>
    </tr>
    <tr>
      <td></td>
      <td>personKey.sourceKey</td>
      <td>문자열</td>
      <td></td>
      <td>예</td>
      <td>예: - 333@999-abc-888.Marketo</td>
    </tr>
    <tr>
      <td></td>
      <td>personKey.sourceID</td>
      <td>문자열</td>
      <td>잠재 고객 ID 또는 연락처 ID</td>
      <td>예</td>
      <td>
        <p>예: - 333, 데이터 소스 테이블에 따라 리드 ID 또는 연락처 ID입니다.</p>
        <p>리드 또는 연락처에 대한 외래 키</p>
      </td>
    </tr>
    <tr>
      <td></td>
      <td>personKey.sourceInstanceID</td>
      <td>문자열</td>
      <td></td>
      <td>예</td>
      <td>예: - 999-abc-888</td>
    </tr>
    <tr>
      <td></td>
      <td>personKey.sourceType</td>
      <td>문자열</td>
      <td></td>
      <td>예</td>
      <td>예: - Marketo</td>
    </tr>
    <tr>
      <td></td>
      <td>campaignKey.sourceKey</td>
      <td>문자열</td>
      <td></td>
      <td>예</td>
      <td>예: - 55555@999-abc-888.Marketo</td>
    </tr>
    <tr>
      <td></td>
      <td>campaignKey.sourceID</td>
      <td>문자열</td>
      <td>캠페인 ID</td>
      <td>예</td>
      <td>
        <p>예: - 55555.</p>
        <p>Campaign의 외래 키</p>
      </td>
    </tr>
    <tr>
      <td></td>
      <td>campaignKey.sourceInstanceID</td>
      <td>문자열</td>
      <td></td>
      <td>예</td>
      <td>예: - 999-abc-888</td>
    </tr>
    <tr>
      <td></td>
      <td>campaignKey.sourceType</td>
      <td>문자열</td>
      <td></td>
      <td>예</td>
      <td>예: - Marketo</td>
    </tr>
    <tr>
      <td></td>
      <td rowspan="4">XDM 비즈니스 캠페인 멤버 세부 정보</td>
      <td>b2b.personType</td>
      <td>문자열</td>
      <td>"잠재 고객" 또는 "연락처</td>
      <td>예</td>
      <td>데이터 소스 테이블에 따라 "잠재 고객" 또는 "연락처"로 설정해야 합니다. 대부분의 사용 사례에는 "연락처"로 설정하는 것이 좋습니다</td>
    </tr>
    <tr>
      <td></td>
      <td>memberStatus</td>
      <td>문자열</td>
      <td>상태</td>
      <td>예</td>
      <td></td>
    </tr>
    <tr>
      <td></td>
      <td>hasResponded</td>
      <td>부울</td>
      <td>HasResponded</td>
      <td>예</td>
      <td></td>
    </tr>
    <tr>
      <td></td>
      <td>최초 응답일</td>
      <td>date-time</td>
      <td>최초 응답일</td>
      <td>아니요</td>
      <td></td>
    </tr>
    <tr>
      <td colspan="7"><strong>사용자</strong>(Salesforce, Marketo의 사용자 연락처 또는 잠재 고객)</td>
    </tr>
    <tr>
      <td>XDM 개별 프로필</td>
      <td rowspan="11">XDM 비즈니스 사용자 세부 정보</td>
      <td>b2b.personKey.sourceKey</td>
      <td>문자열</td>
      <td></td>
      <td>예</td>
      <td>예 - 333@999-abc-888.Marketo</td>
    </tr>
    <tr>
      <td></td>
      <td>b2b.personKey.sourceID</td>
      <td>문자열</td>
      <td>ID</td>
      <td>예</td>
      <td>예를 들어 - 333과 같이 데이터 소스 테이블에 따라 리드 ID 또는 연락처 ID입니다</td>
    </tr>
    <tr>
      <td></td>
      <td>b2b.personKey.sourceInstanceID</td>
      <td>문자열</td>
      <td></td>
      <td>예</td>
      <td>예: - 999-abc-888</td>
    </tr>
    <tr>
      <td></td>
      <td>b2b.personKey.sourceType</td>
      <td>문자열</td>
      <td></td>
      <td>예</td>
      <td>예: - Marketo</td>
    </tr>
    <tr>
      <td></td>
      <td>workEmail.address</td>
      <td>
        <p>문자열</p>
        <p>이메일</p>
      </td>
      <td>이메일</td>
      <td>예</td>
      <td></td>
    </tr>
    <tr>
      <td></td>
      <td>b2b.personStatus</td>
      <td>문자열</td>
      <td>상태</td>
      <td><b><i>가망 고객 개인 유형에 대해서만 예</i></b></td>
      <td>b2b.personType이 "리드"인 경우에만 필요합니다.</td>
    </tr>
    <tr>
      <td></td>
      <td>extSourceSystemAudit.createdDate</td>
      <td>date-time</td>
      <td>CreatedDate</td>
      <td>예</td>
      <td></td>
    </tr>
    <tr>
      <td></td>
      <td>extSourceSystemAudit.lastUpdatedDate</td>
      <td>date-time</td>
      <td>ModifiedDate</td>
      <td>예</td>
      <td></td>
    </tr>
    <tr>
      <td></td>
      <td>b2b.isConverted</td>
      <td>부울</td>
      <td>IsConverted</td>
      <td><b><i>가망 고객 개인 유형에 대해서만 예</i></b></td>
      <td>b2b.personType이 "리드"인 경우에만 필요합니다.</td>
    </tr>
    <tr>
      <td></td>
      <td>b2b.personType</td>
      <td>문자열</td>
      <td>"잠재 고객" 또는 "연락처</td>
      <td>예</td>
      <td>데이터 소스 테이블에 따라 "잠재 고객" 또는 "연락처"로 설정해야 합니다. 대부분의 사용 사례에는 "연락처"로 설정하는 것이 좋습니다</td>
    </tr>
    <tr>
      <td></td>
      <td>extendedWorkDetails.jobTitle</td>
      <td>문자열</td>
      <td></td>
      <td>아니요</td>
      <td></td>
    </tr>
    <tr>
      <td></td>
      <td rowspan="4">XDM 비즈니스 사용자 구성 요소</td>
      <td>personComponents.sourceAccountKey.sourceKey</td>
      <td>문자열</td>
      <td></td>
      <td>아니요</td>
      <td>
        <p>예: - 123@999-abc-888.Marketo.</p>
        <p>sourceAccountKey 필드 집합은 계정에 연결된 개인 레코드로 정의된 실제 연락처 레코드에 대해서만 "필수"입니다. 누락되어도 데이터 세트가 거부되지 않지만 기여도 분석 결과는 해제됩니다.</p>
        <p>personComponents가 배열이지만 Marketo Measure은 첫 번째 요소 personComponents[0]만 사용합니다.</p>
      </td>
    </tr>
    <tr>
      <td></td>
      <td>personComponents.sourceAccountKey.sourceID</td>
      <td>문자열</td>
      <td>계정 ID</td>
      <td>아니요</td>
      <td>
        <p>예: - 123.</p>
        <p>계정 외래 키</p>
      </td>
    </tr>
    <tr>
      <td></td>
      <td>personComponents.sourceAccountKey.sourceInstanceID</td>
      <td>문자열</td>
      <td></td>
      <td>아니요</td>
      <td>예: - 999-abc-888</td>
    </tr>
    <tr>
      <td></td>
      <td>personComponents.sourceAccountKey.sourceType</td>
      <td>문자열</td>
      <td></td>
      <td>아니요</td>
      <td>예: - Marketo</td>
    </tr>
    <tr>
      <td colspan="7"><strong>기회</strong>(Salesforce의 기회, Marketo의 기회)</td>
    </tr>
    <tr>
      <td rowspan="13">XDM 비즈니스 영업 기회</td>
      <td></td>
      <td>opportunityKey.sourceKey</td>
      <td>문자열</td>
      <td></td>
      <td>예</td>
      <td>예: - 77777@999-abc-888.Marketo</td>
    </tr>
    <tr>
      <td></td>
      <td>opportunityKey.sourceID</td>
      <td>문자열</td>
      <td>ID</td>
      <td>예</td>
      <td>예: - 77777</td>
    </tr>
    <tr>
      <td></td>
      <td>opportunityKey.sourceInstanceID</td>
      <td>문자열</td>
      <td></td>
      <td>예</td>
      <td>예: - 999-abc-888</td>
    </tr>
    <tr>
      <td></td>
      <td>opportunityKey.sourceType</td>
      <td>문자열</td>
      <td></td>
      <td>예</td>
      <td>예: - Marketo</td>
    </tr>
    <tr>
      <td></td>
      <td>extSourceSystemAudit.createdDate</td>
      <td>date-time</td>
      <td>CreatedDate</td>
      <td>예</td>
      <td></td>
    </tr>
    <tr>
      <td></td>
      <td>extSourceSystemAudit.lastUpdatedDate</td>
      <td>date-time</td>
      <td>ModifiedDate</td>
      <td>예</td>
      <td></td>
    </tr>
    <tr>
      <td></td>
      <td>accountKey.sourceKey</td>
      <td>문자열</td>
      <td></td>
      <td>예</td>
      <td>예: - 123@999-abc-888.Marketo</td>
    </tr>
    <tr>
      <td></td>
      <td>accountKey.sourceID</td>
      <td>문자열</td>
      <td>계정 ID</td>
      <td>예</td>
      <td>
        <p>예: - 123.</p>
        <p>계정 외래 키</p>
      </td>
    </tr>
    <tr>
      <td></td>
      <td>accountKey.sourceInstanceID</td>
      <td>문자열</td>
      <td></td>
      <td>예</td>
      <td>예: - 999-abc-888</td>
    </tr>
    <tr>
      <td></td>
      <td>accountKey.sourceType</td>
      <td>문자열</td>
      <td></td>
      <td>예</td>
      <td>예: - Marketo</td>
    </tr>
    <tr>
      <td></td>
      <td>opportunityName</td>
      <td>문자열</td>
      <td>이름</td>
      <td>예</td>
      <td></td>
    </tr>
    <tr>
      <td></td>
      <td>opportunityStage</td>
      <td>문자열</td>
      <td>단계</td>
      <td>예</td>
      <td></td>
    </tr>
    <tr>
      <td></td>
      <td>opportunityType</td>
      <td>문자열</td>
      <td></td>
      <td>아니요</td>
      <td></td>
    </tr>
    <tr>
      <td></td>
      <td rowspan="5">XDM 비즈니스 영업 기회 세부 정보</td>
      <td>isWon</td>
      <td>부울</td>
      <td>IsWon</td>
      <td>예</td>
      <td></td>
    </tr>
    <tr>
      <td></td>
      <td>isClosed</td>
      <td>부울</td>
      <td>닫힘</td>
      <td>예</td>
      <td></td>
    </tr>
    <tr>
      <td></td>
      <td>expectedCloseDate</td>
      <td>날짜</td>
      <td>CloseDate</td>
      <td>예</td>
      <td></td>
    </tr>
    <tr>
      <td></td>
      <td>opportunityAmount.amount</td>
      <td>번호</td>
      <td>금액</td>
      <td>예</td>
      <td></td>
    </tr>
    <tr>
      <td></td>
      <td>opportunityAmount.currencyCode</td>
      <td>
        <p>문자열</p>
        <p>^[A-Z]{3}$</p>
      </td>
      <td>CurrencyIsoCode</td>
      <td>예</td>
      <td></td>
    </tr>
    <tr>
      <td colspan="7"><strong>영업 기회 연락처 역할(영업 기회 연락처 역할을 속성의 구매 그룹으로 사용하려는 경우에만 필요함)</strong></td>
    </tr>
    <tr>
      <td rowspan="16">XDM 비즈니스 영업 기회 사용자 관계</td>
      <td></td>
      <td>personKey.sourceKey</td>
      <td>문자열</td>
      <td></td>
      <td>예</td>
      <td>예: - 333@999-abc-888.Marketo</td>
    </tr>
    <tr>
      <td></td>
      <td>personKey.sourceID</td>
      <td>문자열</td>
      <td>연락처 ID</td>
      <td>예</td>
      <td>
        <p>예: - 333.</p>
        <p>연락처 외래 키</p>
      </td>
    </tr>
    <tr>
      <td></td>
      <td>personKey.sourceInstanceID</td>
      <td>문자열</td>
      <td></td>
      <td>예</td>
      <td>예: - 999-abc-888</td>
    </tr>
    <tr>
      <td></td>
      <td>personKey.sourceType</td>
      <td>문자열</td>
      <td></td>
      <td>예</td>
      <td>예: - Marketo</td>
    </tr>
    <tr>
      <td></td>
      <td>isPrimary</td>
      <td>부울</td>
      <td>Isprimary</td>
      <td>예</td>
      <td></td>
    </tr>
    <tr>
      <td></td>
      <td>opportunityKey.sourceKey</td>
      <td>문자열</td>
      <td></td>
      <td>예</td>
      <td>예: - 77777@999-abc-888.Marketo</td>
    </tr>
    <tr>
      <td></td>
      <td>opportunityKey.sourceID</td>
      <td>문자열</td>
      <td>기회 ID</td>
      <td>예</td>
      <td>
        <p>예: - 77777.</p>
        <p>영업 기회에 대한 외래 키</p>
      </td>
    </tr>
    <tr>
      <td></td>
      <td>opportunityKey.sourceInstanceID</td>
      <td>문자열</td>
      <td></td>
      <td>예</td>
      <td>예: - 999-abc-888</td>
    </tr>
    <tr>
      <td></td>
      <td>opportunityKey.sourceType</td>
      <td>문자열</td>
      <td></td>
      <td>예</td>
      <td>예: - Marketo</td>
    </tr>
    <tr>
      <td></td>
      <td>opportunityPersonKey.sourceKey</td>
      <td>문자열</td>
      <td></td>
      <td>예</td>
      <td>예: - 222222@999-abc-888.Marketo</td>
    </tr>
    <tr>
      <td></td>
      <td>opportunityPersonKey.sourceID</td>
      <td>문자열</td>
      <td>ID</td>
      <td>예</td>
      <td>예: - 222222</td>
    </tr>
    <tr>
      <td></td>
      <td>opportunityPersonKey.sourceInstanceID</td>
      <td>문자열</td>
      <td></td>
      <td>예</td>
      <td>예: - 999-abc-888</td>
    </tr>
    <tr>
      <td></td>
      <td>opportunityPersonKey.sourceType</td>
      <td>문자열</td>
      <td></td>
      <td>예</td>
      <td>예: - Marketo</td>
    </tr>
    <tr>
      <td></td>
      <td>person역할</td>
      <td>문자열</td>
      <td>역할</td>
      <td>아니요</td>
      <td></td>
    </tr>
    <tr>
      <td></td>
      <td>extSourceSystemAudit.createdDate</td>
      <td>date-time</td>
      <td>CreatedDate</td>
      <td>예</td>
      <td></td>
    </tr>
    <tr>
      <td></td>
      <td>extSourceSystemAudit.lastUpdatedDate</td>
      <td>date-time</td>
      <td>ModifiedDate</td>
      <td>예</td>
      <td></td>
    </tr>
    <tr>
      <td colspan="7"><strong>전환율 (여러 통화를 사용하는 경우에만 필요함. Marketo Measure에 대해 하나의 전환율 데이터 세트만 활성화할 수 있음)</strong></td>
    </tr>
    <tr>
      <td rowspan="7">전환</td>
      <td></td>
      <td>extSourceSystemAudit.externalKey.sourceKey</td>
      <td>문자열</td>
      <td></td>
      <td>예</td>
      <td>예: - 8888@0x012345.Salesforce</td>
    </tr>
    <tr>
      <td></td>
      <td>extSourceSystemAudit.externalKey.sourceId</td>
      <td>문자열</td>
      <td>ID</td>
      <td>예</td>
      <td>예: - 8888</td>
    </tr>
    <tr>
      <td></td>
      <td>extSourceSystemAudit.externalKey.sourceInstanceId</td>
      <td>문자열</td>
      <td></td>
      <td>예</td>
      <td>예: - 0x012345</td>
    </tr>
    <tr>
      <td></td>
      <td>extSourceSystemAudit.externalKey.sourceType</td>
      <td>문자열</td>
      <td></td>
      <td>예</td>
      <td>예: - Salesforce</td>
    </tr>
    <tr>
      <td></td>
      <td>extSourceSystemAudit.createdDate</td>
      <td>date-time</td>
      <td>CreatedDate</td>
      <td>예</td>
      <td></td>
    </tr>
    <tr>
      <td></td>
      <td>extSourceSystemAudit.lastUpdatedDate</td>
      <td>date-time</td>
      <td>ModifiedDate</td>
      <td>예</td>
      <td></td>
    </tr>
    <tr>
      <td></td>
      <td>isDeleted</td>
      <td>부울</td>
      <td></td>
      <td>예</td>
      <td></td>
    </tr>
    <tr>
      <td></td>
      <td rowspan="5">통화 전환율 세부 정보</td>
      <td>전환율</td>
      <td>번호</td>
      <td>전환율</td>
      <td>예</td>
      <td></td>
    </tr>
    <tr>
      <td></td>
      <td>endDate</td>
      <td>날짜</td>
      <td>다음 시작일</td>
      <td>예</td>
      <td></td>
    </tr>
    <tr>
      <td></td>
      <td>startDate</td>
      <td>날짜</td>
      <td>시작 날짜</td>
      <td>예</td>
      <td></td>
    </tr>
    <tr>
      <td></td>
      <td>sourceISOCode</td>
      <td>문자열</td>
      <td>ISOCode</td>
      <td>예</td>
      <td>예: EUR</td>
    </tr>
    <tr>
      <td></td>
      <td>targetISOCode</td>
      <td>문자열</td>
      <td></td>
      <td>예</td>
      <td>Marketo Measure의 기본 통화 코드 세트(예: USD)</td>
    </tr>
  </tbody>
</table>

## 통화 전환 데이터 요구 사항 {#currency-conversion-data-requirements}

**기본 통화**: Marketo Measure에서 모든 매출과 비용은 보고 시 기본 통화로 전환됩니다. 전환율이 1인 대상 통화 자체에 대한 날짜 범위가 동일한 레코드가 하나 있어야 합니다(예: USD에서 USD로의 전환).

**전환율**: 각(원본 통화, 대상 통화) 쌍은 서로 다른 날짜 기간에 대해 여러 전환율을 가질 수 있습니다. 이 비율은 Salesforce DatedConversionRate 개체에 따라 0001-01-01부터 9999-12-31까지의 전체 시간 범위를 포함해야 합니다.

**날짜 범위**:
* (소스 통화, 대상 통화) 환율 세트 (예: 2023-01-01 ~ 2023-02-01 및 2023-01-01 ~ 2024-01-01) 내에는 겹치는 날짜 범위가 없습니다.
* 날짜 범위 사이에 간격이 없습니다. 시작 날짜는 포함되며 종료 날짜는 제외됩니다.

<p>

## ExperienceEvent {#experienceevent}

<table style="table-layout:auto">
  <tr>
    <th>XDM 클래스</th>
    <th>XDM 필드 그룹</th>
    <th>XDM 경로</th>
    <th>XDM 유형</th>
    <th>데이터 Source 필드</th>
    <th>필수?</th>
    <th>참고</th>
  </tr>
  <tbody>
    <tr>
      <td colspan="7"><strong>활동</strong></td>
    </tr>
    <tr>
      <td rowspan="3">XDM ExperienceEvent</td>
      <td></td>
      <td>_ID</td>
      <td>문자열</td>
      <td>ID</td>
      <td>예</td>
      <td>예</td>
    </tr>
    <tr>
      <td></td>
      <td>eventType</td>
      <td>문자열</td>
      <td>활동 유형</td>
      <td>예</td>
      <td>예</td>
    </tr>
    <tr>
      <td></td>
      <td>타임스탬프</td>
      <td>date-time</td>
      <td>활동 날짜</td>
      <td>예</td>
      <td>예</td>
    </tr>
    <tr>
      <td></td>
      <td>개인 식별자</td>
      <td>personKey.sourceKey</td>
      <td>문자열</td>
      <td></td>
      <td>예</td>
      <td>예: - 333@999-abc-888.Marketo</td>
    </tr>
    <tr>
      <td></td>
      <td></td>
      <td>personKey.sourceID</td>
      <td>문자열</td>
      <td>잠재 고객 ID 또는 연락처 ID</td>
      <td>예</td>
      <td>
        <p>예: - 333, 데이터 소스 테이블에 따라 리드 ID 또는 연락처 ID입니다.</p>
        <p>리드 또는 연락처에 대한 외래 키</p>
      </td>
    </tr>
    <tr>
      <td></td>
      <td></td>
      <td>personKey.sourceInstanceID</td>
      <td>문자열</td>
      <td></td>
      <td>예</td>
      <td>예: - 999-abc-888</td>
    </tr>
    <tr>
      <td></td>
      <td></td>
      <td>personKey.sourceType</td>
      <td>문자열</td>
      <td></td>
      <td>예</td>
      <td>예: - Marketo</td>
    </tr>
    <tr>
      <td></td>
      <td>Campaign에 추가</td>
      <td>leadOperation.addToCampaign.campaignKey.sourceKey</td>
      <td>문자열</td>
      <td></td>
      <td>leadOperation.addToCampaign 유형에 대해서만 예</td>
      <td>예: - 55555@999-abc-888.Marketo</td>
    </tr>
    <tr>
      <td></td>
      <td></td>
      <td>leadOperation.addToCampaign.campaignKey.sourceId</td>
      <td>문자열</td>
      <td>캠페인 ID</td>
      <td>leadOperation.addToCampaign 유형에 대해서만 예</td>
      <td>
        <p>예: - 55555.</p>
        <p>Campaign의 외래 키</p>
      </td>
    </tr>
    <tr>
      <td></td>
      <td></td>
      <td>leadOperation.addToCampaign.campaignKey.sourceInstanceId</td>
      <td>문자열</td>
      <td></td>
      <td>leadOperation.addToCampaign 유형에 대해서만 예</td>
      <td>예: - 999-abc-888</td>
    </tr>
    <tr>
      <td></td>
      <td></td>
      <td>leadOperation.addToCampaign.campaignKey.sourceType</td>
      <td>문자열</td>
      <td></td>
      <td>leadOperation.addToCampaign 유형에 대해서만 예</td>
      <td>예: - Marketo</td>
    </tr>
    <tr>
      <td></td>
      <td>캠페인 진행률 상태 변경됨</td>
      <td>leadOperation.campaignProgression.campaignKey.sourceKey</td>
      <td>문자열</td>
      <td></td>
      <td>leadOperation.campaignProgression 유형에 대해서만 예</td>
      <td>예: - 55555@999-abc-888.Marketo</td>
    </tr>
    <tr>
      <td></td>
      <td></td>
      <td>leadOperation.campaignProgression.campaignKey.sourceId</td>
      <td>문자열</td>
      <td>캠페인 ID</td>
      <td>leadOperation.campaignProgression 유형에 대해서만 예</td>
      <td>
        <p>예: - 55555.</p>
        <p>Campaign의 외래 키</p>
      </td>
    </tr>
    <tr>
      <td></td>
      <td></td>
      <td>leadOperation.campaignProgression.campaignKey.sourceInstanceId</td>
      <td>문자열</td>
      <td></td>
      <td>leadOperation.campaignProgression 유형에 대해서만 예</td>
      <td>예: - 999-abc-888</td>
    </tr>
    <tr>
      <td></td>
      <td></td>
      <td>leadOperation.campaignProgression.campaignKey.sourceType</td>
      <td>문자열</td>
      <td></td>
      <td>leadOperation.campaignProgression 유형에 대해서만 예</td>
      <td>예: - Marketo</td>
    </tr>
  </tbody>
</table>

## ExperienceEvent 유형 지원됨 {#experienceevent-type-supported}

<table style="table-layout:auto">
  <tr>
    <th>이벤트 유형</th>
    <th>XDM 이벤트 유형</th>
    <th>설명</th>
  </tr>
  <tbody>
    <tr>
      <td>새 잠재 고객</td>
      <td>leadOperation.newLead</td>
      <td>새 마케팅 잠재 고객 생성 및 세부 정보를 기록하는 데 사용</td>
    </tr>
    <tr>
      <td>잠재 고객 전환</td>
      <td>leadOperation.convertLead</td>
      <td>마케팅 잠재 고객이 판매 사용자에게 할당된 판매 자격을 갖춘 연락처로 전환되는 경우 사용합니다.</td>
    </tr>
    <tr>
      <td>즐거운 순간</td>
      <td>leadOperation.interestingMoment</td>
      <td>잠재 고객의 가치 높은 활동을 추적하는 데 사용</td>
    </tr>
    <tr>
      <td>양식 작성</td>
      <td>web.formFilledOut</td>
      <td>사용자가 웹 페이지에서 양식을 작성하는 경우 이를 사용하여 세부 정보를 캡처합니다</td>
    </tr>
    <tr>
      <td>이메일 구독 취소</td>
      <td>directMarketing.emailUnsubscribed</td>
      <td>사용자가 이메일에서 가입 해지하는 경우 이를 사용하여 세부 정보를 캡처합니다</td>
    </tr>
    <tr>
      <td>이메일 열기</td>
      <td>directMarketing.emailOpened</td>
      <td>사용자가 마케팅 이메일을 여는 경우 이를 사용하여 세부 정보 캡처</td>
    </tr>
    <tr>
      <td>이메일 클릭</td>
      <td>directMarketing.emailClicked</td>
      <td>사용자가 마케팅 이메일의 링크를 클릭하는 경우 이를 사용하여 세부 정보를 캡처합니다</td>
    </tr>
    <tr>
      <td>진행 상태 변경</td>
      <td>leadOperation.statusInCampaignProgressionChanged</td>
      <td>잠재 고객의 캠페인 상태가 변경되는 경우 이를 사용하여 세부 정보를 캡처합니다.</td>
    </tr>
    <tr>
      <td>참여 프로그램에 추가(양육에 추가)</td>
      <td>leadOperation.addToCampaign</td>
      <td>특정 캠페인에 사용자를 추가하는 데 사용합니다.</td>
    </tr>
  </tbody>
</table>

위 표에서 지원되지 않는 이벤트 유형에 대해 &quot;즐거운 순간&quot; 이벤트 유형을 사용하십시오. 하위 유형 &quot;즐거운 순간&quot;을 나타내는 사용자 정의 필드를 추가합니다.

## 데이터 검사를 위한 쿼리 예 {#query-examples-for-data-inspection}

다음은 AEP 데이터 레이크에서 수집된 데이터 세트를 검사하기 위한 쿼리 예제 목록입니다. 데이터 세트에 대해 사용하려면 아래 쿼리 예제의 테이블 이름을 실제 데이터 세트 테이블 이름으로 바꾸십시오.

우리는 모든 수가 0이 될 것으로 예상한다.

personType 필드의 경우 &quot;리드&quot; 또는 &quot;연락처&quot; 값만 있고 null 값은 없습니다.

모든 &quot;연락처&quot; 개인 레코드에 대해 계정 외래 키가 있을 것으로 예상됩니다.

&quot;잠재 고객&quot; 개인 레코드의 경우 계정 외래 키가 없으며 필수가 아닙니다. &quot;잠재 고객&quot; 개인 레코드를 &quot;연락처&quot; 개인 레코드(권장)로 수집하도록 선택하는 경우, 해당 개인 레코드에 계정 외래 키가 필요하지 않습니다.

### XDM 비즈니스 계정 {#xdm-business-account}

```
select 'account source id', count(*) from salesforce_account where accountKey.sourceId is null
union all
select 'account source type', count(*) from salesforce_account where accountKey.sourceType is null
union all
select 'account source instance id', count(*) from salesforce_account where accountKey.sourceInstanceId is null
union all
select 'account source key', count(*) from salesforce_account where accountKey.sourceKey is null
union all
select 'account name', count(*) from salesforce_account where accountName is null
union all
select 'created date', count(*) from salesforce_account where extSourceSystemAudit.createdDate is null
union all
select 'last updated date', count(*) from salesforce_account where extSourceSystemAudit.lastUpdatedDate is null;
```

### XDM 비즈니스 캠페인 {#xdm-business-campaign}

```
select 'campaign source id', count(*) from salesforce_campaign where campaignKey.sourceId is null
union all
select 'campaign source type', count(*) from salesforce_campaign where campaignKey.sourceType is null
union all
select 'campaign source instance id', count(*) from salesforce_campaign where campaignKey.sourceInstanceId is null
union all
select 'campaign source key', count(*) from salesforce_campaign where campaignKey.sourceKey is null
union all
select 'campaign name', count(*) from salesforce_campaign where campaignName is null
union all
select 'created date', count(*) from salesforce_campaign where extSourceSystemAudit.createdDate is null
union all
select 'last updated date', count(*) from salesforce_campaign where extSourceSystemAudit.lastUpdatedDate is null;
```

### XDM 비즈니스 캠페인 멤버 {#xdm-business-campaign-member}

```
select 'campaign member source id', count(*) from salesforce_campaign_member where campaignMemberKey.sourceId is null
union all
select 'campaign member source type', count(*) from salesforce_campaign_member where campaignMemberKey.sourceType is null
union all
select 'campaign member source instance id', count(*) from salesforce_campaign_member where campaignMemberKey.sourceInstanceId is null
union all
select 'campaign member source key', count(*) from salesforce_campaign_member where campaignMemberKey.sourceKey is null
union all
select 'campaign source id', count(*) from salesforce_campaign_member where campaignKey.sourceId is null
union all
select 'campaign source type', count(*) from salesforce_campaign_member where campaignKey.sourceType is null
union all
select 'campaign source instance id', count(*) from salesforce_campaign_member where campaignKey.sourceInstanceId is null
union all
select 'campaign source key', count(*) from salesforce_campaign_member where campaignKey.sourceKey is null
union all
select 'person source id', count(*) from salesforce_campaign_member where personKey.sourceId is null
union all
select 'person source type', count(*) from salesforce_campaign_member where personKey.sourceType is null
union all
select 'person source instance id', count(*) from salesforce_campaign_member where personKey.sourceInstanceId is null
union all
select 'person source key', count(*) from salesforce_campaign_member where personKey.sourceKey is null
union all
select distinct 'person type', b2b.personType from salesforce_campaign_member
union all
select 'member status', count(*) from salesforce_campaign_member where memberStatus is null
union all
select 'has responded', count(*) from salesforce_campaign_member where hasResponded is null
union all
select 'created date', count(*) from salesforce_campaign_member where extSourceSystemAudit.createdDate is null
union all
select 'last updated date', count(*) from salesforce_campaign_member where extSourceSystemAudit.lastUpdatedDate is null;
```

### XDM 비즈니스 사용자 {#xdm-business-person}

```
select 'person source id', count(*) from marketo_person where b2b.personKey.sourceId is null
union all
select 'person source type', count(*) from marketo_person where b2b.personKey.sourceType is null
union all
select 'person source instance id', count(*) from marketo_person where b2b.personKey.sourceInstanceId is null
union all
select 'person source key', count(*) from marketo_person where b2b.personKey.sourceKey is null
union all
select 'email', count(*) from marketo_person where workEmail.address is null
union all
select 'Lead - person status', count(*) from marketo_person where b2b.personType = 'Lead' and b2b.personStatus is null
union all
select 'Lead - is converted', count(*) from marketo_person where b2b.personType = 'Lead' and b2b.isConverted is null
union all
select distinct 'person type', b2b.personType from marketo_person
union all
select 'created date', count(*) from marketo_person where extSourceSystemAudit.createdDate is null
union all
select 'last updated date', count(*) from marketo_person where extSourceSystemAudit.lastUpdatedDate is null;
```

```
select 'person source id', count(*) from salesforce_contact where b2b.personKey.sourceId is null
union all
select 'person source type', count(*) from salesforce_contact where b2b.personKey.sourceType is null
union all
select 'person source instance id', count(*) from salesforce_contact where b2b.personKey.sourceInstanceId is null
union all
select 'person source key', count(*) from salesforce_contact where b2b.personKey.sourceKey is null
union all
select 'email', count(*) from salesforce_contact where workEmail.address is null
union all
select 'Lead - person status', count(*) from salesforce_contact where b2b.personType = 'Lead' and b2b.personStatus is null
union all
select 'Lead - is converted', count(*) from salesforce_contact where b2b.personType = 'Lead' and b2b.isConverted is null
union all
select distinct 'person type', b2b.personType from salesforce_contact
union all
select 'account source id', count(*) from salesforce_contact where b2b.personType = 'Contact' and personComponents[0].sourceAccountKey.sourceId is null
union all
select 'account source type', count(*) from salesforce_contact where b2b.personType = 'Contact' and personComponents[0].sourceAccountKey.sourceType is null
union all
select 'account source instance id', count(*) from salesforce_contact where b2b.personType = 'Contact' and personComponents[0].sourceAccountKey.sourceInstanceId is null
union all
select 'account source key', count(*) from salesforce_contact where b2b.personType = 'Contact' and personComponents[0].sourceAccountKey.sourceKey is null
union all
select 'created date', count(*) from salesforce_contact where extSourceSystemAudit.createdDate is null
union all
select 'last updated date', count(*) from salesforce_contact where extSourceSystemAudit.lastUpdatedDate is null;
```

### XDM 비즈니스 영업 기회 {#xdm-business-opportunity}

```
select 'opportunity source id', count(*) from salesforce_opportunity where opportunityKey.sourceId is null
union all
select 'opportunity source type', count(*) from salesforce_opportunity where opportunityKey.sourceType is null
union all
select 'opportunity source instance id', count(*) from salesforce_opportunity where opportunityKey.sourceInstanceId is null
union all
select 'opportunity source key', count(*) from salesforce_opportunity where opportunityKey.sourceKey is null
union all
select 'account source id', count(*) from salesforce_opportunity where accountKey.sourceId is null
union all
select 'account source type', count(*) from salesforce_opportunity where accountKey.sourceType is null
union all
select 'account source instance id', count(*) from salesforce_opportunity where accountKey.sourceInstanceId is null
union all
select 'account source key', count(*) from salesforce_opportunity where accountKey.sourceKey is null
union all
select 'opportunity name', count(*) from salesforce_opportunity where opportunityName is null
union all
select 'opportunity stage', count(*) from salesforce_opportunity where opportunityStage is null
union all
select 'is won', count(*) from salesforce_opportunity where isWon is null
union all
select 'is closed', count(*) from salesforce_opportunity where isClosed is null
union all
select 'expected close date', count(*) from salesforce_opportunity where expectedCloseDate is null
union all
select 'opportunity amount', count(*) from salesforce_opportunity where opportunityAmount.amount is null
union all
select 'currency code', count(*) from salesforce_opportunity where opportunityAmount.currencyCode is null
union all
select 'created date', count(*) from salesforce_opportunity where extSourceSystemAudit.createdDate is null
union all
select 'last updated date', count(*) from salesforce_opportunity where extSourceSystemAudit.lastUpdatedDate is null;
```

### XDM ExperienceEvent {#xdm-experienceevent}

```
select 'id', count(*) from marketo_activity where _id is null
union all
select 'event type', count(*) from marketo_activity where eventType is null
union all
select 'timestamp', count(*) from marketo_activity where timestamp is null
union all
select 'person source id', count(*) from marketo_activity where personKey.sourceId is null
union all
select 'person source type', count(*) from marketo_activity where personKey.sourceType is null
union all
select 'person source instance id', count(*) from marketo_activity where personKey.sourceInstanceId is null
union all
select 'person source key', count(*) from marketo_activity where personKey.sourceKey is null
union all
select 'addToCampaign campaign id', count(*) from marketo_activity where eventType = 'leadOperation.addToCampaign' and leadOperation.addToCampaign.campaignKey.sourceId is null
union all
select 'addToCampaign campaign type', count(*) from marketo_activity where eventType = 'leadOperation.addToCampaign' and leadOperation.addToCampaign.campaignKey.sourceType is null
union all
select 'addToCampaign campaign instance id', count(*) from marketo_activity where eventType = 'leadOperation.addToCampaign' and leadOperation.addToCampaign.campaignKey.sourceInstanceId is null
union all
select 'addToCampaign campaign key', count(*) from marketo_activity where eventType = 'leadOperation.addToCampaign' and leadOperation.addToCampaign.campaignKey.sourceKey is null
union all
select 'statusInCampaignProgressionChanged campaign id', count(*) from marketo_activity where eventType = 'leadOperation.statusInCampaignProgressionChanged' and leadOperation.campaignProgression.campaignKey.sourceId is null
union all
select 'statusInCampaignProgressionChanged campaign type', count(*) from marketo_activity where eventType = 'leadOperation.statusInCampaignProgressionChanged' and leadOperation.campaignProgression.campaignKey.sourceType is null
union all
select 'statusInCampaignProgressionChanged campaign instance id', count(*) from marketo_activity where eventType = 'leadOperation.statusInCampaignProgressionChanged' and leadOperation.campaignProgression.campaignKey.sourceInstanceId is null
union all
select 'statusInCampaignProgressionChanged campaign key', count(*) from marketo_activity where eventType = 'leadOperation.statusInCampaignProgressionChanged' and leadOperation.campaignProgression.campaignKey.sourceKey is null;
```

```
select 'id', count(*) from salesforce_task where _id is null
union all
select 'event type', count(*) from salesforce_task where eventType is null
union all
select 'timestamp', count(*) from salesforce_task where timestamp is null
union all
select 'person source id', count(*) from salesforce_task where personKey.sourceId is null
union all
select 'person source type', count(*) from salesforce_task where personKey.sourceType is null
union all
select 'person source instance id', count(*) from salesforce_task where personKey.sourceInstanceId is null
union all
select 'person source key', count(*) from salesforce_task where personKey.sourceKey is null;
```

### 전환 {#conversion}

```
select 'conversion rate', count(*) from currency_conversion_rate where conversionRate is null
union all
select 'end date', count(*) from currency_conversion_rate where endDate is null
union all
select 'start date', count(*) from currency_conversion_rate where startDate is null
union all
select 'source ISO Code', count(*) from currency_conversion_rate where sourceISOCode is null
union all
select 'target ISO Code', count(*) from currency_conversion_rate where targetISOCode is null
union all
select 'source id', count(*) from currency_conversion_rate where extSourceSystemAudit.externalKey.sourceId is null
union all
select 'source type', count(*) from currency_conversion_rate where extSourceSystemAudit.externalKey.sourceType is null
union all
select 'source instance id', count(*) from currency_conversion_rate where extSourceSystemAudit.externalKey.sourceInstanceId is null
union all
select 'source key', count(*) from currency_conversion_rate where extSourceSystemAudit.externalKey.sourceKey is null
union all
select 'created date', count(*) from currency_conversion_rate where extSourceSystemAudit.createdDate is null
union all
select 'last updated date', count(*) from currency_conversion_rate where extSourceSystemAudit.lastUpdatedDate is null;
```

## NULL 값이 있는 필수 필드에 대한 권장 솔루션 {#recommended-solution-for-required-fields-with-a-null-value}

필드 매핑에서 계산된 필드를 사용하여 필드를 NULL이 아닌 값으로 기본 설정하는 것이 좋습니다. 다음은 두 가지 예입니다.

* 일부 영업 기회 레코드의 opportunityName이 null인 경우 필드 매핑에서 다음 계산된 필드를 만들어 사용합니다.
   * `iif(name != null && trim(name) != "", name, "Unknown")`

* 일부 experienceevent 레코드의 leadOperation.campaignProgression.campaignID가 null이면 필드 매핑에서 다음 계산된 필드를 만들어 사용합니다
   * `iif(leadOperation.campaignProgression.campaignID != null && leadOperation.campaignProgression.campaignID != "" , to_object("sourceType", "Marketo", "sourceInstanceID", "123-abc-321", "sourceID", leadOperation.campaignProgression.campaignID, "sourceKey", concat(leadOperation.campaignProgression.campaignID,"@123-abc-321.Marketo")), iif(eventType == "leadOperation.statusInCampaignProgressionChanged", to_object("sourceType", "Marketo", "sourceInstanceID", "123-abc-321", "sourceID", "Unknown", "sourceKey", "Unknown@123-abc-321.Marketo"), null))`
