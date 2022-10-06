<template>
  <!-- {{ projectData }} -->
  <div class="main-container">
    <div
      class="project-card"
      v-for="(items, index) in projectData.projectsArray"
      v-bind:key="items"
    >
      <h2>{{ projectData.projectsArray[index].title }}</h2>
      <img v-bind:src="projectData.projectsArray[index].image" alt="" />
      <p>{{ projectData.projectsArray[index].about }}</p>
      <a :href="projectData.projectsArray[index].Link1" target="_blank" class="link1">GitHub</a>
      <a :href="projectData.projectsArray[index].Link2" target="_blank" class="link2">Look</a>
    </div>
  </div>
</template>
<script>
import jsonData from "../../projects.json";
export default {
  data() {
    return {
      projectData: jsonData,
    };
  },
};
</script>
<style scoped>
.project-card img {
  height: 2rem;
}
/* This is how to display elements two per row but vertical on mobile */
.main-container {
    display: flex;
    justify-content: center;
    align-items: center;
    flex-wrap: wrap;
}

.project-card {
    margin: 10px;
    padding: 10px;
    flex-wrap: 0 0 40%;
    background-color:white;
    border-radius: 25px;
    box-shadow: rgb(58, 54, 54) 0px 3px 8px;
}
</style>
