<template>
  <div class="box">
    <QuickSummary />
    <SkillSection />
    <AppointmentPersmission/>
    <basic-template />
    <Card />
    <Charts />
    <Communication />
  </div>
</template>

<script lang="ts">
import { defineComponent } from 'vue'
import basicTemplate from './components/basic-template.vue'
import Communication from './components/communication.vue'
import Card from './components/card/index.vue'
import Charts from './components/charts/index.vue'
import QuickSummary from './components/quick-summary.vue'
import SkillSection from './components/skill-section.vue'
import AppointmentPersmission from './components/appointment-permission.vue'


export default defineComponent({
  components: {
    Card,
    Charts,
    basicTemplate,
    Communication,
    QuickSummary,
    SkillSection,
    AppointmentPersmission
  }
})
</script>

<style lang="scss" scoped>
  .box {
    padding: 15px;
  }
</style>