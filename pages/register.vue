<template>
  <div class="register-form">
    <h2>ลงทะเบียน</h2>
    <form @submit="registerUser">
      <div class="form-group">
        <label for="firstname">ชื่อ:</label>
        <input
          id="firstname"
          v-model="userData.firstname"
          type="text"
          required
        >
      </div>

      <div class="form-group">
        <label for="lastname">นามสกุล:</label>
        <input id="lastname" v-model="userData.lastname" type="text" required>
      </div>

      <div class="form-group">
        <label for="password">รหัสผ่าน:</label>
        <input
          id="password"
          v-model="userData.password"
          type="password"
          required
        >
      </div>

      <div class="form-group">
        <label for="confirmPassword">ยืนยันรหัสผ่าน:</label>
        <input
          id="confirmPassword"
          v-model="confirmPassword"
          type="password"
          required
        >
      </div>

      <div class="form-group">
        <label for="studentId">รหัสนักศึกษา:</label>
        <input
          id="studentId"
          v-model="userData.studentId"
          type="text"
          required
          @input="formatStudentId"
        >
      </div>

      <div class="form-group">
        <label for="major">สาขา:</label>
        <select id="major" v-model="userData.major" required>
          <option value="CS">
            วิทยาการคอมพิวเตอร์และสารสนเทศ
          </option>
          <option value="DS">
            วิทยาการข้อมูลและปัญญาประดิษฐ์
          </option>
          <option value="SPORT">
            วิทยาศาสตร์การกีฬา นวัตกรรมและสุขภาพ
          </option>
          <option value="ECON">
            เศรษฐศาสตร์ระหว่างประเทศ นวัตกรรมและความยั่งยืน
          </option>
          <option value="PA">
            รัฐประศาสนศาสตร์
          </option>
          <option value="ENVI">
            วิทยาศาสตร์สิ่งแวดล้อมและทรัพยากรธรรมชาติ
          </option>
          <option value="FTI">
            เทคโนโลยีและนวัตกรรมอาหาร
          </option>
          <option value="AQUATICTECH">
            เทคโนโลยีการผลิตสัตว์น้ำ
          </option>
          <option value="LAW">
            นิติศาสตร์
          </option>
          <option value="TEFL">
            การสอนภาษาอังกฤษในฐานะภาษาต่างประเทศ
          </option>
          <option value="FIN">
            การเงินธุรกิจ
          </option>
          <option value="EBM">
            ภาษาอังกฤษเพื่อการจัดการธุรกิจ
          </option>
          <option value="TOUR">
            นวัตกรรมการท่องเที่ยวและการบริการ
          </option>
          <option value="ACC">
            บัญชีบัณฑิต
          </option>
          <option value="IB">
            บริหารธุรกิจะหว่าง
          </option>
        </select>
      </div>

      <button type="submit">
        ลงทะเบียน
      </button>
    </form>
  </div>
</template>
<script>
export default {
  data () {
    return {
      userData: {
        firstname: '',
        lastname: '',
        password: '',
        studentId: '', // เก็บรหัสนักศึกษา
        major: 'CS'
      },
      confirmPassword: ''
    }
  },
  methods: {
    formatStudentId () {
      // ลบทุกอย่างนอกจากตัวเลข
      this.userData.studentId = this.userData.studentId.replace(/[^0-9]/g, '')

      // จำกัดให้รหัสนักศึกษามีแค่ 10 ตัวเลข
      if (this.userData.studentId.length > 10) {
        this.userData.studentId = this.userData.studentId.substring(0, 10)
      }

      // ใส่เครื่องหมาย "-" ระหว่างตัวเลขที่ 9 และ 10 ถ้ามี 10 ตัวเลข
      if (this.userData.studentId.length === 10) {
        this.userData.studentId = this.userData.studentId.replace(
          /(\d{9})(\d{1})/,
          '$1-$2'
        )
      }
    },
    registerUser () {
      if (this.userData.password !== this.confirmPassword) {
        alert('รหัสผ่านและยืนยันรหัสผ่านไม่ตรงกัน')
      }

      // ทำสิ่งที่คุณต้องการเมื่อผู้ใช้ลงทะเบียน
      // คุณสามารถส่งข้อมูลไปยังเซิร์ฟเวอร์ได้ที่นี่
    }
  }
}
</script>

<style scoped>
.register-form {
  width: 300px;
  margin: 0 auto;
  padding: 20px;
  border: 1px solid #ccc;
  border-radius: 5px;
}

.form-group {
  margin-bottom: 10px;
}

label {
  display: block;
}

input,
select {
  width: 100%;
  padding: 5px;
  border: 1px solid #ccc;
  border-radius: 3px;
}

button {
  width: 100%;
  padding: 10px;
  background-color: #007bff;
  color: #fff;
  border: none;
  border-radius: 3px;
  cursor: pointer;
}
</style>
