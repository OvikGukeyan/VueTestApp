<template >
    <select :value="modelValue" @change="changeOption">
        <option disabled value="">Select filter</option>
        <option 
            v-for="option in options" 
            :key="option.value" 
            :value="option.value"
        >
            {{ option.name }}
        </option>
    </select>
</template>
<script>
export default {
    name: 'my-select',
    props: {
        modelValue: {
            type: String,
        },
        options: {
            type: Array,
            default: () => []

        },
    },
    methods: {
        changeOption(event) {
            console.log(event.target.value)
            this.$emit('update:modelValue', event.target.value);
        }
    }
}
</script>
<style lang="">
    
</style>