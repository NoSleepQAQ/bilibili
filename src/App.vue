<template>

  <body>
    <header>
      <div class="view">
        <img src="https://assets.codepen.io/2002878/bilibili-winter-view-1.jpg"
             class="morning"
             alt="">
        <img src="https://assets.codepen.io/2002878/bilibili-winter-view-2.jpg"
             class="afternoon"
             alt="">
        <video autoplay
               loop
               muted
               class="evening">
          <source src="https://assets.codepen.io/2002878/bilibili-winter-view-3.webm"
                  type="video/webm" />
        </video>
        <img src="https://assets.codepen.io/2002878/bilibili-winter-view-3-snow.png"
             class="window-cover"
             alt="">
      </div>

      <div class="tree">
        <img src="https://assets.codepen.io/2002878/bilibili-winter-tree-1.png"
             class="morning"
             alt="">
        <img src="https://assets.codepen.io/2002878/bilibili-winter-tree-2.png"
             class="afternoon"
             alt="">
        <img src="https://assets.codepen.io/2002878/bilibili-winter-tree-3.png"
             class="evening"
             alt="">
      </div>
    </header>
  </body>

</template>

<style lang="scss">
body {
  margin: 0;
}

header {
  height: 160px;
  position: relative;
  overflow: hidden;
  --percentage: 0.5;
}

header .view,
header .tree {
  position: absolute;
  top: 0;
  right: 0;
  bottom: 0;
  left: 0;
  display: flex;
  justify-content: center;
  align-items: center;
}

header img,
header video {
  position: absolute;
  display: block;
  width: 120%;
  height: 100%;
  object-fit: cover;
}

header.morning {
  z-index: 20;
  // opacity: calc(1 - (var(--percentage) - 0.25) / 0.25);
}

header .afternoon {
  z-index: 10;
  // opacity: calc(1 - (var(--percentage) - 0.5) / 0.5);
}

header .view {
  transform: translatex(calc(var(--percentage) * 100px));
}

header.tree {
  transform: translatex(calc(var(--percentage) * 100px));
  // filter: blur(3px);
}

// .view,
// .tree,
// .morning,
// .afternoon {
//   transition: 0.2s all ease-in;
// }

// .moving .view,
// .moving .tree,
// .moving .morning,
// .moving .afternoon {
//   transition: none;
// }

// .window-cover {
//   opacity: calc((var(--percentage) - 0.9) / 0.1);
// }
</style>

<script>
// let startingPoint // eslint-disable-line no-unused-vars
const header = document.querySelector('header')

header.addEventListener('mousemove', (e) => {
  const percentage = e.clientX / window.outerWidth

  header.style.setProperty('--percentage', percentage)
})

// header.addEventListener('mouseout', (e) => {
//   header.classList.remove('moving')
//   header.style.setProperty('--percentage', 0.5)
// })

// header.addEventListener('mousemove', (e) => {
//   const percentage = (e.clientX - startingPoint) / window.outerWidth + 0.5

//   header.style.setProperty('--percentage', percentage)
// })
</script>
