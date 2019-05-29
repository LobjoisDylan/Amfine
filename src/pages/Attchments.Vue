<style src="./css/attchments.css"></style>
<template>
  <q-page class="bg-color">
    <q-toolbar class="nav-color">
      <img src="assets/ubp.png" class="logo-ubp">
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
        <q-btn flat dense><img class="position" src="assets/folder-search.png"></q-btn>
        <p class="p">DOCUMENTS</p>
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
    <div>
      <div class="row margin-block-nav">
          <div class="col-8">
              <q-btn round icon="keyboard_arrow_left" class="image-blue margin-left margin-top bg-blues" />
              <q-btn round icon="refresh" class="image-blue margin-left margin-top bg-blues"/>
              <span class="attchments">attachments</span>
          </div>
          <div class="col-4 padding">
              <q-btn round icon="cloud_download" class="image-blue margin-left margin-top bg-blues"/>
              <q-btn round icon="delete" class="image-blue margin-left margin-top bg-blues"/>
              <q-btn round icon="settings" class="image-blue margin-left margin-top bg-blues"/>
          </div>
      </div>
    </div>
    <q-table class="color-blue" :dense="$q.screen.lt.md" :data="data" :columns="columns" row-key="name"></q-table>
  </q-page>
</template>

<script>
export default {
  name: 'Attchments',
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
          label: 'Normalized file name',
          align: 'left',
          field: row => row.name,
          format: val => `${val}`,
          sortable: true
        },
        { name: 'entityname', align: 'left', label: 'Entity name', field: 'entityname', sortable: true },
        { name: 'documentfile', align: 'left', label: 'Document family', field: 'documentfile', sortable: true },
        { name: 'documenttype', align: 'left', label: 'Document type', field: 'documenttype' },
        { name: 'date', label: 'Date', field: 'date', sortable: true },
        { name: 'country', label: 'Country', field: 'country' },
        { name: 'language', align: 'left', label: 'Language', field: 'language' },
        { name: 'status', align: 'center', label: 'Status', field: 'status' },
        { name: 'entitynature', align: 'left', label: 'Entity Nature', field: 'entitynature' },
        { name: 'entitycide', align: 'left', label: 'Entity Code', field: 'entitycode' }
      ],
      data: [
        {
          name: 'Auxiliaire TEST sénénité EUR_FR0010298984_KIID_2019-02-11_FR_FR.pdf',
          entityname: 'Auxiliaire TEST Sérénité EUR',
          documentfile: 'LEGAL DOCUMENT',
          documenttype: 'KIID',
          date: '11/02/2019',
          country: 'France',
          language: 'French',
          status: 'Current',
          entitynature: 'PART',
          entitycode: 'FR0010298984'
        },
        {
          name: 'Auxiliaire Sérénité_ANNUAL_REPORT_2017-12-29_FR_FR.pdf',
          entityname: 'Auxiliaire Sérénité',
          documentfile: 'LEGAL DOCUMENT',
          documenttype: 'Annual report',
          date: '29/12/2017',
          country: 'France',
          language: 'French',
          status: 'Current',
          entitynature: 'FUND',
          entitycode: '189350'
        },
        {
          name: 'Auxiliaire Sérénité_PROSPECTUS_2019-05-14_FR_FR.pdf',
          entityname: 'Auxiliaire Sérénité',
          documentfile: 'LEGAL DOCUMENT',
          documenttype: 'Prospectus',
          date: '14/05/2019',
          country: 'France',
          language: 'French',
          status: 'Current',
          entitynature: 'FUND',
          entitycode: '189350'
        },
        {
          name: 'Auxiliaire Sérénité_SEMI_ANNUAL-05-14_FR_FR.pdf',
          entityname: 'Auxiliaire Sérénité',
          documentfile: 'LEGAL DOCUMENT',
          documenttype: 'Semi-annual-report',
          date: '29/06/2019',
          country: 'France',
          language: 'French',
          status: 'Current',
          entitynature: 'FUND',
          entitycode: '189350'
        },
        {
          name: 'Aviva Rendement Oblig 2020 EUR_FR0011285949_KIID_2016-02-11_FR_FR.pdf',
          entityname: 'Aviva Rendement Oblig 2020 EUR',
          documentfile: 'LEGAL DOCUMENT',
          documenttype: 'KIID',
          date: '11/02/2016',
          country: 'France',
          language: 'French',
          status: 'Current',
          entitynature: 'FUND',
          entitycode: 'FR0011285949'
        },
        {
          name: 'CIPAV Appenzel_ANNUAL_REPORT_2017-12-29_FR_FR.pdf',
          entityname: 'CIPAV Appenzell',
          documentfile: 'LEGAL DOCUMENT',
          documenttype: 'Annual report',
          date: '29/12/2017',
          country: 'France',
          language: 'French',
          status: 'Current',
          entitynature: 'FUND',
          entitycode: '19250'
        },
        {
          name: 'CIPAV Appenzel_PROSPECTUS_REPORT_2019-02-11_FR_FR.pdf',
          entityname: 'CIPAV Appenzell',
          documentfile: 'LEGAL DOCUMENT',
          documenttype: 'Prospectus',
          date: '11/02/2019',
          country: 'France',
          language: 'French',
          status: 'Current',
          entitynature: 'FUND',
          entitycode: '19250'
        },
        {
          name: 'CIPAV Appenzel_SEMI_ANNUAL_REPORT_2019-02-11_FR_FR.pdf',
          entityname: 'CIPAV Appenzell',
          documentfile: 'LEGAL DOCUMENT',
          documenttype: 'Prospectus',
          date: '29/06/2018',
          country: 'France',
          language: 'French',
          status: 'Current',
          entitynature: 'FUND',
          entitycode: '19250'
        },
        {
          name: 'CIPAV Appenzel_EUR_FR0013134798_KIID_2019-02-11_FR_FR.pdf',
          entityname: 'CIPAV Appenzell EUR',
          documentfile: 'LEGAL DOCUMENT',
          documenttype: 'KIID',
          date: '11/02/2019',
          country: 'France',
          language: 'French',
          status: 'Current',
          entitynature: 'FUND',
          entitycode: 'FR0013134798'
        },
        {
          name: 'CIPAV Appenzel_EUR_FR0013134798_KIID_2019-02-11_FR_FR.pdf',
          entityname: 'CIPAV Appenzell EUR',
          documentfile: 'LEGAL DOCUMENT',
          documenttype: 'KIID',
          date: '11/02/2019',
          country: 'France',
          language: 'French',
          status: 'Current',
          entitynature: 'PART',
          entitycode: 'FR0013134798'
        },
        {
          name: 'CNP USB Convertibles Europe_PROSPECTUS_2019-02-11_FR_FR.pdf',
          entityname: 'CNP UBP Convertibles Europe',
          documentfile: 'LEGAL DOCUMENT',
          documenttype: 'Prospectus',
          date: '11/02/2019',
          country: 'France',
          language: 'French',
          status: 'Current',
          entitynature: 'FUND',
          entitycode: '31'
        },
        {
          name: 'CNP USB Convertibles Europe_SEMI_ANNUAL_2019-02-11_FR_FR.pdf',
          entityname: 'CNP UBP Convertibles Europe',
          documentfile: 'LEGAL DOCUMENT',
          documenttype: 'Semi_annual report',
          date: '29/06/2018',
          country: 'France',
          language: 'French',
          status: 'Current',
          entitynature: 'FUND',
          entitycode: '31'
        },
        {
          name: 'CNP USB Convertibles Europe_FR00130986548_KIID_2019-02-11_FR_FR.pdf',
          entityname: 'CNP UBP Convertibles Europe',
          documentfile: 'LEGAL DOCUMENT',
          documenttype: 'Semi_annual report',
          date: '11/02/2019',
          country: 'France',
          language: 'French',
          status: 'Current',
          entitynature: 'FUND',
          entitycode: '31'
        },
        {
          name: 'Convertilbles Europe Responsable ZD_EUR_FR0012383727_KIID_2018-02-09_FR_CH',
          entityname: 'Convertibles Europe Responsable ZD EUR',
          documentfile: 'LEGAL DOCUMENT',
          documenttype: 'KIID',
          date: '09/02/2018',
          country: 'Switzerland',
          language: 'French',
          status: 'Current',
          entitynature: 'PART',
          entitycode: 'FR0012383727'
        },
        {
          name: 'Convertilbles Europe Responsable ZD_EUR_FR0012383727_KIID_2018-02-09_FR_CH',
          entityname: 'Convertibles Europe Responsable ZD EUR',
          documentfile: 'LEGAL DOCUMENT',
          documenttype: 'KIID',
          date: '10/10/2016',
          country: 'France',
          language: 'English',
          status: 'Current',
          entitynature: 'PART',
          entitycode: 'FR0012383727'
        },
        {
          name: 'Convertilbles Europe Responsable ZD_EUR_FR0012383727_KIID_2018-02-09_FR_FR',
          entityname: 'Convertibles Europe Responsable ZD EUR',
          documentfile: 'LEGAL DOCUMENT',
          documenttype: 'KIID',
          date: '09/02/2018',
          country: 'France',
          language: 'French',
          status: 'Current',
          entitynature: 'PART',
          entitycode: 'FR0012383727'
        },
        {
          name: 'Dinvest_ANNUAL_REPORT_2017-12-31_FR_CH.PDF',
          entityname: 'Dinvest',
          documentfile: 'LEGAL DOCUMENT',
          documenttype: 'Annual report',
          date: '31/12/2017',
          country: 'Switzerland',
          language: 'French',
          status: 'Current',
          entitynature: 'FUND',
          entitycode: '191260'
        },
        {
          name: 'Dinvest_ANNUAL_REPORT_2017-12-31_FR_00.pdf',
          entityname: 'Dinvest',
          documentfile: 'LEGAL DOCUMENT',
          documenttype: 'Annual report',
          date: '31/12/2017',
          country: '',
          language: 'English',
          status: 'Current',
          entitynature: 'FUND',
          entitycode: '191260'
        },
        {
          name: 'Dinvest_PROSPECTUS_2017-06-01_EN_CH.pdf',
          entityname: 'Dinvest',
          documentfile: 'LEGAL DOCUMENT',
          documenttype: 'Prospectus',
          date: '01/06/2017',
          country: 'Switzerland',
          language: 'English',
          status: 'Current',
          entitynature: 'FUND',
          entitycode: '191260'
        },
        {
          name: 'Dinvest_PROSPECTUS_2017-06-01_EN_SG.pdf',
          entityname: 'Dinvest',
          documentfile: 'LEGAL DOCUMENT',
          documenttype: 'Prospetcus',
          date: '01/10/2016',
          country: 'Singapore',
          language: 'English',
          status: 'Current',
          entitynature: 'FUND',
          entitycode: '191260'
        },
        {
          name: 'Dinvest_PROSPECTUS_2017-06-01_EN_00.pdf',
          entityname: 'Dinvest',
          documentfile: 'LEGAL DOCUMENT',
          documenttype: 'Prospetcus',
          date: '01/06/2017',
          country: '',
          language: 'English',
          status: 'Current',
          entitynature: 'FUND',
          entitycode: '191260'
        }
      ]
    }
  }
}
</script>
