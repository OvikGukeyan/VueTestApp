<template>
    <div class="my-dialog" v-if="show" @click="hideDialog">
        <div @click.stop class="content">
            <slot>

            </slot>
        </div>

    </div>
</template>

<script>
export default {
    name: 'my-dialog',
    props: {
        show: {
            type: Boolean,
            default: false
        }
    },

    methods: { 
        hideDialog() {
            this.$emit('update:show', false)
        }
    }
}

</script>

<style>
.my-dialog {

    width: 100%;
    height: 100%;
    position: absolute;
    top: 0;
    background-color: rgba(0, 0, 0, 0.5);
    display: flex;
    align-items: center;
    justify-content: center;

}

.content {
    background-color: #fff;
    width: 40%;
    height: 300px;
    border-radius: 15px;
}
</style>