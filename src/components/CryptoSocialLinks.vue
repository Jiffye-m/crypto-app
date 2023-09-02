<template>
    <div class="row q-pt-lg">
       <div class="col flex flex-center">

        <q-btn
        v-if="facebookUserName"
        type="a"
        color="primary"
        class="q-mr-md"
        :href="`https://facebook.com/${facebookUserName}`"
        target="_blank"
        >
        <q-icon class="q-pr-sm" name="mdi-facebook"></q-icon>
        Facebook
        </q-btn>


        <q-btn
        v-if="twitterUserName"
        type="a"
        color="blue"
        class="q-mr-md"
        :href="`https://twitter.com/${twitterUserName}`"
        target="_blank"
        >
        <q-icon class="q-pr-sm" name="mdi-twitter"></q-icon>
        Twitter
        </q-btn>

        <q-btn
        v-if="redditUserName"
        type="a"
        color="black"
        class="q-mr-md" 
        :href="`https://reddit.com/${redditUserName}`"
        target="_blank"
        >
        <q-icon class="q-pr-sm" name="mdi-reddit"></q-icon>
        Reddit
        </q-btn>

       </div>
    </div>
</template>

<script>
    export default {
        name:"CryptoSocialLinks",
        props:{
            facebookUserName:{
                type: String,
                required: true
            },
            twitterUserName:{
                type: String,
                required: true
            },
            redditUserName:{
                type: String,
                required: true
            }
        } 
    }
</script>

<style lang="scss" scoped>

</style>