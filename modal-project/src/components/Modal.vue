<template>
    <div class="backdrop" @click="closeModal">
        <div class="modal" :class="{sale: theme === 'sale'}">
            <h1>{{header}}</h1>
            <p>{{msg}}</p>
        </div>
    </div>
</template>

<script>
    export default {
        props: ['header', 'msg', 'theme'],
        methods: {
            closeModal() {
                this.$emit('close')
            }
        }
    }
</script>

<style>
    .modal {
        width: 400px;
        padding: 20px;
        margin: 100px auto;
        background: white;
        border-radius: 10px;
    }

    .backdrop {
        top: 0;
        position: fixed;
        background: rgba(0, 0, 0, 0.5);
        width: 100%;
        height: 100%;
    }

    .modal h1 {
        color: #03cfb4;
        border: none;
        padding: 0;
    }

    .modal.sale {
        background: red;
        color: white;
    }

    .modal.sale h1{
        color: white;
    }
</style>