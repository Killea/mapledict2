<template>
  <div
    id="app"
    style="text-align:left"
  >
    <div
      class="navbar"
      style="margin-top:10px"
    >
      <div style="margin-left:10px;">
        <span style="margin-right:10px">Search</span>

        <el-input
          v-model="myWord"
          placeholder
          style="width:50%"
          @keyup.enter.native="search"
        />

        <el-button
          type="primary"
          @click="search()"
          icon="el-icon-search"
          style="margin-left:10px"
        >
          Search
        </el-button>
      </div>
    </div>

    <div style="margin-top:58px">
      <div class="left">
        <el-card
          :body-style="{ padding: '0px' }"
          shadow="never"
          style="height:calc(100% - 56px);margin-left:4px;margin-bottom:2px"
        >
          <el-tree :data="treeData" />
        </el-card>
      </div>

      <div class="right">
        <div style="margin-left:4px;">
          <el-card
            :body-style="{ padding: '0px' }"
            shadow="never"
            style="margin-right:4px;margin-bottom:4px;"
          >
            <div style="margin-left:6px;margin-bottom:4px">
              <span>New word</span>

              <div style="margin-left:74px;margin-top:-18px">
                <el-rate v-model="star" />
              </div>
            </div>
          </el-card>

          <el-card
            :body-style="{ padding: '0px' }"
            shadow="never"
            style="margin-right:4px;margin-bottom:4px;"
          >
            <!--   @contextmenu.prevent="$refs.menu.open" 11-->
            <div
              class="text"
              id="text"
            >
              MapleDict
            </div>
          </el-card>
        </div>
      </div>
    </div>
  </div>
</template>

<script>

export default {
  components: {

  },
  data() {
    return {
      star: 0,
      treeData: [],
      items: [
        'Cras justo odio',
        'Dapibus ac facilisis in',
        'Morbi leo risus',
        'Porta ac consectetur ac',
        'Vestibulum at eros',
      ],
      myWord: '',
    };
  },
  methods: {
    searchSelected() {},
    search() {
      console.log(this.myWord);
    },
    menuRead() {},
    onClick(text) {
      alert(`You clicked ${text}!`);
    },
  },
  created() {},
  mounted() {},
  computed: {},
  watch: {},
};
</script>

<style>
#app {
  font-family: "Avenir", Helvetica, Arial, sans-serif;
  -webkit-font-smoothing: antialiased;
  -moz-osx-font-smoothing: grayscale;
  text-align: center;
  color: #2c3e50;
}

body {
  margin: 0;
}

.navbar {
  overflow: hidden;
  position: fixed;
  top: 0;
  width: 100%;
  background: white;
  height: 45px;
  z-index: 9999;
}

.left {
  width: 175px;
  height: 250px;

  position: fixed;
  height: calc(100vh - 8px);
}

.right {
  width: calc(100% - 175px);
  left: 175px;
  height: 600px;
  position: fixed;
  height: 100%;
}

.text {
  height: calc(100vh - 95px);
  margin-left: 5px;
  padding-right: 5px;
  overflow-y: auto;
  overflow-x: hidden;
}
</style>
