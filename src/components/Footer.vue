<template>
  <div class="footer">
    <div class="first">
      <span class="footer__gray">© 2003–2020, ООО «Кострома»</span>
    </div>
    <div class="second">
      <span>help@kostroma.ru</span>
      <p class="footer__gray">
        156005, г.Кострома, ул.Лесная
      </p>
    </div>
    <div class="third">
      <span>Политика конфиденциальности</span>
      <p>Условия использования</p>
    </div>
    <div class="last">
      <span class="footer__gray">Создание — <strong>Медиасеть</strong></span>
    </div>
  </div>
</template>

<script>
export default {
  data() {
    return {
      name: "Footer",
    };
  },
};
</script>

<style lang="scss" scoped>
.footer {
  box-sizing: border-box;
  padding: 31px 31px 0;
  display: flex;
  text-align: left;

  .first {
    margin-right: 185px;
  }
  .second {
    margin-right: 194px;
  }
  .last {
    margin-left: auto;
  }

  height: 112px;
  font-size: 13px;

  &__gray {
    color: #838588;
  }
}
</style>
