<template>
    <div>
        <ul>
            <li  :class="{active: aunt === index && aunt !== ''}" v-for="(item,index) in list" :key='index' @click="chose(index)">
                {{item}}
            </li>
        </ul>
        <button @click="add()">copy</button>
        <ul>
            <li v-for="(item,index) in num" :key='index'>{{item}}</li>
        </ul>
    </div>
</template>

<script>
    export default {
        name: 'list',
        data () {
            return {
                list: [1,2,3,4,5,6,7,8],
                aunt: '',
                num:[]
            }
        },
        methods: {
            chose (index) {
                console.log(index);
                this.aunt = index;
            },
            add () {
                if (this.aunt !== '') {
                    this.num.push(this.list[this.aunt]);
                    this.aunt = '';
                }
            }
        }
    }
</script>

<style lang="scss">
    .active{
        background-color: aquamarine;
    }
</style>
