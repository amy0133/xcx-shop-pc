<template>
  <div class="home">
    <HelloWorld msg="管理系统首页"/>
  </div>
</template>

<script lang="ts">
import { Component, Vue } from 'vue-property-decorator'
import HelloWorld from '@/components/HelloWorld.vue' // @ is an alias to /src

@Component({
  components: {
    HelloWorld
  }
})
export default class Home extends Vue {
  private mounted (): void {
    if (!localStorage.getItem('username')) {
      this.$router.replace('/login')
    }
  }
}
</script>
