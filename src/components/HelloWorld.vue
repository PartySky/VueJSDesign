<template>
  <div class="wrapper">
    <div v-if="isReferenceShown" class="reference">
      <img class="header__logo" 
           src="../assets/full-page.svg"/>
    </div>

    <div class="block-aligner"
         v-bind:class="{ 'is-opacity-reduced': isReferenceShown }">
      <div class="header">
        <img class="header__logo"
             src="../assets/logo.svg"/>
        <div class="header__menu-btn">
          <img src="../assets/menu.svg"/>
        </div>
        <div class="header__menu-item">Мастера</div>
        <div class="header__menu-item">Студии</div>
        <div class="header__menu-item">Галерея татуировок</div>
        <div class="header__city">
          <span class="header__city__label">Ваш город:</span>
          <span class="header__city__value">Санкт Петербург</span>
        </div>

        <img class="header__user-pic"
             src="../assets/user-avatar.png"/>
        <span class="header__user-name">Дмитрий</span>
      </div>
    </div>

    <div class="filters-menu max-wight-limiter"
         v-bind:class="{ 'is-opacity-reduced': isReferenceShown }">
      <span class="filters-menu__title">Тату мастера</span>
      <span class="filters-menu__type">Тату студии</span>
      <div class="filters-menu__search-input">
        <img class="filters-menu__icon"
             src="../assets/search-icon.svg"/>
        <span class="filters-menu__search-text">Найти мастера</span>
      </div>
      <div class="filters-menu__filter-btn">
        <img class="filters-menu__icon"
             src="../assets/filter.svg"/>
        <span class="filters-menu__filter-text">Фильтр</span>
      </div>
      <div class="filters-menu__map-btn">
        <img class="filters-menu__icon" 
             src="../assets/location-marker.svg"/>
        <span class="filters-menu__location-text">Показать на карте</span>
      </div>
    </div>

    <div class="content"
         v-bind:class="{ 'is-opacity-reduced': isReferenceShown }">
      <div class="content__section_title max-wight-limiter padding-box">Обратите внимание</div>
      <div class="content__section">
        <div class="content__section__store-item content__section__adv-div">
          <img src="../assets/adv-banner-vertical.png"/>
          
        </div>
        
        <StoreItem class="content__section__store-item"/>
        <StoreItem v-bind:isHot="true"
                   class="content__section__store-item"/>

        <StoreItem class="content__section__store-item"/>
        <StoreItem class="content__section__store-item"/>
        <StoreItem class="content__section__store-item"/>

        <StoreItemShowMore/>
      </div>
        
    </div>
    <div class="content best-rating"
         v-bind:class="{ 'is-opacity-reduced': isReferenceShown }">

      <div class="content__section_title max-wight-limiter padding-box">Лучший рейтинг</div>
      <div class="content__section ">

        <div class="content__section__store-item content__section__adv-div">
          <img src="../assets/adv-banner-vertical.png"/>

        </div>

        <StoreItem class="content__section__store-item"/>


        <StoreItem v-bind:isHot="true"
                   class="content__section__store-item"/>
        <StoreItem v-bind:isHot="true"
                   class="content__section__store-item"/>
        
        <StoreItem class="content__section__store-item"/>
        <StoreItem class="content__section__store-item"/>

        <StoreItemShowMore/>
        
      </div>
    </div>
    <div class="content"
         v-bind:class="{ 'is-opacity-reduced': isReferenceShown }">
      
      <div class="content__section_title max-wight-limiter padding-box">Мастера из Санкт-Петербурга</div>
      <div class="content__section">

        <StoreItem class="content__section__store-item" 
                   v-for="item in 20" :key="item.id"/>
        
      </div>
    </div>

    <div class="page-selector max-wight-limiter page-selector-extra-margins"
         v-bind:class="{ 'is-opacity-reduced': isReferenceShown }">
      <div class="page-selector__item page-selector__is-active">1</div>
      <div class="page-selector__item"
           v-for="item in 4" :key="item.id">{{item + 1}}</div>
    </div>
    
    <div class="adv-horizontal max-wight-limiter padding-box"
         v-bind:class="{ 'is-opacity-reduced': isReferenceShown }">
      <img class="adv-horizontal__img" 
           src="../assets/adv-banner-big.png"
           alt="">
    </div>
    
    <div class="reference-btn" 
         v-on:click="isReferenceShown = !isReferenceShown">
      Show Reference
    </div>
  </div>
</template>

<script lang="ts">
import { Component, Prop, Vue } from 'vue-property-decorator';
import StoreItem from "@/components/StoreItem.vue";
import StoreItemHot from "@/components/StoreItemHot.vue";
import StoreItemShowMore from "@/components/StoreItemShowMore.vue";
@Component({
  components: {StoreItemShowMore, StoreItem}
})
export default class HelloWorld extends Vue {
  isReferenceShown = false;
  @Prop() private msg!: string;
}
</script>

<!-- Add "scoped" attribute to limit CSS to this component only -->
<style src="./HelloWorld.less"
       scoped 
       lang="less"></style>