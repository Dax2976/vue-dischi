<template>
    <main>
        <section v-if="!loading">
        <div class="container pt-4">
            <div class="row text-center justify-content-between">
                <AlbumComp :song="item" v-for="(item, index) in songs" :key="index" class="w18"/>
            </div>
        </div>
        </section>
            <div class="d-flex min-vh-100 align-item-center justify-content-center" v-else>
                <div class="lds-roller"><div></div><div></div><div></div><div></div><div></div><div></div><div></div><div></div></div>
            </div>
    </main>
    
        
    
  
</template>

<script>
import AlbumComp from '@/components/AlbumComp.vue'
import axios from 'axios'
export default {
    name:'MainComp',
    components:{
        AlbumComp
    },
    data(){
        return{
            songs:[],
            loading: true,
            error: false
        }
    },
    mounted(){
        let timeStart = Date.now()
        axios.get('https://flynn.boolean.careers/exercises/api/array/music').then((response)  => {
            this.songs = response.data.response;

            let timeEnd = Date.now();
            let timeToEndAnimation = (1 * 1000) - (timeEnd - timeStart);

            setTimeout(() => {
                this.loading = false
            }, timeToEndAnimation > 0 ? timeToEndAnimation : 1)
            
        })
        .catch(error =>{
            console.log(error)
            this.error = `Sorry This Page is UnderMaintace ${error}`
        })
    }
}
</script>

<style lang="scss" scoped>
    .w18{
        width: 18%;
    }

.lds-roller {
  display: inline-block;
  position: relative;
  width: 80px;
  height: 80px;
}
.lds-roller div {
  animation: lds-roller 1.2s cubic-bezier(0.5, 0, 0.5, 1) infinite;
  transform-origin: 40px 40px;
}
.lds-roller div:after {
  content: " ";
  display: block;
  position: absolute;
  width: 7px;
  height: 7px;
  border-radius: 50%;
  background: #fff;
  margin: -4px 0 0 -4px;
}
.lds-roller div:nth-child(1) {
  animation-delay: -0.036s;
}
.lds-roller div:nth-child(1):after {
  top: 63px;
  left: 63px;
}
.lds-roller div:nth-child(2) {
  animation-delay: -0.072s;
}
.lds-roller div:nth-child(2):after {
  top: 68px;
  left: 56px;
}
.lds-roller div:nth-child(3) {
  animation-delay: -0.108s;
}
.lds-roller div:nth-child(3):after {
  top: 71px;
  left: 48px;
}
.lds-roller div:nth-child(4) {
  animation-delay: -0.144s;
}
.lds-roller div:nth-child(4):after {
  top: 72px;
  left: 40px;
}
.lds-roller div:nth-child(5) {
  animation-delay: -0.18s;
}
.lds-roller div:nth-child(5):after {
  top: 71px;
  left: 32px;
}
.lds-roller div:nth-child(6) {
  animation-delay: -0.216s;
}
.lds-roller div:nth-child(6):after {
  top: 68px;
  left: 24px;
}
.lds-roller div:nth-child(7) {
  animation-delay: -0.252s;
}
.lds-roller div:nth-child(7):after {
  top: 63px;
  left: 17px;
}
.lds-roller div:nth-child(8) {
  animation-delay: -0.288s;
}
.lds-roller div:nth-child(8):after {
  top: 56px;
  left: 12px;
}
@keyframes lds-roller {
  0% {
    transform: rotate(0deg);
  }
  100% {
    transform: rotate(360deg);
  }
}

</style>