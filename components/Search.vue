<template>
  <div class="m_container">
    <!--大湾区入口-->
    <div class="dw_inlet">
      <router-link to="http://hk.centanet.com/greater-bay-area/?lang=zh"
        ><img src="~/assets/dw_inlet.png"
      /></router-link>
    </div>
    <!--搜索-->
    <div class="b_box">
      <!--搜索导航-->
      <div class="i-newsearch">
        <div class="i-tip-search">樓盤搜索</div>
        <div class="i-newsearch-labelPanel">
          <div class="i-newsearch-labes">
            <div data-area-index="1" class="i-newsearch-label active">澳門</div>
            <div data-area-index="2" class="i-newsearch-label">氹仔</div>
            <div data-area-index="3" class="i-newsearch-label">路環</div>
          </div>
        </div>
        <div class="i-newsearch-wrap">
          <form id="searchForm" action="/testmacau/Project/Searchs">
            <input
              type="text"
              id="text-staff"
              autocomplete="off"
              name="Building"
              class="i-newsearch-search"
              placeholder="請輸入樓盤名稱/經紀人"
            />
            <input type="hidden" id="hl_areas" name="areas" />
            <input type="hidden" id="hl_pItemType" name="pItemType" value="" />
            <span id="searchSubmit" class="i-newsearch-button">
              <img src="~/assets/c-search3.jpg" />
            </span>
          </form>
        </div>
      </div>
      <!-- 轮播 -->
      <div class="lun_bo">
        <el-carousel indicator-position="outside">
          <el-carousel-item v-for="item in pic" :key="item">
            <img :src="item.img" alt="" srcset="" />
          </el-carousel-item>
        </el-carousel>
      </div>
    </div>
    <!-- 大图标导航 -->
    <div class="big_pic">
      <div class="b_content">
        <router-link to="" class="l_home">
          <i class="el-icon-edit l_home_icon"></i>
          <div class="l_home_text">
            <div>筍盤推介</div>
            <div>為您搜羅全澳筍盤</div>
          </div>
        </router-link>
      </div>
    </div>
  </div>
</template>

<script>
export default {
  data() {
    return {
      pic: [{ img: require("../assets/banner.jpg") }],
    };
  },
};
</script>

<style lang="scss" scoped>
.m_container {
  position: relative;
  display: flex;
  justify-content: center;
  flex-wrap: wrap;
  width: 100%;
  height: 100%;
  .dw_inlet {
    position: fixed;
    top: 80%;
    right: 52px;
    z-index: 999;
  }
  .b_box {
    position: relative;
    display: flex;
    justify-content: center;
    align-content: center;
    flex-wrap: wrap;
    width: 100%;
    height: 464px;
    // border: 1px solid pink;
    .i-newsearch {
      background: rgba(0, 0, 0, 0.3);
      border-radius: 5px;
      box-shadow: #464343 5px 5px 15px;
      width: 720px;
      height: 200px;
      padding: 40px 0 0 40px;
      display: inline-block;
      vertical-align: middle;
      text-align: left;
      color: white;
      background: rgba(0, 0, 0, 0.3);
      border-radius: 5px;
      box-shadow: #464343 5px 5px 15px;
      z-index: 11;
      .i-tip-search {
        font-size: 30px;
        letter-spacing: 2px;
      }
      .i-newsearch-labelPanel {
        width: 720px;
        height: 36px;
        margin-top: 17px;
        z-index: 123;
        position: relative;
        .i-newsearch-labes {
          float: left;
          height: 36px;
          line-height: 36px;
          font-size: 15px;
          position: relative;
          .i-newsearch-label {
            float: left;
            padding: 0 10px;
            font-size: 15px;
            color: #fff;
            text-decoration: none;
            cursor: pointer;
          }
          .i-newsearch-label.active {
            background: #df2f30;
            border-radius: 3px;
          }
        }
      }
      .i-newsearch-wrap {
        width: 720px;
        height: 42px;
        margin-top: 10px;
        z-index: 777;
        .i-newsearch-search {
          box-sizing: border-box;
          float: left;
          width: 610px;
          height: 42px;
          line-height: 42px;
          color: #888;
          overflow: hidden;
          border: 0;
          font-size: 14px;
          text-indent: 10px;
          overflow: hidden;
          background-color: white;
          outline: none;
          font-family: "Microsoft Yahei";
        }
        .i-newsearch-button {
          text-align: center;
          padding-top: 2px;
        }
        .i-newsearch-button {
          box-sizing: border-box;
          float: left;
          cursor: pointer;
          border: 0;
          width: 60px;
          height: 42px;
          line-height: 42px;
          outline: none;
          background-color: #da1617;
          border-top-right-radius: 4px;
          border-bottom-right-radius: 4px;
          display: flex;
          align-items: center;
          justify-content: center;
        }
      }
    }
    .i-newserach {
      position: relative;
      z-index: 11;
    }
    .lun_bo {
      position: absolute;
      top: auto;
      width: 100%;
      height: 477px;
      /deep/ .el-carousel__container {
        position: relative;
        display: flex;
        justify-content: center;
        align-items: center;
        width: 100%;
        height: 477px;
      }
      /deep/.el-carousel__indicator--horizontal {
        display: none;
        // padding: 12px 4px;
      }
      .el-carousel__item {
        display: flex;
        justify-content: center;
        align-items: center;
      }
      .el-carousel__item h3 {
        color: #475669;
        font-size: 18px;
        opacity: 0.75;
        line-height: 300px;
        margin: 0;
      }

      .el-carousel__item:nth-child(2n) {
        background-color: #99a9bf;
      }

      .el-carousel__item:nth-child(2n + 1) {
        background-color: #d3dce6;
      }
    }
  }
  .big_pic {
    position: relative;
    margin-top: 15px;
    height: 104px;
    padding-top: 21px;
    padding-bottom: 21px;
    display: flex;
    justify-content: center;
    width: 100%;
    // border: 1px solid blue;
    .b_content {
      display: flex;
      justify-content: space-between;
      width: 1290px;
      margin: 0 auto;
      .l_home {
        display: flex;
        justify-content: center;
        align-items: center;
        text-decoration:none;
        .l_home_icon {
          display: flex;
          justify-content: center;
          align-items: center;
          font-size: 46px;
          border-radius: 50%;
          width: 81px;
          height: 81px;
          border: 1px solid;
        }
        .l_home_text {
          font-size: 20px;
          padding-left: 42px;
         div:nth-child(0){
           font-size: 14px;
         }
        }
      }
    }
  }
}
</style>