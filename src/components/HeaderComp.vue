<template>
    <header>
        <div class="container-fluid">
            <div class="row">
                <div class="col-12">
                    <div class="SpfLogo p-2">
                        <img src="https://www.geekslab.it/wp-content/uploads/2019/03/logo-spotify.png" alt="" class="w-50">
                    </div>
                </div>
            </div>
        </div>
    </header>
    
  
</template>

<script>
export default {
    name:'HeaderComp',
    props:{
        GenExit: Array
    },
    data(){
        return {
            GenSelected:''
        }
    }
}
</script>

<style lang="scss" scoped>

header{
    background-color:#2E3A46;
}

.SpfLogo{
    width: 5%;
}
    
</style>