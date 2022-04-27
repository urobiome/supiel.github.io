<template>

  <div class="content">
    <div class="titleTop backBlue">
      <i class="fi fi-rr-angle-left"></i>
      <h5>비밀번호 찾기</h5>
    </div>
    <div class="container subCon">
      <div class="subTop">
        <img src="../../public/img/password.png">
        <div class="subTopTxt">
          <h5>비밀번호 찾기</h5>
          <div class="smallTxt">등록하신 이메일을 입력해주세요.
임시 비밀번호를 메일로 보내드립니다. 
</div>
        </div>
    </div>
    <b-card bg-variant="white" text-variant="dark" class="basicCard">
        <b-card-text class="cardBar">
            <b-form class="accountEdit passwordFind">
                <label for="text-email">임시 비밀번호 발송</label>
                <b-form-input type="email" id="emailNew" placeholder="전송받을 이메일을 입력해주세요." class="bottomMargin1"></b-form-input>
            </b-form>
        </b-card-text>
        <router-link to='/sent'><b-button block variant="primary">확 인</b-button> </router-link>
    </b-card>
 

    </div><!--container-->
  </div><!--content-->
</template>
<script>
export default {};
</script>