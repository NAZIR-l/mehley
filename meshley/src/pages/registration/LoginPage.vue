<template>
  <div class="fullscreen bg-image flex flex-center">
    <!-- <q-img class="absolute-full " src="../../assets/th.jpeg" /> -->
    <q-card class="card q-pa-md">
      <q-card-section>
        <q-avatar size="103px" class="absolute-center shadow-10  q-pb-sm">
          <img src="../../assets/OIP1.jpeg">
        </q-avatar>
        <div class="float-right q-pb-xl vertical-top">
          <q-btn href="signup" flat color="primary" label="Sign_Up" />
        </div>
      </q-card-section>
      <q-card-section>
        <div class="text-center q-pt-lg">
          <div class="col text-h6 ellipsis">
            Login
          </div>
        </div>
      </q-card-section>
      <q-card-section>
        <q-form class="q-gutter-md" @submit.prevent.stop="onSubmit">
          <q-input v-model="email" label="Username" lazy-rules bottom-slots outlined />
          <q-input type="password" v-model="password" label="Password" id="bor" outlined bottom-slots />
          <div class="flex">
            <q-checkbox right-label v-model="left" label="Remember Me" />
            <q-space />
            <q-btn color="primary" type="submit" label="Login" />

          </div>
        </q-form>
      </q-card-section>
    </q-card>
  </div>
</template>

<script>
import { ref } from 'vue'
export default {
  data () {
    return {
      email: '',
      password: ''
    }
  },
  setup () {
    return {
      left: ref(true),
      errors: ref([])
    }
  },
  methods: {
    async Signin () {
      await this.$axios.post('http://127.0.0.1:8000/Signin', {
        email: this.email,
        password: this.password
      }).then((res) => {
        console.log(res)
      }).catch((err) => {
        this.errors.push(err.message)
        console.log(err)
      })
    }
  }

}
</script>
<style lang="scss" scoped>
.card {
  width: 100%;
  max-width: 450px;
  border-radius: 20px;
  background: #eeeef261;
}

#bor {
  border-radius: 10px;
}

// #a {
// top
// }
</style>
