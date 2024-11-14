<template>
  <div class="product">
    <div class="wrapper">
      <!-- Левая колонка (десктоп) -->
      <div class="product__content">
        <!-- Основной свайпер -->
        <div class="product__swiper">
          <div class="swiper product__swiper-main product__image">
            <div class="swiper-wrapper">
              <div class="swiper-slide">
                <img src="img/product__img1.jpg" alt="Slide 1" />
              </div>
              <div class="swiper-slide">
                <img src="img/product__img2.jpg" alt="Slide 2" />
              </div>
              <div class="swiper-slide">
                <img src="img/product__img3.jpg" alt="Slide 3" />
              </div>
              <div class="swiper-pagination product__swiper-main-pagination"></div>
            </div>
          </div>
          <!-- Дополнительный свайпер -->
          <div class="swiper product__swiper-additional">
            <div class="swiper-wrapper">
              <div class="swiper-slide product__image-mini">
                <img src="img/product__img1.jpg" alt="Thumbnail 1" />
              </div>
              <div class="swiper-slide product__image-mini">
                <img src="img/product__img2.jpg" alt="Thumbnail 2" />
              </div>
              <div class="swiper-slide product__image-mini">
                <img src="img/product__img3.jpg" alt="Thumbnail 3" />
              </div>
            </div>
          </div>
        </div>
        <!-- Правая колонка (десктоп) -->
        <div class="product__info">
          <h3 class="product__title">Жакет удлиненный, белый</h3>
          <h3 class="product__price">
            8900 RUB
          </h3>


          <p class="product__info-text product__sizes-text">
            Размеры
          </p>
          <div class="product__sizes-row">
            <div class="product__sizes-element">
              <div class="product__sizes-size">XS</div>
              <div class="product__sizes-stock">мало</div>
            </div>
            <div class="product__sizes-element">
              <div class="product__sizes-size">S</div>
              <div class="product__sizes-stock"></div>
            </div>
            <div class="product__sizes-element product__sizes-element_inactive">
              <div class="product__sizes-size">M</div>
              <div class="product__sizes-stock">подписка</div>
            </div>
          </div>


          <p class="product__info-text product__color-text">
            Цвет: белый
          </p>
          <div class="product__color-row">
            <div class="product__color-element product__color-element_active">
              <div class="product__color white"></div>
            </div>
            <div class="product__color-element">
              <div class="product__color black"></div>
            </div>
            <div class="product__color-element">
              <div class="product__color beige"></div>
            </div>
          </div>


          <div class="product__buttons-row">
            <button class="product__button button">Добавить в корзину</button>
            <div class="product__button-favorite">
              <img src="img/Favorite.svg" alt="" class="product__button-favorite-img">
            </div>
          </div>


          <div class="product__description-column">
            <div class="product__description-element">
              <div class="product__description-title">
                Описание
              </div>
              <div class="product__description-extra">
                +
              </div>
            </div>
            <div class="product__description-element">
              <div class="product__description-title">
                Состав и уход
              </div>
              <div class="product__description-extra">
                +
              </div>
            </div>
          </div>


        </div>
      </div>
    </div>
  </div>
</template>

<script>
import Swiper from 'swiper';
import 'swiper/css/swiper.min.css';

export default {
  mounted() {
    let swiperThumbs;
    let swiperMain;

    // Проверка размера окна
    const isMobileDirection = () => window.innerWidth <= 1100 ? "horizontal" : "vertical";

    const initSwiper = () => {
      // Мини свайпер
      swiperThumbs = new Swiper('.product__swiper-additional', {
        loop: false,
        spaceBetween: 4,
        slidesPerView: 5,
        freeMode: false,
        touchMove: false,
        allowTouchMove: false,
        watchSlidesProgress: true,
        direction: isMobileDirection(),
      });
      // Основной свайпер
      swiperMain = new Swiper('.product__swiper-main', {
        loop: false,
        effect: "fade",
        spaceBetween: 10,
        freeMode: false,
        pagination: {
          el: '.swiper-pagination',
          clickable: true,
          type: 'bullets',
        },
        thumbs: {
          swiper: swiperThumbs,
        },
      });
      updateSwiperParams();
    };

    // Обновление направления
    const updateSwiperParams = () => {
      const direction = isMobileDirection();
      swiperThumbs.changeDirection(direction);
      swiperThumbs.params.slidesPerView = direction === "horizontal" ? 3 : 5;
      swiperThumbs.update();
      swiperMain.update();
    };

    window.addEventListener('resize', updateSwiperParams);
    window.addEventListener('load', () => {
      initSwiper();
    });
  }
}
</script>


<style scoped>
.product__content {
  display: flex;
  justify-content: center;
}

.product__price {
  font-weight: 400;
  font-size: 12px;
  line-height: 133%;
  text-transform: uppercase;
  color: #333;
  margin: 10px 0;
}

.product__info {
  margin-left: 61px;
  margin-right: 60px;
}

.product__title {
  font-weight: 400;
  font-size: 12px;
  line-height: 133%;
  text-transform: uppercase;
  color: #333;
}

.product__sizes-row {
  display: flex;
  margin-bottom: 36px;
}

.product__sizes-element {
  display: flex;
  flex-direction: column;
  align-items: center;
}

.product__sizes-element_inactive .product__sizes-size {
  color: #bdbdbd;
  border: 1px solid #bdbdbd;

}

.product__sizes-element+.product__sizes-element {
  margin-left: 14px;
}

.product__sizes-stock {
  font-weight: 400;
  font-size: 10px;
  line-height: 140%;
  text-align: center;
  color: #828282;
  margin-top: 3px;
}

.product__sizes-text {
  margin: 32px 0 6px;
}

.product__sizes-size {
  font-weight: 400;
  font-size: 10px;
  line-height: 140%;
  text-transform: uppercase;
  color: #333;
  height: 31px;
  width: 65px;
  border: 1px solid #333;
  display: flex;
  align-items: center;
  justify-content: center;
}

.product__info-text {
  font-weight: 400;
  font-size: 10px;
  line-height: 140%;
  color: #4f4f4f;
}

.product__color-row {
  display: flex;

}

.product__color-element {
  width: 36px;
  height: 36px;
  padding: 3px;
}

.product__color-element_active {
  border-bottom: 2px solid #4f4f4f;
}

.product__color {
  width: 100%;
  height: 100%;
}

.product__color-element .white {
  background-color: #fff;
  border: 1px solid #BDBDBD;
}

.product__color-element .black {
  background-color: #000;
}

.product__color-element .beige {
  background-color: #f9f1dc;
}

.product__color-element+.product__color-element {
  margin-left: 9px;
}

.product__button {
  margin: 0 10px 0 0;
}

.product__buttons-row {
  margin-top: 36px;
  display: flex;
}

.product__button-favorite {
  display: flex;
  align-items: center;
  justify-content: center;
  border: 1px solid #000;
  width: 44px;
  height: 44px;
}

.product__description-column {
  margin-top: 40px;
}

.product__description-element {
  display: flex;
  justify-content: space-between;
  align-items: center;
  font-weight: 400;
  font-size: 10px;
  line-height: 140%;
  text-transform: uppercase;
  color: #333;
  height: 41px;
  border-top: 1px solid #e0e0e0;
}

.product__description-element:nth-last-child(1) {
  border-bottom: 1px solid #e0e0e0;
}


.product__swiper {
  display: flex;
  flex-direction: row-reverse;
}

.product__swiper-main-pagination {
  display: none;
}

.product__image {
  height: 693px;
  width: 518px;
  margin-left: 30px;
}

.product__image-mini {
  height: 87px !important;
  width: 70px !important;
}

.product__swiper-additional .swiper-slide {
  opacity: 1;
}

.product__swiper-additional .swiper-slide-thumb-active {
  opacity: 0.5;
}

.swiper-slide img {
  object-fit: cover;
  width: 100%;
  height: 100%;
}

@media (max-width: 1100px) {
  .product__image {
    height: 400px;
    width: 300px;
    margin-left: 0;
    margin-bottom: 10px;
  }

  .product__swiper {
    flex-direction: column;
  }

  .product__info {
    margin: 0 20px;
  }
}

@media (max-width: 760px) {
  .product__content {
    flex-direction: column;
  }
  .product__info {
    margin: 0 0;
  }
  .product__swiper-main{
    height: auto;
    width: calc(100% + 32px);
    margin-left: -16px;
  }
  .product__swiper-additional{
    display: none;
  }
  .product__swiper-main-pagination {
  display: flex;
  gap: 6px;
  left: 50%;
  transform: translateX(-50%);
  bottom: 15px;
}
  .product__info {
    margin-top: 20px;
    position: relative;
  }
  .product__button {
    display: none;
  }
  .product__button-favorite {
    position: absolute;
    right: 0;
    top: 0;
    border: none;
    height: 20px;
    width: 20px;
    
  }
  .product__description-column {
    margin-top: 0;
  }
}

</style>
