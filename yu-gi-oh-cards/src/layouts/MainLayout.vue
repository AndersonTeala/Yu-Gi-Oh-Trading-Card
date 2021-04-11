<template>
  <q-layout view="lHh Lpr lFf">
    <q-header elevated>
      <q-toolbar>
        <q-toolbar-title>
          <q-img style="width: 150px" src="https://www.gtnm.at/wp-content/uploads/bfi_thumb/a32dad516b6d10c5ab6ac415a297eaf0_yugioh-yugioh-clipart-logo_500-175-12ekhwr9cwpb8ltduwezv7j09s8bt55i3z2bjnit5p3jqfgw.png" />
        </q-toolbar-title>
      </q-toolbar>
    </q-header>
    <q-page-container>
      <router-view />
    </q-page-container>
  </q-layout>
</template>

<script>
import EssentialLink from 'components/EssentialLink.vue'

export default {
  name: 'MainLayout',
  components: {
    //
  },
  data () {
    return {
      //
    }
  }
}
</script>
