<template>
    <div class="row q-pt-lg">
        <div class="col flex flex-center">
            <q-img width="50px" :src="image"></q-img>
            <spaan class="text-h3 q-pt-md q-pb-md">
                {{ name }} - {{ symbol }}
            </spaan>
        </div>
    </div>
</template>

<script>
    export default {
       name:"CryptoDetailsHeader",
       props:{
        image:{
          type: String,
          required:true
        },
        name:{
          type: String,
          required:true
        },
        symbol:{
          type: String,
          required:true
        }
       } 
    }
</script>

