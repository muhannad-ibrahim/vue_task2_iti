<template>
    <table class="table table-striped table-bordered">
        <thead>
            <tr>
                <th>ID</th>
                <th>Name</th>
                <th>City</th>
            </tr>
        </thead>
        <tbody>
            <tr v-for="studnet in students" :key="studnet.id">
                <td>{{ studnet.id }}</td>
                <td>{{ studnet.name }}</td>
                <td>{{ studnet.city }}</td>
            </tr>
        </tbody>
        <tfoot>
            <tr>
                <th colspan="3">Number of students : {{ students.length }}</th>
            </tr>
        </tfoot>
    </table>
    <!-- <button class="btn btn-primary" @click="students.push({id:4,name:'muhannad',city:'amman'})">Add Student</button> -->
    <button type="button" class="btn btn-primary" data-toggle="modal" data-target="#exampleModal" data-whatever="@mdo">Add
        Student</button>

    <div class="modal fade" id="exampleModal" tabindex="-1" role="dialog" aria-labelledby="exampleModalLabel"
        aria-hidden="true">
        <div class="modal-dialog" role="document">
            <div class="modal-content">
                <div class="modal-header">
                    <h5 class="modal-title" id="exampleModalLabel">Add New Student</h5>
                    <button type="button" class="close" data-dismiss="modal" aria-label="Close">
                        <span aria-hidden="true">&times;</span>
                    </button>
                </div>
                <div class="modal-body">
                    <form ref="addStudentForm">
                        <div class="form-group">
                            <label for="student-name" class="col-form-label">Name:</label>
                            <input type="text" class="form-control" id="student-name" v-model="studentName">
                        </div>
                        <div class="form-group">
                            <label for="city-name" class="col-form-label">City:</label>
                            <input type="text" class="form-control" id="city-name" v-model="cityName">
                        </div>
                    </form>
                </div>
                <div class="modal-footer">
                    <button type="button" class="btn btn-primary" @click="addStudent()">Okay</button>
                    <button type="button" class="btn btn-secondary" data-dismiss="modal">Close</button>
                </div>
            </div>
        </div>
    </div>
</template>

<script>
import students from '../students';
export default {
    data: () => ({
        studentName:'',
        cityName:'',
        students: students
    }),
    methods: {
        addStudent() {
            // const form = this.$refs.addStudentForm;
            // const name = form.elements['student-name'].value;
            // const city = form.elements['city-name'].value;
            const name = this.studentName;
            const city = this.cityName;
            const id = this.students.length > 0 ? this.students[this.students.length - 1].id + 1 : 1;
            this.students.push({ id, name, city });
            // form.reset();
            $('#exampleModal').modal('hide');
        }
    }
}
</script>