<template>
    <q-card class="q-ms-md q-pa-sm">
       <q-card-section>

        <div class="text-h4">{{ ticker.market.name }}</div>
       <div class="text-h6">
        Trust: <q-avatar size="sm" :color="ticker.trust_score"></q-avatar>
       </div>
       
       </q-card-section>

       <q-seperator></q-seperator>

       <q-card-section>

        <div class="colimn flex flex-center">
            <div class="text-h4">
                <q-icon :name="changeInLast24Hr > 0 ? 'trending_up' : 'trending_down'"
                    :color="changeInLast24Hr > 0 ? 'green' : 'red'"
                    size="24px"
                    />
                    ${{ ticker.last }}
            </div>
            <div class="text-h5 q-pt-md">
                Volume: {{ ticker.volume.toFixed(2) }}
            </div>
        </div>

       </q-card-section>


       <q-card-actions>
        <q-btn
        type="a"
        class="flex flex-center"
        color="primary"
        size="lg"
        :href="ticker.trade_url"
        target="__blank"
        >
        Trade
        </q-btn>
       </q-card-actions>

    </q-card>
</template>

<script>
    export default {
        name: "CryptoExchangeCard",
        props:{
           ticker:{
            type:Object,
            required:true
           },
           changeInLast24Hr:{
            type:Number,
            required:true
           }  
        }
    }
</script>

<style lang="scss" scoped>

</style>