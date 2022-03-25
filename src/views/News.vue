<template>
  <div class="container-fluid newsPage">
    <div class="row">
      <div class="col-12 px-0 newsBanner">
        <div class="clipart"></div>
      </div>
    </div>
    <div class="container newsWrapper pb-5">
      <div class="row">
        <div class="col-lg-4">
          <div class="newsFloatingImg">
            <img src="@/assets/images/newsFloating.png" width="100%" alt="">
          </div>
        </div>
        <div class="col-lg-8">
          <div class="row">
            <div class="col-md-6 mb-3" v-for="(v, k) in newsData" :key="k" @click="selectNews(k)">
              <div class="newsBlock">
                <div class="topImg">
                  <img :src="require('@/assets/images/'+v['imgName'])" alt="">
                </div>
                <div class="description">
                  <div class="currentDate">{{v['date']}}</div>
                  <div class="title">{{v['title']}}</div>
                </div>
              </div>
            </div>
          </div>
        </div>
      </div>
    </div>

    <b-modal v-model="showNewsModal" hide-footer hide-header>
      <img class="newsModalImg" :src="getImgUrl(selectedNews['imgName'])" alt="">
      <div class="modalDesc">
        <div class="title">{{selectedNews['title']}}</div>
        <div class="date">{{selectedNews['date']}}</div>
        <div class="content">{{selectedNews['desc']}}</div>
      </div>
    </b-modal>
  </div>
</template>

<script>
// @ is an alias to /src

export default {
  name: 'News',
  data: function() {
    return {
      newsData: [
        {imgName: 'news1.jpg', date: '22/03/2022', title: 'Lorem ipsum dolor sit amet', desc: 'Lorem ipsum dolor sit amet consectetur, adipisicing elit. Quam nam perferendis id hic, praesentium accusamus et fuga corporis earum amet commodi dolor, consequatur eos qui voluptate nisi doloribus suscipit neque.'},
        {imgName: 'news2.jpg', date: '23/03/2022', title: 'Lorem ipsum dolor sit amet', desc: 'Lorem ipsum dolor sit amet consectetur, adipisicing elit. Quam nam perferendis id hic, praesentium accusamus et fuga corporis earum amet commodi dolor, consequatur eos qui voluptate nisi doloribus suscipit neque.'},
        {imgName: 'news3.jpg', date: '25/03/2022', title: 'Lorem ipsum dolor sit amet', desc: 'Lorem ipsum dolor sit amet consectetur, adipisicing elit. Quam nam perferendis id hic, praesentium accusamus et fuga corporis earum amet commodi dolor, consequatur eos qui voluptate nisi doloribus suscipit neque.'},
        {imgName: 'news4.jpg', date: '26/03/2022', title: 'Lorem ipsum dolor sit amet', desc: 'Lorem ipsum dolor sit amet consectetur, adipisicing elit. Quam nam perferendis id hic, praesentium accusamus et fuga corporis earum amet commodi dolor, consequatur eos qui voluptate nisi doloribus suscipit neque.'},
      ],
      showNewsModal: false,
      selectedNews: {
        imgName: null,
        date: null,
        title: null,
        desc: null,
      }
    }
  },
  mounted: function() {
  },
  methods: {
    getImgUrl(pic) {
      if (pic)
        return require('@/assets/images/'+pic)

      else 
        return null
    },
    selectNews(ind) {
      this.selectedNews = this.newsData[ind]

      this.showNewsModal = true
    }
  }
}
</script>