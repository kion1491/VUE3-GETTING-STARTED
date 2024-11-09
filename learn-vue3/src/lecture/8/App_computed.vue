<template>
  <div>
    <h2>
      {{ teacher.name }}
    </h2>
    <h3>강의가 있습니까?</h3>
    <!-- 아래처럼 직접 콧수염 안에서 모든 함수를 동작한다면, 매우매우 코드가 복잡해지겠지. -->
    <!-- <p>{{ teacher.lectures.length > 0 ? "있음" : "없음" }}</p> -->

    <!-- 그래서 사용하는게 computed라는 개념이다! -->
    <p>{{ hasLecturesCheck }}</p>

    <!-- computed가 아닌 일반적인 method를 사용해도 된다. 뒤에 괄호 붙여서 호출해야한다.-->
    <p>{{ existLecturesCheck() }}</p>

    <hr />

    <h2>Computed와 일반적인 method의 차이점은?</h2>
    <p>
      동작 자체는 같아보이지만, Computed는 해당 동작의 결과값을 캐싱을 해서
      가지고 있기 때문에, 효율성 측면에서 더 좋다!
    </p>

    <hr />

    <h2>Computed는 기본적으로 getter 전용이다!</h2>
    <p>계산된 속성값에 새로운 값을 할당하려고 하면 런타임 경고가 뜬다.</p>
    <p>setter를 직접 제공해서 새로 계산된 속성을 넣어줄 수도 있다.</p>
    <h3>이름은,</h3>
    <p>{{ fullName }}</p>
  </div>
</template>

<script>
import { computed, reactive, ref } from "vue";
export default {
  setup() {
    const teacher = reactive({
      name: "카이온",
      lectures: ["HTML/CSS", "JS", "Vue3"],
    });

    const hasLecturesCheck = computed(() => {
      return teacher.lectures.length > 0 ? "있음" : "없음";
    });
    const existLecturesCheck = () =>
      teacher.lectures.length > 0 ? "있음" : "없음";

    const firstName = ref("홍");
    const lastName = ref("길동");
    const fullName = computed({
      get() {
        return firstName.value + " " + lastName.value;
      },
      set(value) {
        [firstName.value, lastName.value] = value.split(" ");
        // const [first, last] = value.split("");
      },
    });
    fullName.value = "카 이온";

    return {
      teacher,
      hasLecturesCheck,
      existLecturesCheck,
      fullName,
    };
  },
};
</script>

<style lang="scss" scoped></style>
