<template>
  <div class="modals">
    <h1>Modals</h1>
    <div>
      <label
        >Show dark modals?
        <input type="checkbox" v-model="showDarkModal" />
      </label>
    </div>
    <button @click="showModal = true">Show modal</button>

    <component
      v-model="showModal"
      :is="showDarkModals ? ModalDark : Modal"
      title="My modal title (via props)"
      subTitle="My subTitle (via props)"
    >
      <p>
        Loren ipsum color dfdf afdfaf afss asfa fa sdbskdbfs<br />
        is a unique code or identifier that is assigned to each tenant in a
        multi-tenant system or application. In a multi-tenant architecture, a
        single instance of the software or service serves multiple clients or
        tenants, keeping their data and configurations separate to ensure
        privacy and data isolation. This is required to identify the API calls
        related to a specific tenant in the logs for monitoring and
        troubleshooting
      </p>
    </component>
  </div>
</template>

<script setup>
/*
    imports
*/

import { ref } from "vue";
import Modal from "@/components/Modal.vue";
import ModalDark from "@/components/ModalDark.vue";

/*
    modals
*/

const showDarkModals = ref(false);
const showModal = ref(false);
</script>

<!--
<script>
import Modal from "@/components/Modal.vue";
export default {
  components: {
    Modal,
  },
};
</script>
-->
