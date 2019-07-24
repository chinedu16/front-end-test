.<template>
  <div class="main-header">
    <div class="header-item">
      <div class="logo"> 
        <img src="../assets/internia_logo.png" alt="">
      </div>
      <div class="menu">
        <nav>
          <a>Calender</a>
          <a>Statistic</a>
          <a class="active">Employee</a>
          <a>Client</a>
          <a>Equipment</a>
        </nav>
      </div>
      <div class="setting">
        <i class="far fa-bell"></i>
        <i class="far fa-envelope"></i>
        <div class="user-info-image"><img src="http://api.randomuser.me/portraits/men/22.jpg" alt="avatar"></div>
      </div>
    </div>
  </div>
</template>

<script>
export default {

}
</script>
<style lang="scss">
.main-header {
  background: white;
  height: 96px;
  margin: -8px;

  .header-item {
    display: flex;
    justify-content: space-between;
    padding: 30px 30px;
    align-items: center;

    .logo {
      img {
        height: 40px;
      }
    }
    .menu {
      nav {
        .active {
          color: #333;
          border-bottom: 5px solid lightseagreen;
          padding-bottom: 30px;
          border-radius: 3px;
        }
        color: #adb5bd;
        font-weight: bold;
        a:first-child {
          margin: 0px;
        }
        a {
          cursor: pointer;
          margin-left: 40px;
          &:hover {
            color: #333;
            border-bottom: 5px solid lightseagreen;
            padding-bottom: 30px;
            border-radius: 3px;
          }
        }
      }
    }
    .setting {
      color: #adb5bd;
      font-weight: bold;
      display: flex;
      
      .user-info-image {
        img {
          border-radius: 50%;
          width: 36px;
          margin-left: 20px;
          width: 33px;
        }
      }
      i {
        margin-left: 20px;
        font-size: 32px;

        &:hover {
          color: #333;
          cursor: pointer;
        }
      }
    }
  }
}
</style>
