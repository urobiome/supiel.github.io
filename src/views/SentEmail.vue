<template>

  <div class="content">
    <div class="titleTop backBlue">
      <i class="fi fi-rr-angle-left"></i>
      <h5>이메일 발송</h5>
    </div>
    <div class="container subCon">
      <div class="subTop">
        <img src="../../public/img/sent.png">
        <div class="subTopTxt">
          <h5>이메일 발송 완료t</h5>
          <div class="smallTxt">ABCD@rexsw.com로 임시 비밀번호가 발송되었습니다.</div>
        </div>
    </div>
    <b-card bg-variant="white" text-variant="dark" class="basicCard">
        <b-card-text class="cardBar">
            이메일을 확인해주세요.
        </b-card-text>
        <router-link to='/'><b-button block variant="primary">확 인</b-button></router-link>
    </b-card>
 

    </div><!--container-->
  </div><!--content-->
</template>
<script>
export default {};
</script>