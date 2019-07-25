<template>
  <div class="home">
    <section class="main">
        <Header></Header>
        <div class="main-content-body">
          <div class="menu-tab">
            <h1>employee</h1>
            <Button msg="add employer" />
          </div>
          <div class="menu-body">
            <Sidebar/>
            <div class="content">
              <div class="content-header" >
                <div class="employee" style=" width: 22.5%; display: flex; justify-content: space-between;">
                  <input type="checkbox" name="" id="">
                  <div>
                    <span>Employee</span>
                    <i class="fas fa-long-arrow-alt-up"></i>
                  </div>
                  
                </div>
                <div class="employee">
                  <span>Salary</span>
                  <i class="fas fa-long-arrow-alt-up"></i>
                </div>
                <div class="employee">
                  <span>Status</span>
                  <i class="fas fa-long-arrow-alt-down"></i>
                </div>
                <div class="employee" style="width: 14.5%;">
                  <span>manage</span>
                </div>
              </div>

              <div class="cards" v-for="data in gitData.items" :key="data.id">
                <div class="employee">
                  <input type="checkbox" name="" id="">
                  <img :src="data.owner.avatar_url" alt="avatar">
                  <div class="user">
                    <div class="name">{{data.name}}</div>
                    <div class="role">{{data.owner.type}}</div>
                  </div>
                </div>

                <div class="salary" style="width: 15%">
                  <div class="amount">
                    ${{data.score}}
                  </div>
                  <div class="time"> {{data.owner.login}}</div>
                </div>

                <div class="status" style="width:15%">
                  <div class="period">{{data.default_branch}}</div>
                  <div class="duration"> {{data.forks}} months</div>
                </div>

                <div class="manage" >
                  <i class="far fa-edit"></i>
                  <div class="line"></div>
                  <i class="delete far fa-trash-alt"></i>
                </div>
              </div>

            </div>
          </div>
       
      </div>
    </section>
  </div>
</template>

<script>
import Header from '../components/Header.vue'
import Button from '../components/Buttton.vue'
import Sidebar from '../components/Sidebar.vue'
export default {
  name: 'home',
  components: {
    Header,
    Button,
    Sidebar
  },
  data: function () {
    return {
      gitData: ''
    }
  },
  methods: {
    getUser: function () {
      let vm = this
      console.log('tested')
      fetch('https://api.github.com/search/repositories?q=tetris+language:assembly&sort=stars&order=desc&page=1&per_page=7')
        .then(function(response) {
          return response.json();
        })
        .then(function(myJson) {
          vm.gitData = myJson
        });
    }
  },
  created: function () {
    this.getUser()
  }
}
</script>
<style lang="scss">
body {
  background: whitesmoke;
}
.main {
  // padding: 60px 100px;
}
.inner-container {
    transition: box-shadow 0.3s ease-in-out;
    box-shadow: 2px 4px 20px -4px rgba(0, 0, 0, 0.1);
    border: 1px solid #ececec;
    border-radius: 20px;
    padding-bottom: 20px;
}
.main-content-body {
  margin: auto 70px auto;

  .menu-tab {
    display: flex;
    align-items: center;
    justify-content: space-between;
    margin: 15px 0px;
    h1 {
      font-size: 32px;
    }
  }

  .menu-body {
    display: grid;
    grid-template-columns: 300px auto;
    grid-column-gap: 35px;

    .content {
      border-radius: 20px;

      .content-header{
        display: flex;
        justify-content: space-between;
        margin-bottom: 15px;
        margin: 0px 18px 15px 18px;

        .employee {
          text-transform: uppercase; 
          font-size: 11px; 
          font-weight: bolder;
        }
      }
      .cards {
        cursor: pointer;
        margin-bottom: 15px;
        align-items: center;
        background: white;
        border-radius: 10px;
        padding: 18px;
        display: flex;
        justify-content: space-between;
        transition: box-shadow .3s;
        box-shadow: 2px 4px 20px -4px rgba(0, 0, 0, 0.1);

        .employee {
          display: flex;
          // justify-content: space-between;
          align-items: center;
          width: 31%;
          input, img {
            margin-right: 20px;
          }
          .role {
            font-weight: lighter;
            font-size: 13px;
          }
          .name {
            font-weight: bold;
          }
          img{
            height: 50px;
            border-radius: 50%;
          }
        }

        .salary {
          .time {
            font-weight: lighter;
            font-size: 13px;
          }
        }


        .status {
          .duration {
            font-weight: lighter;
            font-size: 13px;
          }
        }

        .manage {
          display: flex;
          justify-content: space-between;
          width: 14%;

          .line {
              border-left: 1px solid silver;
              height: 40px;
          }
          i {
            font-size: 30px;
            color: silver;
            cursor: pointer;
          }
        }

        &:hover {
          transform: scale(1.02);
          box-shadow: 0 5px 15px rgba(0,0,0,0.3);
          .manage {
            .delete {
              color: tomato;
            }
          }
        }
      }
    }
  }
}
</style>
