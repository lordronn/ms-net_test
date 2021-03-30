<template>
  <div class="header">
    <div class="header__wrapper-info">
      <div class="header__controls">
        <button><span>Назад</span></button>
        <p class="header__controls_name">
          Просроченая заявка
        </p>
      </div>
      <div class="header__title">
        <h1>№13534774376</h1>
        <span class="header__waiting-time">Ждет ответ 3 д 12 ч</span>
      </div>
      <p>
        Публичное акционерное общество / Территориальная генерирующая компания
        №2
      </p>
    </div>
    <div class="header__admin-info">
      <div>
        <p>Константин</p>
        <span>Админимтратор</span>
      </div>
      <div>
        <button><span>Выйти</span></button>
      </div>
    </div>
  </div>
</template>

<script>
export default {
  data() {
    return {
      name: "Header",
    };
  },
};
</script>

<style lang="scss" scoped>
.header {
  background-color: #e5e5e5;
  box-sizing: border-box;
  display: flex;
  justify-content: space-between;

  &__wrapper-info {
    padding-top: 65px;
    padding-left: 18px;
  }

  &__admin-info {
    display: flex;
    padding-top: 23px;
    margin-right: 66px;
    & > :first-child {
      margin-right: 90px;
      p {
        margin-top: 0;
        margin-bottom: 5px;
      }
      span {
        font-size: 13px;
        color: #838588;
      }
    }
    & > :last-child > button {
      padding: 0;
      width: 64px;
      height: 20px;
      border: none;
      background: none;
      font-size: 13px;
      color: #1473fa;
      & > span {
        vertical-align: top;
      }
      &:before {
        content: url("data:image/svg+xml,%3Csvg width='16' height='16' viewBox='0 0 16 17' fill='none' xmlns='http://www.w3.org/2000/svg'%3E%3Ccircle cx='8' cy='8.8877' r='8' fill='%231473FA'/%3E%3Cpath d='M10.2422 4.64502L5.99955 8.88766L10.2422 13.1303' stroke='white' stroke-width='2'/%3E%3Cpath d='M7 8.8877C7.36 8.8877 13.15 8.8877 16 8.8877' stroke='white' stroke-width='2'/%3E%3C/svg%3E ");
        margin-right: 6px;
        width: 17px;
        height: 17px;
      }
      &:hover {
        font-size: 14px;
        cursor: pointer;
        outline: none;
      }
    }
  }

  &__controls {
    display: flex;
    margin-bottom: 18px;
    & > button {
      width: 65px;
      height: 25px;
      background-color: rgba(20, 115, 250, 0.1);
      border-radius: 2px;
      border: none;
      padding: 0;
      margin-right: 18px;

      &:hover {
        background-color: #f2fbff;
        outline: none;
        cursor: pointer;
      }
      & > span {
        font-weight: 500;
        font-size: 11px;
        color: #1473fa;
      }
      &:before {
        content: url("data:image/svg+xml,%3Csvg width='12' height='8.5' viewBox='0 0 13 11' fill='none' xmlns='http://www.w3.org/2000/svg'%3E%3Cpath d='M13 5.5H1' stroke='%231473FA'/%3E%3Cpath d='M5.24219 1.25732L0.999547 5.49996L5.24219 9.74261' stroke='%231473FA'/%3E%3C/svg%3E%0A");
        margin-right: 8px;
      }
    }
    &_name {
      margin: auto 0;
      font-weight: 500;
      font-size: 11px;
      color: #1473fa;
      border-bottom: 1px solid rgba(20, 115, 250, 0.4);
    }
  }
  &__title {
    h1 {
      margin: 0;
      margin-right: 7px;
      line-height: 34px;
      font-size: 40px;
      font-weight: 400;
    }
    display: flex;
  }
  &__waiting-time {
    font-weight: 500;
    font-size: 11px;
    padding: 3px 11px;
    color: #ffffff;
    background-color: #ff144d;
    font-weight: 500;
    border-radius: 30px;
    align-self: flex-start;
  }
}
</style>
