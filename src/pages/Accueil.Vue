<style src="./css/accueil.css"></style>

<template>
  <q-page class="bg-color">
    <!-- GRAND ECRAN -->
    <q-toolbar class="nav-color">
        <img src="assets/amfine-logo-favicon.png" class="logo-accueil">
        <q-toolbar-title></q-toolbar-title>
        <div class="block">
          <q-btn flat dense icon="home"/>
          <p class="p">HOME</p>
        </div>
        <div class="block">
          <q-btn flat dense to="/products"><img src="assets/database-search.png"></q-btn>
          <p class="p">PRODUCTS</p>
        </div>
        <div class="block">
          <q-btn flat dense to="/attchments"><img class="position" src="assets/folder-search.png"></q-btn>
          <p class="p">ATTACHMENTS</p>
        </div>
        <div class="block">
          <q-btn-dropdown flat dense icon="view_module">
            <q-list>
              <q-item clickable v-close-popup>
                <q-item-section class="color-block">
                  <q-item-label><q-btn to="/studio" class="studio" flat round dense icon="build" />STUDIO</q-item-label>
                </q-item-section>
              </q-item>
              <q-item clickable v-close-popup>
                <q-item-section class="color-block" >
                  <q-item-label><q-btn to="/portfolio" flat round dense icon="pie_chart" />PORTFOLIO</q-item-label>
                </q-item-section>
              </q-item>
            </q-list>
          </q-btn-dropdown>
          <p class="p">MAIA MODULES</p>
        </div>
        <div class="block">
          <q-btn-dropdown flat dense icon="perm_identity">
            <q-list>
              <q-item clickable v-close-popup>
                <q-item-section>
                  <q-item-label>
                    <img src="assets/amfine-logo-favicon.png" class="logo-accueil">
                    <h4 class="kevin">KEVIN BAQUI</h4>
                    <q-btn class="create color-block" flat round dense icon="create" />
                  </q-item-label>
                </q-item-section>
              </q-item>
              <q-item clickable v-close-popup>
                <q-item-section>
                  <q-item-label>
                    <span>kbaqui@amfinesoft.com</span>
                  </q-item-label>
                </q-item-section>
              </q-item>
              <q-item clickable v-close-popup>
                <q-item-section>
                  <q-item-label>
                    <q-select v-model="model" :options="options" label="Language"></q-select>
                  </q-item-label>
                </q-item-section>
              </q-item>
              <q-item clickable v-close-popup>
                <q-item-section>
                  <q-item-label>
                    <q-select v-model="models" :options="theme" label="Theme"></q-select>
                  </q-item-label>
                </q-item-section>
              </q-item>
              <q-item clickable v-close-popup>
                <q-item-section>
                  <q-item-label>
                    <p class="grey-color">UI Version<span class="margin-ui">2.0</span><br />
                    API Version<span class="margin-api">2.0</span></p>
                  </q-item-label>
                </q-item-section>
              </q-item>
              <q-item clickable v-close-popup>
                <q-item-section>
                  <q-item-label>
                    <q-btn to="/" class="color-logout" label="LOGOUT" icon="power_settings_new" />
                  </q-item-label>
                </q-item-section>
              </q-item>
            </q-list>
          </q-btn-dropdown>
          <p class="p">PROFILE</p>
        </div>
    </q-toolbar>
    <!-- GRAND ECRAN -->
    <!-- PETIT ECRAN -->
    <div class="row no-wrap">
      <q-toolbar class="nav-min col-2">
        <q-btn flat round dense icon="menu" color="white menu-center"></q-btn>
      </q-toolbar>
      <q-toolbar class="nav-min col-10">
        <q-input v-model="search" placeholder="Quick search">
        <template v-slot:append>
          <q-icon name="search" color="white"></q-icon>
        </template>
        </q-input>
      </q-toolbar>
    </div>
    <!-- PETIT ECRAN -->
    <div class="align">
      <div class="row inline-block">
        <img  class="logo" alt="Amfine logo" src="assets/amfine-logo-favicon.png">
        <div class="amfine-none">
          <span class="amfine">AMFINE</span><br />
          <span class="asset blue">ASSET</span><br />
          <span class="management blue">MANAGEMENT</span>
        </div>
      </div>
    </div>
    <q-input v-model="search" placeholder="Quick search" class="center input-min bg-white">
      <template v-slot:prepend>
        <q-icon name="search" ></q-icon>
      </template>
    </q-input>
    <div class="row justify-center shadow">
      <div class="white-align blue">
        <q-btn flat dense icon="img:assets/database-blue.png" to="/products" class="size-icon"></q-btn>
        <p>Products</p>
      </div>
      <div class="white-align blue">
        <q-btn flat dense icon="img:assets/search-folder.png" to="/attchments" class="size-icon"></q-btn>
        <p>Attachments</p>
      </div>
      <div class="white-align blue">
        <q-btn flat dense icon="build" to="/studio" class="size-icon" />
        <p>Studio</p>
      </div>
      <div class="white-align blue">
        <q-btn flat dense icon="pie_chart" to="/portfolio" class="size-icon"></q-btn>
        <p>Portfolio</p>
      </div>
    </div>
  </q-page>
</template>

<script>

export default {
  name: 'Accueil',
  data () {
    return {
      model: 'English',
      options: [
        'English', 'French'
      ],
      models: 'AMFINE theme',
      theme: [
        'AMFINE theme', 'Dark'
      ],
      search: '',
      dense: false,
      methods: {
        onItemClick () {
          console.log('Clicked on an Item')
        }
      }
    }
  }
}
</script>
