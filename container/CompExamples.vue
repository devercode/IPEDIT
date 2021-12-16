<template>
  <div class="examples">
    <div class="contentt examples__container container">
      <div v-for="(item, index) in data" :key="index" class="cardd exmodule">
        <div
          class="front"
          v-bind:style="{ backgroundImage: 'url(' + item.background + ')' }"
        >
          <div class="module-text">
            <div class="img-icon">
              <img v-bind:src="item.img" v-bind:alt="item.img" />
            </div>
            <div class="text">
              <p>{{ item.text_1 }}</p>
              <p>{{ item.text_2 }}</p>
            </div>
          </div>
        </div>
        <div class="back">
          <div>
            <p>{{ item.text_3 }}</p>
            <p>{{ item.text_4 }}</p>
            <p>{{ item.text_5 }}</p>
          </div>
        </div>
      </div>
    </div>
  </div>
</template>

<style lang="scss" scoped>
@import "../assets/stylesheets/compExamples.scss";
</style>

<script>
import Banner1 from "../assets/images/example1.svg";
import Banner2 from "../assets/images/example2.svg";
import Banner3 from "../assets/images/example3.svg";
import Banner4 from "../assets/images/example4.svg";
import Banner5 from "../assets/images/example5.svg";
import Banner6 from "../assets/images/example6.svg";
import icon1 from "../assets/images/iconExample1.svg";
import icon2 from "../assets/images/iconExample2.svg";
import icon3 from "../assets/images/iconExample3.svg";
import icon4 from "../assets/images/iconExample4.svg";
import icon5 from "../assets/images/iconExample5.svg";
import icon6 from "../assets/images/iconExample6.svg";
export default {
  data() {
    return {
      data: [
        {
          background: Banner1,
          img: icon1,
          text_1: "최적화된",
          text_2: "UI/UX",
          text_3:
            "와이 아이피에딧 영역에서 마우스 오버 시 카드가 뒤집히는 애니메이션이 구현되며 뒷면에 자세한 소개가 나옵니다.",
          text_4:
            "뒷면은 한 문단으로 소개하기보다 두세가지 항목으로 구분하면 좋겠습니다. 각 항목의 글자는 띄어쓰기 포함 50~80글자가 가장 보기 좋습니다.",
          text_5: "",
        },
        {
          background: Banner2,
          img: icon2,
          text_1: "안전한",
          text_2: "데이터 저장",
          text_3:
            "항목이 세가지일 때는 각 항목의 글자 수가 조금씩 줄어드는데, 약 25~45글자",
          text_4:
            "정도면 충분합니다. 짧으면서 여러가지를 소개해야 할 기능에 적합합니다.",
          text_5:
            "한줄에 대략 20글자 정도이며, 적어도 한줄 이상은 되어야 보기 좋습니다.",
        },
        {
          background: Banner3,
          img: icon3,
          text_1: "자동완성",
          text_2: "기능",
          text_3:
            "Lorem ipsum dolor sit amet, consectetur adipiscing elit. Cras in posuere lorem. Pellentesque quis augue sit amet arcu vehicula.",
          text_4:
            "Nulla interdum a nulla eu blandit. Nulla at eros non lorem elementum convallis. Proin pharetra nulla tortor, quis scelerisque nulla auctor et.",
          text_5: "",
        },
        {
          background: Banner4,
          img: icon4,
          text_1: "AI",
          text_2: "어시스턴트",
          text_3:
            "Nullam enim enim, eleifend nec odio in, interdum gravida neque.",
          text_4:
            "Praesent ac pharetra mi, at posuere libero. Donec ut ex ac nibh.",
          text_5:
            "Morbi dictum bibendum faucibus. Aliquam sit amet bibendum neque.",
        },
        {
          background: Banner5,
          img: icon5,
          text_1: "빅데이터",
          text_2: "데이터베이스",
          text_3:
            "代タヲハヤ品退日もか話返じ講貿きぐレう写就モクオ獲名リヘウア鳴載98時名づざ中含れけ芸亡るづリ日守ヨニツ義憲伎ル。",
          text_4:
            "掲問なやンか再政政で投本未メケツサ室引ヲハノ元中レトシコ続1毎宿す反6行ぶき場相るくめよ独写ヲスヱマ固格ふぞぱ業会郎吸ほさなを。",
          text_5: "",
        },
        {
          background: Banner6,
          img: icon6,
          text_1: "읽기 편한",
          text_2: "결과물",
          text_3:
            "擢雲またらよカアロニナウゆれう、すそ他譜以こほくきそた尾譜鵜。",
          text_4: "露遊やそ尾名樹以ょゆ派模絵日トカトソハョ根列舳雲、な。",
          text_5: "さおつすろこむれみ手目区毛くいヘヨホカリチす保尾露とゅ。",
        },
      ],
    };
  },
  components: {},
};
</script>