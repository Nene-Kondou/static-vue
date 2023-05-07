<template>
    <div class="card alert-primary">
        <div class="card-body text-left">
            <h2 class="card-title text-center">{{ title }}</h2>
            <p class="card-text h5">{{ message }}</p>
            <hr>
            <div>
                <div class="form-group">
                    <label>Formula:</label>
                    <textarea cols="30" rows="10" class="form-control mb-2" v-model="fomula"></textarea>
                </div>
                <div class="text-center">
                    <button class="btn btn-primary" v-on:click="doAction">CALC</button>
                </div>
            </div>
        </div>
    </div>
</template>

<script>
export default {
    name: 'Calc',
    props: {
        title: String,
    },
    data() {
        return {
            message: 'Enter expression:',
            fomula: '0',
        }
    },
    methods: {
        doAction() {
            let arr = this.fomula.trim().split('\n') // 1
            let last = arr.pop() // 2
            let fn = ''
            for ( let n in arr ) { // 3
                if ( arr[n].trim() != '' ) { // 4
                    fn += 'let ' + arr[n] + ';'
                    
                }
            }
            fn += 'return ' + last + ';' // 5
            let exp = 'function f() {' + fn + '} f();' // 6
            let ans = eval(exp) // 7
            this.message = 'answer: ' + ans // 8
            let re = arr.join(';').trim() // 9
            if ( re != '' ) { re += ';' } // 10
            re += last
            this.$emit( 'result-event', re, ans ) // 11
        }
    },
}
</script>