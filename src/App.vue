<template>
  <div id="app">
    <h1> Transit ACF </h1>
      <div id="nav">
          <router-link to="/">
            <div class="button">
              <p class="btnText">HOME</p>
              <div class="btnTwo">
                <p class="btnText2">GO!</p>
              </div>
            </div>
          </router-link> 
           <router-link to="/about">
            <div class="button">
              <p class="btnText">ABOUT</p>
              <div class="btnTwo">
                <p class="btnText2">GO!</p>
              </div>
            </div>
          </router-link>
      </div>
    <b-container>
      <router-view/>
    </b-container>
    <div class="footer">
      <div class="line-it-button" data-lang="ja" data-type="like" data-url="https://org-media.line.me/ja/how_to_install#likebutton" data-share="true" style="display: none;"></div>
    </div>
  </div>
</template>

<style lang="scss">
@import url(https://fonts.googleapis.com/css?family=Roboto:700);
#app {
  font-family: 'Avenir', Helvetica, Arial, sans-serif;
  -webkit-font-smoothing: antialiased;
  -moz-osx-font-smoothing: grayscale;
  text-align: center;
  margin-top:3em;
}
#nav {
  position:fixed;
  top:70vh;
  left:0;
  text-align:center;  
  -moz-user-select: -moz-none;
  -khtml-user-select: none;
  -webkit-user-select: none;
  transform: translateY(-65%);
  .button {
    background: #3D4C53;
    margin : 20px auto;
    width : 100px;
    height : 50px;
    overflow: hidden;
    text-align : center;
    transition : .2s;
    cursor : pointer;
    border-radius: 3px;
    box-shadow: 0px 1px 2px rgba(0,0,0,.2);
  }
  .btnTwo {
    position : relative;
    width : 180px;
    height : 100px;
    margin-top: -100px;
    padding-top: 2px;
    background : #26A69A;
    left : -250px;
    transition : .3s;
  }
  .btnText {
    color : white;
    transition : .3s;
  }
  .btnText2 {
    margin-top : 63px;
    margin-right : -130px;
    color : #FFF;
  }
  .button:hover .btnTwo{ /*When hovering over .button change .btnTwo*/
    left: -130px;
  }
  .button:hover .btnText{ /*When hovering over .button change .btnText*/
    margin-left : 65px;
  }
  .button:active { /*Clicked and held*/
    box-shadow: 0px 5px 6px rgba(0,0,0,0.3);
  }
}
.footer{

}
</style>
