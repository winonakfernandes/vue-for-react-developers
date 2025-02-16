<script setup>
import Button from "../generic/form/Button.vue";
import { defineEmits } from "vue";

const emit = defineEmits(["select-emoji"]);

// List of available emojis
const emojis = ["shrug", "octopus", "mushroom", "fire", "tent"];

/**
 * Sends an emoji as a message
 * @param {String} emoji - The selected emoji
 */

 function sendEmoji(emoji) {
    emit("select-emoji", emoji);
}
</script>

<template>
  <div class="emoji-picker">
    <Button
      v-for="emoji in emojis"
      :key="emoji"
      :icon="emoji"
      @click="sendEmoji(emoji)"
    />
  </div>
</template>
