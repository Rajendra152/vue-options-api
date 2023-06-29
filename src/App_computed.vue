<script>

export default {
    name: "App",
    data(){
        return{
            firstName: "Rajendra",
            lastName: "Prasad",
            items: [
                {
                    id: 1,
                    title: 'TV',
                    price: 100,
                },
                {
                    id: 2,
                    title: 'Phone',
                    price: 200,
                },
                {
                    id: 3,
                    title: 'Laptop',
                    price: 300,
                },
                ],
                country: '',
        }
    },
    methods:{
      getTotal() {
      console.log('getTotal method')
      return this.items.reduce((total, curr) => (total = total + curr.price), 0)
    },
    changeFullName() {
      this.fullName = 'Sachin koppad'
    },
    },
    computed: {
        // fullName(){
        //     return `${this.firstName} ${this.lastName}`
        // },
        fullName: {
        get() {
            return `${this.firstName} ${this.lastName}`
        },
        set(value) {
            const names = value.split(' ')
            this.firstName = names[0]
            this.lastName = names[1]
        },
        },
        total(){
            console.log('total computed property');
            return this.items.reduce((total,curr) => (total = total + curr.price),0)
        },
        expensiveItems() {
        return this.items.filter((item) => item.price > 100)
    },
    }
}

</script>

<template>
<div>
<h2>Full Name - {{firstName}}{{ lastName }}</h2>
<h2>Computed Name - {{ fullName }}</h2>
<button @click="items.push({ id: 4, title: 'Keyboard', price: 50 })">
    Add item
  </button>
<h2>Total - {{ items.reduce((total,curr) => (total = total + curr.price),0)}} </h2>
<h2>Computed total - {{total}}</h2>
 <h2>Method Total - {{ getTotal() }}</h2>
  <div>
    <input type="text" v-model="country" />
  </div>

<template v-for="item in items" :key="item.id">
    <h2 v-if="item.price > 100">{{ item.title }} - {{ item.price }}</h2>
  </template>

 <h2 v-for="item in expensiveItems" :key="item.id">
    {{ item.title }} - {{ item.price }}
  </h2>

  <button @click="changeFullName">Change fullname</button>
</div>
</template>

<style>

</style>