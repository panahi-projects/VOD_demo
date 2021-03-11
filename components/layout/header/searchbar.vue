<template>
  <div>
    <b-container fluid>
      <div class="search-bar">
        <b-form-input type="search" class="search-bar-input"></b-form-input>
        <span class="search-icon">
          <font-awesome-icon icon="search" />
        </span>
      </div>
    </b-container>
  </div>
</template>
<style scoped>
.search-bar{
    position:relative;
}
.search-bar-input {
  margin: 0;
  padding-top: 6px;
  padding-bottom: 6px;
  padding-right: 48px;
  border: none;
  color: #c0c0c0;
  float: left;
  background-color: #202020;
  height: 32px;
  transition:0.3s;
}
.search-bar-input:focus{
    border:1px solid #e41f43;
    box-shadow: 1px 0 10px rgb(224, 72, 100,0.5);
}
.search-icon {
  color: #e41f43;
  position: absolute;
  right: 5px;
  top:50%;
  padding:2px;
  cursor:pointer;
  transition: 0.3s;
}
.search-icon:hover,
.search-icon:focus{
    color: #c09aa1;
}
.search-icon * {
  width: 25px;
}
</style>
