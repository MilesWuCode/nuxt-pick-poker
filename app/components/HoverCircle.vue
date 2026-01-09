<template>
  <div class="circle-wrapper">
    <a class="circle-hover">
      <span>查看網站</span>
    </a>
  </div>
</template>

<style lang="css" scoped>
.circle-wrapper {
  border-radius: 50%;
  background-color: #fff;
}

.circle-hover {
  width: 150px;
  height: 150px;
  align-items: center;
  color: #000;
  display: flex;
  justify-content: center;
  position: relative;
  transition: transform 0.3s;
}

.circle-hover:hover {
  color: white;
  transform: scale(1.3);
}

.circle-hover:before {
  background-color: #000;
  border-radius: 50%;
  content: "";
  height: 90%;
  position: absolute;
  transform: scale(0);
  transition: transform 0.3s;
  width: 90%;
  z-index: -1;
}

.circle-hover:hover:before {
  transform: scale(0.95);
}

.circle-hover:after {
  border-radius: 50%;
  content: "";
  height: 90%;
  position: absolute;
  transition: transform 0.3s;
  width: 90%;
  background-color: #fff;
  transform: scale(1);
  z-index: -2;
}

.circle-hover:hover:after {
  background-color: #fff;
  transform: scale(1);
  z-index: -2;
}
</style>
