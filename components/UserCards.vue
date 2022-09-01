<template>
  <div>
    <div class="wrapper">
      <card v-for="user in users" :key="user._id">
        <div class="card__header">
          <img v-bind:src="user.picture" @click="showModal" alt="card__image" class="card__image" width="600" />
        </div>
        <div class="card__body">
          <p><span class="muted">name:</span> {{ user.name }}</p>
          <p><span class="muted">email:</span> {{ user.email }}</p>
        </div>
      </card>
    </div>
    <Modal
      v-show="isModalVisible"
      @close="closeModal"
    />
  </div>
</template>

<script>
import Card from '@/components/Card.vue'
import Modal from '@/components/Modal.vue';

export default {
  name: 'Users',
  props: {
    users: {
      type: Array,
      required: true
    }
  },
  components: {
    Card,
    Modal
  },
  data() {
    return {
      isModalVisible: false,
    };
  },
  methods: {
    showModal() {
      this.isModalVisible = true;
    },
    closeModal() {
      this.isModalVisible = false;
    }
  }
}
</script>

<style scoped>
.wrapper {
  font-family: Roboto, sans-serif;
  display: flex;
  flex-wrap: wrap;
  justify-content: center;
  /*//max-width: 1200px;*/
  margin-block: 2rem;
  gap: 2rem;
}

img {
  max-width: 100%;
  height: clamp(20rem, calc(15rem + 2vw), 22rem);
  display: block;
  object-fit: cover;
  object-position: top;
}

.card__body {
  padding: 43px 17px;
  /*display: flex;*/
  /*flex-direction: column;*/
  /*gap: .5rem;*/
}

.card__body h4 {
  font-size: 1.5rem;
  text-transform: capitalize;
}

.card__body .muted {
  color: #BDBDBD;
  font-family: Roboto, sans-serif;
  font-weight: 700;
}

.card__footer {
  display: flex;
  padding: 1rem;
  margin-top: auto;
}
</style>
