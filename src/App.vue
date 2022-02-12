<template>
  <div class="view">
    <img src="https://assets.codepen.io/2002878/bilibili-winter-view-1.jpg" class="morning" alt="">
    <img src="https://assets.codepen.io/2002878/bilibili-winter-view-2.jpg" class="afternoon" alt="">
    <video autoplay loop muted class="evening">
      <source src="https://assets.codepen.io/2002878/bilibili-winter-view-3.webm" type="video/webm" />
    </video>
    <img src="https://assets.codepen.io/2002878/bilibili-winter-view-3-snow.png" class="window-cover" alt="">
  </div>

  <div class="tree">
    <img src="https://assets.codepen.io/2002878/bilibili-winter-tree-1.png" class="morning" alt="">
    <img src="https://assets.codepen.io/2002878/bilibili-winter-tree-2.png" class="afternoon" alt="">
    <img src="https://assets.codepen.io/2002878/bilibili-winter-tree-3.png" class="evening" alt="">
  </div>
</template>

<style lang="scss">
.view {
  position: absolute;
  top: 0;
  right: 0;
  bottom: 0;
  left: 0;
  display: flex;
  justify-content: center;
  align-items: center;
  &__img{
  position: absolute;
  display: block;
  width: 120%;
  height: 100%;
  object-fit: cover;
  }
  &__video{
  position: absolute;
  display: block;
  width: 120%;
  height: 100%;
  object-fit: cover;
  }
}

.tree {
  position: absolute;
  top: 0;
  right: 0;
  bottom: 0;
  left: 0;
  display: flex;
  justify-content: center;
  align-items: center;
  &__img{
  position: absolute;
  display: block;
  width: 120%;
  height: 100%;
  object-fit: cover;
  }
}

.morning {
  z-index: 20;
  opacity: calc(1 - (var(--percentage) - 0.25) / 0.25);
}

.afternoon {
  z-index: 10;
  opacity: calc(1 - (var(--percentage) - 0.5) / 0.5);
}

.view {
  transform: translatex(calc(var(--percentage) * 100px));
}

.tree {
  transform: translatex(calc(var(--percentage) * 50px));
  filter: blur(3px);
}

.view,
.tree,
.morning,
.afternoon {
  transition: .2s all ease-in;
}

.moving .view,
.moving .tree,
.moving .morning,
.moving .afternoon {
  transition: none;
}

.window-cover {
  opacity: calc((var(--percentage) - 0.9) / 0.1);
}
</style>

<script>
// let startingPoint
// const header = document.querySelector('header')

// header.addEventListener('mouseenter', (e) => {
//   startingPoint = e.clientX
//   header.classList.add('moving')
// })

// header.addEventListener('mouseout', (e) => {
//   header.classList.remove('moving')
//   header.style.setProperty('--percentage', 0.5)
// })

// header.addEventListener('mousemove', (e) => {
//   const percentage = (e.clientX - startingPoint) / window.outerWidth + 0.5

//   header.style.setProperty('--percentage', percentage)
// })
</script>
