<template>
  <teleport to=".modals-container">
    <div v-if="modelValue" class="modal">
      <h1>
        {{ title }}
        {{ subTitle }}
      </h1>
      <slot />

      <button @click="$emit('update:modelValue', false)">Hide modal 1</button>
    </div>
  </teleport>
</template>

<script setup>
/*
  props
*/

const props = defineProps({
  modelValue: {
    type: Boolean,
    default: false,
  },
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

const emit = defineEmits(["update:modelValue", "hideModal"]);

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
