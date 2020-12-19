<template>
  <div class="container">
    <CGrid
      d="flex"
      position="sticky"
      w="100vw"
      h="80px"
      p="1rem"
      flex-dir="column"
      justify-content="center"
      column="2"
    >
      <CBox w="10%">
        <CButton mr="3" variant="link"> Bantu Kami </CButton>
      </CBox>
      <CBox w="10%">
        <CIconButton
          mr="3"
          :icon="colorMode === 'light' ? 'moon' : 'sun'"
          :aria-label="`Switch to ${
            colorMode === 'light' ? 'dark' : 'light'
          } mode`"
          @click="$toggleColorMode"
        />
      </CBox>
    </CGrid>
  </div>
</template>

<script lang="js">
import {
  CGrid,
  CBox,
  CButton,
  CIconButton
} from '@chakra-ui/vue';

export default {
  name: 'Navbar',
  inject: ['$toggleColorMode'],
  components: {
    CGrid,
    CBox,
    CButton,
    CIconButton
  },
  computed: {
    toggleColorMode () {
      return this.$toggleColorMode
    }
  },
};
</script>
