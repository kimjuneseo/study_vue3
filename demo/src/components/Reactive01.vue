<template lang="">
    <div>
        
        <button @click="handleBtn">
            Reactive {{count}}
        </button>
        <button @click="handleDebounceBtn">
            de {{count}}
        </button>
    </div>
</template>
<script>
import { debounce } from 'lodash-es'
import { nextTick } from 'vue'
export default {
    name: 'Reactive',
    data(){
        return {
            count: 0
        }
    },
    methods: {
        handleBtn() {
            this.count++;
            // console.log(document.querySelector('button').innerText = "11");
            nextTick(() => {
                // console.log(document.querySelector('button').innerText = "112");
            })
        },
        handleDebounceBtn: debounce(function() {
            this.count++;
            
        }, 500)
    }
}
</script>
<style lang="">
    
</style>