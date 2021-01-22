<template>
  <div id="app">
    <div class="bg">
      <div class="bg-text">
        <p id="original-bg-text-1" style="font-family: 'Exo-Light'">
          Student Developer
        </p>
        <!-- Moblie Only Text -->
        <p id="instead-bg-text-1" style="font-family: 'Exo-Light'">
          Student Developer
        </p>
        <p style="margin-top: -1.1em; font-family: 'Exo-Regular'">ANTEGRAL</p>
      </div>
    </div>
    <div class="projects">
      <el-row>
        <el-col :span="4" id="pcOnly"
          ><div class="grid-content bg-purple">.</div></el-col
        >
        <el-col :span="16"
          ><div class="grid-content">
            <div class="projects-inner">
              <!-- Projects -->
              <div class="projects-header">
                <!-- Projects header -->
                <b id="projects-header-text-1">프로젝트 살펴보기</b>
                <p id="projects-header-text-2">
                  하단 바를 통해 진행내역을 살펴보세요.
                </p>
              </div>
              <div class="projects-menu">
                <el-menu
                  :default-active="1"
                  class="el-menu-demo"
                  mode="horizontal"
                  @select="handleSelect"
                >
                  <el-menu-item index="1">MAIN</el-menu-item>
                  <el-menu-item index="2">ACTIVE</el-menu-item>
                  <el-menu-item index="3">MAINTAIN</el-menu-item>
                  <el-menu-item index="4">LEGACY</el-menu-item>
                </el-menu>
              </div>
              <div
                class="projects-body"
                v-loading="true"
                element-loading-text="현재 지원하지 않는 기능입니다. 조금만 더 기다려주세요..!"
                element-loading-background="rgba(0, 0, 0, 0.15)"
              ></div>
            </div></div
        ></el-col>
        <el-col id="pcOnly" :span="4"
          ><div class="grid-content bg-purple"></div
        ></el-col>
      </el-row>
    </div>
    <div class="servers">
      <el-row>
        <el-col :span="4" id="pcOnly"
          ><div class="grid-content bg-purple">.</div></el-col
        >
        <el-col :span="16">
          <!-- Projects -->
          <div class="servers-header">
            <!-- Projects header -->
            <b id="projects-header-text-1">서버상태 확인</b>
            <p id="projects-header-text-2">
              현재 가동되고 있는 서버 상태를 확인 할 수 있습니다.
            </p>
          </div>
          <div
            class="projects-body"
            v-loading="true"
            element-loading-text="현재 지원하지 않는 기능입니다. 조금만 더 기다려주세요..!"
            element-loading-background="rgba(0, 0, 0, 0.15)"
          ></div>
        </el-col>
        <el-col id="pcOnly" :span="4"
          ><div class="grid-content bg-purple"></div
        ></el-col>
      </el-row>
    </div>
    <div class="footer"></div>
  </div>
</template>

<script>
export default {
  name: "app",
};
</script>

<style lang="scss">
@import url("https://fonts.googleapis.com/css2?family=Noto+Sans+KR&display=swap");
@import url("./assets/fonts/Exo-Light/font.css");
@import url("./assets/fonts/Exo-Regular/font.css");

html,
body {
  font-family: "Noto Sans KR", sans-serif;
  height: 100%;
  width: 100%;
  margin: 0;
}

#projects-header-text-1 {
  font-size: 2rem;
}

#projects-header-text-2 {
  font-size: 1.4rem;
  margin-top: 0.2rem;
}

.servers {
  background-color: rgb(250, 250, 250);
}

.servers-header {
  margin-top: 3rem;
}

.projects {
  margin-bottom: 3rem;
}

// Not Available Only
.projects-body {
  padding-bottom: 50%;
  background-color: rgb(245, 245, 245);
}

// Not Available Only
.servers-body {
  padding-bottom: 50%;
  background-color: rgb(245, 245, 245);
}

.projects-menu {
  margin-bottom: 3rem;
}

.projects-header {
  margin-bottom: 2rem;
}

.bg-text {
  color: white;
  font-size: 2.7em;
  padding-top: 5em;
  padding-left: 10%;
}

.projects {
  padding-top: 3%;
}

.footer {
  background-color: rgb(245, 245, 245);
  padding-top: 3%;
  margin-top: 3%;
}

.bg {
  /* The image used */
  background-image: url("./assets/temp_logo.jpg");

  /* Full height */
  height: 100vh;

  /* Center and scale the image nicely */
  background-position: center;
  background-repeat: no-repeat;
  background-size: cover;
}

// PC
@media screen and (min-width: 1241px) {
  #instead-bg-text-1 {
    display: none;
  }

  #original-bg-text-1 {
    display: block;
  }
}

// Moblie
@media screen and (max-width: 1240px) {
  #pcOnly {
    display: none;
  }

  .bg-text {
    font-size: 2em;
  }

  #original-bg-text-1 {
    display: none;
  }

  #instead-bg-text-1 {
    display: block;
  }
}
/* #app {
  font-family: Avenir, Helvetica, Arial, sans-serif;
  -webkit-font-smoothing: antialiased;
  -moz-osx-font-smoothing: grayscale;
  text-align: center;
  color: #2c3e50;
  margin-top: 60px;
} */
</style>
