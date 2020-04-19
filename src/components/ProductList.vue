<template>
  <main class="main-content">
    <div class="product-title">
      <span class="circle"></span>
      <h2 class="product-title__h2">КОРЗИНА ТОВАРОВ</h2>
    </div>
    
    <div class="wrapper-content">
      <div class="table-header">
        <h3 class="table-header__h3 table-header__h3--articul">Артикул</h3>
        <h3 class="table-header__h3 table-header__h3--name">Наименование</h3>
        <h3 class="table-header__h3 table-header__h3--info">Информация</h3>
        <h3 class="table-header__h3 table-header__h3--do">Действие</h3>
        <h3 class="table-header__h3 table-header__h3--count">Количество</h3>
        <h3 class="table-header__h3 table-header__h3--price">Цена</h3>
      </div>
      <form action="#" class="product-list">
        <div class="wrapper-product">
          <section class="product-form" v-for="product in products" :key="product.title">
            <div class="product-img">
              <img :src="product.img" alt="product">
              <a href="#" class="product-img__comment">{{product.articule}}</a>
            </div>
            
            <div class="product-name">
              <div class="product-title">
                <h3 class="product-title__h3">{{product.nameOne}}</h3>
                <h3 class="product-title__h3 product-title__h3--change-blue"
                    v-bind:class="{ change: product.classTextRed }">{{product.nameTwo}}</h3>
              </div>
              <p class="product-description">{{product.description}}</p>
              <div class="product-comment">
                <label class="product-comment__label" for="comment">Комментарий: </label>
                <input class="product-comment__input" id="comment" type="text">
              </div>
              <div class="product-name__sale" v-bind:class="{ active: product.classSale }">
                <span class="product-name__span">Цена уменшилась на 15%</span>
                <span class="product-name__span-tick">подтверждаю</span>
              </div>
              
              <span class="product-name__red-text" v-bind:class="{ red: product.classRed }">Данная позиция не подлежит возврату, так как относится к категории “Жидкости”</span>
            </div>
            
            <div class="product-info">
              <p class="product-info__p"><b>партиями по 10 шт.</b></p>
              <div class="circle"></div>
              <p class="product-info__p"><b>Ожидаем на складе МШ: 1-1 дн.</b></p>
              <div class="product-info__data">
                <span class="product-info__data product-info__data--small">{{product.basketData}}</span>
                <span class="product-info__data product-info__data--small">{{product.data}}</span>
              </div>
            </div>
            <div class="product-radio">
              <div class="product-radio__wrapper">
                <input class="visually-hidden product-radio__input" type="radio" :id="product.radio"
                       :name="product.radio"
                       value="delete">
                <label class="product-radio__label" :for="product.radio">удалить</label>
              </div>
              
              <div class="product-radio__wrapper">
                <input class="visually-hidden product-radio__input" type="radio" :id="product.radioId"
                       :name="product.radio" value="order"
                       checked="checked">
                <label class="product-radio__label" :for="product.radioId">заказать</label>
              </div>
            </div>
            <div class="product-counter">
              <input class="product-counter__input" type="text" :value="product.count">
              <div class="product-counter__wrapper">
                <button class="product-counter__minus" v-on:click="product.count--">&#8722;</button>
                <button class="product-counter__plus" v-on:click="product.count++">+</button>
              </div>
            </div>
            <div class="product-price">
              <span class="product-price__counter">{{product.count*2 + ' .00руб'}}</span>
            </div>
          </section>
        </div>
        <section class="product-cost">
          <div class="cost-main">
            <p class="cost-main__p">Общая стоимость: <span class="cost-main__span-blue">3500.00 руб.</span>
              (включая НДС)</p>
            <p class="cost-main__p">Заказано позиций: <span class="count-product">1 шт.</span></p>
            <p class="cost-main__p">Заказано деталей: <span class="count-product">10 шт</span>.</p>
            <div class="product-button">
              <button class="product-button__blue button">пересчитать</button>
              <button class="product-button__basket button">очистить корзину</button>
            </div>
          </div>
          <div class="cost-last">
            <p class="cost-last__p">Итого: <span class="cost-last__span-blue">3213.00 руб.</span></p>
            <span class="cost-last__span">Если вы набрали в корзину все необходимые запчасти и указали их количество, нажмите «Перейти к оформлению» и ваш заказ будет передан на обработку операторам компании.</span>
          </div>
        </section>
        <div class="form-footer">
          <p class="form-footer__red-text">Внимание! В корзине находятся позиции, найденные по спискам оригинальных
            замен или кросс-листов!</p>
          <p class="form-footer__small-text">Внимание! В корзине находятся позиции, найденные по спискам оригинальных
            замен или кросс-листов!Внимание! В корзине находятся позиции, найденные по спискам оригинальных замен или
            кросс-листов!Внимание! В корзине находятся позиции, найденные по спискам оригинальных замен или
            кросс-листов!Внимание! В корзине находятся позиции, найденные по спискам оригинальных замен или
            кросс-листов!Внимание! В корзине находятся позиции, найденные по спискам оригинальных замен или
            кросс-листов!Внимание! В корзине находятся позиции, найденные по спискам оригинальных замен или
            кросс-листов!Внимание! В корзине находятся позиции, найденные по спискам оригинальных замен или
            кросс-листов!Внимание! В корзине находятся позиции, найденные по спискам оригинальных замен или
            кросс-листов!Внимание! </p>
          <div class="form-footer__check">
            <input type="checkbox" id="result" class="form-footer__input visually-hidden">
            <label class="form-footer__label" for="result">Да, я тщательно проверил правильность заказываемых запчастей. С
              <a class="form-footer__link" href="#">правилами возврата</a> согласен.</label>
          </div>
          <button type="submit" class="form-footer__button-blue button">оформить заказ на эти товары</button>
        </div>
      </form>
    </div>
  </main>
</template>

<script>
  export default {
    data: function () {
      return {
        products: [
          this.productItem(
            require('../assets/img/lamp.png'),
            '1987674542',
            'Bosch',
            'Оригинал',
            'Лампа накаливания, фонарь освещения номерного знака; Лампа накаливания,\n стояночные огни / габаритные фонари; Лампа накаливания, габаритный огонь',
            'Добавлено в корзину: 24.02.2020 14:17',
            'Актуальность: 24.02.2020 14:17',
            0,
            'nameOne',
            'idOne',
            false,
            false,
            false
          ),
          this.productItem(
            require('../assets/img/lamp.png'),
            '1987674542',
            'Bosch',
            'Неоригинальная замена',
            'Лампа накаливания, фонарь освещения номерного знака; Лампа накаливания,\n стояночные огни / габаритные фонари; Лампа накаливания, габаритный огонь',
            'Добавлено в корзину: 24.02.2020 14:17',
            'Актуальность: 24.02.2020 14:17',
            0,
            'nameTwo',
            'idTwo',
            true,
            false,
            true
          ),
          this.productItem(
            require('../assets/img/battle.png'),
            '1987674542',
            'Bosch',
            'Неоригинальная замена',
            'Лампа накаливания, фонарь освещения номерного знака; Лампа накаливания,\n стояночные огни / габаритные фонари; Лампа накаливания, габаритный огонь',
            'Добавлено в корзину: 24.02.2020 14:17',
            'Актуальность: 24.02.2020 14:17',
            0,
            'nameThree',
            'idThree',
            false,
            true,
            false
          ),
          this.productItem(
            require('../assets/img/lamp.png'),
            '1987674542',
            'Bosch',
            'Оригинальная замена',
            'Лампа накаливания, фонарь освещения номерного знака; Лампа накаливания,\n стояночные огни / габаритные фонари; Лампа накаливания, габаритный огонь',
            'Добавлено в корзину: 24.02.2020 14:17',
            'Актуальность: 24.02.2020 14:17',
            0,
            'nameFourth',
            'idFourth',
            true,
            false,
            true
          ),
        ],
      }
    },
    methods: {
      productItem: (img, articule, nameOne, nameTwo, description, basketData, data, count = Number, radio, radioId, classSale = Boolean, classRed = Boolean, classTextRed = Boolean) => ({
        img,
        articule,
        nameOne,
        nameTwo,
        description,
        basketData,
        data,
        count,
        radio,
        radioId,
        classSale,
        classRed,
        classTextRed
      }),
    }
  }
</script>

<style scoped lang="scss">
  .main-content {
    max-width: 1180px;
    padding: 0 20px;
    margin: 0 auto;
  }

  .button {
    font-size: 14px;
    font-family: "GothamPro", sans-serif;
    color: rgb(117, 116, 116);
    text-transform: uppercase;
    line-height: 36px;
    outline: none;
    border-radius: 50px;
    font-weight: bold;
    cursor: pointer;
    transition: .3s ease-in-out;
  }

  .product-title {
    position: relative;
  
    &__h2 {
      text-align: left;
      margin-left: 30px;
    }

    .circle {
      content: "";
      border-radius: 50%;
      background-color: #de2a1b;
      width: 10px;
      height: 10px;
      display: block;
      position: absolute;
      margin-bottom: 5px;
      top: 10px;
      left: -20px;
    
      &:before,
      &:after {
        content: "";
        border-radius: 50%;
        width: 10px;
        height: 10px;
        display: block;
        margin: 0 12px;
      }
      
      &:before {
        background-color: #0074af;
      }
    
      &:after {
        margin: 0 24px;
        position: absolute;
        top: 0;
        background-color: #000000;
      }
    }
  }
  
  .wrapper-content {
    margin-bottom: 50px;
  }
  
  .table-header {
    display: flex;
    flex-wrap: wrap;
    align-items: center;
    justify-content: space-between;
    background: #c6e2ff;
    padding: 20px;
    text-align: left;
    
    &__h3 {
      margin: 0;
      font-size: 14px;
      color: rgb(0, 0, 0);
      line-height: 1.714;
      text-align: left;
      width: 100%;
      
      &--articul {
        max-width: 90px;
      }
      
      &--name {
        max-width: 320px;
      }
      
      &--info {
        max-width: 235px;
      }
      
      &--do {
        max-width: 100px;
      }
      
      &--count {
        max-width: 120px;
      }
      
      &--price {
        max-width: 60px;
      }
    }
  }
  
  .product-form {
    display: flex;
    flex-wrap: wrap;
    justify-content: space-around;
    border-bottom: 1px solid #c6e2ff;
    padding: 20px 0;
    
    &:last-child {
      border-bottom: 8px solid #c6e2ff;
    }
  }
  
  .product-img {
    display: flex;
    flex-direction: column;
    margin: 10px 0 0;
    
    &__comment {
      font-size: 12px;
      color: rgb(0, 116, 175);
      text-decoration: underline;
      line-height: 2;
      font-weight: 600;
      padding: 10px 0;
      text-align: left;
    }
  }
  
  .product-name,
  .product-info {
    text-align: left;
  }
  
  .product-name {
    max-width: 320px;
    
    .product-title {
      display: flex;
      
      &__h3 {
        font-size: 14px;
        color: rgb(0, 0, 0);
        line-height: 1.714;
        text-align: left;
        margin: 0;
        padding-right: 10px;
        
        &--change-blue {
          color: rgb(0, 116, 175);
        }
        
        &--change-blue.change {
          color: rgb(222, 42, 27);
        }
      }
    }
    
    .product-description {
      font-size: 14px;
      color: rgb(0, 0, 0);
      line-height: 1.714;
      font-family: "GothamPro", sans-serif;
      margin: 5px 0 10px;
    }
    
    .product-comment {
      &__label {
        font-size: 12px;
        color: rgb(0, 116, 175);
        line-height: 2;
        font-family: "GothamPro", sans-serif;
        color: rgb(0, 116, 175);
      }
      
      &__input {
        border: 1px solid rgb(198, 226, 255);
        border-radius: 50px;
        max-width: 223px;
        width: 100%;
        padding: 8px;
        outline: none;
        box-sizing: border-box;
      }
    }
    
    &__red-text {
      display: block;
      max-width: 235px;
      font-size: 12px;
      color: rgb(222, 42, 27);
      line-height: 1.2;
      margin: 20px 0 0;
      display: none;
    }
    
    &__red-text.red {
      display: block;
    }
    
    &__sale {
      display: none;
      margin: 20px 0 0;
    }
    
    &__sale.active {
      display: block;
    }
    
    &__span {
      font-size: 12px;
      font-family: "GothamPro", sans-serif;
      color: rgb(0, 116, 175);
      font-weight: bold;
      line-height: 2;
      padding-right: 10px;
    }
    
    &__span-tick {
      font-size: 14px;
      font-family: "GothamPro", sans-serif;
      color: rgb(255, 255, 255);
      line-height: 1.714;
      background: #de2a1b;
      font-weight: bold;
      padding: 10px 10px 10px 30px;
      border-radius: 50px;
      position: relative;
      
      &:before {
        content: url("../assets/img/tick.svg");
        position: absolute;
        top: 5px;
        left: 5px;
        width: 20px;
        height: 20px;
        border-radius: 50%;
        background: #ffffff;
      }
    }
  }
  
  .product-info {
    max-width: 240px;
    
    &__p {
      font-family: "GothamPro", sans-serif;
      font-size: 14px;
      color: rgb(11, 12, 12);
      line-height: 1.714;
      margin: 0px 0 5px;
    }
    
    &__data {
      display: inline-block;
      font-size: 12px;
      font-family: "GothamPro", sans-serif;
      color: rgb(11, 12, 12);
      line-height: 1.2;
    }
    
    .circle {
      content: "";
      border-radius: 50%;
      background-color: rgb(11, 137, 0);
      width: 16px;
      height: 16px;
      display: block;
      position: relative;
      margin-bottom: 5px;
      
      &:before,
      &:after {
        content: "";
        border-radius: 50%;
        background-color: rgb(11, 137, 0);
        width: 16px;
        height: 16px;
        display: block;
        margin: 0 20px;
      }
      
      &:after {
        margin: 0 40px;
        position: absolute;
        top: 0;
      }
    }
  }
  
  .product-radio {
    text-align: left;
    
    &__wrapper {
      margin: 15px 0;
    }
    
    &__label {
      font-size: 14px;
      font-family: "GothamPro", sans-serif;
      color: rgb(0, 0, 0);
      line-height: 1.2;
      position: relative;
      
      &:before {
        content: "";
        border-radius: 50%;
        background-color: rgb(255, 255, 255);
        box-shadow: inset 0px 1px 4px 0px rgba(1, 1, 1, 0.44);
        position: absolute;
        left: -25px;
        top: -1px;
        width: 16px;
        height: 16px;
        cursor: pointer;
      }
    }
    
    &__input:checked + label::after {
      content: "";
      position: absolute;
      top: 4px;
      left: -20px;
      width: 6px;
      height: 6px;
      border-radius: 50%;
      background-color: rgb(11, 137, 0);
      box-shadow: inset 0px 1px 5px 0px rgba(1, 1, 1, 0.54);
    }
  }
  
  .product-counter {
    &__input {
      border: 1px solid rgb(198, 226, 255);
      background-color: rgba(0, 0, 0, 0);
      width: 113px;
      height: 32px;
      border-radius: 50px;
      font-size: 18px;
      font-family: "GothamPro", sans-serif;
      color: rgb(0, 0, 0);
      line-height: 1.2;
      text-align: center;
    }
    
    &__wrapper {
      display: flex;
      justify-content: center;
      align-items: center;
      margin: 10px auto;
    }
    
    &__minus,
    &__plus {
      color: #ffffff;
      width: 38px;
      height: 26px;
      display: flex;
      justify-content: center;
      align-items: center;
      cursor: pointer;
      transition: .3s ease-in-out;
      border: none;
      
      &:hover {
        transform: scale(0.9);
        transition: .3s ease-in-out;
      }
    }
    
    &__minus {
      background-color: rgb(198, 226, 255);
    }
    
    &__plus {
      background-color: rgb(0, 116, 175);
    }
  }


  .product-price__counter {
    font-size: 14px;
    font-family: "GothamPro", sans-serif;
    color: rgb(0, 116, 175);
    font-weight: bold;
    line-height: 1.714;
  }


  .product-cost {
    display: flex;
    justify-content: space-between;
    align-items: baseline;
    margin: 45px 0;
  }
  
  .cost-main {
    text-align: left;
    flex: 1;
    
    &__p {
      font-size: 18px;
      font-family: "GothamPro", sans-serif;
      color: rgb(0, 0, 0);
      line-height: 1.333;
      margin: 0;
    }
    
    &__span-blue {
      color: rgb(0, 116, 175);
      font-weight: bold;
    }
  }
  
  .product-button {
    margin-top: 20px;
  }
  
  .product-button__blue {
    color: rgb(255, 255, 255);
    line-height: 36px;
    border: 1px solid rgb(198, 226, 255);
    background-color: rgb(0, 116, 175);
    width: 168px;
    height: 37px;
    margin-right: 20px;
  }

  .product-button__basket {
    color: rgb(117, 116, 116);
    text-decoration: underline;
    border: none;
    background: none;
  }
  
  .cost-last {
    text-align: right;
    flex: 1;
    max-width: 460px;
    
    &__p {
      font-size: 24px;
      font-family: "GothamPro", sans-serif;
      color: rgb(0, 0, 0);
      line-height: 1;
      margin: 0 0 30px 0;
    }
    
    &__span-blue {
      font-size: 30px;
      font-family: "GothamPro", sans-serif;
      color: rgb(0, 116, 175);
      font-weight: bold;
      line-height: 0.8;
    }
    
    &__span {
      font-size: 14px;
      font-family: "GothamPro", sans-serif;
      color: rgb(0, 0, 0);
      line-height: 1.2;
    }
  }
  
  .form-footer {
    &__red-text {
      font-size: 14px;
      font-family: "GothamPro", sans-serif;
      color: rgb(222, 42, 27);
      line-height: 1.2;
      text-align: center;
    }
  
    &__small-text {
      font-size: 12px;
      font-family: "GothamPro", sans-serif;
      color: rgb(0, 0, 0);
      line-height: 1.2;
      text-align: center;
    }
  
    &__check {
      font-size: 12px;
      color: rgb(0, 0, 0);
      line-height: 2;
    }
  
    &__link {
      color: #0074af;
      text-decoration: underline;
    }
  
    &__button-blue {
      color: rgb(255, 255, 255);
      border: 1px solid rgb(198, 226, 255);
      background-color: rgb(0, 116, 175);
      border-radius: 50px;
      outline: none;
      cursor: pointer;
      transition: .3s ease-in-out;
      margin: 20px auto;
      padding: 5px 20px;
    }
  }

  .form-footer__label {
    position: relative;
    &:before {
      content: "";
      border-radius: 50%;
      border: 1px solid rgb(0, 116, 175);
      background-color: white;
      position: absolute;
      left: -25px;
      top: -1px;
      width: 16px;
      height: 16px;
      cursor: pointer;
    }
  }

  .form-footer__input:checked + label::after {
    content: url("../assets/img/tick.svg");
    position: absolute;
    top: 0px;
    left: -25px;
  }
  
  @media(max-width: 1023px) {
    .table-header {
      display: none;
    }
    
    .wrapper-product {
      display: flex;
      flex-wrap: wrap;
      justify-content: space-around;
      align-items: baseline;
    }
    
    .product-form {
      width: 40%;
    }
  
    .product-form {
      width: 40%;
      flex-direction: column;
      align-items: baseline;
    }
  
    .product-radio {
      text-align: left;
      margin-left: 30px;
    }
  
    .product-name__sale.active {
      display: flex;
      flex-direction: column;
      text-align: center;
    }
  
    .product-name__span-tick:before {
      top: 12px;
      left: 20px;
    }
  }

  @media(max-width: 768px) {
    .product-form {
      width: 100%;
      align-items: center;
    }
  
    .product-cost {
      align-items: center;
      flex-direction: column;
    }
  }
</style>
