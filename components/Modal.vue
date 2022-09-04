<script>

export default {
  name: 'Modal',
  props: {
    user: {
      type: Object,
      required: true
    }
  },
  methods: {
    close() {
      this.$emit('close');
      console.log(this.user);
    },
  },
};
</script>

<template>
  <transition name="modal-fade">
    <div class="modal-backdrop">
      <div class="modal"
           role="dialog"
           aria-labelledby="modalTitle"
           aria-describedby="modalDescription"
      >
        <div
          class="modal__header"
          id="modalTitle"
        >
          <span
            class="modal__btn-close"
            @click="close"
            aria-label="Close modal"
          ></span>
          <img v-bind:src="user.picture" alt="modal__image" class="modal__image" width="600" />
        </div>

        <div
          class="modal__body"
          id="modalDescription"
        >
          <p><span class="muted">name: </span>{{ user.name }}</p>
          <p><span class="muted">age: </span>{{ user.age }}</p>
          <p><span class="muted">email: </span>{{ user.email }}</p>
          <p><span class="muted">phone: </span>{{ user.phone }}</p>
          <p style="display: flex"><span class="muted">about:&nbsp;</span><span class="big" style="display: inline-block">{{ user.about }}</span></p>
        </div>
      </div>
    </div>
  </transition>
</template>

<style>
.modal-backdrop {
  position: fixed;
  top: 0;
  bottom: 0;
  left: 0;
  right: 0;
  background-color: rgba(0, 0, 0, 0.3);
  display: flex;
  justify-content: center;
  align-items: center;
}

.modal {
  display: flex;
  flex-direction: column;
  /*width: 320px;*/
  width: 800px;
  box-shadow: 0px 4px 10px 3px #94949440;
  border-radius: 20px;
  background: white;
}

.modal__image {
  width: 100%;
  height: 480px;
  border-radius: 20px 20px 0 0;
  display: block;
  object-fit: cover;
  object-position: top;
}

.modal__body {
  padding: 30px 17px;
}

.modal__body .muted {
  color: #BDBDBD;
  font-family: Roboto, sans-serif;
  font-weight: 700;
}

.modal__btn-close {
  margin-bottom: -60px;
  padding: 14px;
  border: 0;
  background: #EB5757;
  border-radius: 20px;
  position: relative;
  width: 32px;
  height: 32px;
  display: block;
  bottom: 30px;
  left: 770px;
}

.modal__btn-close:before, .modal__btn-close:after {
  content: "";
  position: absolute;
  top: 30.5px;
  left: 10px;
  right: 0;
  height: 1px;
  background: #fff;
  border-radius: 1px;
  width: 40px;
}

.modal__btn-close:before {
  transform: rotate(45deg);
}

.modal__btn-close:after {
  transform: rotate(-45deg);
}

.modal-fade-enter,
.modal-fade-leave-to {
  opacity: 0;
}

.modal-fade-enter-active,
.modal-fade-leave-active {
  transition: opacity .5s ease;
}

@media screen and (max-width: 576px) {
  .modal {
    width: 300px;
    font-size: 14px;
  }
  .modal__btn-close {
    left: 270px;
  }
  .modal__image {
    height: 180px;
  }
}

@media (min-width: 576px) and (max-width: 768px) {
  .modal {
    width: 400px;
  }
  .modal__btn-close {
    left: 370px;
  }
  .modal__image {
    height: 280px;
  }
}

@media (min-width: 768px) and (max-width: 1200px) {
  .modal {
    width: 600px;
  }
  .modal__btn-close {
    left: 570px;
  }
  .modal__image {
    height: 380px;
  }
}

</style>
