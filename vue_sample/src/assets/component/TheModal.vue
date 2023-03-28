<template>
    <div class="black-bg" v-if="modal == true">
        <div class="white-bg">
            <p>자세히 보기</p>
            <img :src="products[detail].image" class="small-img">
            <h4>{{ products[detail].title }}</h4>
            <p>{{ products[detail].content }}</p>

            <!-- <button @click="modal = false">창 닫기</button> -->
        </div> 
    </div>
</template>

<script>
export default {
    name: 'modal',

    props: {
        products: Array,
        detail: Number,
        modal: Boolean,
    }

}
</script>

<style>
    .black-bg {
        width: 100%; height:100%;
        background: rgba(0,0,0,0.5);
        position: fixed; padding: 20px;
    }

    .white-bg {
        width: 100%; background: white;
        border-radius: 8px;
        padding: 20px;
        margin-top: 50%;
    } 
    .small-img {
        width: 85%;
    }

</style>