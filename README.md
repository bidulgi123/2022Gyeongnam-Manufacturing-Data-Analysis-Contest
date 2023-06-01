<h1> 대회 링크 및 데이터 다운 </h1>
<h2> https://myfactorydata.com/bbs/board.php?bo_table=competition&wr_id=2 </h2>
<h5>
  분석목표 

● 케이블 단자 압착 설비에서 발생하는 압력 센서의 시계열 데이터를 분석합니다.

● 이상적인 압력 파형(REFERENCE_WAVE)을 참조하여 측정된 압력 파형(MEASURED_WAVE)으로부터 해당 케이블의 압착부 불량 여부를 판별하는 것이 목표입니다.



데이터 구성

● REFERENCE_WAVE.csv : 케이블과 단자의 치수에 따라 생성된 이상적인 압력 파형으로 기준 파형이라고 보면 됩니다. 

   - REFERENCE_ID : 기준 파형의 고유 ID

   - REFERENCE_WAVE : 기준 파형의 시계열 값 



● MEASURED_WAVE_TRAIN.csv : 케이블에 단자를 압착할 때 측정된 압력 파형입니다.

   - REFERENCE_ID : 압착 당시 케이블과 단자의 치수에 해당하는 기준 파형의 ID

   - MEASURED_WAVE : 압착 당시 측정된 압력 파형의 시계열 값

   - QUALITY : 공정 후 압착부의 불량 여부 {GOOD : 정상, BAD : 불량}



● MEASURED_WAVE_TEST.csv : 모델의 검증을 위해 사용되며, REFERENCE_ID와 MEASURED_WAVE를 통해 QUALITY를 판별해야 합니다.

   - INDEX : ANSWER_FORM.csv에 해당하는 인덱스 번호

   - REFERENCE_ID : 압착 당시 케이블과 단자의 치수에 해당하는 기준 파형

   - MEASURED_WAVE : 압착 당시 측정된 압력 파형의 시계열 값



● ANSWER_FORM.csv : 정답 제출 양식

   - INDEX : MEASURED_WAVE_TEST.csv에 해당하는 인덱스 번호

   - QUALITY : MEASURED_WAVE_TEST.csv로부터 판별한 불량 여부 {GOOD : 정상, BAD : 불량}
  </h5>
  
<h2>분석 방법</h2>

<h5>
기준 파형 데이터를 기준으로 REFERENCE_ID와 매칭 시켜 차이를 구한후 파생변수화 하였음
불량과 정상의 비율이 차이났기 때문에 Oversampling 후 MLP(Multilayer Perceptron)진행
  <br>
   <img src="https://github.com/bidulgi123/2022Gyeongnam-Manufacturing-Data-Analysis-Contest/assets/121657338/1a7338d0-d4ae-463e-900b-83ecf1f264f4" alt="My Image">
   <img src="https://github.com/bidulgi123/2022Gyeongnam-Manufacturing-Data-Analysis-Contest/assets/121657338/1d91d226-eb0f-440f-8e7e-48cad7e6bee8" alt="My Image2">
</h5>
<h2> 역할 </h2>
<h5> 팀장, 시계열 데이터 전처리 및 시각화 MLP 모델링 구현 </h5>

<h2> 결과 </h2>
<h5> 우수상 </h5>
