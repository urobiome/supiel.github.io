<template>
<div class="content mainCon">

    <div class="container">
        <h2 class="logo"><span>Rex</span> 유로바이옴</h2>
        <b-card bg-variant="white" text-variant="dark" class="topCard">
            <b-card-text>
                <span class="bicTxt">Rex 유로바이옴</span>에<br>
                오신걸 환영합니다.<br>
                <div class="smallTxt">
                  검사결과를 보시려면<br>
                  로그인 해주세요.
                </div>
            </b-card-text>
        </b-card>

        <b-card bg-variant="white" text-variant="dark" class="basicCard rexLogin">
            <b-card-text>
              <b-form @submit="onSubmit" v-if="show">
                <b-form-group id="input-group-1" label-for="input-1" class="bottomMargin05">
                  <b-input-group>
                    <b-input-group-prepend is-text>
                      <i class="fi fi-rr-envelope"></i>
                    </b-input-group-prepend>
                      <b-form-input id="input-1" v-model="form.email" type="email" placeholder="Enter email" required></b-form-input>
                  </b-input-group>
                </b-form-group>

                <b-form @submit.stop.prevent>
                  <b-input-group>
                    <b-input-group-prepend is-text>
                      <i class="fi fi-rr-lock"></i>
                    </b-input-group-prepend>
                      <b-form-input type="password" id="text-password" aria-describedby="password-help-block"  placeholder="Enter password" required></b-form-input>
                  </b-input-group>
                </b-form>

                <b-button block variant="primary" class="topMargin1" type="submit">로그인</b-button>
                <div class="passwordLink"><router-link to='/password'>비밀번호 찾기</router-link></div>
              </b-form>

            </b-card-text>
        </b-card>
    </div><!--container-->
  </div><!--content-->
</template>

<script>
  export default {
    data() {
      return {
        form: {
          email: '',
          name: '',
        },
        show: true
      }
    },
    methods: {
      onSubmit(event) {
        event.preventDefault()
        alert(JSON.stringify(this.form))
      },
      onReset(event) {
        event.preventDefault()
        // Reset our form values
        this.form.email = ''
        this.form.name = ''
        this.show = false
        this.$nextTick(() => {
          this.show = true
        })
      }
    }
  }
</script>