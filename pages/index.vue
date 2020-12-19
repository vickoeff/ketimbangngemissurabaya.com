<template>
  <CBox v-bind="mainStyles[colorMode]">
    <Navbar />
  </CBox>
</template>

<script lang="js">
import { CBox } from '@chakra-ui/vue';
import Navbar from '../layouts/Navbar';

export default {
  name: 'App',
  inject: ['$chakraColorMode'],
  components: {
    Navbar,
    CBox,
  },
  data () {
    return {
      showModal: false,
      mainStyles: {
        dark: {
          bg: 'gray.700',
          color: 'whiteAlpha.900'
        },
        light: {
          bg: 'white',
          color: 'gray.900'
        }
      }
    }
  },
  computed: {
    colorMode () {
      return this.$chakraColorMode()
    },
    theme () {
      return this.$chakraTheme()
    },
  },
}
</script>
