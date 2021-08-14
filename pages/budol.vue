<template>
  <div class="pb-14">
    <div class="container mx-auto px-5 sm:px-6 lg:px-8">
      <div class="md:ml-20">
        <div class="py-5">
          <nuxt-link to="/">
            <svg
              xmlns="http://www.w3.org/2000/svg"
              class="h-6 w-6"
              fill="none"
              viewBox="0 0 24 24"
              stroke="currentColor"
            >
              <path
                stroke-linecap="round"
                stroke-linejoin="round"
                stroke-width="2"
                d="M11 19l-7-7 7-7m8 14l-7-7 7-7"
              />
            </svg>
          </nuxt-link>
        </div>

        <div class="grid items-center justify-center space-x-4 mt-5">
          <img
            src="../assets/tatwina4.jpg"
            class="
              mx-auto
              rounded-full
              h-16
              w-16
              shadow-md
              ring-4 ring-pink-200
              flex-shrink-0
            "
            alt=""
          />

          <h1 class="text-4xl font-bold text-gray-600">
            &#128717; Budol &#128717;
          </h1>
        </div>

        <div class="relative my-5">
          <div class="absolute inset-0 flex items-center" aria-hidden="true">
            <div class="w-full border-t border-gray-300"></div>
          </div>
          <div class="relative flex justify-center">
            <span
              v-cloak
              v-show="tab == 'clothing'"
              class="px-2 bg-red-50 text-gray-600"
            >
              &#128090; Clothing &#128090;</span
            >
            <span
              v-cloak
              v-show="tab == 'accessories'"
              class="px-2 bg-red-50 text-gray-600"
            >
              &#127878; Accessories &#127878;</span
            >
            <span
              v-cloak
              v-show="tab == 'others'"
              class="px-2 bg-red-50 text-gray-600"
            >
              &#128536; Others &#128536;</span
            >
          </div>
        </div>
        <div>
          <!--
          Slide-over panel, show/hide based on slide-over state.

          Entering: "transform transition ease-in-out duration-500 sm:duration-700"
            From: "translate-x-full"
            To: "translate-x-0"
          Leaving: "transform transition ease-in-out duration-500 sm:duration-700"
            From: "translate-x-0"
            To: "translate-x-full"
        -->

          <!-- clothing -->

          <div
            v-cloak
            v-show="tab == 'clothing'"
            class="bg-white rounded-md shadow"
          >
            <div
              class="
                max-w-2xl
                mx-auto
                py-16
                px-4
                sm:py-24 sm:px-6
                lg:max-w-7xl lg:px-8
              "
            >
              <div
                class="
                  mt-6
                  grid grid-cols-1
                  gap-y-10 gap-x-6
                  sm:grid-cols-2
                  lg:grid-cols-4
                  xl:gap-x-8
                "
              >
                <!--  -->
                <div v-for="clothing in clothings" :key="clothing.name">
                  <Clothing :clothing="clothing" />
                  <hr class="block sm:hidden" />
                </div>
                <!--  -->

                <!-- More products... -->
              </div>
            </div>
          </div>

          <!-- accessories -->

          <div
            v-cloak
            v-show="tab == 'accessories'"
            class="bg-white rounded-md shadow"
          >
            <div
              class="
                max-w-2xl
                mx-auto
                py-16
                px-4
                sm:py-24 sm:px-6
                lg:max-w-7xl lg:px-8
              "
            >
              <div
                class="
                  mt-6
                  grid grid-cols-1
                  gap-y-10 gap-x-6
                  sm:grid-cols-2
                  lg:grid-cols-4
                  xl:gap-x-8
                "
              >
                <!--  -->
                <div v-for="accessory in accessories" :key="accessory.accs">
                  <Accessories :accessory="accessory" />
                </div>
                <!--  -->

                <!-- More products... -->
              </div>
            </div>
          </div>

          <!-- others -->
          <div
            v-cloak
            v-show="tab == 'others'"
            class="bg-white rounded-md shadow"
          >
            <div
              class="
                max-w-2xl
                mx-auto
                py-16
                px-4
                sm:py-24 sm:px-6
                lg:max-w-7xl lg:px-8
              "
            >
              <div
                class="
                  mt-6
                  grid grid-cols-1
                  gap-y-10 gap-x-6
                  sm:grid-cols-2
                  lg:grid-cols-4
                  xl:gap-x-8
                "
              >
                <!--  -->
                <div v-for="other in others" :key="other.name">
                  <Other :other="other" />
                </div>
                <!--  -->
              </div>
            </div>
          </div>
        </div>
      </div>
    </div>
    <BudolTab class="fixed bottom-0 bg-red-50" v-on:tabFromChild="newTab" />
  </div>
</template>

<script>
import Clothing from '../components/Clothing.vue'
import BudolTab from '../components/BudolTab.vue'
import Accessory from '../components/Accessories.vue'
import Other from '../components/Others.vue'

export default {
  transition: 'page',
  components: {
    Clothing,
    BudolTab,
    Accessory,
    Other,
  },

  methods: {
    newTab(tab) {
      this.tab = tab
    },
  },

  data() {
    return {
      tab: 'clothing',
      clothings: [
        {
          name: 'Black Coordinates',
          description: ' Cropped Hoodie and Skirt',
          url: 'https://sea-m.yoins.com/YOINS-Letter-Hooded-Long-Sleeves-Top---Skirt-Set-p-1801861.html?utm_source=mopubipro_tommy&utm_campaign=ios-share&utm_medium=none&utm_content=agent&utm_design=-&ios_share=1&_i=I8hxaEWxibwkZkdkTplDyj1vF3V%2B7CkLrF%2F3CMDlWX6zOkCes7FEMvvFzN%2FhtmZY&_branch_match_id=953209404634762276',
          imgUrl:
            'https://images.chiccdn.com/thumb/zoom//oaupload/yoins/images/24/DC/5e5184a2-861c-4d7e-a403-243c1f663e5f.jpg',
        },

        {
          name: 'Black cut out long sleeve',
          description: 'Tie up design',
          url: 'https://sea-m.yoins.com/Black-Cut-Out-Design-Round-Neck-Long-Sleeves-Tee-p-1575516.html?utm_source=mopubipro_tommy&utm_campaign=ios-share&utm_medium=none&utm_content=agent&utm_design=-&ios_share=1&_i=WLtRdMNI%2FomxNowBta%2B4kgAUQnYnZjfJN4mVt7rBdBfeAylN5Gxnupnp8CtcplXg&_branch_match_id=953209404634762276',
          imgUrl:
            'https://images.chiccdn.com/thumb/zoom//oaupload/yoins/images/8C/7B/59d367cd-9259-4c78-b578-50ea52f74008.jpeg',
        },
        {
          name: 'Lettuce type coordinates',
          description: 'White shirt and skirt',
          url: 'https://sea-m.yoins.com/Lettuce-edge-Design-Letter-Short-Sleeves-Two-Pieces-Outfit-p-1814269.html?utm_source=mopubipro_tommy&utm_campaign=ios-share&utm_medium=none&utm_content=agent&utm_design=-&ios_share=1&_i=WLtRdMNI%2FomxNowBta%2B4kgAUQnYnZjfJN4mVt7rBdBfeAylN5Gxnupnp8CtcplXg&_branch_match_id=953209404634762276',
          imgUrl:
            'https://images.chiccdn.com/thumb/zoom//oaupload/yoins/images/B0/57/eeb28d86-6ec6-4704-8567-85ed9db50231.jpg',
        },
        {
          name: 'Piosonous snake crop top',
          description: '',
          url: 'https://sea-m.yoins.com/YOINS-Dark-Grey-Snake-Graphic-Letter-Print-Crew-Neck-Short-Sleeves-Tee-p-1829458.html?utm_source=mopubipro_tommy&utm_campaign=ios-share&utm_medium=none&utm_content=agent&utm_design=-&ios_share=1&_i=WLtRdMNI%2FomxNowBta%2B4kgAUQnYnZjfJN4mVt7rBdBfeAylN5Gxnupnp8CtcplXg&_branch_match_id=953209404634762276',
          imgUrl:
            'https://images.chiccdn.com/thumb/zoom//oaupload/yoins/images/5A/B4/d29d49c2-4f2b-44ca-a3dc-71a68e762db0.jpg',
        },
        {
          name: 'White off shoulder long sleeve',
          description: '',
          url: 'https://sea-m.yoins.com/YOINS-Plain-Off-The-Shoulder-Long-Sleeves-Blouse-p-1828596.html?utm_source=mopubipro_tommy&utm_campaign=ios-share&utm_medium=none&utm_content=agent&utm_design=-&ios_share=1&_i=WLtRdMNI%2FomxNowBta%2B4kgAUQnYnZjfJN4mVt7rBdBfeAylN5Gxnupnp8CtcplXg&_branch_match_id=953209404634762276',
          imgUrl:
            'https://images.chiccdn.com/thumb/zoom//oaupload/yoins/images/20/0C/b8563bd7-bec4-4d83-95df-d4e36e4210cc.jpeg',
        },
        {
          name: 'Mocha brown crop top',
          description: '',
          url: 'https://shopee.ph/product/11113506/7455882037?smtt=0.315498918-1628580010.9&utm_source=an_13204220000&utm_medium=affiliates&utm_campaign=-&utm_content=f11f2a30f93011eb95258d14c7c37d71-117601-00090--&af_siteid=an_13204220000&pid=affiliates&af_click_lookback=7d&af_viewthrough_lookback=1d&is_retargeting=true&af_reengagement_window=7d&af_sub_siteid=f11f2a30f93011eb95258d14c7c37d71-117601-00090--&c=-',
          imgUrl: 'https://cf.shopee.ph/file/38a2ac5cc215445e2313b5b9807f40af',
        },
        {
          name: 'Plain white crop top',
          description: '',
          url: 'https://shopee.ph/product/25587666/9141254695?smtt=0.315498918-1628580953.9&utm_source=an_13204220000&utm_medium=affiliates&utm_campaign=-&utm_content=f11f2a30f93011eb95258d14c7c37d71-117611-00090--&af_siteid=an_13204220000&pid=affiliates&af_click_lookback=7d&af_viewthrough_lookback=1d&is_retargeting=true&af_reengagement_window=7d&af_sub_siteid=f11f2a30f93011eb95258d14c7c37d71-117611-00090--&c=-',
          imgUrl: 'https://cf.shopee.ph/file/1952d763ea210e2a1a30b13f166512d7',
        },
        {
          name: 'Oversize sweatshits',
          description: 'got this in black, white and gray',
          url: 'https://shopee.ph/product/39469478/5378240973?smtt=0.315498918-1628580744.9&utm_source=an_13204220000&utm_medium=affiliates&utm_campaign=-&utm_content=f11f2a30f93011eb95258d14c7c37d71-117608-00090--&af_siteid=an_13204220000&pid=affiliates&af_click_lookback=7d&af_viewthrough_lookback=1d&is_retargeting=true&af_reengagement_window=7d&af_sub_siteid=f11f2a30f93011eb95258d14c7c37d71-117608-00090--&c=-',
          imgUrl: 'https://cf.shopee.ph/file/e2cdff541f3dd01be3ba1d79a3d52b9a',
        },
        {
          name: 'Khaki sweater',
          description: '',
          url: 'https://shopee.ph/product/36128470/3957796326?smtt=0.315498918-1628581526.9&utm_source=an_13204220000&utm_medium=affiliates&utm_campaign=-&utm_content=f11f2a30f93011eb95258d14c7c37d71-117622-00090--&af_siteid=an_13204220000&pid=affiliates&af_click_lookback=7d&af_viewthrough_lookback=1d&is_retargeting=true&af_reengagement_window=7d&af_sub_siteid=f11f2a30f93011eb95258d14c7c37d71-117622-00090--&c=-',
          imgUrl: 'https://cf.shopee.ph/file/88a0a6ae747e53f015d27f4ff2bed7b8',
        },
        {
          name: 'Jennie inspired: knitted cropped cardigan',
          description: 'got this in white & beige',
          url: 'https://shopee.ph/product/216736857/9714576870?smtt=0.315498918-1628580874.9&utm_source=an_13204220000&utm_medium=affiliates&utm_campaign=-&utm_content=f11f2a30f93011eb95258d14c7c37d71-117610-00090--&af_siteid=an_13204220000&pid=affiliates&af_click_lookback=7d&af_viewthrough_lookback=1d&is_retargeting=true&af_reengagement_window=7d&af_sub_siteid=f11f2a30f93011eb95258d14c7c37d71-117610-00090--&c=-',
          imgUrl: 'https://cf.shopee.ph/file/6658ac72ae1feba375a7c7375f0e1763',
        },
        {
          name: 'Jennie inspired: knitted open button top',
          description: 'got this in white, green and pink',
          url: 'https://shopee.ph/product/25717546/7543788697?smtt=0.315498918-1628581759.9&utm_source=an_13204220000&utm_medium=affiliates&utm_campaign=-&utm_content=f11f2a30f93011eb95258d14c7c37d71-117625-00090--&af_siteid=an_13204220000&pid=affiliates&af_click_lookback=7d&af_viewthrough_lookback=1d&is_retargeting=true&af_reengagement_window=7d&af_sub_siteid=f11f2a30f93011eb95258d14c7c37d71-117625-00090--&c=-',
          imgUrl: 'https://cf.shopee.ph/file/636db91a43f03c22b3f6609c899d3c42',
        },
        {
          name: 'puffed sleeve top',
          description: 'got this black',
          url: 'https://shopee.ph/product/269998620/5050686667?smtt=0.315498918-1628581618.9&utm_source=an_13204220000&utm_medium=affiliates&utm_campaign=-&utm_content=f11f2a30f93011eb95258d14c7c37d71-117623-00090--&af_siteid=an_13204220000&pid=affiliates&af_click_lookback=7d&af_viewthrough_lookback=1d&is_retargeting=true&af_reengagement_window=7d&af_sub_siteid=f11f2a30f93011eb95258d14c7c37d71-117623-00090--&c=-',
          imgUrl: 'https://cf.shopee.ph/file/40a1e51071eb3122aec08c5096e269f9',
        },
        {
          name: 'Argyle sweater',
          description: '',
          url: 'https://shopee.ph/product/321867635/6259616697?smtt=0.315498918-1628581678.9&utm_source=an_13204220000&utm_medium=affiliates&utm_campaign=-&utm_content=f11f2a30f93011eb95258d14c7c37d71-117624-00090--&af_siteid=an_13204220000&pid=affiliates&af_click_lookback=7d&af_viewthrough_lookback=1d&is_retargeting=true&af_reengagement_window=7d&af_sub_siteid=f11f2a30f93011eb95258d14c7c37d71-117624-00090--&c=-',
          imgUrl: 'https://cf.shopee.ph/file/99ab0fa0dd467a28a592ea73629819d3',
        },
        {
          name: 'high waist baggy jeans ',
          description: 'got this in all colors/shades',
          url: 'https://shopee.ph/product/60978656/7472486744?smtt=0.315498918-1628581339.9&utm_source=an_13204220000&utm_medium=affiliates&utm_campaign=-&utm_content=f11f2a30f93011eb95258d14c7c37d71-117619-00090--&af_siteid=an_13204220000&pid=affiliates&af_click_lookback=7d&af_viewthrough_lookback=1d&is_retargeting=true&af_reengagement_window=7d&af_sub_siteid=f11f2a30f93011eb95258d14c7c37d71-117619-00090--&c=-',
          imgUrl: 'https://cf.shopee.ph/file/7931ab87423550113bed6a1614404006',
        },
      ],
      accessories: [
        {
          accs: 'Initial Necklace',
          desc: '',
          accsUrl:
            'https://shopee.ph/product/411274059/4986209965?smtt=0.315498918-1628580229.9&utm_source=an_13204220000&utm_medium=affiliates&utm_campaign=-&utm_content=f11f2a30f93011eb95258d14c7c37d71-117602-00090--&af_siteid=an_13204220000&pid=affiliates&af_click_lookback=7d&af_viewthrough_lookback=1d&is_retargeting=true&af_reengagement_window=7d&af_sub_siteid=f11f2a30f93011eb95258d14c7c37d71-117602-00090--&c=-',
          accsImgUrl:
            'https://cf.shopee.ph/file/14e29e74259ec82a19ee6c8b1330b732',
        },
        {
          accs: 'Rastaclat dupes',
          desc: 'got this in black and off white',
          accsUrl:
            'https://shopee.ph/product/103479086/6346993027?smtt=0.315498918-1628581124.9&utm_source=an_13204220000&utm_medium=affiliates&utm_campaign=-&utm_content=f11f2a30f93011eb95258d14c7c37d71-117615-00090--&af_siteid=an_13204220000&pid=affiliates&af_click_lookback=7d&af_viewthrough_lookback=1d&is_retargeting=true&af_reengagement_window=7d&af_sub_siteid=f11f2a30f93011eb95258d14c7c37d71-117615-00090--&c=-',
          accsImgUrl:
            'https://cf.shopee.ph/file/45d8712650fc5a89ef496f0ae3dd00a1',
        },
        {
          accs: 'Retro cat eye sunglasses',
          desc: '',
          accsUrl:
            'https://shopee.ph/product/162341146/7075198640?smtt=0.315498918-1628580643.9&utm_source=an_13204220000&utm_medium=affiliates&utm_campaign=-&utm_content=f11f2a30f93011eb95258d14c7c37d71-117607-00090--&af_siteid=an_13204220000&pid=affiliates&af_click_lookback=7d&af_viewthrough_lookback=1d&is_retargeting=true&af_reengagement_window=7d&af_sub_siteid=f11f2a30f93011eb95258d14c7c37d71-117607-00090--&c=-',
          accsImgUrl:
            'https://cf.shopee.ph/file/b80f4a6ddccf04b03b62dfb157aa0ad7',
        },

        {
          accs: 'Ear hook for eyeglass wearers ',
          desc: '',
          accsUrl:
            'https://shopee.ph/product/157000812/4140822553?smtt=0.315498918-1628581013.9&utm_source=an_13204220000&utm_medium=affiliates&utm_campaign=-&utm_content=f11f2a30f93011eb95258d14c7c37d71-117612-00090--&af_siteid=an_13204220000&pid=affiliates&af_click_lookback=7d&af_viewthrough_lookback=1d&is_retargeting=true&af_reengagement_window=7d&af_sub_siteid=f11f2a30f93011eb95258d14c7c37d71-117612-00090--&c=-',
          accsImgUrl:
            'https://cf.shopee.ph/file/4c3f68421dd8a6002a8415fe1e2fbd9d',
        },

        {
          accs: 'Hair calms',
          desc: '',
          accsUrl:
            'https://shopee.ph/product/140216258/4160093979?smtt=0.315498918-1628581243.9&utm_source=an_13204220000&utm_medium=affiliates&utm_campaign=-&utm_content=f11f2a30f93011eb95258d14c7c37d71-117617-00090--&af_siteid=an_13204220000&pid=affiliates&af_click_lookback=7d&af_viewthrough_lookback=1d&is_retargeting=true&af_reengagement_window=7d&af_sub_siteid=f11f2a30f93011eb95258d14c7c37d71-117617-00090--&c=-',
          accsImgUrl:
            'https://cf.shopee.ph/file/e44945091f297b44b38ca0fb7483f548',
        },
        {
          accs: 'Rectangular Hair calms',
          desc: '',
          accsUrl:
            'https://shopee.ph/product/140216258/6658442666?smtt=0.315498918-1628581286.9&utm_source=an_13204220000&utm_medium=affiliates&utm_campaign=-&utm_content=f11f2a30f93011eb95258d14c7c37d71-117618-00090--&af_siteid=an_13204220000&pid=affiliates&af_click_lookback=7d&af_viewthrough_lookback=1d&is_retargeting=true&af_reengagement_window=7d&af_sub_siteid=f11f2a30f93011eb95258d14c7c37d71-117618-00090--&c=-',
          accsImgUrl:
            'https://cf.shopee.ph/file/ce0a0f98f66a6976ae4386ebfb3be4e4',
        },
        {
          accs: 'crocodile skin mumu bags',
          desc: '',
          accsUrl:
            'https://shopee.ph/product/165806482/4738526508?smtt=0.315498918-1628581467.9&utm_source=an_13204220000&utm_medium=affiliates&utm_campaign=-&utm_content=f11f2a30f93011eb95258d14c7c37d71-117621-00090--&af_siteid=an_13204220000&pid=affiliates&af_click_lookback=7d&af_viewthrough_lookback=1d&is_retargeting=true&af_reengagement_window=7d&af_sub_siteid=f11f2a30f93011eb95258d14c7c37d71-117621-00090--&c=-',
          accsImgUrl:
            'https://cf.shopee.ph/file/9ff10251e76f9fb12d2ea9c3993286b7',
        },
      ],
      others: [
        {
          name: 'LED Lights',
          decs: '',
          url: 'https://shopee.ph/product/298217184/3749280264?smtt=0.315498918-1628580465.9&utm_source=an_13204220000&utm_medium=affiliates&utm_campaign=-&utm_content=f11f2a30f93011eb95258d14c7c37d71-117604-00090--&af_siteid=an_13204220000&pid=affiliates&af_click_lookback=7d&af_viewthrough_lookback=1d&is_retargeting=true&af_reengagement_window=7d&af_sub_siteid=f11f2a30f93011eb95258d14c7c37d71-117604-00090--&c=-',
          imgUrl: 'https://cf.shopee.ph/file/0a9dec5f922cf01f499dc2fea8213ef8',
        },

        {
          name: 'Sunset lamp (sunset red)',
          decs: '',
          url: 'https://shopee.ph/product/432272549/11400478731?smtt=0.315498918-1628580801.9&utm_source=an_13204220000&utm_medium=affiliates&utm_campaign=-&utm_content=f11f2a30f93011eb95258d14c7c37d71-117609-00090--&af_siteid=an_13204220000&pid=affiliates&af_click_lookback=7d&af_viewthrough_lookback=1d&is_retargeting=true&af_reengagement_window=7d&af_sub_siteid=f11f2a30f93011eb95258d14c7c37d71-117609-00090--&c=-',
          imgUrl: 'https://cf.shopee.ph/file/d8136ca82f8b42e30724cf3877b5c08f',
        },

        {
          name: 'Mini sunset lamp (yellow)',
          decs: '',
          url: 'https://shopee.ph/product/60431423/6679927603?smtt=0.315498918-1628581073.9&utm_source=an_13204220000&utm_medium=affiliates&utm_campaign=-&utm_content=f11f2a30f93011eb95258d14c7c37d71-117614-00090--&af_siteid=an_13204220000&pid=affiliates&af_click_lookback=7d&af_viewthrough_lookback=1d&is_retargeting=true&af_reengagement_window=7d&af_sub_siteid=f11f2a30f93011eb95258d14c7c37d71-117614-00090--&c=-',
          imgUrl: 'https://cf.shopee.ph/file/7ca268fdfc6e8cd1b7de41fd00996804',
        },

        {
          name: 'Adjustable buttons ',
          decs: '',
          url: 'https://shopee.ph/product/262845064/5441546929?smtt=0.315498918-1628581181.9&utm_source=an_13204220000&utm_medium=affiliates&utm_campaign=-&utm_content=f11f2a30f93011eb95258d14c7c37d71-117616-00090--&af_siteid=an_13204220000&pid=affiliates&af_click_lookback=7d&af_viewthrough_lookback=1d&is_retargeting=true&af_reengagement_window=7d&af_sub_siteid=f11f2a30f93011eb95258d14c7c37d71-117616-00090--&c=-',
          imgUrl: 'https://cf.shopee.ph/file/d70690fefe34f33d49914989e29663a4',
        },
      ],
    }
  },
}
</script>

<style>
.page-enter-active,
.page-leave-active {
  transition-property: opacity;
  transition-timing-function: ease-in-out;
  transition-duration: 300ms;
}
.page-enter,
.page-leave-to {
  opacity: 0;
}
body {
  background-color: #fef2f2;
}
</style>
