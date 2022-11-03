<template>
  <div class="wrapper">
  <div class="main-container">
    <div class="container-one">
      <!--Put images here along with job titles and other experience, and links-->
      <div class="profile">
        <img src="../assets/profilepic.jpg" alt="" />
        <h3>Juan Velazquez</h3>
        <p>Software Developer</p>
      </div>
      <div class="social-links">
        <div class="link">
          <a href="https://github.com/RiceDaddy321" target="_blank" class="">
            <img src="../assets/GitHub-Mark/PNG/GitHub-Mark-64px.png" alt="" />
            <h2>GitHub</h2>
          </a>
        </div>
        <div class="link">
          <a href="https://www.linkedin.com/in/jc-velazquez/" target="_blank" class="">
            <img src="../assets/LinkedIn-Logos/LI-In-Bug.png" alt="" />
            <h2>LinkedIn</h2>
          </a>
        </div>
        <div class="link">
          <a href="https://utrgv.joinhandshake.com/stu/users/31851884" target="_blank" class="">
            <img src="../assets/handshakeLogo.webp" alt="" />
            <h2>Handshake</h2>
          </a>
        </div>
      </div>
    </div>
    <div class="container-two">
      <div class="about-me">
        <h1>About Me</h1>
        <p>
          Firstly, thank you for taking the time to look at my website. My name is Juan Velazquez and I am a third-year Computer Science undergraduate at the University of Texas Rio Grande Valley (UTRGV) in Edinburg (and Brownsville), Texas. My biggest responsibility at the moment is being the web master for the Machine Intellince at UTRGV, which has me maintaing, creating, and scaling their sites in order to help the research team move efficiently. You can learn more about the lab
          <a href="https://miutrgv.github.io/" target="_blank">here</a>.
        </p>
      </div>
      <div class="technologies">
        <h1>Technologies Studied</h1>
        <div class="logos">
          <!-- TODO: put all of the technology logos here, or create a cool bar to represent profieciency -->
          <BarCard/>
        </div>
      </div>
      <!-- temporary, not sure where to put -->
      <div class="button-container">
        <div class="projects-button">
          <a href="">My Projects</a>
        </div>
        <div class="projects-button">
          <a :href="`${publicPath}Resume.pdf`" target="_blank">My Resume</a>
        </div>
      </div>
    </div>
  </div>
  </div>
</template>

<script>
  import BarCard from './LanguagesBarCard.vue'
export default {
    components: {BarCard},
    data() {
      return {
        publicPath: process.env.BASE_URL
      }
    }
};
</script>

<style scoped>
.wrapper {
  display: flex;
  justify-content: center;
}

.main-container {
  display: flex;
  flex-direction: row;
  width: 60%;
  background-color: rgb(155, 141, 141);
  border-radius: 25px;
}

.container-one {
  background-color: pink;
  padding: 2.5%;
  width: 40%;
  border-radius: 25px;

}

.link a {
  text-decoration: none;
  color: black;
  font-size: 10px;
}

.link img {
    height:2rem;
    padding: 0.2rem;
    border-color: rgb(188, 105, 158);
    border-width: thin;
    box-shadow: rgb(190, 118, 118) 2px 2px 2px;
    border-style: solid;
}

.logos {
  display: flex;
  flex-wrap: wrap;
  justify-content: center;
}

.profile img {
  height: 5rem;
  border-radius: 50%;
}

.container-two {
  background-color: lightgreen;
  margin: 2.5%;
  width: 60%;
}

.button-container {
  display: flex;
  flex-direction: row;
  justify-content: center;
  align-content: center;
}

.projects-button {
  background-color: purple;
  margin: 5px;
  padding: 0.5rem;
  border-radius: 0.8rem;
}

.projects-button a{
  text-decoration: none;
  color: whitesmoke;
}
</style>
