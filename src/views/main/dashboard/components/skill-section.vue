<template>
  <div class="skills-section">
    <div class="header">
      <div class="">
        <p class="title">Skills Section</p>
      </div>
      <div class="right-c1">
        <el-select v-model="value" class="m-2" placeholder="Select" size="large">
          <el-option v-for="item in options2" :key="item.value" :label="item.label" :value="item.value"
            :append-to-body="true" />
        </el-select>
      </div>
    </div>
    <div class="section-body">
      <div class="summary-card card1">
        <div class="top-row">
          Summary
        </div>
        <div class="body">
          <div class="box">
            <Chart :option="chartOption" />
          </div>
        </div>
      </div>
      <div class="summary-card card2">
        <div class="top-row">
          Skill Report
        </div>
        <div class="body">
          <el-scrollbar>
            <div class="scrollbar-flex-content">
              <div class="scrollbar-demo-item" v-for="index in 5" :key="index">
                <div class="body-card">
                  <div class="row1">
                    <div class="row-left">
                      <img :src="walker" />

                    </div>
                    <div class="row-right">
                      <div class="left-row-header">Dance</div>
                      <div class="left-row-flex">
                        <div class="metrics">
                          <div>Students</div>
                          <div>15</div>
                        </div>
                        <div class="metrics">
                          <div>Sessions token</div>
                          <div>7</div>
                        </div>

                      </div>
                    </div>

                  </div>
                  <div class="row2">

                    <div class="row-left"></div>
                    <div class="row-right">
                      <div>Performance</div>
                      <div class="icon-text">
                        <div class="icon">
                          <img :src="arrowUp" />
                        </div>
                        <div class="text">
                          18 % improved from last week
                        </div>

                      </div>
                    </div>

                  </div>
                </div>
              </div>
            </div>
          </el-scrollbar>

        </div>
      </div>
    </div>
  </div>
</template>

<script lang="ts">
import { defineComponent, reactive } from 'vue';
import { ref } from 'vue';
import doubleArrow from "@/assets/svg/doubleArrow.svg"
import Chart from '@/components/charts/index.vue'
import option from '../../dashboard/components/charts/modules/circle'
import walker from "@/assets/svg/walker.svg"
import arrowUp from "@/assets/svg/arrowUp.svg"



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



    const chartOption = {

      legend: {
        orient: 'vertical', 
        left: '80%', 
        top: 'center', 
        data: ['搜索引擎', '直接访问', '邮件营销', '联盟广告'], 
      },
      series: [
        {
          name: '访问来源',
          type: 'pie',
          radius: ['40%', '70%'],
          avoidLabelOverlap: false,
          itemStyle: {
            borderRadius: 10,
            borderColor: '#fff',
            borderWidth: 10
          },
          label: {
            show: false,
            position: 'center'
          },
          emphasis: {
            label: {
              show: true,
              fontSize: 26,
              fontWeight: 'bold',
              formatter: (p) => {
                let dom = `<div backgroundColor="red">1</div>`
                return p.name + '\n' + p.value
              }
            }
          },
          labelLine: {
            show: false
          },
          data: [
            { value: 1048, name: '搜索引擎' },
            { value: 735, name: '直接访问' },
            { value: 580, name: '邮件营销' },
            { value: 484, name: '联盟广告' },
    
          ]
        }
      ]
    };





    return { value, options, doubleArrow, options2, walker, arrowUp, chartOption };
  },
});
</script>

<style lang="scss" scoped >
.skills-section {
  height: 400px;

  @media (max-width: 655px) {
    width: 100%;
    height: 100%;
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

  .section-body {
    display: flex;
    justify-content: space-between;
    flex-wrap: wrap;
    column-gap: 10px;
    margin-top: 10px;

    .summary-card {
      border-radius: 15px;
      width: 48%;
      height: 300px;
      background: #ffffff;

      &.card1 {
        flex: 1;
      }

      &.card2 {
        flex: 2;
      }

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
        flex-direction: row;
        row-gap: 30px;
        padding: 30px;
        background: #ffffff;
        column-gap: 10px;

        border-bottom-right-radius: 15px;
        border-bottom-left-radius: 15px;

        overflow-x: auto;

        .body-card {
          width: 273px;
          border: 1px solid #E6EAED;
          border-radius: 10px;


          .row1 {
            display: flex;
            column-gap: 10px;
            height: 90px;
            align-items: flex-start;
            padding: 20px;
            background-color: #ffffff;
            color: #000000;

            .row-left {
              display: flex;
              width: 20px;
              row-gap: 10px;

              img {
                width: 10px;
                height: 20px;


              }
            }

            .row-right {
              display: flex;
              flex-direction: column;
              row-gap: 10px;
              background-color: #ffffff;


              .left-row-header {
                display: flex;
                justify-content: flex-start;
                font-size: 16px;
                font-weight: 600;
              }

              .left-row-flex {
                display: flex;
                column-gap: 20px;

                .metrics {
                  display: flex;
                  flex-direction: column;
                  justify-content: flex-start;
                  align-items: flex-start;
                  row-gap: 10px;
                }


              }

            }
          }

          .row2 {
            height: 50px;
            background-color: #E6EAED;
            display: flex;
            color: #000000;

            column-gap: 10px;
            align-items: flex-start;
            padding: 20px;
            border-radius: 10px;

            .row-left {
              display: flex;
              width: 20px;
              row-gap: 10px;

              img {
                width: 10px;
                height: 20px;


              }
            }

            .row-right {
              display: flex;
              flex-direction: column;
              row-gap: 10px;
              justify-content: flex-start;
              align-items: flex-start;

              .icon-text {
                display: flex;
                column-gap: 5px;

                .icon {
                  display: flex;
                  justify-content: center;
                  align-items: center;
                  width: 35px;
                  height: 30px;
                  border: 1px solid #0BC32E;
                  border-radius: 1000px;
                  background-color: #ffffff;
                }

                .text {
                  font-size: 14px;
                  color: #0BC32E;
                  text-align: left;
                }
              }
            }
          }
        }
      }

      @media (max-width: 655px) {
        width: 100%;
        height: 100%;
      }
    }
  }
}


.box {
  width: calc(100% - 40px);
  height: 150px;
  background: var(--system-page-background);
}

.scrollbar-flex-content {
  display: flex;
}

.scrollbar-demo-item {
  flex-shrink: 0;
  display: flex;
  align-items: center;
  justify-content: center;
  // width: 100px;
  // height: 50px;
  margin: 10px;
  text-align: center;
  border-radius: 4px;
  background: var(--el-color-danger-light-9);
  color: var(--el-color-danger);
}


</style>
