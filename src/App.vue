<template>
  <div id="app" style="margin-top: 0px;">
    <navbar text="Vue-Recipes"></navbar>
    <button class="btn btn_success" @click="isnew = !isnew"> show</button>
    <RacityForm v-if="isnew" @savereceipt="getdata"></RacityForm>

    <input type="text" class="form-control" v-model="searchText">

    <ul>
      <li v-for="(receipt,index) in filterList" :key="index + receipt.title">
        {{ receipt }}
      </li>
    </ul>
  </div>
</template>

<script>
import navbar from './components/Navbar.vue'
import RacityForm from './components/RacityForm.vue'

export default {
  name: 'app',
  components: {
    navbar, RacityForm
  },
  data () {
    return {
      receipts: [],
      isnew : false,
      searchText : ""
    }
  },
  computed:{
    filterList() {
      return this.receipts.filter(receipt => {
        return  receipt.title.toLowerCase().indexOf(this.searchText.toLowerCase()
        ) > -1
      })
    }

  },
  methods: {
    setlocalStorage (){
      localStorage.setItem('receipts',JSON.stringify(this.receipts))
    },
    getdata (receipt) {
      this.receipts.push(receipt)
      this.setlocalStorage()
      this.isnew = false
    }
  }
}
</script>

<style scoped[]>
#app {
  font-family: "Avenir", Helvetica, Arial, sans-serif;
  -webkit-font-smoothing: antialiased;
  -moz-osx-font-smoothing: grayscale;
  text-align: center;
  color: #2c3e50;
  margin-top: 60px;
}
</style>
