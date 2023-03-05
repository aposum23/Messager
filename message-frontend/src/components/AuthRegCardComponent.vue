<template>
  <div class="reg-auth-card">
    <input type="button" value="Sign in" @click="openCloseReg(false, 1, $event)" class="sign-in" />
    <input type="button" value="Sign up" @click="openCloseReg(true, 0, $event)" class="sign-up" />
    <input type="text" v-if="registration" v-model="first_name" class="form" />
    <input type="text" v-if="registration" v-model="last_name" class="form" />
    <input type="text" v-if="registration" v-model="email" class="form" />
    <input type="text" v-if="registration" v-model="phone_number" class="form" />
    <input type="text" v-model="login" class="form" />
    <input type="text" v-model="password" class="form" />
    <input type="text" v-if="registration" v-model="password_rep" class="form" />
    <input type="button" value="Sign in" v-if="!registration" class="form" />
    <input type="button" value="Sign up" v-if="registration" class="form" />
  </div>
</template>

<script>
export default {
  name: 'AuthRegCardComponent',
  data() {
    return {
      registration: false,
      first_name: 'First name',
      last_name: 'Last name',
      email: 'Email',
      phone_number: 'Phone number',
      login: 'Login',
      password: 'Password',
      password_rep: 'Repeat password',
    }
  },
  methods: {
    openCloseReg(registration, inp_num, event) {
      /* inp_num - Номер инпута, который должен стать деактивированным
        registration - Булево значение для переключения формы на регистрацию или авторизацию
        event - Эвент для того чтобы получить доступ к объекту DOM*/
      this.registration = registration;

      let input_active = event.target;
      let input_deactive = input_active.parentElement.children[inp_num];
      input_active.style.backgroundColor = '#1e455a';
      input_deactive.style.backgroundColor = '#19313E';
    }
  },
  mounted:
    function () {
      let sign_in = document.getElementsByClassName('sign-in')[0].style;
      sign_in.backgroundColor = '#1e455a';
    }
}
</script>

<!-- Add "scoped" attribute to limit CSS to this component only -->
<style scoped lang="scss">
.reg-auth-card {
  width: 30%;
  height: 40vh;
  background-color: #0F2632;
  border: 1px solid #0A1D27;
  border-right: 0px;
  border-radius: 15px;
  padding: 1rem;
  overflow-y: scroll;
  text-align: center;
}

.reg-auth-card::-webkit-scrollbar {
  background-color: #0F2632;
  width: 10px;
  border-radius: 0px 15px 15px 0px;
}

.reg-auth-card::-webkit-scrollbar-thumb {
  background-color: #1A2226;
  width: 10px;
  border-radius: 0px 15px 15px 0px;
}

.form {
  display: block;
  margin: .5rem auto
}

.sign-in,
.sign-up {
  margin: 1rem;
  width: 5rem;
  height: 2rem;
}

input {
  background-color: #19313E;
  border: none;
  color: #ffffff;
  padding: .5rem;
}
</style>
