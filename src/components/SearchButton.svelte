<form action="#" class="search-container">
  <input type="search" name="q" id="search-box" class="search-box" />
  <label for="search-box">
    <svg
      viewBox="0 0 24 24"
      width="24"
      height="24"
      stroke="#060705"
      stroke-width="2"
      fill="none"
      stroke-linecap="round"
      stroke-linejoin="round"
      class="search-icon"
    >
      <circle cx="11" cy="11" r="8"></circle>
      <line x1="21" y1="21" x2="16.65" y2="16.65"></line>
    </svg>
  </label>
  <input type="submit" value="" id="search-submit" />
</form>

<style>
  .search-box {
    -webkit-transition: width 0.6s, border-radius 0.6s, background 0.6s,
      box-shadow 0.6s;
    transition: width 0.6s, border-radius 0.6s, background 0.6s, box-shadow 0.6s;
    width: 40px;
    height: 40px;
    border-radius: 20px;
    border: none;
    cursor: pointer;
    background: #fed121;
  }
  .search-box + label .search-icon {
    color: black;
  }
  .search-box:hover {
    color: white;
    background: #ae901a;
    box-shadow: 0 0 0 5px #3d4752;
  }
  .search-box:hover + label .search-icon {
    color: white;
  }
  .search-box:focus {
    -webkit-transition: width 0.6s cubic-bezier(0, 1.22, 0.66, 1.39),
      border-radius 0.6s, background 0.6s;
    transition: width 0.6s cubic-bezier(0, 1.22, 0.66, 1.39), border-radius 0.6s,
      background 0.6s;
    border: none;
    outline: none;
    box-shadow: none;
    padding-left: 15px;
    cursor: text;
    width: 300px;
    border-radius: auto;
    background: #ebebeb;
    color: black;
  }
  .search-box:focus + label .search-icon {
    color: black;
  }
  .search-box:not(:focus) {
    text-indent: -5000px;
  }

  #search-submit {
    position: relative;
    left: -5000px;
  }

  .search-icon {
    position: relative;
    left: -34px;
    color: white;
    cursor: pointer;
    top: 5px;
  }
</style>
