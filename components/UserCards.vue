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
  /*display: flex;*/
  /*flex-wrap: wrap;*/
  justify-content: center;
  display: grid;
  grid-template-columns: 1fr 1fr 1fr;
  row-gap: 70px;
  /*//max-width: 1200px;*/
  /*margin-block: 2rem;*/
  /*gap: 35px;*/
}

img {
  max-width: 100%;
  height: 210px;
  display: block;
  object-fit: cover;
  object-position: top;
}

.card__body {
  padding: 30px 17px;
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


@media (min-width: 576px) and (max-width: 768px) {
  img {
    height: 250px;
  }
  .card__body {
    padding: 43px 17px;
  }
}

@media (max-width: 768px) {
  .wrapper {
    grid-template-columns: 1fr;
  }
}

@media (min-width: 768px) and (max-width: 1200px) {
  .wrapper {
    grid-template-columns: 1fr 1fr;
  }
}

@media (min-width: 1400px) {
  img {
    height: 250px;
  }
  .card__body {
    padding: 43px 17px;
  }
}


</style>
