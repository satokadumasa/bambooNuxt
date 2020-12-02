<template>
  <div class="modal__overlay">
    <div class="modal__window">
      <div class="modal__content">
        <div class="container detail_table">
          <div class="row ">
            <div class="col-4 detail_label">
              ID
            </div>
            <div class="col-8 detail_val">
              {{modalData.id}}
            </div>
          </div>
          <div class="row">
            <div class="col-4 detail_label">
              username
            </div>
            <div class="col-8 detail_val">
              {{modalData.username}}
            </div>
          </div>
          <div class="row">
            <div class="col-4 detail_label">
              email
            </div>
            <div class="col-8 detail_val">
              {{modalData.email}}
            </div>
          </div>
        </div>
        <button @click="$emit('close')">閉じる</button>
      </div>
    </div>
  </div>
</template>
<script>
export default {
  name: 'UserDetailModal',
  props: ["modalData"],
}
</script>
export default {
  name:
}
<style lang="scss" scoped>
.modal {
  &__overlay {
    display: flex;
    align-items: center;
    justify-content: center;
    position: fixed;
    z-index: 100;
    top: 0;
    left: 0;
    height: 100%;
    width: 100%;
    background: rgba(255, 255, 255, 0.4);
  }

  &__window {
    height: 40%;
    width: 70%;
    overflow: hidden;
    background-color: white;
  }

  &__content {
    height: 100%;
    padding: 30px;
  }
}

// transition
.modal-enter-active,
.modal-leave-active {
  transition: opacity 0.4s;
  .modal__window {
    transition: opacity 0.4s, transform 0.4s;
  }
}
.modal-leave-active {
  transition: opacity 0.6s ease 0.4s;
}
.modal-enter,
.modal-leave-to {
  opacity: 0;
  .modal__window {
    opacity: 0;
    transform: translateY(-20px);
  }
}
</style>
