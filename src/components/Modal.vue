<template>
  <teleport to=".modals-container">
    <div class="modal">
      <h1>
        {{ title }}
        {{ subTitle }}
      </h1>
      <slot />

      <button @click="$emit('hideModal')">Hide modal 1</button>
      <button @click="handleButtonClick">Hide modal 2</button>
    </div>
  </teleport>
</template>

<script setup>
/*
  props
*/

const props = defineProps({
  title: {
    type: String,
    default: "No title specified",
  },
  subTitle: {
    type: String,
    default: "No subType specified",
  },
});

console.log(props.title, props.subTitle);

/*
  emits
*/

const emit = defineEmits(["hideModal"]);

/*
  handle button click
*/

const handleButtonClick = () => {
  emit("hideModal");
};
</script>

<!--
<script>
export default {
  emits: ["hideModal"],
  props: {
    title: {
      type: String,
      default: "No title specified",
    },
    subTitle: {
      type: String,
      default: "No subType specified",
    },
  },
};
</script>
-->

<style>
.modal {
  background: beige;
  padding: 10px;
  position: absolute;
  left: 0;
  top: 0;
  width: 100%;
  height: 100%;
  z-index: 1;
}
</style>
