<template>

  <div class="container">
    <div class="row">
      <div class="col-12">
        <div class="title">
          User List
        </div>
      </div>
    </div>
    <div class="row">
      <div class="col-2 col-sm-2 col-md-2 col-xl-2">
        ID
      </div>
      <div class="col-4 col-sm-4 col-md-4 col-xl-4">
        Name
      </div>
      <div class="col-4 col-sm-4 col-md-4 col-xl-4">
        email
      </div>
      <div class="col-2 col-sm-2 col-md-2 col-xl-2">
        Detail
      </div>
    </div>

    <div class="row" v-for="(item, index) in user_list">
      <div class="col-2 col-sm-2 col-md-2 col-xl-2">
        {{item.id}}
      </div>
      <div class="col-4 col-sm-4 col-md-4 col-xl-4">
        {{item.username}}
      </div>
      <div class="col-4 col-sm-4 col-md-4 col-xl-4">
        {{item.email}}
      </div>
      <div class="col-2 col-sm-2 col-md-2 col-xl-2">
        <button class="btn btn-primary" v-on:click="openModal">
          Detail
        </button>
      </div>
    </div>
    <Modal v-if="modalFlag">
      <div>モーダルの内容</div>
      <div>モーダルの内容</div>
      <div>モーダルの内容</div>
      <div>モーダルの内容</div>
      <div>モーダルの内容</div>
      <button @click="closeModal">閉じる</button>
    </Modal>
  </div>
</template>

<script>
import Vue from 'vue'
import Modal from '~/components/Modal.vue'

export default {
  components: {
    Modal
  },
  data() {
    return {
      user_list: [],
      modalFlag: false
    }
  },
  mounted(){
    init(this);
  },
  methods: {
    detail() {
      alert('detail');
    },
    openModal() {
      this.modalFlag = true
    },
    closeModal() {
      this.modalFlag = false
    },
  }
}

async function init(self){
  console.log(self);
  const data = {};
  self.$axios.post('/api/users/list', data)
    .then(response => {
        console.log('success!');
        console.log(response);
        self.user_list = response.data.users;
    }).catch(() => {
        console.log('Failed');
    }).then(() => {
        console.log('Complete!');
    });
}
</script>

<style>

.title {
  font-family:
    'Quicksand',
    'Source Sans Pro',
    -apple-system,
    BlinkMacSystemFont,
    'Segoe UI',
    Roboto,
    'Helvetica Neue',
    Arial,
    sans-serif;
  display: block;
  font-weight: 300;
  font-size: 1.75em;
  color: #35495e;
  letter-spacing: 1px;
}

.subtitle {
  font-weight: 300;
  font-size: 42px;
  color: #526488;
  word-spacing: 5px;
  padding-bottom: 15px;
}

.links {
  padding-top: 15px;
}
</style>
