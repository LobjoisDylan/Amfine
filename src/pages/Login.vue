<style src="./css/login.css"></style>

<template>
  <q-page>
    <div class="absolute-center align">
      <div class="row inline">
        <img  class="logo" alt="Amfine logo" src="assets/amfine-logo-favicon.png">
        <div>
          <span class="amfine">AMFINE</span><br />
          <span class="asset blue">ASSET</span><br />
          <span class="management blue">MANAGEMENT</span>
        </div>
      </div>
      <h2 class="size">MAIA Funds (MFR)</h2>
      <div class="background-white">
        <div class="row">
          <q-input class="col-11" v-model="email" type="email" label="Enter your email" :dense="dense" :rules="[val => !!val || 'Field is required']"></q-input>
        </div>
        <div class="row">
          <q-input class="col-11" v-model="password" label="Enter your password" :dense="dense" :type="isPwd ? 'password' : 'text'" :rules="[val => !!val || 'Field is required']">
            <template v-slot:append>
              <q-icon
                :name="isPwd ? 'visibility_off' : 'visibility'"
                class="cursor-pointer"
                @click="isPwd = !isPwd"
              ></q-icon>
            </template>
          </q-input>
        </div>
        <div class="row">
          <q-select class="col-11" v-model="model" :options="options" label="Language"></q-select>
          <q-icon class="circle" name="add_circle_outline" />
        </div>
        <div class="row">
          <q-btn class="col-11 width-btn" flat style="color: rgb(55,61,140)" label="Login" to="accueil/"></q-btn>
        </div>
        <q-btn class="forgotten" flat style="color: rgb(158,164,171)" label="forgoten password" to="/"></q-btn>
      </div>
    </div>
    <img class="amfine-logo" src="assets/amfine-logo.png">
  </q-page>
</template>

<script>
export default {
  name: 'Login',

  data () {
    return {
      email: '',
      password: '',
      isPwd: true,
      dense: false,
      model: 'English',
      options: [
        'English', 'French'
      ]
    }
  }
}
</script>
