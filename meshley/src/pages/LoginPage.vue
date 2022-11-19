<template>
  <div class="fullscreen bg-image flex flex-center">
    <!-- <q-img class="absolute-full dimmed" src="../assets/bg-01.jpg" /> -->
    <q-card class="card q-pa-md">
      <q-card-section>
        <q-avatar size="103px" class="absolute-center shadow-10  q-pb-sm">
          <img src="../assets/OIP1.jpeg">
        </q-avatar>
      </q-card-section>
      <q-card-section>
        <div class="text-center q-pt-lg">
          <div class="col text-h6 ellipsis">
            Login
          </div>
        </div>
      </q-card-section>
      <q-card-section>
        <q-form class="q-gutter-md">
          <q-input outlined v-model="username" label="Username" lazy-rules standout/>
          <q-input type="password" outlined v-model="password" label="Password" id="bor" standout />
          <div class="flex">
            <q-checkbox right-label v-model="left" label="Remember Me" />
            <q-space />
            <q-btn color="primary" label="Login" />
          </div>
        </q-form>
      </q-card-section>
    </q-card>
  </div>
</template>

<script>
import { ref } from 'vue'

export default {
  setup () {
    return {
      left: ref(true),
      username: ref(''),
      password: ref('')
    }
  }
}
</script>
<style lang="scss" scoped>
.card {
  width: 100%;
  max-width: 450px;
  border-radius: 20px;
  background: #eeeef2f7;
}

#bor {
  border-radius: 10px;
}
</style>
