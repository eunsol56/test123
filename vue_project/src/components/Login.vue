<template>
  <section class="test">
    <button v-on:click="kakaoLoginBtn" class="kakaoLogin">카카오 로그인</button>
  </section>
</template>

<script>

export default {
  name: "test",
  methods: {
    kakaoLoginBtn:function(){

      window.Kakao.init('f9b99efb3567227e7a5dda5e4db30648') // Kakao Developers에서 요약 정보 -> JavaScript 키

      if (window.Kakao.Auth.getAccessToken()) {
        window.Kakao.API.request({
          url: '/v1/user/unlink',
          success: function (response) {
            console.log(response)
          },
          fail: function (error) {
            console.log(error)
          },
        })
        window.Kakao.Auth.setAccessToken(undefined)
      }


      window.Kakao.Auth.login({
        success: function () {
          window.Kakao.API.request({
            url: '/v2/user/me',
            data: {
              property_keys: ["kakao_account.email"]
            },
            success: async function (response) {
                alert('성공');
              console.log(response);
            },
            fail: function (error) {
                alert('실패');
              console.log(error)
            },
          })
        },
        fail: function (error) {
          console.log(error)
        },
      })
    }
  }
}
</script>

<style scoped>
.kakaoLogin{
     background-color:#fdd101;
}
</style>