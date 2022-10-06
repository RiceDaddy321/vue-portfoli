<template>
  <div class="home">
    <UnderConstructionCard/>
    <MainCard/>
    <ProjectsCard/>
  </div>
</template>

<script>
// @ is an alias to /src
import UnderConstructionCard from '@/components/UnderConstructionCard.vue';
import MainCard from '@/components/MainCard.vue';
import ProjectsCard from '@/components/ProjectsCard.vue';
export default {
  name: 'HomeView',
  components: {
    UnderConstructionCard,
    MainCard,
    ProjectsCard
    
}
}
</script>
