<template>
  <div id="app">
    <div class="grid-x grid-padding-x">
      <div class="cell">
        <div class="off-canvas-wrapper">

          <div
            class="off-canvas position-left"
            :class="[
              { 'is-transition-push is-open': offCanvasPush.isOpenedLeft },
              { 'is-closed': offCanvasPush.isClosedLeft }
            ]">
            <button 
              class="close-button" aria-label="Close panel" type="button"
              @click="closeLeftPushOffCanvas">
              <span aria-hidden="true">&times;</span>
            </button>
            <h3>This is a left off-canvas panel</h3>
          </div>

          <div 
            class="js-off-canvas-overlay is-overlay-fixed is-visible is-closable"
            v-if="offCanvasPush.isOpenedLeft"
            @click="closeLeftPushOffCanvas"></div>

          <div 
            class="off-canvas position-right"
            :class="[
              { 'is-transition-push is-open': offCanvasPush.isOpenedRight },
              { 'is-closed': offCanvasPush.isClosedRight }
            ]">
            <button 
              class="close-button" aria-label="Close panel" type="button"
              @click="closeRightPushOffCanvas">
              <span aria-hidden="true">&times;</span>
            </button>
            <h3>This is a right off-canvas panel</h3>
          </div>

          <div 
            class="js-off-canvas-overlay is-overlay-fixed is-visible is-closable"
            v-if="offCanvasPush.isOpenedRight"
            @click="closeRightPushOffCanvas"></div>

          <div 
            class="off-canvas-content"
            :class="[
              { 'is-open-left has-transition-push has-position-left': offCanvasPush.isOpenedLeft },
              { 'is-open-right has-transition-push has-position-right': offCanvasPush.isOpenedRight },
              { '': offCanvasPush.isClosedLeft },
              { '': offCanvasPush.isClosedRight }
            ]">
            <div class="row column">

              <div class="button-group expanded">
                <button 
                  type="button" 
                  class="button"
                  @click="toggleLeftPushOffCanvas">
                  Left Push
                </button>
                <button 
                  type="button" 
                  class="button"
                  @click="toggleRightPushOffCanvas">
                  Right Push
                </button>
              </div>

              <h1>Left Push and Right Push off canvas</h1>

              <p>Lorem ipsum dolor sit amet, consectetur adipiscing elit. Proin eros massa, lacinia sed rutrum non, sodales quis urna. In hac habitasse platea dictumst. Pellentesque habitant morbi tristique senectus et netus et malesuada fames ac turpis egestas. Vivamus in rutrum magna, a varius lorem. Suspendisse nec nisi massa. Sed id lacus feugiat, commodo risus id, vulputate odio. Quisque aliquam lacus id mi euismod, ut sodales odio porttitor. Donec finibus dui vitae odio ultricies, sit amet volutpat risus bibendum. Nulla sagittis rhoncus fermentum. Nulla nisi mi, cursus posuere mollis in, faucibus ut lacus.</p>
            </div>
          </div>
        </div>
      </div>
    </div>
  </div>
</template>

<script>
export default {
  name: 'app',
  data() {
    return {
      offCanvasPush: {
        isOpenedLeft: false,
        isClosedLeft: true,
        isOpenedRight: false,
        isClosedRight: true,
      },
    };
  },
  methods: {
    toggleLeftPushOffCanvas() {
      if (this.offCanvasPush.isOpenedLeft === true) {
        this.offCanvasPush.isOpenedLeft = false;
        this.offCanvasPush.isClosedLeft = true;
      } else {
        this.offCanvasPush.isOpenedLeft = true;
        this.offCanvasPush.isClosedLeft = false;
      }
    },
    closeLeftPushOffCanvas() {
      this.offCanvasPush.isOpenedLeft = false;
      this.offCanvasPush.isClosedLeft = true;
    },
    toggleRightPushOffCanvas() {
      if (this.offCanvasPush.isOpenedRight === true) {
        this.offCanvasPush.isOpenedRight = false;
        this.offCanvasPush.isClosedRight = true;
      } else {
        this.offCanvasPush.isOpenedRight = true;
        this.offCanvasPush.isClosedRight = false;
      }
    },
    closeRightPushOffCanvas() {
      this.offCanvasPush.isOpenedRight = false;
      this.offCanvasPush.isClosedRight = true;
    },
  },
};
</script>

<style lang="scss">
</style>
