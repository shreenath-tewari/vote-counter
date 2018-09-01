<template>
    <div class="container">
        <div class="card" v-bind:style="{ display: displayVote }">
            <div class="card-header">
                <h2 class="title">Choose the JavaScript Library/Framework of your Choice</h2>
            </div>
            <form class="form-horizontal form" @submit.prevent="castVote">
                <div class="card-body">
                    <div class="form-group">
                        <input class="form-control-md" type="radio" value="react" v-model="framework"> React.js
                    </div>
                </div>
                <div class="card-body">
                    <div class="form-group">
                        <input class="form-control-md" type="radio" value="vue" v-model="framework"> Vue.js
                    </div>
                </div>
                <div class="card-body">
                    <div class="form-group">
                        <input class="form-control-md" type="radio" value="angular" v-model="framework"> Angular
                    </div>
                </div>
                <div class="card-footer">
                    <div class="row">
                        <div class="col-md-4">
                            <input class="btn btn-success" type="submit">
                        </div>
                        <div class="col-md-4">
                            <button class="btn btn-danger" type="reset">Reset</button>
                        </div>
                        <div class="col-md-4">
                            <button class="btn btn-primary" v-on:click="showResult">Result</button>
                        </div>
                    </div>
                </div>
            </form>
        </div>
        <div class="card" v-bind:style="{ display: displayResult }">
            <div class="card-header">
                <h2 class="title">Results</h2>
            </div>
            <div class="card-body score">
                <h4>React.js: <b>{{ react }}</b></h4>
            </div>
            <div class="card-body score">
                <h4>Vue.js: <b>{{ vue }}</b></h4>
            </div>
            <div class="card-body score">
                <h4>Angular: <b>{{ angular }}</b></h4>
            </div>
            <div class="card-footer">
                <div class="row">
                    <div class="col-md-6">
                        <button class="btn btn-success" v-on:click="showVote">Back to Vote</button>
                    </div>
                    <div class="col-md-6">
                        <button class="btn btn-danger" v-on:click="resetVote">Reset Votes</button>
                    </div>
                </div>
            </div>
        </div>
    </div>
</template>

<script>
    export default {
        name: "Vote",
        data() {
            return {
                displayVote: 'block',
                displayResult: 'none',
                framework: '',
                frameworks: [
                    { "framework": "React.js" },
                    { "framework": "Vue.js" },
                    { "framework": "Angular" },
                ],
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
                this.framework = '';
            },
            showResult() {
                this.displayVote = 'none';
                this.displayResult = 'block';
            },
            showVote() {
                this.displayVote = "block";
                this.displayResult = "none";
            },
            resetVote() {
                this.react = 0;
                this.vue = 0;
                this.angular = 0;
                this.displayVote = "block";
                this.displayResult = "none";
            }
        }
    }
</script>

<style scoped>

    .form-group {
        text-align: left;
    }

    .title {
        text-align: left;
    }

    .score {
        text-align: left;
    }
</style>