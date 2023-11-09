<main>
  <slot />
</main>

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
    display: -webkit-box;
    display: -ms-flexbox;
    display: box;
    display: flex;
    width: 100vw;
    height: 100vh;
    overflow: hidden;
  }
</style>
