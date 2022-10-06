<template>
  <div class="main-container">
    <div
      class="bar-container"
      v-for="(language, index) in sortedArray"
      :key="language.id"
    >
      <p class="txt">{{ language.Name }}</p>
      <img :src="language.Image" alt="" />
      <svg :width="data.Width" :height="heights[index]">
        <rect
          class="bar"
          :width="data.Width"
          :height="heights[index]"
          style="stroke-width: 10; stroke: rgb(0, 0, 0)"
          :style="{ fill: language.BarColor }"
        />
      </svg>
    </div>
  </div>
</template>

<script>
import jsonData from "../../languageProficiency.json";
import { reactive, computed } from "vue";

// send a sorted array
let languageArray = reactive(jsonData.LanguagesArray);
let sortedArray = computed(() => {
  return languageArray.sort(function (a, b) {
    return a.Skill - b.Skill;
  });
});
// //We need to create an array of lengths
// let obj = JSON.parse(jsonData);
let heights = computed(()=> {
  var heightsArray = [];
  sortedArray.value.forEach((element) => {
   let result = element.Skill * jsonData.MaxLength;
   heightsArray.push(result + jsonData.Dimension);
  });

  return heightsArray;
});
// sortedArray.value.target.forEach((element) => {
//   let result = element.Skill * jsonData.MaxLength;
//   heights.push(result.value + jsonData.Dimension);
// });
// checking that the array is sorted
console.log(heights);
export default {
  data() {
    return {
      data: jsonData,
      spacing: jsonData.Spacing,
      heights: heights,
      sortedArray: sortedArray,
    };
  },
  methods: {
    getLength(maxLength, modifier) {
      return maxLength * modifier;
    },
  },
};
</script>
<style scoped>
.main-container {
  
  background-color: aquamarine;
  height: fit-content;
  width: fit-content;

  display: flex;
  padding: 1rem;
  flex-direction: row;
  justify-content: center;
  align-items: flex-end;
}

.bar-container {
  display: flex;
  flex-direction: column;
  align-items: center;
  justify-content: center;
  padding: 5px;
}
.bar-container img {
  height: auto;
  width: 2rem;
  margin: 2%;
}
.txt {
  width: fit-content;
}
</style>
