<template>
    <div>
        <section class="h-screen w-full flex flex-col justify-center items-center" >
            <h1>Custom Background Colors</h1>
            <select >
                <option v-for="color in colors" value="">color</option>
            </select>
        </section>
    </div>
</template>

<script>
    export default {
        data(){
            return{
                colors:[
                    {item: 'white'},
                    {item: 'black'},
                    {item: 'red'},
                    {item: 'green'},
                    {item: 'pink'},
            ]
            }
        }
    }
</script>

<style lang="scss" scoped>

</style>