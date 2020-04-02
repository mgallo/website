<style>
  main {
    -webkit-overflow-scrolling: touch;
    -webkit-box-pack: center;
    -o-box-pack: center;
    -ms-flex-pack: center;
    justify-content: center;
    -webkit-box-align: center;
    -o-box-align: center;
    -ms-flex-align: center;
    align-items: center;
    overflow-y: scroll;
    position: absolute;
    display: -webkit-box;
    display: -ms-flexbox;
    display: box;
    display: flex;
    bottom: 50px;
    right: 0;
    left: 0;
    top: 4rem;
    overflow: hidden;
  }
</style>

<main>
  <slot />
</main>
