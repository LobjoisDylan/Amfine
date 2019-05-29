<style src="./css/products.css"></style>
<template>
    <q-page class="bg-color">
        <q-toolbar class="nav-color">
        <img src="assets/amfine-logo-favicon.png" class="logo-accueil">
        <q-input v-model="search" placeholder="Quick search" class="bg-white-input">
        <template v-slot:prepend>
          <q-icon name="search" color="grey"></q-icon>
        </template>
        </q-input>
        <q-toolbar-title></q-toolbar-title>
        <div class="block">
          <q-btn to="/accueil" flat dense icon="home"/>
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
    <div class="margin-bottom">
        <div class="row">
            <div class="col-8">
                <q-btn round icon="keyboard_arrow_left" class="blues margin-left margin-top" />
                <q-btn round icon="refresh" class="blues margin-left margin-top"/>
                <q-btn round icon="filter_list" class="blues margin-left margin-top"/>
            </div>
            <div class="col-4 paddings">
                <q-btn icon="img:assets/menu.png" class="margin-top" />
                <q-btn icon="img:assets/three_square.png" class="margin-top" />
                <q-btn icon="img:assets/two_square.png" class="margin-top"/>
                <q-btn icon="img:assets/one_square.png" class="margin-top"/>
                <q-btn round icon="delete" class="blues margin-left margin-top"/>
                <q-btn round icon="settings" class="blues margin-left margin-top"/>
            </div>
        </div>
    </div>
    <div class="table">
      <q-table class="color-blues" :dense="$q.screen.lt.md" :data="data" :columns="columns" row-key="name"></q-table>
    </div>
    <!--<q-btn round icon="visibility" class="blues"/>
    <q-btn round icon="img:assets/folder-search.png" class="blues" />
    <q-btn round icon="restore" class="blues"/> -->
    </q-page>
</template>

<script>

export default {
  name: 'Product',
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
      columns: [
        {
          name: 'name',
          required: true,
          label: 'Name (Classiffication)',
          align: 'left',
          field: row => row.name,
          format: val => `${val}`,
          sortable: true
        },
        { name: 'code', align: 'left', label: 'Code (Classification)', field: 'code', sortable: true },
        { name: 'currency', label: 'Currency (Classification)', field: 'currency', sortable: true },
        { name: 'lauch', label: 'Lauch (Share Class)', field: 'lauch', sortable: true },
        { name: 'start', label: 'Start date (Classification)', field: 'start', sortable: true },
        { name: 'end', label: 'End date (Classification)', field: 'end' },
        { name: 'one', align: 'right', label: '', field: 'one' },
        { name: 'two', align: 'right', label: '', field: 'two' },
        { name: 'three', align: 'right', label: '', field: 'three' }
      ],
      data: [
        {
          name: 'AMFINE EQUITY EMERGING MARKETS EUR - RETAOM',
          code: 'CLAS001',
          currency: '',
          lauch: '01/11/2018',
          start: '02/11/2018',
          end: ''
        },
        {
          name: 'AMFINE COVERED BOUND USD - A HEDGED',
          code: 'CLAS002',
          currency: '',
          lauch: '01/10/2018',
          start: '01/11/2018',
          end: ''
        },
        {
          name: 'AMFINE DIVERSIFIED FUND OF FUND GBP - INSTIT',
          code: 'CLAS003',
          currency: '',
          lauch: '01/11/2018',
          start: '01/11/2018',
          end: ''
        }
      ]
    }
  }
}
</script>
