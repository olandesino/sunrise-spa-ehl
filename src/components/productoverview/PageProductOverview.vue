<template>
  <div class="pop-page">
    <div id="pop-page" class="container">
      <div class="pop-alert-overlay hidden">
        <div class="pop-alert-wrapper">
          <div class="pop-alert-box">
            <div class="pop-alert-text">
              {{ $t('pleaseWait') }}
            </div>
          </div>
        </div>
      </div>
      <div class="row">
        <div class="col-xs-12 figure-col">
          <!--{{> catalog/pop/banner banner=content.banner}}-->
        </div>
      </div>
      <div class="row row-offcanvas row-offcanvas-left">
        <div class="col-xs-12">
          <Breadcrumb :categorySlug="categorySlug" />
        </div>
        <div class="col-sm-12">
          <div class="dark-overlay"></div>

          <!-- Mobile version -->
          <div class="row visible-xs">
            <div class="col-xs-12">
              <ul class="mobile-filter-list clearfix">
                <li class="pull-left">
                  <button type="button"
                          class="offcanvas-btn offcanvas-open"
                          data-toggle="modal"
                          data-target="#sidebar-overlay">
                    {{ $t('open') }}
                  </button>
                </li>
              </ul>
            </div>
            <!--{{> catalog/pop/filters-sidebar-mobile}}-->
          </div>
          <!-- End mobile version -->

          <ProductList :categorySlug="categorySlug" />

          <div class="row">
            <div class="col-sm-9 col-sm-offset-3 col-xs-12 text-center custom-pagination">
              <ul class="page-numbers page-numbers-bottom">
                <!--{{> common/pagination pagination=content.pagination}}-->
              </ul>
            </div>
          </div>
          <hr class="hr">
        </div>
      </div>
    </div>
  </div>
</template>

<script>
import ProductList from './ProductList.vue';
import Breadcrumb from '../common/Breadcrumb.vue';

export default {
  components: {
    ProductList,
    Breadcrumb,
  },

  props: ['categorySlug'],
};
</script>

<!-- eslint-disable -->
<i18n>
{
  "en": {
    "pleaseWait": "Please wait...",
    "open": "Filter"
  },
  "de": {
    "pleaseWait": "Bitte warten...",
    "open": "Filter öffnen"
  }
}
</i18n>
