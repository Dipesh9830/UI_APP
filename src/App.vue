<template>
  <div>
  <app-header />
  <router-view/>
  <br>
  <AirportComponent/>
  <br>
  <app-footer/>
</div>
</template>

<script>
import AppHeader from '@/components/AppHeader.vue'
import AirportComponent from './components/AirportComponent.vue';

import AppFooter from '@/components/AppFooter.vue'

export default {
  components: {
    AppHeader,
    AirportComponent,
    AppFooter
  }
}

</script>