<template>
  <div class="fullscreen  flex flex-center">
    <q-card class="card q-pa-md">
      <q-card-section>
        <q-avatar  size="103px" class="absolute-center shadow-10  q-pb-sm">
          <img src="../../assets/OIP1.jpeg" alt="">
        </q-avatar>
      </q-card-section>
      <q-card-section>
        <div class="text-center q-pt-lg">
          <div class="col text-h6 ellipsis">
            SignUp
          </div>
        </div>
      </q-card-section>
      <q-card-section>
        <q-form class="q-gutter-md">
          <q-input  v-model="username" label="User Name" bottom-slots outlined ></q-input>
          <q-input  v-model="email" label="Email" bottom-slots outlined ></q-input>
          <q-input  v-model="password" id="bor" label="Password" bottom-slots outlined ></q-input>
          <div class="flex">
              <div icon="arrow" >
                <q-btn label="BACK TO Login" href="login" color="primary" flat class="q-ml-sm" />
              </div>
            <q-space />
            <q-btn color="primary" label="Rigister" />
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
      password: '',
      username: ''

    }
  },
  setup () {
    return {
      left: ref(true)
    }
  },
  methods: {
    async Signin () {
      await this.$axios.post('http://127.0.0.1:8000/Signup', {
        email: this.email,
        password: this.password,
        username: this.username
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
  text-decoration: none;
}

#bor {
  border-radius: 10px;
}
// .dropdown{

// }
</style>
