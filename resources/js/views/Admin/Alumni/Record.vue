<template>
  <div class="container-fluid">
    <div class="row p-5">
      <div class="col-12 shadow p-3 bg-light rounded">
        <h4 class="text-uppercase text-muted ps-3 py-3 fw-bold">
          BASIC INFORMATION
        </h4>
        <div class="row p-4" v-if="record.student_basic_info">
          <div class="col-3">
            <img :src="imagePath(record.id_image)" class="img-fluid" />
          </div>
          <div class="col-9">
            <div class="row px-5">
              <div class="col-6">
                <h3 class="text-uppercase fw-bold">
                  {{
                    `${record.student_basic_info.last_name}, ${
                      record.student_basic_info.first_name
                    } ${setValue(
                      record.student_basic_info.middle_name
                    )}   ${setValue(record.student_basic_info.middle_name)} `
                  }}
                </h3>
                <div class="col-12 mb-2">
                  <p class="text-primary m-0 p-0">
                    {{ record.student_basic_info.email }}
                  </p>
                </div>
                <div class="col-12">
                  <p class="fw-bold p-0 m-0">
                    (Batch {{ record.student_account_info.batch.batch }})
                  </p>
                </div>
              </div>
              <div class="col-6 float-left">
                <span class="bg-primary px-3 py-2 rounded text-light fw-bold">{{
                  record.student_basic_info.student_number
                }}</span>
              </div>
            </div>
            <div class="row px-5 py-3">
              <div class="col-4">
                <h5 class="text-muted">Sex</h5>
                <h5 class="fw-bold">
                  {{ record.student_basic_info.gender }}
                </h5>
              </div>
              <div class="col-4">
                <h5 class="text-muted">Birthdate</h5>
                <h5 class="fw-bold">
                  {{ formatDate(record.student_basic_info.birthdate) }}
                </h5>
              </div>
              <div class="col-4">
                <h5 class="text-muted">Birthplace</h5>
                <h5 class="fw-bold">
                  {{ record.student_basic_info.birthplace }}
                </h5>
              </div>
            </div>
            <div class="row px-5">
              <div class="col-4">
                <h5 class="text-muted">Religion</h5>
                <h5 class="fw-bold">
                  {{ record.student_basic_info.religion }}
                </h5>
              </div>
              <div class="col-4">
                <h5 class="text-muted">Civit Status</h5>
                <h5 class="fw-bold">
                  {{ record.student_basic_info.civil_status }}
                </h5>
              </div>
            </div>
            <div class="row px-5 py-3">
              <h5 class="text-muted fw-bold mb-3 text-uppercase">
                Contact Number
              </h5>
              <div class="col-6">
                <h5 class="text-muted">Mobile</h5>
                <h5 class="fw-bold">
                  {{ record.student_basic_info.mobile_number }}
                </h5>
              </div>
              <div class="col-6">
                <h5 class="text-muted">Telephone</h5>
                <h5 class="fw-bold">
                  {{ record.student_basic_info.telephone_number }}
                </h5>
              </div>
            </div>
            <div class="row px-5 py-3">
              <h5 class="text-muted fw-bold mb-3 text-uppercase">Address</h5>
              <div class="col-6">
                <h5 class="text-muted">Current</h5>
                <h5 class="fw-bold">
                  {{ record.student_basic_info.current_address }}
                </h5>
              </div>
              <div class="col-6">
                <h5 class="text-muted">Permanent</h5>
                <h5 class="fw-bold">
                  {{ record.student_basic_info.permanent_address }}
                </h5>
              </div>
            </div>
          </div>
        </div>
        <div class="row px-3">
          <h4 class="text-uppercase text-muted py-3 fw-bold">
            EDUCATION INFORMATION
          </h4>
          <div class="row mb-3" v-if="record.student_education_info">
            <div class="col-6">
              <span class="text-muted">Elementary</span>
              <h5 class="text-uppercase fw-bold">
                {{ setInfo(record.student_education_info.elem) }}
              </h5>
            </div>
            <div class="col-6">
              <span class="text-muted"> Year</span>
              <h5 class="text-uppercase fw-bold">
                {{ setInfo(record.student_education_info.elem_year) }}
              </h5>
            </div>
          </div>
          <div class="row mb-3">
            <div class="col-6">
              <span class="text-muted">Junior High School</span>
              <h5 class="text-uppercase fw-bold">
                {{ setInfo(record.student_education_info.jhs) }}
              </h5>
            </div>
            <div class="col-6">
              <span class="text-muted"> Year</span>
              <h5 class="text-uppercase fw-bold">
                {{ setInfo(record.student_education_info.jhs_year) }}
              </h5>
            </div>
          </div>
          <div class="row mb-3">
            <div class="col-4">
              <span class="text-muted">Senior High School</span>
              <h5 class="text-uppercase fw-bold">
                {{ setInfo(record.student_education_info.shs) }}
              </h5>
            </div>
            <div class="col-4">
              <span class="text-muted"> Year</span>
              <h5 class="text-uppercase fw-bold">
                {{ setInfo(record.student_education_info.shs_year) }}
              </h5>
            </div>
            <div class="col-4">
              <span class="text-muted"> Strand</span>
              <h5 class="text-uppercase fw-bold">
                {{ setInfo(record.student_education_info.shs_strand) }}
              </h5>
            </div>
          </div>
          <div class="row mb-3">
            <div class="col-4">
              <span class="text-muted">Graduate Studies</span>
              <h5 class="text-uppercase fw-bold">
                {{ setInfo(record.student_education_info.gs) }}
              </h5>
            </div>
            <div class="col-4">
              <span class="text-muted"> Year</span>
              <h5 class="text-uppercase fw-bold">
                {{ setInfo(record.student_education_info.gs_year) }}
              </h5>
            </div>
            <div class="col-4">
              <span class="text-muted"> Course</span>
              <h5 class="text-uppercase fw-bold">
                {{ setInfo(record.student_education_info.gs_course) }}
              </h5>
            </div>
          </div>
          <div class="row mb-3">
            <div class="col-4">
              <span class="text-muted">Post Graduate Studies</span>
              <h5 class="text-uppercase fw-bold">
                {{ setInfo(record.student_education_info.pgs) }}
              </h5>
            </div>
            <div class="col-4">
              <span class="text-muted">Year</span>
              <h5 class="text-uppercase fw-bold">
                {{ setInfo(record.student_education_info.pgs_year) }}
              </h5>
            </div>
            <div class="col-4">
              <span class="text-muted"> Course</span>
              <h5 class="text-uppercase fw-bold">
                {{ setInfo(record.student_education_info.pgs_course) }}
              </h5>
            </div>
          </div>
        </div>
        <div class="row px-3 pb-5">
          <h4 class="text-uppercase text-muted py-3 fw-bold">
            EMPLOYEE INFORMATION
          </h4>
          <div class="row mb-3" v-if="record.student_employee_info">
            <div class="col-4">
              <span class="text-muted">Company</span>
              <h5 class="text-uppercase fw-bold">
                {{ setInfo(record.student_employee_info.company) }}
              </h5>
            </div>
            <div class="col-4">
              <span class="text-muted">Designation</span>
              <h5 class="text-uppercase fw-bold">
                {{ setInfo(record.student_employee_info.designation) }}
              </h5>
            </div>
            <div class="col-4">
              <span class="text-muted">Address</span>
              <h5 class="text-uppercase fw-bold">
                {{ setInfo(record.student_employee_info.address) }}
              </h5>
            </div>
          </div>
          <div class="row mb-3">
            <div class="col-4">
              <span class="text-muted">Telephone Number</span>
              <h5 class="text-uppercase fw-bold">
                {{ setInfo(record.student_employee_info.tel_no) }}
              </h5>
            </div>
            <div class="col-4">
              <span class="text-muted">Mobile Number</span>
              <h5 class="text-uppercase fw-bold">
                {{ setInfo(record.student_employee_info.mobile_number) }}
              </h5>
            </div>
            <div class="col-4">
              <span class="text-muted">Email</span>
              <h5 class="text-uppercase fw-bold">
                {{ setInfo(record.student_employee_info.email) }}
              </h5>
            </div>
          </div>
          <div class="row mb-3">
            <div class="col-4">
              <span class="text-muted">Spouse Name</span>
              <h5 class="text-uppercase fw-bold">
                {{ setInfo(record.student_employee_info.sp_name) }}
              </h5>
            </div>
            <div class="col-4">
              <span class="text-muted">Occupation</span>
              <h5 class="text-uppercase fw-bold">
                {{ setInfo(record.student_employee_info.sp_occupation) }}
              </h5>
            </div>
            <div class="col-4">
              <span class="text-muted">Mobile Number</span>
              <h5 class="text-uppercase fw-bold">
                {{ setInfo(record.student_employee_info.sp_mobile_no) }}
              </h5>
            </div>
          </div>

          <div class="row mb-3">
            <div class="col-4">
              <span class="text-muted">Company</span>
              <h5 class="text-uppercase fw-bold">
                {{ setInfo(record.student_employee_info.sp_company) }}
              </h5>
            </div>
            <div class="col-4">
              <span class="text-muted">Position</span>
              <h5 class="text-uppercase fw-bold">
                {{ setInfo(record.student_employee_info.sp_position) }}
              </h5>
            </div>
            <div class="col-4">
              <span class="text-muted">Business Address</span>
              <h5 class="text-uppercase fw-bold">
                {{ setInfo(record.student_employee_info.sp_buss_address) }}
              </h5>
            </div>
          </div>
          <div class="row mb-3">
            <div class="col-4">
              <span class="text-muted">Fax Number</span>
              <h5 class="text-uppercase fw-bold">
                {{ setInfo(record.student_employee_info.sp_fax_no) }}
              </h5>
            </div>
            <div class="col-4">
              <span class="text-muted">Email</span>
              <h5 class="text-uppercase fw-bold">
                {{ setInfo(record.student_employee_info.sp_email) }}
              </h5>
            </div>
          </div>
        </div>
      </div>
    </div>
  </div>
</template>
<script>
import moment from "moment";
export default {
  props: ["id"],
  computed: {
    record() {
      return this.$store.getters["ALUMNAE_APPROVAL/GET_ALUMNAE_RECORD"];
    },
  },

  methods: {
    imagePath(path) {
      return `http://localhost:8000${path}`;
    },
    setValue(value) {
      return value ?? "";
    },
    setInfo(value) {
      return value ?? "No Data";
    },
    formatDate(date) {
      return moment(date).format("LL");
    },
  },

  async mounted() {
    await this.$store.dispatch(
      "ALUMNAE_APPROVAL/FETCH_ALUMNAE_RECORD",
      this.id
    );
  },
};
</script>