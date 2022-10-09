<template>
    <div class="row m-lg-5">

        <table class="table ">
            <thead>
            <tr>
                <th scope="col">ID</th>
                <th scope="col">Name</th>
                <th scope="col">Age</th>
                <th scope="col">Job</th>
                <th scope="col">Edit</th>
                <th scope="col">Delete</th>
            </tr>
            </thead>
            <tbody>
            <template v-for="person in people">
                <ShowComponent :person="person" :ref="`show_${person.id}`"></ShowComponent>
                <EditComponent :person="person" :ref="`edit_${person.id}`"></EditComponent>
            </template>
            </tbody>
        </table>

    </div>
</template>

<script>
import ShowComponent from "./ShowComponent";
import EditComponent from "./EditComponent";

export default {
    name: "IndexComponent",

    components: {
        EditComponent,
        ShowComponent,
    },

    data() {
        return {
            people: null,
            editPersonId: null,
            name: null,
            age: null,
            job: null,
        }
    },

    mounted() {
        this.getPeople();
    },

    methods: {
        getPeople() {
            axios.get('/api/people')
                .then(res => {
                    this.people = res.data
                })
        },

        deletePerson(id) {
            axios.delete(`/api/people/${id}`)
                .then(res => {
                    this.getPeople();
                })
        },

        changePersonId(id, name, age, job) {
            this.editPersonId = id

            let editName = `edit_${id}`
            let fullEditName = this.$refs[editName][0];
            fullEditName.name = name
            fullEditName.age = age
            fullEditName.job = job
        },

        isEdit(id) {
            return this.editPersonId === id
        }
    },


    computed: {}
}
</script>

<style scoped>

</style>
