<script setup>
import PrimaryButton from '@/components/buttons/PrimaryButton.vue'
import { ref } from 'vue'
import router from '@/router/index.js'

const emailAddress = ref('')

const resetPassword = () => {
  const user = {
    email_address: emailAddress.value,
  }

  console.log('User', user)

  setTimeout(() => {
    router.push('/reset_done')
  }, 2000)
}
</script>

<template>
  <div class="main-container">
    <v-row>
      <v-col class="right-column d-flex align-center">
        <v-container class="form-container">
          <img src="@/assets/images/logo.png" alt="Logo" />
          <div class="text-center mt-10">
            <h1>Reset Password</h1>
            <p class="create-account-text mt-5">
              Enter your email address and we’ll send you an email with instructions to reset your
              password
            </p>
          </div>

          <v-row class="mt-5">
            <v-col>
              <v-label>Email</v-label>
              <v-text-field
                v-model="emailAddress"
                color="primary"
                variant="outlined"
                class="mt-2"
              ></v-text-field>
            </v-col>
          </v-row>

          <div class="text-center mt-7">
            <PrimaryButton label="Reset" width="188" height="44" @click="resetPassword" />
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

  .left-column img {
    width: 100%;
    height: 100vh;
  }

  .right-column {
    .form-container {
      padding-left: 200px;
      padding-right: 200px;

      h1 {
        font-size: 33px;
      }

      .create-account-text {
        font-size: 16px;
        color: #8a92a6;
      }
    }

    a {
      color: #3a57e8;
      text-decoration: none;
    }
  }
}
</style>
