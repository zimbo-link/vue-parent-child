<template>
    <div style="border:1px solid black; margin: 10px;">
        <h3>Child Component </h3>
        <div>
            <button @click="toggleBookmark">change bool</button>
        </div>
        <div>
            <p>
                <input v-on:keyup="changeText($event.target.value)" type="text" name="display" value="">
            </p>
        </div>
    </div>
</template>

<script>
export default {
    name: 'ChildComponent',
    props: {

    },
    data () {
        return {
            text: ''
        }
    },
    methods: {
        toggleBookmark () {
            this.$emit('toggle-bool');
        },
        changeText (val) {
 
            this.$emit('change-text', val);
        }
    }
};
</script>