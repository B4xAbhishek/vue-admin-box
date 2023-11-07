<template>
  <div class="sub-head">

    <div class="sub-div">
      <div class="top-row">
        <div class="title">Appointments</div>
        <div class="top-roww">
          <img style="width: 5px;" :src="doubleArrow" />
        </div>
      </div>
      <el-card class="box-card">
        <div class="text item">
          <div class="row-line">
            <div class="">
              <div class="title">Active</div>
              <div class="values">23</div>
            </div>
            <div class="metrics">
              <div class="title">Upcoming</div>
              <div class="values">55</div>
            </div>
            <div class="metrics">
              <div class="title">Past</div>
              <div class="values">44</div>
            </div>
          </div>
          <div class="row-lines">
            <div class="action">
              <el-button class="btns">View Appiontments</el-button>
            </div>
            <div class="metric">
              <div class="title">You will be taken to a new tab of the permission slip section</div>
            </div>
          </div>
        </div>
      </el-card>
    </div>
    <div class="sub-div">
      <div class="top-row">
        <div class="title">Permission Slips</div>
        <div class="top-roww">
          <img style="width: 5px;" :src="doubleArrow" />
        </div>
      </div>
      <el-card class="box-card">
        <div class="text item">
          <div class="row-line">
            <div class="metrics">
              <div class="title">Active</div>
              <div class="values">23</div>
            </div>
            <div class="metrics">
              <div class="title">Upcoming</div>
              <div class="values">55</div>
            </div>
            <div class="metrics">
              <div class="title">Past</div>
              <div class="values">44</div>
            </div>
          </div>
          <div class="row-lines">
            <div class="action">
              <el-button class="btns">View permission Slips</el-button>
            </div>
            <div class="metric">
              <div class="title">You will be taken to a new tab of the permission slip section</div>
            </div>
          </div>
        </div>
      </el-card>
    </div>
  </div>
</template>

<script lang="ts">
import { defineComponent, reactive } from 'vue';
import { ref } from 'vue';
import doubleArrow from "@/assets/images/forwardArrow.png"
import Chart from '@/components/charts/index.vue'
import option from '../../dashboard/components/charts/modules/circle'

export default defineComponent({
  components: {
    Chart
  },
  setup() {

    const options = reactive(option)


    const value = ref('This Week');

    const options2 = ref([
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

    return { value, options, doubleArrow, options2 };
  },
});
</script>

<style lang="scss" scoped >
.sub-head {
  display: flex;
  justify-content: space-between;
  margin-top: 14px;
  column-gap: 25px;
  margin-bottom: 20px;
  flex-wrap: wrap;

  @media (max-width: 655px) {
    width: 100%;

  }

  .sub-div {
    width: 48%;

    @media (max-width: 655px) {
    width: 100%;

  }

    .text {
      font-size: 14px;
    }

    .item {
      padding: 24px 0;
    }

    .row-line {
      display: flex;
      justify-content: space-between;
      text-align: left;
      padding-right: 40px;

      .metrics {
        display: flex;
        flex-direction: column;
        row-gap: 10px;
      }
    }

    .row-lines {
      display: flex;
      justify-content: space-between;
      margin-top: 40px;
      text-align: left;
      gap: 20px
    }

    .box-card {
      border-radius: 10px;
      padding: 15px;

      @media (max-width: 655px) {
        width: 100% !important;
        padding: 0;

      }
    }

    .values {
      font-weight: bold;
      font-size: 20px;
    }

    .btns {
      width: 160px;
      height: 39px;
      background-color: #BC6C42;
      color: white;
      font-weight: 600;
      font-size: 15px
    }

    .title {
      justify-content: left;
      color: #8C8C8C
    }

    .top-row {
      display: flex;
      flex-direction: row;
      justify-content: space-between;
      align-items: center;
      margin-bottom: 10px;
      cursor: pointer;

      @media (max-width: 655px) {
        width: 100%;
        margin-top: 10px;

      }

      .title {
        font-size: 14px;
        color: #000000;
        text-align: start;
        font-weight: 600;
      }
    }

    .top-roww {
      display: flex;
      justify-content: center;
      align-items: center;
      border-radius: 100%;
      border: 1px solid #BC6C42;
      height: 30px;
      width: 30px;
      background-color: #ffffff;
    }
  }


}
</style>
