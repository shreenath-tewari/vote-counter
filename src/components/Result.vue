<template>
    <div class="container">
        <div class="card">
            <div class="card-header">
                <h2 class="title">Results</h2>
            </div>
            <div class="card-body">
            </div>
            <!--<div class="card-body">-->
                <!--{{ framework.vue }}-->
            <!--</div>-->
            <!--<div class="card-body">-->
                <!--{{ framework.angular }}-->
            <!--</div>-->
            <div class="card-footer">

            </div>
        </div>
    </div>
</template>

<script>
    export default {
        name: "Result",

        data() {
            return {

            }
        },
        created() {
            this.score = this.$route.params.score;
        }
    }
</script>

<style scoped>

</style>