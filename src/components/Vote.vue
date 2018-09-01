<template>
    <div class="container">
        <h3>Choose the JavaScript Library/Framework of your Choice</h3>
        <form @submit.prevent="castVote">
            <input type="radio" value="react" v-model="framework"> React.js
            <br>
            <input type="radio" value="vue" v-model="framework"> Vue.js
            <br>
            <input type="radio" value="angular" v-model="framework"> Angular
            <br>
            <input type="submit">
        </form>
        {{ react }}<br>
        {{ vue }}<br>
        {{ angular }}
    </div>
</template>

<script>
    export default {
        name: "Vote",
        data() {
            return {
                framework: '',
                react: 0,
                angular: 0,
                vue: 0
            }
        },
        methods: {
            castVote() {
                if(this.framework == "react") {
                    this.react++;
                }
                if(this.framework == "vue") {
                    this.vue++;
                }
                if(this.framework == "angular") {
                    this.angular++;
                }
            }
        }
    }
</script>

<style scoped>

</style>