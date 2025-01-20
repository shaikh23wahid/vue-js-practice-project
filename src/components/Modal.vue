<template>
  <teleport to=".modals-container">
    <div class="modal">
      <h1>This is a modal</h1>
      <p>Loren ipsum color dfdf afdfaf afss asfa fa sdbskdbfs</p>
      <button>Hide modal</button>
    </div>
  </teleport>
</template>

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
