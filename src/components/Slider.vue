<template>
  <div>
    <carousel  class="slider"
               :per-page="1"
               :autoplay="true"
               :autoplayTimeout="5000"
               :autoplayHoverPause="true"
               :paginationEnabled="false">
      <slide class="slider-item" v-for="(movie, index) in popular" :key="index">
        <img :src="'https://image.tmdb.org/t/p/original/' + movie.backdrop_path" alt="">

        <article class="slider-desc">
          <div class="container">
            <h2>{{movie.title}}</h2>
            <p class="desc">{{movie.overview}}</p>
          </div>

        </article>
      </slide>
    </carousel>
  </div>
</template>

<script>
export default {
  name: "Slider",
  props: ['popular'],
  mounted() {
    console.log(1.1);
  }
}
</script>

<style lang="scss" scoped>

  .slider{
    position: relative;

    .slider-item{
      position: relative;
      max-height: 450px;
      .slider-desc{
        background: $black;
        background: -moz-linear-gradient(top,  rgba($white,0) 0%, rgba($black,1) 100%);
        background: -webkit-linear-gradient(top,  rgba($white,0) 0%,rgba($black,1) 100%);
        background: linear-gradient(to bottom,  rgba($white,0) 0%,rgba($black,1) 100%);
        position: absolute;
        left: 0;
        right: 0;
        bottom: 0;
        color: $white;
        padding: 10px 0;
        .desc{
          line-height: 1.5;
          font-size: 16px;
          @include media(desktop){
            font-size: 14px;
            line-height: 1.2;
          }
          @include media(table){
            font-size: 12px;
          }
          @include media(mobile){
            display: none;
          }
        }
      }
    }
  }
</style>