<template>
  <router-view />
</template>
<script>
import { useQuasar } from 'quasar'
import customIcons from 'src/custom-icons/custom-icons.js'

export default {
  setup () {
    const $q = useQuasar()
  
    $q.iconSet.set(customIcons)
  
  }
}
</script>
