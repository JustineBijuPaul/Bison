<template>
  <div class="mlogowork">
    <a href="http://localhost:5173">
      <img src="../assets/img/logo.png" alt="logo">
      <p>ISON</p>
    </a>
  </div>
  <nav class="navbar navbar-expand-custom navbar-mainbg">
    <a class="navbar-brand" href="#">
      <div class="logo">
        <div class="logowork">
          <a href="http://localhost:5173">
            <img src="../assets/img/logo.png" alt="logo">
            <p>ISON</p>
          </a>
        </div>
      </div>
    </a>
    <button class="navbar-toggler" type="button" aria-controls="navbarSupportedContent" aria-expanded="false"
      aria-label="Toggle navigation">
      <i class="fas fa-bars text-white"></i>
    </button>
    <div class="collapse navbar-collapse navbar-link" id="navbarSupportedContent">
      <ul class="navbar-nav ml-auto">
        <div class="hori-selector">
          <div class="left"></div>
          <div class="right"></div>
        </div>
        <li class="nav-item">
          <a class="nav-link" href="#dashboard"><i class="fas"></i>Dashboard</a>
        </li>
        <li class="nav-item active">
          <a class="nav-link" href="#addressbook"><i class="far"></i>Address Book</a>
        </li>
        <li class="nav-item">
          <a class="nav-link" href="#Components"><i class="far"></i>Components</a>
        </li>
        <li class="nav-item">
          <a class="nav-link" href="#calendar"><i class="far"></i>Calendar</a>
        </li>
        <li class="nav-item">
          <a class="nav-link" href="#charts"><i class="far"></i>Charts</a>
        </li>
        <li class="nav-item">
          <a class="nav-link" href="#documents"><i class="far"></i>Documents</a>
        </li>
      </ul>
    </div>
  </nav>
</template>

<script>
export default {
  mounted() {
    this.test();
    window.addEventListener('resize', this.handleResize);
    document.querySelector('.navbar-toggler').addEventListener('click', this.handleToggle);
  },
  methods: {
    test() {
      var tabsNewAnim = document.querySelector('#navbarSupportedContent');
      var selectorNewAnim = tabsNewAnim.querySelectorAll('li').length;
      var activeItemNewAnim = tabsNewAnim.querySelector('.active');
      var activeWidthNewAnimHeight = activeItemNewAnim.offsetHeight;
      var activeWidthNewAnimWidth = activeItemNewAnim.offsetWidth;
      var itemPosNewAnimTop = activeItemNewAnim.offsetTop;
      var itemPosNewAnimLeft = activeItemNewAnim.offsetLeft;
      document.querySelector('.hori-selector').style.top = itemPosNewAnimTop + 'px';
      document.querySelector('.hori-selector').style.left = itemPosNewAnimLeft + 'px';
      document.querySelector('.hori-selector').style.height = activeWidthNewAnimHeight + 'px';
      document.querySelector('.hori-selector').style.width = activeWidthNewAnimWidth + 'px';
      document.querySelectorAll('#navbarSupportedContent li').forEach((item) => {
        item.addEventListener('click', (e) => {
          document.querySelectorAll('#navbarSupportedContent li').forEach((item) => {
            item.classList.remove('active');
          });
          e.target.parentNode.classList.add('active');
          var activeWidthNewAnimHeight = e.target.parentNode.offsetHeight;
          var activeWidthNewAnimWidth = e.target.parentNode.offsetWidth;
          var itemPosNewAnimTop = e.target.parentNode.offsetTop;
          var itemPosNewAnimLeft = e.target.parentNode.offsetLeft;
          document.querySelector('.hori-selector').style.top = itemPosNewAnimTop + 'px';
          document.querySelector('.hori-selector').style.left = itemPosNewAnimLeft + 'px';
          document.querySelector('.hori-selector').style.height = activeWidthNewAnimHeight + 'px';
          document.querySelector('.hori-selector').style.width = activeWidthNewAnimWidth + 'px';
        });
      });
    },
    handleResize() {
      setTimeout(this.test, 500);
    },
    handleToggle() {
      const navbarCollapse = document.querySelector('.navbar-collapse');
      navbarCollapse.classList.toggle('collapse');
      navbarCollapse.classList.toggle('show');
      setTimeout(this.test, 300);
    }
  }
}
</script>

<style scoped></style>
