<template>
  <router-link :to="{ name: 'actor', params: { id: actor.id } }">
    <div class="actors-info" v-if="actor">
      <div class="img-style">
        <img v-bind:src="actorImg" v-if="actor.profile_path" />
        <img src="../assets/no-image.jpg" v-else />
      </div>
      <div>
        <div class="actor-name">Name: {{ actor.name }}</div>
        <div class="actor-character">Character: {{ actor.character }}</div>
        <div class="clear"></div>
      </div>
    </div>
  </router-link>
</template>

<script>
import { IMG_W500 } from '@/config';
export default {
  name: 'ActorCard',

  props: ['actor', 'image_url'],
  computed: {
    actorImg: function() {
      return IMG_W500 + this.actor.profile_path;
    }
  }
};
</script>

<style scoped>
.clear {
  clear: both;
}
.actor-name {
  display: block;
  font-size: 18px;
  padding: 20px;
  float: left;
}
.actor-character {
  display: block;
  font-size: 18px;
  float: left;
  padding: 20px;
}
.img-style {
  max-width: 120px;
  width: 100%;
}
</style>
