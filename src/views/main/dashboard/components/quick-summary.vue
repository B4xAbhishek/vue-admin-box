<template>
  <div class="quick-summary">
    <div class="quick-summary-left">
      <div class="header">
        <div class="">
          <p class="title">Quick Summary</p>
        </div>
        <div class="right-c1">
          <el-select v-model="value" class="m-2" placeholder="Select" size="large">
            <el-option v-for="item in options" :key="item.value" :label="item.label" :value="item.value"
              :append-to-body="true" />
          </el-select>
        </div>
      </div>
      <div class="row">
        <div class="summary-card">
          <div class="top-row">
            Finance
          </div>
          <div class="body">
            <div class="row">
              <div class="metrics">
                <div class="title">Total Fee (INR)</div>
                <div class="value">28,0000</div>
              </div>
              <div class="metrics">
                <div class="title">Total Collected (INR)</div>
                <div class="value">28,5000</div>
              </div>
            </div>
            <div class="row">
              <div class="metrics">
                <div class="title">Total Fee (INR)</div>
                <div class="value">28,0000</div>
              </div>
              <div class="action">
                <el-button class="btn">View Finance</el-button>
              </div>
            </div>

          </div>
        </div>
        <div class="summary-card">
          <div class="top-row">
            School
          </div>
          <div class="body">
            <div class="row">
              <div class="metrics">
                <div class="title">Exam</div>
                <div class="value">32 Ongoing</div>
              </div>
              <div class="metrics">
                <div class="title">Report card</div>
                <div class="value">14 Generated</div>
              </div>
            </div>
            <div class="row">
              <div class="metrics">
                <div class="title">Performance</div>

                <div class="value_text">
                  <div class="value_img">
                    <img :src="doubleArrow" />
                  </div> 18 % improved
                </div>

              </div>
              <div class="action">
                <el-button class="btn">View Finance</el-button>
              </div>
            </div>

          </div>
        </div>
      </div>

      <!-- second row -->
      <div class="row">
        <div class="summary-card">
          <div class="top-row">
            Learn
          </div>
          <div class="body">
            <div class="row">
              <div class="metrics">
                <div class="title">Test</div>
                <div class="value">32 Ongoing</div>
              </div>
              <div class="metrics">
                <div class="title">Syllabus</div>
                <div class="value">32 Ongoing</div>
              </div>
            </div>
            <div class="row">
              <div class="metrics">
                <div class="title">Assignment</div>
                <div class="value">32 Ongoing</div>
              </div>
              <div class="action">
                <el-button class="btn">View Learn</el-button>
              </div>
            </div>

          </div>
        </div>
        <div>
          <div class="summary-card"></div>
        </div>
      </div>

    </div>
    <div class="quick-summary-right">
      <div class="header">
        <div class="">
          <p class="title">Deadline</p>
        </div>
        <div class="right-c1">
          <el-select v-model="value2" class="m-2" placeholder="Select" size="large">
            <el-option v-for="item in options" :key="item.value" :label="item.label" :value="item.value"
              :append-to-body="true" />
          </el-select>
        </div>
      </div>
      <div class="row">
        <div class="summary-card">
          <div class="top-row">
            Appointment
          </div>
          <div class="body">
            <div class="row">
              <div class="content">impedit quo minus id quod maxime placeat facere possimus, omnis voluptas assumenda est,
                omnis dolor
                repellendus. Temporibus autem quibusdam et aut offici
              </div>
            </div>
            <hr class="horizontal-line" />
            <div class="row">
              <div class="content">impedit quo minus id quod maxime placeat facere possimus, omnis voluptas assumenda est,
                omnis dolor
                repellendus. Temporibus autem quibusdam et aut offici
              </div>
            </div>
            <hr class="horizontal-line" />
            <div class="row">
              <div class="content">impedit quo minus id quod maxime placeat facere possimus, omnis voluptas assumenda est,
                omnis dolor
                repellendus. Temporibus autem quibusdam et aut offici
              </div>
            </div>
            <hr class="horizontal-line" />
            <div class="row">
              <div class="content">impedit quo minus id quod maxime placeat facere possimus, omnis voluptas assumenda est,
                omnis dolor
                repellendus. Temporibus autem quibusdam et aut offici
              </div>
            </div>
            <hr class="horizontal-line" />

          </div>
        </div>
      </div>
    </div>
  </div>
</template>

<script lang="ts">
import { defineComponent } from 'vue';
import { ref } from 'vue';
import doubleArrow from "@/assets/svg/doubleArrow.svg"

export default defineComponent({
  setup() {
    const value = ref('This Week');
    const value2 = ref('Appointments');
    const options = ref([
      {
        value: 'Option1',
        label: 'Option1',
      },
      {
        value: 'Option2',
        label: 'Option2',
      },
      {
        value: 'Option3',
        label: 'Option3',
      },
      {
        value: 'Option4',
        label: 'Option4',
      },
      {
        value: 'Option5',
        label: 'Option5',
      },
    ]);

    return { value, options, doubleArrow, value2 };
  },
});
</script>

<style lang="scss" >
.quick-summary {
  display: flex;
  align-items: flex-start;
  justify-content: space-between;
  column-gap: 30px;
  margin-bottom: 40px;
  flex-wrap: wrap; 


  .quick-summary-left {
    flex: 2;
    display: flex;
    flex-direction: column;
    row-gap: 20px;

    .row {
      display: flex;
      justify-content: space-between;
      column-gap: 20px;
      flex-wrap: wrap;
    }

    .header {
      display: flex;
      justify-content: space-between;

      .title {
        font-size: 14px;
        color: #000000;
        text-align: start;
        font-weight: 600;
      }
    }

    .summary-card {
      border-radius: 15px;
      width: 48%;
      height: 275px;
      background: #ffffff;
      // width: 100%; 

      .top-row {
        background: #E6EAED;
        color: #BC6C42;
        height: 58px;
        text-align: left;
        font-weight: 600;
        display: flex;
        align-items: center;
        padding-left: 30px;
        border-top-right-radius: 15px;
        border-top-left-radius: 15px;
      }

      .body {
        display: flex;
        flex-direction: column;
        row-gap: 30px;
        padding: 30px;
        background: #ffffff;

        border-bottom-right-radius: 15px;
        border-bottom-left-radius: 15px;

        .row {
          display: flex;
          justify-content: space-between;
          column-gap: 20px;

          .metrics {
            display: flex;
            flex-direction: column;
            row-gap: 10px;

            .title {
              font-size: 14px;
              color: #8C8C8C;
              text-align: start;
            }

            .value {
              color: #333333;
              font-weight: 600;
            }

            .value_text {
              display: flex;
              align-items: center;
              justify-content: center;
              color: #0BC32E;
              column-gap: 5px;
              cursor: pointer;
              font-size: 12px;

              .value_img {
                display: flex;
                align-items: center;
                justify-content: center;
                border: 1px solid #0BC32E;
                border-radius: 1000px;
                height: 25px;
                width: 25px;
              }
            }

          }

          .btn {
            width: 120px;
            height: 39px;
            color: #BC6C42;
            border: 1px solid #BC6C42;
            font-weight: 600;
          }
        }
      }
    }
  }

  .quick-summary-right {
    flex: 1;
    display: flex;
    flex-direction: column;
    row-gap: 20px;

    .header {
      display: flex;
      justify-content: space-between;


      .title {
        font-size: 14px;
        color: #000000;
        text-align: start;
        font-weight: 600;
      }
    }

    .summary-card {
      border-radius: 15px;
      width: 100%;
      height: 100%;
      background: #ffffff;
      overflow-x: auto;

      .top-row {
        background: #E6EAED;
        color: #BC6C42;
        height: 58px;
        font-weight: 600;
        text-align: left;
        display: flex;
        align-items: center;
        padding-left: 30px;
        border-top-right-radius: 15px;
        border-top-left-radius: 15px;
      }

      .body {
        display: flex;
        flex-direction: column;
        row-gap: 10px;
        background: #ffffff;
        border-bottom-right-radius: 15px;
        border-bottom-left-radius: 15px;

        .row {
          display: flex;

          .content {
            text-align: left;
            padding-top: 15px;
            padding-left: 30px;
            padding-right: 30px;
            font-size: 14px;
            color: #000000;
            opacity: 0.8;
          }
        }

        .horizontal-line {
          margin: 0px 0;
          color: #ccc;
          background-color: #ccc;
          border: 1px solid #F7F9FB;
        }
      }
    }
  }
}




.el-select .el-input .el-select__caret {
  color: #BC6C42;
}

.el-input__wrapper {
  border: 1px solid #BC6C42 !important;
  color: #D9B29E !important;
}

.el-select .el-input__inner {
  color: #D9B29E !important;
}
</style>
