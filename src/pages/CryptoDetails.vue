<template>
    <q-page padding>
    <div v-if="details">

    <CryptoDetailsHeader 
    :image="details.image.small"
    :name="details.name"
    :symbol="details.symbol"
    />


    <CryptoSocialLinks 
    :facebookUserName="details.links.facebook_username"
    :twitterUserName="details.links.twitter_screen_name"
    :redditUserName="details.links.subreddit_url"
    />


    <div class="row q-pt-lg">
        <div class="col">
            <p v-html="details.description.en"></p>
        </div>
    </div>


    <div class="row">
        <div class="col">
            <h4>Exchanges</h4>
        </div>
    </div>

    <div class="row">
        <div class="col-md-4 col-sm-6 col-ms-12" v-for="(ticker, index) in usdTickers" :key="index">
        <CryptoExchangeCard 
        :ticker="ticker"
        :changeInLast24Hr="details.market_data.price_change_24h"
        />
        </div>
    </div>

    </div>
    </q-page>
</template>

<script>
import axios from 'axios'
import CryptoDetailsHeader from 'src/components/CryptoDetailsHeader.vue'
import CryptoSocialLinks from 'src/components/CryptoSocialLinks.vue'
import CryptoExchangeCard from 'src/components/CryptoExchangeCard.vue'
export default{
    components:{
        CryptoDetailsHeader,
        CryptoSocialLinks,
        CryptoExchangeCard
    },
    data(){
        return{
            details: undefined
        }
    },
    computed:{
        usdTickers(){
            return this.details.tickers.filter((ticker) => ticker.target === "USD") 
        }
    },
    async created(){

        const id = this.$route.params.id

        await axios.get(`https://api.coingecko.com/api/v3/coins/${id}`)
   .then(res => {
    if(!id){
        alert("No ID specified!! Please try again")
    }
    if(res.status === 200){
        this.details = res.data
    } else{
        alert("There was an error fetching Coin")
    }

    })
}}

</script>

<style>

</style>