<template>
    <div class="backdrop" @click="closeModal">
        <div class="modal" :class="{ sale: theme === 'sale'}">
            <h1>{{ header }}</h1>
            <p>{{ text }}</p>
        </div>
    </div>
</template>

<script>
export default{
    props: ['header', 'text', 'theme'],
    methods:{
        closeModal(){
            this.$emit('close')
        }
    }
}
</script>

<style scoped>
    .modal{
        width: 400px;
        padding: 20px;
        margin: 100px auto;
        background: white;
        border-radius: 10px;
    }
    .backdrop{
        top: 0;
        position: fixed;
        background: rgba(0,0,0,0.5);
        width:100%;
        height: 100%;
    }
    h1{
        color:brown;
        border: none;
        padding: 0;
    }
    p{
        font-style: normal;  
    }
    .sale{
        background: crimson;
        color: white;
    }
    .sale h1{
        color: white;
    }
</style>