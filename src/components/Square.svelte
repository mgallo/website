<script>
  import { onMount } from "svelte";
  import anime from "animejs/lib/anime.es.js";

  onMount(() => {
    setTimeout(() => {
      const animatedSquare = document.querySelector("#animated-square");
      const fragment = document.createDocumentFragment();
      const grid = [10, 10];
      const col = grid[0];
      const row = grid[1];
      const numberOfElements = col * row;

      for (let i = 0; i < numberOfElements; i++) {
        const child = document.createElement("div");
        child.style.width = `${3 / 10}em`;
        child.style.height = `${3 / 10}em`;
        child.style.backgroundColor = "#fff";
        fragment.appendChild(child);
      }

      animatedSquare.appendChild(fragment);

      const animations = anime
        .timeline({
          targets: "#animated-square div",
          easing: "easeInOutSine",
          delay: anime.stagger(50),
          loop: false,
          autoplay: false
        })
        .add({
          translateX: [
            {
              value: anime.stagger(".2rem", {
                grid: grid,
                from: "center",
                axis: "x"
              })
            }
          ],
          translateY: [
            {
              value: anime.stagger(".2rem", {
                grid: grid,
                from: "center",
                axis: "y"
              })
            }
          ],
          duration: 500,
          scale: 0.2,
          scale: 0.5,
          scaleX: 1,
          delay: anime.stagger(59, { grid: grid, from: "center" })
        })
        .add({
          translateX: [
            {
              value: anime.stagger(".2rem", {
                grid: grid,
                from: "center",
                axis: "x"
              })
            }
          ],
          translateY: [
            {
              value: anime.stagger(".2rem", {
                grid: grid,
                from: "center",
                axis: "y"
              })
            }
          ],
          duration: 1000,
          scale: 0.5,
          scaleX: 1.3,
          scaleY: 3.6,
          delay: anime.stagger(59, { grid: grid, from: "center" })
        });

      const cubeAnimations = anime
        .timeline({
          targets: "#animated-square",
          loop: false,
          easing: "easeInOutSine",
          autoplay: true,
          delay: 1000
        })
        .add({
          rotate: 45,
          duration: 1000,
          scale: 1
        });
      animations.play();
    }, 500);
  });
</script>

<style>
  #animated-square {
    width: 3em;
    height: 3em;
    margin: 5em;
    display: flex;
    flex-wrap: wrap;
    justify-content: center;
    align-items: center;
    transform: rotate(45deg);
  }
</style>

<div id="animated-square" />
