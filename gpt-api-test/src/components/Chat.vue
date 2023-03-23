<template>
  <div class="chat-wrapper">
    <div class="message-wrapper reverse">
      <img class="message-pp" v-if="chat.isAi" src="@/assets/bot.svg" alt=""/>
      <img class="message-pp" v-else src="@/assets/user.svg" alt=""/>
      <div class="message-box-wrapper">
        <div class="message-box">
          {{ chat.value }}
        </div>
      </div>
    </div>
  </div>
</template>

<script setup>
import {nextTick, onMounted, ref, watch} from "vue";

defineProps({
  chat: {
    type: Object || null,
  },
});
const currentMessage = ref(null);
onMounted(async () => {
  await nextTick();
  const div = currentMessage.value;
  div.scrollIntoView({behavior: "smooth"});
});
</script>

<style lang="scss" scoped>
</style>