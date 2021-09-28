<template>
  <v-app>
    <v-main>
      <v-row align="center" justify="center" style="height: 100vh;">
        <v-col class="left px-18 pt-16" md="7">
          <v-carousel cycle
            height="80vh"
            class="mt-10"

            hide-delimiter-background
          >
            <v-carousel-item v-for="i in 3" :key="i" class="text-center">
              <img
                width="70%"
                src="../static/assets/1st_illustration.svg"
                alt=""
              />
              <h3 class="mt-5">Trade Globally</h3>
              <p>
                Lorem ipsum dolor sit amet, consetetur sadipscing elitr, sed
                diam nonumy eirmod tempor invidunt ut labore et dolore magna
              </p>
            </v-carousel-item>
          </v-carousel>
        </v-col>
        <v-col class="right" md="5">
          <nuxt />
        </v-col>
      </v-row>
    </v-main>
  </v-app>
</template>
<style lang="scss" scoped>
.left {
  background-image: url('../static/assets/bg1.svg');
  background-size: cover;
  height: 101.7vh;

  h3 {
    letter-spacing: 0px;
    color: #ffffff;
  }
  p {
    letter-spacing: 0px;
    color: #ffffff;
  }
}
.px-18 {
  padding-left: 12%;
  padding-right: 12%;
}
.right {
  height: 101.7vh;
  background-image: url('../static/assets/bg2.svg');
  background-size: cover;

}
</style>
