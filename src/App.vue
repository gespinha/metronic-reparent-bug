<template>
  <div class="flex grow">
    <Sidebar />
    <div class="wrapper flex grow flex-col">
      <Header />
      <main class="grow content pt-5" id="content" role="content">
        <div class="container-fixed">

          <div id="redbox" style="color: #fff; background: #f00;">This is the red box</div>

          <ExampleMenu />

        </div>
      </main>
      <Footer />
    </div>
  </div>
  <SearchModal />
</template>

<script lang="ts" setup>
import Sidebar from './components/Sidebar.vue'
import Header from './components/Header.vue'
import Footer from './components/Footer.vue'
import SearchModal from "./components/SearchModal.vue";
import { nextTick, onMounted } from 'vue';
import KTComponent from './metronic/core/index';
import KTLayout from './metronic/app/layouts/demo1.js';
import ExampleMenu from "./components/ExampleMenu.vue";

onMounted(() => {
	nextTick(() => {
		KTComponent.init();
		KTLayout.init();
	});
});
</script>