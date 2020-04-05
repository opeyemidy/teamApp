<template>
  <v-container fluid class="pa-0 ma-0" hight="100vh">
    <v-row wrap no-gutters>
      <v-col class="pa-0 cont-height col-md-6 col-lg-8 co-sm-12">
        <v-img src="/01.jpg" height="100%">
          <div class="img-overlays">
            <v-row class="img-cont-height align-center" height="100%">
              <div class="ma-5 pa-5 white--text">
                <h1 class="display-2 font-weight-bold mb-2">
                  Welcome To Elisyam!
                </h1>
                <p>
                  Etiam consequat urna at magna bibendum, in tempor arcu
                  fermentum vitae mi massa egestas.
                </p>
              </div>
            </v-row>
          </div>
        </v-img>
      </v-col>
      <v-col class="col-md-6 col-lg-4 co-sm-12">
        <v-row class="cont-height px-5" align="center">
          <v-col class="px-5 mx-5">
            <v-row justify="center">
              <div class="logo-size">
                <v-img src="/logo.png" class="text-center"></v-img>
              </div>
            </v-row>
            <h1 class="title grey--text">Login</h1>
            <v-form ref="form">
              <v-text-field label="E-mail" required></v-text-field>
              <v-text-field
                label="password"
                required
                type="password"
              ></v-text-field>
              <v-row align="center">
                <v-col class="col-md-6">
                  <v-checkbox label="Do you agree?" required></v-checkbox>
                </v-col>
                <v-col class="col-md-6 text-right grey--text darken-5 body-2">
                  <v-btn text rounded class="text-capitalize">
                    <span class="forgot-pass-color font-weight-light">
                      Forgot password?
                    </span>
                  </v-btn>
                </v-col>
              </v-row>

              <v-btn
                color="success"
                class="mr-4"
                router-link
                to="/dashboard"
                rounded
              >
                Validate
              </v-btn>
            </v-form>
          </v-col>
        </v-row>
      </v-col>
    </v-row>
  </v-container>
</template>
<style scoped>
.cont-height {
  min-height: 100vh;
}
.img-overlays {
  background: linear-gradient(
    135deg,
    rgba(46, 52, 81, 0.4) 0%,
    rgba(52, 40, 104, 0.95) 100%
  );
  height: 100%;
}
.img-cont-height {
  height: 100%;
}
.forgot-pass-color {
  color: rgba(52, 40, 104, 0.95);
}
.logo-size {
  width: 140px;
}
</style>
