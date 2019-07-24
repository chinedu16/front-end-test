.<template>
  <div class="sidebar">
    <div class="item-1">
        <div class="line-item">
        <div class="circle-header">
          <img src="../assets/small_internia.png" alt="">
        </div>
        <div class="name">All Employers</div>
      </div>
    </div>
    <div class="title"> Project</div>
    <div class="item-2">
      <div class="line-item">
        <div class="circle">
          <img src="../assets/avatar-1.png" alt="">
        </div>
        <div class="name">Arena Sport</div>
      </div>
      <div class="line-item">
        <div class="circle" style="background:lightseagreen; ">
          <span class="initials">DV</span>
        </div>
        <div class="name">DSV</div>
      </div>
      <div class="line-item">
        <div class="circle" style="background: mediumturquoise;" >
          <span class="initials">SM</span>
        </div>
        <div class="name">Seafood Mall</div>
      </div>
      <div class="line-item">
        <div class="circle" style="background:tomato; ">
          <span class="initials">FS</span>
        </div>
        <div class="name">FireStar</div>
      </div>
      <div class="line-item">
        <div class="circle">
          <img src="../assets/small_internia.png" alt="">
        </div>
        <div class="name">Zeta Bank</div>
      </div>

    </div>
    <div class="title">Status</div>
    <div class="item-3">
      <div class="line-item">
        <div class="circle" style="background: dodgerblue;">
          <span class="initials">FT</span>
        </div>
        <div class="name">Full time</div>
      </div>
      <div class="line-item">
        <div class="circle" style="background: mediumaquamarine">
          <span class="initials">PT</span>
        </div>
        <div class="name">Part time</div>
      </div>
    </div>
    <div class="item-4">
      <button>add project</button>
    </div>
  </div>
</template>

<script>
export default {

}
</script>

<style lang="scss">
.sidebar {
  background: white;
  padding: 25px 35px;
  border-radius: 20px;
  box-shadow: 2px 4px 20px -4px rgba(0, 0, 0, 0.1);
}

.line-item {
  cursor: pointer;
  padding: 10px 10px;
  display: flex;
  align-items: center;
  i {
    font-size: 47px;
  }
  .name {
    // letter-spacing: 1px;
    margin-left: 20px;
  }

  &:hover{
    font-weight: bold;
    border-radius: 10px;
    background: darken($color: whitesmoke, $amount: 3%);
  } 
}
.title {
  color: silver;
  font-weight: bolder;
  font-size: 14px;
  text-transform: uppercase;
  margin: 20px 16px;
}

:root {
  --avatar-size: 50px;
  /* change this value anything, e.g., 100px, 10rem, etc. */
}

.circle {
  // background-color: #ccc;
  border-radius: 50%;
  height: var(--avatar-size);
  text-align: center;
  width: var(--avatar-size);

  img {
    height: 50px;
  }
}

.initials {
  color: white;
  font-size: calc(var(--avatar-size) / 2); /* 50% of parent */
  line-height: 1;
  position: relative;
  top: calc(var(--avatar-size) / 4); /* 25% of parent */
}


.circle-header {
  img {
    border-radius: 50%;
    height: 50px;
  }
}

.item-4 {
  margin-top: -30px;
  position: relative;
  top: 50px;
  left: 30px;
  button {
    background: mediumslateblue;
    height: 50px;
    animation: none;
    font-size: 16px;
  }
}
</style>
