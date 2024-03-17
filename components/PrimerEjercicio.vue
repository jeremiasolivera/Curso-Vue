<template>
    <h3>Ejercicio 1 - Profesores</h3>

    <div>
        <h3>Añadir Profesor</h3>
        <div>
            <label>
                Nombre de Profesor:
                <input type="text" placeholder="Walter" v-model="teacher.teacherName">
            </label>
            <br>
            <label>
                Apellido de Profesor:
                <input type="text" placeholder="Stroppiana" v-model="teacher.teacherSurname">
            </label>
            <br>
            <label>
                DNI de Profesor:
                <input type="text" placeholder="123123" v-model="teacher.teacherDni">
            </label>
            <br>
            <label>
                Materias de Profesor:
                <input type="text" placeholder="Matemáticas" v-model="subject">
                <button @click="addSubject()">Agregar materia</button>
                <ul>
                    <li v-for="(sub,index) in teacher.teacherSubjects" :key="index">{{ sub }}</li>
                </ul>
            </label>
            <br>
            <label>
                Documentación entregada:
                <input type="checkbox" v-model="teacher.teacherDocumentation">
            </label>
            <br>
            <button @click="handlerAddTeacher()">Agregar Profesor</button>
        </div>
    </div>

    <div>
        <h2>Listado de profesores.</h2>
        <table>
            <tr>
                <th>Nombre:</th>
                <th>Apellido:</th>
                <th>Dni:</th>
                <th>Materias:</th>
                <th>Documentación:</th>
            </tr>
            <tr v-for="teacher in teachers" :key="teacher.teacherDni">
                <th>{{ teacher.teacherName }}</th>
                <th>{{ teacher.teacherSurname }}</th>
                <th>{{ teacher.teacherDni }}</th>
                <ul>
                    <li v-for="(sub,index) in teacher.teacherSubjects" :key="index">{{ sub }}</li>
                </ul>
                <th v-if="teacher.teacherDocumentation">Aprobada la inscripción</th>
                <th v-else>No ha entregado la documentación</th>
            </tr>
        </table>
    </div>
</template>



<script lang="ts" setup>
    import {Ref,ref} from 'vue'

    interface ITeacher {
        teacherName:string,
        teacherSurname:string,
        teacherDni:string,
        teacherSubjects:Array<string>,
        teacherDocumentation:boolean
    }

    let teacher:Ref<ITeacher> = ref({
        teacherName:'',
        teacherSurname:'',
        teacherDni:'',
        teacherSubjects:[],
        teacherDocumentation:false
    })

    let teachers:Ref<Array<ITeacher>> = ref([])
    let subject:Ref<string> = ref('')
    
    const addSubject = () => {
        teacher.value.teacherSubjects.push(subject.value)
        subject.value=""
    }

    function handlerAddTeacher(){
        teachers.value.push({
            teacherName:teacher.value.teacherName,
            teacherSurname:teacher.value.teacherSurname,
            teacherDni:teacher.value.teacherDni,
            teacherSubjects:teacher.value.teacherSubjects,
            teacherDocumentation:teacher.value.teacherDocumentation
        })
        teacher.value.teacherName = ""
        teacher.value.teacherSurname = ""
        teacher.value.teacherDni = ""
        teacher.value.teacherSubjects = []
        teacher.value.teacherDocumentation = false
    }

</script>


<style scoped>
</style>