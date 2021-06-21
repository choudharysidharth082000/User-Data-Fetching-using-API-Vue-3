 <template>
<main v-if="!loading" class="containor">  
  
  <div v-for="item in list" v-bind:key="item.id" class="cardcontainor">
    <Header :data=item.name :email= item.email :phone=item.phone :website= item.website :username= item.username />
    <body>
      
  
  
</body>
    
   
  </div>
    
   
 </main>
 <main class="containor" v-else>
   <Loaderspinner />
 </main>

 </template>

<script>

import Header from './components/Header.vue'
import Loaderspinner from './components/Loaderspinner.vue'

 

export default {
  name: 'App',
  components: {
     Header, 
     Loaderspinner,
     
  },
  data()
  {
    return{
      loading : true,
      list: undefined,
      list1: undefined
    }

  },

  methods:
  {
    async fetchuserdata() //fetching the api data
    {
      const res = await fetch('https://jsonplaceholder.typicode.com/users');
      const data = await res.json();
      return data;
    },
    

  }, 
  async created()  // lifecycle method to create the certain things and printing it 
  {
    
    const data = await this.fetchuserdata();    
    this.list = data;
    
    
    this.loading = false;
    
  }
}
</script>

<style>
*
{
  margin: 0;
  padding: 0;
  box-sizing: border-box;

}

.containor

{
  
  height: 100%;
  width: 100%;
  display: flex;
  justify-content: center;

  align-content: center;
  flex-wrap: wrap;
}

</style>