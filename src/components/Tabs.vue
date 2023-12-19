<script>
  import Main from './Main.vue';
  import Selected from './Selected.vue';
  export default {
    name: 'Tabs',
    components: { Main, Selected },
    data() {
      return {
        tabs: ['Main', 'Selected'],
        selectedTab: 'Main',
      }
    }
  }
</script>

<template>
  <div class="tabs">
    <div class="tabs__links">
      <span
        class="tabs__tab"
        v-for="tab, index in tabs"
        :key="index"
        @click="selectedTab = tab"
        :class="{ 'tabs__tab--selected': selectedTab === tab }"
      >
        {{ tab }}
      </span>
    </div>

    <div class="tabs__content">
      <Main v-if="selectedTab === 'Main'"/>
      <Selected v-else/>
    </div>
  </div>
</template>

<style>
</style>