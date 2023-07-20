<template>
    <form @submit.prevent>

            <h4>Название поста</h4>
            <MyInput
                v-model="post.title"
                type="text" 
                placeholder="Названиие"
            />

            <MyInput
                v-model="post.body"
                type="text" 
                placeholder="Описпние"
            />

            <MyButton 
                style="align-self: flex-end; margin-top: 15px;"
                @click="createPost"
            >
                Создать
            </MyButton>

    </form>
</template>

<script>

    export default {
        data(){
            return{
                post:{
                    title:'',
                    body:''
                }
            }
        },
        methods:{
            createPost(){
                this.post.id = Date.now()
                this.$emit('create', this.post) //Связывается с родительским компонентом и передает данные(второй аргуиень). Первый аргумент это название события
                this.post = {   //Это нужно чтобы после добавления поле ввода стиралось
                    title:'',
                    bode:''
                }            
            }
        },
    }
</script>

<style scoped>
form{
    display: flex;
    flex-direction: column;
}
</style>