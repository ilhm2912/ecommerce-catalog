<template>

    <div >
        <section class="bg1">
        </section>
        
        <div v-for="product in products" v-bind:key="product.id">
            <div class="card">
                <div class="produk-img">
                    <img src="../assets/Intersect.svg" alt="produk">
                </div>

                <div class="detail">
                    <div class="title">{{products.title}}</div>
                    <div class="category">{{products.category}}</div>
                    <div class="description">{{products.description}}</div>
                    <div class="price">{{products.price}}</div>
                        <div class="btn">
                            <button class="buy"> BUY</button>
                            <button class="next"> NEXT</button>
                        </div>                    
                </div>
                
            </div>
        </div>

    </div>

</template>

<script>
import axios from 'axios';

        export default {
            name: 'ProductDisplay',
            data (){
                return {
                    products: []
                }
            },
            
            mounted(){
                axios
                .get('https://fakestoreapi.com/products/1')
                .then(response => (this.products = response.data))
            },
        }

</script>

<style>

.card{
    
    display: flex;
    flex-wrap: wrap;
    justify-content:space-around;
    align-content: center;
    position: absolute;
    width: 1034px;
    height: 580px;
    left: 147px;
    top: 126px;
    top: 50%;
    left: 50%;
    transform: translate(-50%, -50%);
    background: #FFFFFF;
    box-shadow: 0px 4px 4px #00000040;
    border-radius: 10px;
    
}

img {
    max-width: 100%;
    width: 100%;
    height: auto;
}

.bg1 {
background-color: #FDE2FF;
background-size: cover;
background-repeat: no-repeat;
background-image: url('../assets/bg-pattern.svg');
width: 100%;
height: 350px;
}

.detail {

    display: flex;
    flex-wrap: wrap;
    flex-direction: column;
    justify-content: center;
    
    
}

div >.title {

    font-family: 'Inter';
    font-style: normal;
    font-weight: 600;
    font-size: 28px;
    line-height: 34px;
    margin-bottom: 10px;
    color: #720060;


}

div >.category{

    width: 149px;
    height: 22px;
    left: 577px;
    top: 269px;

    font-family: 'Inter';
    font-style: normal;
    font-weight: 400;
    font-size: 18px;
    line-height: 22px;
    /* identical to box height */
    color: #3F3F3F;

}

div >.description {

    width: 517px;
    height: 163px;
    left: 577px;
    top: 328px;
    padding-top: 20px;

    font-family: 'Inter';
    font-style: normal;
    font-weight: 400;
    font-size: 20px;
    line-height: 24px;

    color: #1E1E1E;
}

div >.price{

    width: 97px;
    height: 34px;
    left: 577px;
    top: 569px;

    font-family: 'Inter';
    font-style: normal;
    font-weight: 600;
    font-size: 28px;
    line-height: 34px;
    /* identical to box height */


    color: #720060;

}

div >.btn{

    display: flex;
    justify-content: space-around;
    align-items: center;
    

}

.buy {

    box-sizing: border-box;
    width: 259px;
    height: 42px;
    left: 577px;
    top: 618px;

    background: #720060;
    border-radius: 4px;
    font-family: 'Inter';
    font-style: normal;
    font-weight: 600;
    font-size: 20px;
    line-height: 24px;

    color: #FFFFFF;


}

.next {
    box-sizing: border-box;
    width: 259px;
    height: 42px;
    left: 855px;
    top: 618px;

    background: #FFFFFF;
    border: 3px solid #720060;
    border-radius: 4px;

    font-family: 'Inter';
    font-style: normal;
    font-weight: 600;
    font-size: 20px;
    line-height: 24px;

    color: #720060;



}


</style>