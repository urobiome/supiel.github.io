<template>
  <div class="content">
    <div class="titleTop backBlue">
      <i class="fi fi-rr-angle-left" @click="goback"></i>
      <h5>서비스 안내</h5>
    </div>
    <div class="container subCon">
      <div class="subTop">
        <img src="../../public/img/health-care.png">
        <div class="subTopTxt">
          <h5>Rex 유로바이옴</h5>        
          <div class="smallTxt">Rex 유로바이옴으로 나의 마이크로바이옴 상태를
확인하고 건강을 지킬 수 있습니다. 
</div>
        </div>
      </div>   
        <b-card bg-variant="white" text-variant="dark" class="basicCard infoCard" header="서비스 절차">
            <b-card-text>
                <div class="cardTxt">
                    <img src="../../public/img/healthy.png">
                    <div><b>step.01</b><br>나는 건강할까?</div>
                </div>
                <div class="cardIcon"><b-icon icon="caret-down-fill" aria-hidden="true"></b-icon></div>
                <div class="cardTxt">
                    <img src="../../public/img/pc.png">
                    <div><b>step.02</b><br>Rex 유로바이옴 신청</div>
                </div>
                <div class="cardIcon"><b-icon icon="caret-down-fill" aria-hidden="true"></b-icon></div>
                <div class="cardTxt">
                    <img src="../../public/img/hospital.png">
                    <div><b>step.03</b><br>병원 검사 진행</div>
                </div>
                <div class="cardIcon"><b-icon icon="caret-down-fill" aria-hidden="true"></b-icon></div>
                <div class="cardTxt">
                    <img src="../../public/img/microscope.png">
                    <div><b>step.04</b><br>데이터 분석</div>
                </div>
                <div class="cardIcon"><b-icon icon="caret-down-fill" aria-hidden="true"></b-icon></div>
                <div class="cardTxt">
                    <img src="../../public/img/smartphone.png">
                    <div><b>step.05</b><br>APP으로 결과 확인</div>
                </div>
            </b-card-text>
        </b-card>
        <b-card bg-variant="white" text-variant="dark" class="basicCard" header="Rex Soft">
            
                <img src="../../public/img/rex-img.jpg">
                
        </b-card>

        <b-button block variant="primary" class="bottomMargin1 rexHomeBtn" href="http://rexsw.com/"><i class="fi fi-rr-home-location-alt"></i> 홈페이지 방문</b-button>

    </div><!--container-->
  </div><!--content-->
</template>
<script>
export default {
  methods:{ 
      goback(){
          this.$router.go(-1);//     
      } 
  }
};
</script>