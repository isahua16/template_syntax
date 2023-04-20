<template>
    <div class="items_section">
        <div>
            <input type="number" ref="price">
            <button @click="filter_items">Submit</button>
        </div>
        
        <section class="item_card" v-for="(item, i) in items" :key="i">
            <article v-if="price_comparison >= item[`price`]">
                <img :src="item[`image_url`]">
                <h3>{{item[`title`]}}</h3>
                <p>${{item[`price`]}}</p>
                <p>{{item[`description`]}}</p>
            </article>
        </section>
    </div>
</template>

<script>
    export default {
        methods: {
            filter_items: function()
            {
               let input_price = this.$refs[`price`][`value`];
               this.price_comparison = input_price;
            }
        },
        data() {
            return {
                price_comparison: 100,
                items: [
                    {
                        title: `Title One`,
                        price: 10,
                        description: `This is the first description`,
                        image_url: `https://images.unsplash.com/photo-1546069901-ba9599a7e63c?ixlib=rb-4.0.3&ixid=MnwxMjA3fDB8MHxwaG90by1wYWdlfHx8fGVufDB8fHx8&auto=format&fit=crop&w=1780&q=80`
                    },
                    {
                        title: `Title Two`,
                        price: 20,
                        description: `This is the second description`,
                        image_url: `https://images.unsplash.com/photo-1546069901-ba9599a7e63c?ixlib=rb-4.0.3&ixid=MnwxMjA3fDB8MHxwaG90by1wYWdlfHx8fGVufDB8fHx8&auto=format&fit=crop&w=1780&q=80`
                    }
                ]
            }
        },
    }
</script>

<style scoped>
img {
    width:200px;
    border-radius: 30px;    
}
.items_section{
    display: grid;
    place-items: center;
    row-gap: 20px;
}
.item_card{
    width: 300px;
    padding:10px 10px;
    border-radius: 30px;
    box-shadow: rgba(149, 157, 165, 0.2) 0px 8px 24px;

}
</style>