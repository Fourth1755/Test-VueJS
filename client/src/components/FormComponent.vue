<template>
    <form>
        <div class="form-control">
            <label>ชื่อวง</label>
            <input type="text" v-model.trim="artist.name"/>
        </div>
        <div class="form-control">
            <label>ประเทศ</label>
            <input type="text" v-model="artist.country"/>
        </div>
        <div class="form-control">
            <label for="country">ประเทศ</label>
            <select v-model="artist.country">
                <option value="Korea">Korea</option>
                <option value="Japan">Japan</option>
                <option value="Thailand">Thailand</option>
                <option value="England">England</option>
            </select>
        </div>
        <div class="form-control">
            <h3>ประเภท</h3>
            <div>
                <input type="radio" value="เดี่ยว" v-model="artist.type"/>
                <label for="type-name">เดี่ยว</label>
            </div>
            <div>
                <input type="radio" value="กลุ่ม" v-model="artist.type"/>
                <label for="type-name">กลุ่ม</label>
            </div>
        </div>
        <div>
        <div class="form-control">
            <h3>ทักษะด้านภาษา</h3>
            <div>
                <input type="checkbox" value="ภาษาอังกฤษ" v-model="artist.skill"/>
                <label>ภาษาอังกฤษ</label>
            </div>
            <div>
                <input type="checkbox" value="ภาษาเกาหลี" v-model="artist.skill"/>
                <label>ภาษาเกาหลี</label>
            </div>
            <div>
                <input type="checkbox" value="ภาษาญี่ปุ่น" v-model="artist.skill"/>
                <label>ภาษาญี่ปุ่น</label>
            </div>
        </div>
            <button>บันทึกข้อมูล</button>
        </div>
    </form>

</template>

<script>
export default {
    name:"FormComponent",
    data(){
        return{
            artist:{
                name:"BTS",
                country:"Korea",
                type:"กลุ่ม",
                skill:[]
            }
        }
    }
}
</script>

<style scoped>
    form{
        margin: 2rem auto;
        max-width: 40rem;
        border-radius: 12px;
        box-shadow: 0 2px 10px rgba(0,0 ,0 , 0.25);
        padding: 2rem;
        background-color: #fff;
    }
    .form-control{
        margin: 0.5rem 0;
    }
    label{
        font-weight: bold;
    }
    input,select{
        display: block;
        width: 100%;
        margin-top: 0.5rem ;
    }
    button{
        background: green;
        padding: 0.75rem 2rem;
        border-radius: 20px;
        cursor: pointer;
    }
    input[type="radio"],input[type="checkbox"]{
        display: inline-block;
        width: auto;
        margin-right: 1rem;
    }
    input[type="checkbox"]+label,
    input[type="radio"]+label{
        font-weight: normal;
    }
    h3{
        font-size: 1rem;
        margin: 0.5rem 0;
    }
</style>