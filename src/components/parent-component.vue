<template>
    <div style="border:1px solid black; margin: 10px;">
        <h1>Parent Component</h1>
        <div>Bool: <span>{{this.bool}}</span></div>
        <div>Text: <span>{{this.text}}</span></div>
        <child-component
            v-on:toggle-bool="toggleBool" 
            v-on:change-text="changeText"
            />
    </div>
</template>

<script>
import ChildComponent from './child-component';

export default {
    name: 'ParentComponent',
    components: {
        ChildComponent
    },
    data () {
        return {
            bool: false,
            text: ''
        }
    },
    methods: {
        toggleBool () {
            this.bool = !this.bool
        },
        changeText ( val ) {
            this.text = val
        }
    }
}
</script>