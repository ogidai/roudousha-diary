<template>
<header>
  <div class="header-inner">
  <h1 class="header-logo">労働者日記</h1>
  <span class="toggle-icon">
    <b-icon v-b-toggle.my-sidebar icon="filter-right" font-scale="2"></b-icon>
  </span>
  <Sidebar/>
  </div>
</header>
</template>

<script>
import Sidebar from './Sidebar.vue'

export default {
    name: 'Header',
    components: {
      Sidebar
    },
    data() {
      return {
        visible: false,
      }
    },
    methods: {
      hideSidebar() {
        this.localShow = false
        console.log(this.localShow)
      }
    }

}
</script>

<style>
header {
  position: fixed;
  top: 0;
  left: 0;
  width: 100%;
  border-bottom: 1px solid #ddd;
}
.header-inner {
  display: flex;
  justify-content: center;
  align-content: center;
  padding: 10px 30px;
}
.header-logo {
  padding: 0;
  margin: 0;
  width: 150px;
  font-size: 30px;
}
.toggle-icon {
  position: absolute;
  top: 50%;
  right: 30px;
  transform: translateY(-50%);
}
svg {
  outline: none;
}
</style>