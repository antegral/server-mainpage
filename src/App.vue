<template>
  <div id="app">
    <div class="bg">
      <div class="bg-text">
        <div id="original-bg-text-1">
          <p
            class="head-text-animated"
            style="font-size: 2.3rem; font-famrily: 'Exo-Light'"
          >
            Student Developer.
          </p>
          <p
            style="
              margin-top: -0.9em;
              font-size: 3rem;
              font-family: 'Exo-Regular';
            "
          >
            ANTEGRAL
          </p>
        </div>
        <!-- Moblie Only Text -->
        <div id="instead-bg-text-1">
          <p style="font-size: 1.5rem; font-family: 'Exo-Light'">
            Student Developer
          </p>
          <p
            style="
              margin-top: -0.75em;
              font-size: 2.2rem;
              font-family: 'Exo-Regular';
            "
          >
            ANTEGRAL
          </p>
          <p
            style="
              margin-top: -0.75em;
              font-size: 1rem;
              font-family: 'Exo-Light';
            "
          >
            아직 모바일은 지원하지 않아요!<br />조금만 더 기다려주세요!
          </p>
        </div>
      </div>
    </div>
    <div class="projects" id="pcOnly">
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
    <div class="servers" id="pcOnly">
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
          <br />
        </el-col>
        <el-col id="pcOnly" :span="4"
          ><div class="grid-content bg-purple"></div
        ></el-col>
      </el-row>
    </div>
    <div class="footer">
      <p id="footer-copyright-text">
        Copyright {{ new Date().getFullYear() }}, Antegral, All rights
        reserved.<br />and, Thanks to all! ✨
      </p>
    </div>
  </div>
</template>

<script>
export default {
  name: "app",
  data() {
    return {
      headText: "JavaScript",
    };
  },
  computed: {
    changeHeadText: () => {},
  },
  mounted() {},
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

#footer-copyright-text {
  color: rgb(150, 150, 150);
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
  padding-bottom: 1rem;
}

.servers-header {
  margin-top: 3rem;
}

.projects {
  margin-bottom: 3rem;
}

.head-text-animated {
  border-right: solid 1.7px rgba(255, 255, 255, 0.75);
  white-space: nowrap;
  overflow: hidden;
  font-family: "Exo-Light";
  color: rgb(255, 255, 255);
}

.head-text-animated {
  animation: animated-text 1s steps(20, end) 1s 1 normal both,
    animated-cursor 600ms steps(20, end) infinite;
}

@keyframes animated-text {
  from {
    width: 0;
  }
  to {
    width: 20rem;
  }
}

@keyframes animated-cursor {
  from {
    border-right-color: rgba(236, 236, 236, 0.75);
  }
  to {
    border-right-color: transparent;
  }
}

// Not Available Only
.projects-body {
  padding-bottom: 50%;
  background-color: rgb(245, 245, 245);
}

// Not Available Only
.servers-body {
  padding-bottom: 50%;
  background-color: rgb(247, 247, 247);
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

.bg {
  /* The image used */
  background-image: url("./assets/main.png");

  /* Full height */
  height: 100vh;

  /* Center and scale the image nicely */
  background-position: center;
  background-repeat: no-repeat;
  background-size: cover;
}

// PC
@media screen and (min-width: 1024px) {
  #footer-copyright-text {
    padding-left: 3rem;
  }

  #instead-bg-text-1 {
    display: none;
  }

  #original-bg-text-1 {
    display: block;
  }

  .footer {
    background-color: rgb(245, 245, 245);
    margin-top: 1rem;
    padding-top: 0.5rem;
    padding-bottom: 0.4rem;
  }
}

// Moblie
@media screen and (max-width: 1023px) {
  #pcOnly {
    display: none;
  }

  #footer-copyright-text {
    padding-left: 1rem;
    font-size: 0.5rem;
  }

  #original-bg-text-1 {
    display: none;
  }

  #instead-bg-text-1 {
    display: block;
  }

  .footer {
    background-color: rgb(245, 245, 245);
    margin-top: 0rem;
    padding-top: 0.5rem;
    padding-bottom: 0.4rem;
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
