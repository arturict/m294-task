<script setup>
//https://play.vuejs.org/#eNq1Vn9v2zYQ/SoHD0NSzJZkJ+k6LS3QFR3Qoc2KZcD+mIeAliiLiUSqJJU4DfLd90hR/hXH7YoMhgXyjny8e3e8493gddNE1y0fpINTk2nRWDLcts2rqRR1o7SlO9K8oHsqtKrpAEsPlqozfmN+5Tx/Z3kd9FG8LnTIBz9PZaaksSQgMfTS4R3+PZUEaPclEnlK42E3tsJWPKWD90oDVDSmrSlXldJkhCVWczskB8ctzISQ5ViTCTknXgmrD4YB03JmuAbQa0vXXCviyhAHQpa1htVueNkaqyhv8XcHcK/nDPbN2jqic5xAGUAZXTGT07ydcT3XXA5JKrDEyLIrUTPoDZOZbbEfXj5ueHQQfJRtDajfi7+Uzk1KJ+NJUABt7pwvrW1MGsdNxTKeMWuiTNVxLapK8AvJVTxJEvfvAO/9d53MHq8n8ys4eEjc0/tPTx+Lxzgd/zg5+ipSwebFjEn8vkRqj9eT+ubxLByCnpxyAd+kgmW3xIWuVQ5y3c2hh2RXbAavndOd/wSjJSNWiU/traNIMyT+EvVaVW1jW/Z/UPrU6f1i0t/t/ZGY8araEYR/nk3ladzVJlQlTByJFbMcM6LTcvzKlZwCJec0xsQtgTgX1/COGfNyOpipxXTgV28pZNi41FKIC9ZtFLfrUaE0NrgSRkJ2pWw6IEq9T0ET+QnEqc+RXuonXuqjvRT7mZNvENarN4RYFfcOxPCgcz2MTuM1RjA19rZyw5nKb+nOrZyx7GquVSuRxt8lBS4HQ1UmFFIEEKKiKPy8ZnouZErHLsastSpIF6MbkdsypeeTpFl4YcPyHPmOWtNJ7t3REZgOJ6rFyJQsVzcp+MI9oYTGzQLfhEpTscNkSMn3Qxon7ptEyckzD7tuqZ7PDo8SOh7TyU/xOOjBBtcjjQvXutIZrFG4A0XlDitFnnO5NKiPcGdV71+y6YKbbi6/uPChRMbOu525MGD4NqVZpbIrvz1Q4jzw85KLeWnXBGp2yTM7KgSEmbNwxzGWL9BiHyd0zSCXepu2zLXI/UluMOqTYISotrUEO7hHoDzEcRuv5OAQBctDFkrakRGfcTvHLwKnPVljB7KLoi6BHwL0QamE5KMlK9HkZAcG6gb7bwjLrEV6sMPJycmQVp8keu7yZCd3P9BONkNGWdXgCHhqVCXyPTkKbJSjcMUGw4E1eI4UYh5dGiXxjPKg0wEqWiMqXODGCjSK6SDtjnM6ViFVf/Myq1seqiP2lDy72iG/NKhfKQYfUcW5vkYxWeososRtp357foZ0WlOi5bSu9OxR/sHhcOts7Jb9gqsHs9fWeWvf+Rcf8uVP83ZhuTS9U87QVb+cDvDie7PH9ZW5R9Gx3wdGweL2q3HHezTnBdLho1aNOfR4oZ0EbHvbYHJuNYwMtmv+qRWao5Qs6ezMDC38W3aGhv0NW7fa4gbCmdftR7h32ecL/KobbvXCXb2ty/X9/S+Uu7U2eOoqX2p05tpR6GqsspjtbEWP4rr6tg5bTnYsCqVobR1eXnddlOgeGRI2x+VkhdTsPK1rqVs4XZ1aB3L5tAfHVSWg3N19YLaM0FiUPtwIH8V0lCTPgEkfhGxxIeg9ruZnLuwK/AudenD/L3LDeKI=
import { ref } from "vue";
import Feed from "./components/feeds.vue";
const items = ref([
  {
    id: 1,
    title: "Lorem ipsum dolor sit amet, consetetur sadipscing elitr",
    teaser:
      "At vero eos et accusam et justo duo dolores et ea rebum. Stet clita kasd gubergren, no sea takimata sanctus est Lorem ipsum dolor sit amet.",
    numberOfWords: 512,
    image: "https://placecats.com/millie_neo/200/200",
  },
  {
    id: 2,
    title: "At vero eos et accusam et justo duo",
    teaser:
      "Stet clita kasd gubergren, no sea takimata sanctus est Lorem ipsum dolor sit amet. At vero eos et accusam et justo duo dolores et ea rebum. Stet clita kasd gubergren.",
    numberOfWords: 1723,
    image: "https://placecats.com/neo_banana/200/200",
  },
  {
    id: 3,
    title: "Consetetur sadipscing elitr, sed diam nonumy eirmod tempor ",
    teaser:
      "labore et dolore magna aliquyam erat, sed diam voluptua. At vero eos et accusam et justo duo dolores et ea rebum. Stet clita kasd gubergren, no sea takimata sanctus est Lorem ipsum dolor sit amet.",
    numberOfWords: 821,
    image: "https://placecats.com/bella/200/200",
  },
]);
</script>

<template>
  <h1>Newsfeed</h1>

  <div class="box">
    <div class="newsfeed">
      <Feed
        v-for="item in items"
        :image="item.image"
        :title="item.title"
        :teaser="item.teaser"
        :numberOfWords="item.numberOfWords"
      />
    </div>
  </div>
</template>

<style>
body {
  background: #0f172a;
  color: #fff;
  margin: 4rem auto;
  max-width: 620px;
  padding: 20px;
}

.box {
  box-shadow: inset 0 1px 0 0 hsla(0, 0%, 100%, 0.05);
  background: rgb(30 41 59/1);
  border-radius: 5px;
  overflow: hidden;
}

.newsfeed {
  margin: 0;
  padding: 0;
}

.newsfeed__image img {
  display: block;
  width: 100%;
  height: 100%;
  object-fit: cover;
}

.newsfeed__text {
  padding: 20px;
}

.newsfeed__item {
  display: grid;
  grid-template-columns: 200px auto;
}

.newsfeed__heading {
  font-size: 18px;
  margin: 10px 0;
}

.newsfeed__teaser {
  font-size: 15px;
  line-height: 1.25;
}

.newsfeed__meta {
  font-size: 15px;
  line-height: 1.25;
  color: rgba(255, 255, 255, 0.6);
}

.newsfeed__item + .newsfeed__item {
  border-top: 1px solid hsla(0, 0%, 100%, 0.05);
}
</style>
