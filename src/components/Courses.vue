<template>
    <div id="courses-container" class="tab active">
        <h1 class="title">Courses</h1>
        <table id="courses">
            <thead>
            <tr>
                <th>#</th>
                <th>Course Title</th>
                <th>Semester</th>
                <th>Grade</th>
            </tr>
            </thead>
            <tbody>
            <tr v-for="(item, index) in courses" :key="index">
                <td>{{index + 1}}</td>
                <td>{{item.title}}</td>
                <td>{{item.semester}}</td>
                <td>{{item.grade}}</td>
            </tr>

            </tbody>
        </table>
        <br>
        <br>
        <div>
            <button id="add-course-button" class="blue-button" v-on:click="input = !input">+</button>
            <span id="add-course" v-show="this.input" style="display: inline">
                                <input class="input" type="text" placeholder="Course title" id="title">
                                <input class="input" type="number" min="1" max="8" placeholder="Semester" id="semester">
                                <input class="input" type="number" min="0" max="100" placeholder="Grade" id="grade">
                                <button class="green-button" id="save-course">Save</button>
                                <button class="grey-button" id="cancel-course">Cancel</button>
                            </span>
        </div>
    </div>
</template>

<script>
    export default {
        name: "Courses",
        data() {
            return {
                input: false
            }
        },
        methods: {},

        props: {
            courses: Array
        }

    }
</script>

<style scoped>

</style>