<template>
<div>

    <div class="row m-lg-5" style="font-size: 42px;
    display: flex;
    justify-content: center;
    align-items: center;
    background: #9999ff;
    color: white;
    border-radius: 20px;"> ТЕСТОВОЕ ЗАДАНИЕ С ИСПОЛЬЗОВАНИЕМ <span style="font-weight: bold;     display: flex;
    justify-content: center;">CRUD</span></div>

    <CreateComponent></CreateComponent>
    <IndexComponent ref="index"></IndexComponent>

<!--    <table class="table">-->
<!--        <thead>-->
<!--        <tr>-->
<!--            <th scope="col">Name</th>-->
<!--            <th scope="col">Age</th>-->
<!--            <th scope="col">Sport</th>-->
<!--        </tr>-->
<!--        </thead>-->
<!--        <tbody>-->
<!--        <tr v-for="person in vzaimosvyaz">-->
<!--            <td>{{ person.name }}</td>-->
<!--            <td>{{ person.age }}</td>-->
<!--            <td>{{ person.sport }}</td>-->
<!--        </tr>-->

<!--        </tbody>-->
<!--    </table>-->


</div>
</template>

<script>
import IndexComponent from "./IndexComponent";
import CreateComponent from "./CreateComponent";

export default {
    name: "PostComponent",
    components: {
        CreateComponent,
        IndexComponent
    },

    // mounted() {
    //     this.getPosts()
    // },

    // methods: {
    //     getPosts() {
    //         axios.get('/post')
    //             .then(function (data) {
    //                 console.log(data.data)
    //             })
    //     }
    //
    //
    // },

}
</script>

<style scoped>

</style>
