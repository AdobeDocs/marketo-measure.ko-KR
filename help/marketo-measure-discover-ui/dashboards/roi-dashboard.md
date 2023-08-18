---
description: ROI 대시보드 - [!DNL Marketo Measure] - 제품
title: ROI 대시보드
feature: Reporting
source-git-commit: 436e30c2a4138d780232d6ba9e64456d6277ac9b
workflow-type: tm+mt
source-wordcount: '663'
ht-degree: 4%

---

# ROI 대시보드 {#roi-dashboard}

ROI 대시보드는 마케터에게 채널, 하위 채널 및 캠페인의 투자 수익에 대한 세분화된 보기를 제공합니다. 비용 및 매출 패턴을 꼼꼼히 분석하는 동시에 리드당 비용, 거래 및 기회와 같은 지표를 파악하여 마케팅 기여도를 포괄적으로 파악합니다.

질문과 대답은 다음과 같습니다.

* 각 채널, 하위 채널 및 캠페인에 대한 ROI 값은 무엇입니까?
* 비용과 수익이 각 채널, 하위 채널 및 캠페인에 어떻게 분배되었습니까?
* Cost-per-Lead, Cost-per-Deal, and cost-per-Opportunity는 무엇입니까?

<table style="table-layout:auto"> 
<tbody>
 <tr> 
   <th>구성 요소</th> 
   <th>설명</th>
   <th>날짜 유형</th>
   <th>드릴스루 필드</th>
   <th>필터</th>
  </tr>
  <tr>
    <td>비용 타일</td>
    <td>발생한 총 비용</td>
    <td>비용 발생 일자</td>
    <td><li>캠페인 ID</li>
<li>캠페인 이름</li>
<li>채널</li>
<li>부채널</li>
<li>날짜</li>
<li>지출</li></td>
    <td rowspan="15"><li>날짜</li>
<li>속성 모델(설정)</li>
<li>채널</li>
<li>부채널</li>
<li>캠페인</li></td>
  </tr>
  <tr>
    <td>속성 수익 타일</td>
    <td>총 속성 수익</td>
    <td>마감일</td>
    <td><li>영업 기회 ID</li>
<li>영업 기회 이름</li>
<li>영업 기회 생성 날짜</li>
<li>영업 기회 종료 날짜</li>
<li>닫힘(Y/N)</li>
<li>성공(Y/N)</li>
<li>속성 모델</li>
<li>속성 수익</li>
<li>실현된 수익</li></td>
  </tr>
  <tr>
    <td>단순 ROI 타일</td>
    <td>기존 ROI: 지정된 기간 동안 수익을 비용으로 나눈 값입니다. 
    <li>비용: 필터링된 날짜 기간에 발생한 비용입니다.</li>
    <li>매출: 해당 일정의 "종료된" 기회로 인한 매출.</li></td>
    <td>마감일</td>
    <td>해당 없음</td>
  </tr>
  <tr>
    <td>실현된 ROI 타일</td>
    <td>실현된 ROI: 지정된 기간 내에 캠페인으로 생성된 터치포인트의 가시적인 결과를 나타냅니다.
    <li>비용: 필터링된 날짜 기간에 발생한 비용입니다.</li>
    <li>매출: 모든 "마감된 원화" 거래에서 실현된 매출, 특히 요약된 기간 내의 터치포인트에 의해 영향을 받는 매출.</li>
    <br/><img src="assets/roi-dashboard-1.png" width="600"></td>
    <td>비용 발생 일자</td>
    <td>해당 없음</td>
  </tr>
  <tr>
    <td>총 새 리드 타일</td>
    <td>터치된 리드와 터치되지 않은 리드를 포함하여 지정된 기간 내에 생성된 총 새 리드 수(전체 개수).</td>
    <td>만든 날짜</td>
    <td rowspan="2">
    <li>잠재 고객 ID</li>
    <li>잠재 고객 이메일</li>
    <li>LC 날짜</li></td>
  </tr>
  <tr>
    <td>새 리드 타일당 비용</td>
    <td>비용으로 나눈 새 잠재 고객의 총 수(전체 개수).</td>
    <td>만든 날짜</td>
  </tr>
  <tr>
    <td>총 새 영업 기회 타일</td>
    <td>터치된 리드와 터치되지 않은 리드를 포함하여 지정된 기간 내에 생성된 총 새 Opportunity 수 (전체 개수) 입니다.</td>
    <td>만든 날짜</td>
    <td rowspan="2">
    <li>영업 기회 ID</li>
    <li>영업 기회 이름</li>
    <li>영업 기회 생성 날짜</li>
    <li>영업 기회 종료 날짜</li>
    <li>닫힘(Y/N)</li>
    <li>성공(Y/N)</li>
    <li>현재 단계</li></td>
  </tr>
  <tr>
    <td>새 영업 기회당 비용 타일</td>
    <td>비용으로 나눈 새 Opportunity 의 총 개수 ( 전체 개수 ) 입니다.</td>
    <td>만든 날짜</td>
  </tr>
  <tr>
    <td>총 거래 타일</td>
    <td>지정된 기간 내에 종료된 총 거래 수(연결된 터치포인트가 없는 거래 포함)</td>
    <td>마감일</td>
    <td><li>영업 기회 ID</li>
<li>영업 기회 이름</li>
<li>영업 기회 생성 날짜</li>
<li>영업 기회 종료 날짜</li>
<li>닫힘(Y/N)</li>
<li>성공(Y/N)</li>
<li>현재 단계</li>
<li>통화</li>
<li>속성 모델</li>
<li>속성 수익</li>
<li>실현된 수익</li></td>
  </tr>
  <tr>
    <td>채널별 비용 및 수익 그래프</td>
    <td>다양한 채널, 하위 채널 및 캠페인과 상대적인 크기에 대한 비교 관점을 제공하도록 설계된 비용 및 매출을 모두 보여 주는 막대 차트입니다.
    <br/><img src="assets/roi-dashboard-2.png" width="600"></td>
    <td>마감일</td>
    <td>비용:
<br/>
<li>캠페인 ID</li>
<li>캠페인 이름</li>
<li>채널</li>
<li>부채널</li>
<li>비용 발생 일자</li>
<li>통화</li>
<li>지출</li>
<p>
매출:
<br/>
<li>영업 기회 ID</li>
<li>영업 기회 이름</li>
<li>영업 기회 생성 날짜</li>
<li>영업 기회 종료 날짜</li>
<li>닫힘(Y/N)</li>
<li>성공(Y/N)</li>
<li>속성 수익</li>
<li>속성 모델</li>
<li>속성 수익</li>
<li>실현된 수익</li></td>
  </tr>
  <tr>
    <td>시간 경과에 따른 실현 및 단순 ROI</td>
    <td>시간 경과에 따른 진행을 추적하면서 실현된 ROI와 간단한 ROI 간의 비교를 표시하는 시계열 라인 차트입니다.
    <br/><img src="assets/roi-dashboard-3.png" width="600"></td>
    <td>단순 ROI: 비용 발생 날짜 및 종료 날짜
    <p>실현된 ROI: 비용 발생 날짜 및 접점 날짜</td>
    <td>해당 없음</td>
  </tr>
  <tr>
    <td>시간 경과에 따른 비용 그래프</td>
    <td>세부 분류를 위해 개별 채널별로 세그먼트화된 분기별/월별 총 비용을 표시하는 스택 막대 차트.
    <br/><img src="assets/roi-dashboard-4.png" width="600"></td>
    <td>비용 발생 일자</td>
    <td rowspan="2"><li>캠페인 ID</li>
<li>캠페인 이름</li>
<li>채널</li>
<li>부채널</li>
<li>비용 발생 일자</li>
<li>통화</li>
<li>지출</li></td>
  </tr>
  <tr>
    <td>채널별 비용 그래프</td>
    <td>채널별로 세그먼트화된 마케팅 지출을 표시하는 막대 차트입니다.
    <br/><img src="assets/roi-dashboard-5.png" width="600"></td>
    <td>비용 발생 일자</td>
  </tr>
  <tr>
    <td>ROI 요약 테이블</td>
    <td>세부 분류를 위해 개별 채널별로 분류된 속성 매출, 비용 및 ROI를 표시하는 표
<p>
<b>열:</b>
<p>
<li>채널/서브채널/캠페인</li>
<li>비용</li>
<li>속성 수익</li>
<li>단순 ROI</li>
<li>실현된 ROI</li>
<li>실현되지 않은 파이프라인</li>
<ul style="padding-left: 30px;"><li>지정된 일정의 캠페인과 연결된 터치포인트의 파이프라인(열린 기회)</li></ul></td>
    <td>단순 ROI: 비용 발생 날짜 및 종료 날짜
    <p>실현된 ROI: 비용 발생 날짜 및 접점 날짜</td>
    <td>해당 없음</td>
  </tr>
  <tr>
    <td>마케팅 지출 테이블</td>
    <td>세부 분류를 위해 개별 채널별로 분류된 비용, 신규 리드, 기회 및 거래를 표시하는 표
<p>
<b>열:</b>
<p>
<li>채널/서브채널/캠페인</li>
<li>비용</li>
<li>새 잠재 고객</li>
<li>새 잠재 고객당 비용</li>
<li>새로운 영업 기회</li>
<li>새 영업 기회당 비용</li>
<li>거래 마감됨</li>
<li>거래당 비용 마감됨</li></td>
    <td><li>비용: 비용 발생 일자</li>
<li>새 잠재 고객: 만든 날짜</li>
<li>새 영업 기회: 만든 날짜</li>
<li>거래 마감: 마감 일자</li></td>
    <td>해당 없음</td>
  </tr>
</tbody>
</table>

>[!MORELIKETHIS]
>
>[대시보드 기본 사항 살펴보기](/help/marketo-measure-discover-ui/dashboards/discover-dashboard-basics.md){target="_blank"}
