<template>
  <div class="result">
    <b-container class="main-wrapper">
      <b-navbar class="header">
        <b-col class="text-center">
          <typical
            class="brandName"
            :steps="[
              1000,
              'GoodBye 🤟🏽',
              1500,
              'Are you Ready?',
              1000,
              'Quastionaire'
            ]"
            :wrapper="'h1'"
          ></typical>
        </b-col>
      </b-navbar>
      <b-row>
        <b-col>
          <b-container>
            <finisher />
          </b-container>
        </b-col>
      </b-row>
      <b-row class="navBot" fixed="bottom">
        <b-nav>
          <b-col
            ><b-link class="text-light" href="https://github.com/MahykBurak"
              >My github page</b-link
            >
          </b-col>
        </b-nav>
        <b-nav class="ml-auto" disabled
          ><b-col class="text-right"
            ><typical
              class="helloType"
              :steps="[
                ' ',
                500,
                '{',
                1000,
                '{Made',
                500,
                '{Made by',
                100,
                '{Made by Burak Mike ©}',
                1000
              ]"
              :loop="Infinity"
              :wrapper="'div'"
            ></typical
          ></b-col>
        </b-nav>
      </b-row>
    </b-container>
  </div>
</template>

<script>
import typical from 'vue-typical'
import Finisher from '@/components/inComponents/finisher'
export default {
  components: {
    Finisher,
    typical
  }
}
</script>
<style>
.header {
  height: 100px;
}

.brandName {
  color: whitesmoke;
}

.helloType {
  color: navajowhite;
}
</style>
