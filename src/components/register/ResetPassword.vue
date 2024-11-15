<script setup>
import PrimaryButton from '@/components/buttons/PrimaryButton.vue'
import router from '@/router/index.js'

const goBack = () => {
  router.push('/login')
}
</script>

<template>
  <div class="main-container">
    <v-row>
      <v-col class="right-column d-flex align-center">
        <v-container class="form-container">
          <img src="@/assets/images/logo.png" alt="Logo" />
          <div class="text-center mt-7">
            <img src="@/assets/images/check.png" alt="Logo" />
            <h1>Success !</h1>
            <p class="info-text mt-6">
              An email has been sent to your email@domain.com. Please check for an email from
              company and click on the included link to reset your password.
            </p>
          </div>
          <div class="text-center mt-9">
            <PrimaryButton label="Back to home" width="188" height="44" @click="goBack" />
          </div>
        </v-container>
      </v-col>
      <v-col class="left-column">
        <img src="@/assets/images/register-background.png" alt="Background" />
      </v-col>
    </v-row>
  </div>
</template>

<style scoped>
.main-container {
  height: 100vh;
  overflow: hidden;

  .left-column img {
    width: 100%;
    height: 100%;
  }

  .right-column {
    .form-container {
      padding-left: 200px;
      padding-right: 200px;

      h1 {
        font-size: 64px;
        color: #0048b2;
      }

      .info-text {
        font-size: 16px;
        color: #232d42;
      }
    }

    a {
      color: #3a57e8;
      text-decoration: none;
    }
  }
}
</style>
