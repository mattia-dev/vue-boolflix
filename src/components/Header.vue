<template>
  <header class="d-flex justify-content-between">
    <div class="left-content d-flex">
      <img src="../assets/netflix-logo.png" alt="boolflix-logo">

      <ul class="d-flex align-items-center">
        <li>Home</li>
        <li>SerieTV</li>
        <li>Film</li>
        <li>Originali</li>
        <li>Aggiunti di recente</li>
        <li>La mia lista</li>
      </ul>
    </div>

    <div class="right-content d-flex">
      <ul class="d-flex align-items-center">
        <li class="d-flex align-items-center">
          <i class="fas fa-search"></i>
        </li>

        <li>BAMBINI</li>
        
        <li class="d-flex align-items-center position-relative">
          <i class="fas fa-bell"></i>
          
          <span class="position-absolute top-20 start-100 translate-middle badge rounded-pill bg-danger">1<span class="visually-hidden">unread messages</span></span>
        </li>

        <li class="d-flex align-items-center">
          <img src="../assets/netflix-profile.png" alt="profile-image">

          <i class="fas fa-caret-down"></i>
        </li>
      </ul>
    </div>
  </header>
</template>

<script>

export default {
  name: 'Header',
}
</script>

<style lang="scss" scoped>
@import "../style/app.scss";

header {
  height: 80px;
  padding: 0 12px;

  .left-content {
    height: 100%;

    img {
      height: 100%;
    }

    ul {
      margin: 0;
      padding-left: 48px;
      list-style: none;
      color: $text-secondary;
      font-weight: 500;

      li {
        margin-right: 24px;
        cursor: pointer;
        transition: .2s;

        &:hover {
          color: $text-primary;
        }
      }
    }
  }

  .right-content {

    ul {
      margin: 0;
      padding: 0;
      list-style: none;
      color: $text-primary;

      li {
        margin-right: 24px;
        cursor: pointer;
        transition: .2s;

        &:hover {
          color: $text-white;
        }

        .svg-inline--fa {
          font-size: 20px;
        }

        .badge {
          padding: .20em .45em .25em .45em;
          font-size: .65em;
        }

        img {
          height: 40px;
          margin-right: 8px;
        }
      }
    }
  }
}
</style>