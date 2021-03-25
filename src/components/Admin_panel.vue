<template>
  <div class="panel">
    <div class="panel__content content">
      <div
        v-for="item in panelInfo"
        :key="item.name"
      >
        <p
          class="content__item content__item_father"
          :class="{ content__item_active: activeMenuItem === item.name }"
          @click="(activeMenuItem === item.name)? activeMenuItem = '' : activeMenuItem = item.name"
        >
          {{ item.name }}
        </p>
        <ul
          v-if="item.name === activeMenuItem"
          class="content__params"
        >
          <li
            @click="(activeItem === val) ? activeItem = '' : activeItem = val"
            class="content__item"
            :class="{ content__item_active: activeItem === val }"
            v-for="(val, key) in item.params"
            :key="key"
          >
            <span>{{ key }}</span> {{ val }}
          </li>
        </ul>
      </div>
    </div>
    <button class="content__btn">
      Новое уведомление
    </button>
  </div>
</template>

<script>
export default {
  data() {
    return {
      name: "AdminPanel",
      panelInfo: [
        {
          name: "Заявки",
          params: {
            "В работе": 128,
            "Истекает срок": 3,
            Просрочены: 4,
          },
        },
        { name: "Контрагенты" },
        { name: "Операторы" },
        { name: "Статистика" },
        { name: "Уведомление" },
        { name: "Настройки" },
      ],
      activeMenuItem: String,
      activeItem: String,
      items: [{ message: "Foo" }, { message: "Bar" }],
    };
  },
};
</script>

<style lang="scss" scoped>
.panel {
  margin-top: 90px;
  height: calc(100% - 90px);
  box-sizing: border-box;
  background-color: #0047ba;
  padding: 6px 6px 12px 30px;
  display: flex;
  flex-direction: column;
  justify-content: space-between;

  .content {
    color: #ffffff;

    &__params {
      padding: 0;
      margin: 0;
      list-style: none;
      & > li {
        display: flex;
        justify-content: space-between;
        padding-right: 8px;
      }
    }
    &__item {
      margin: 0;
      padding: 13px 0 16px 20px;
      &_father {
        font-size: 16px;
        font-weight: 700;
        line-height: 24px;
        font-weight: bold;
        border-bottom: 1px solid rgba($color: #ffffff, $alpha: 0.2);
      }
      &_active {
        color: red;
        border: none;
      }
      &:hover {
        background-color: rgba($color: #d2f0ff, $alpha: 0.2);
        border-radius: 4px;
        cursor: pointer;
      }
    }
    &__btn {
      padding: 16px 63px;
      font-size: 14px;
      color: #1473fa;
    }
  }
}

.red {
  color: red;
}
</style>