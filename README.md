# 練習 - 形象首頁版型

- [Github Page](https://hedgehogkucc.github.io/Pr-Bootstrap-1/index.html)

## Bootstrap Template + Font Awesome

``` html
<!doctype html>
<html lang="en">
  <head>
    <!-- Required meta tags -->
    <meta charset="utf-8">
    <meta name="viewport" content="width=device-width, initial-scale=1, shrink-to-fit=no">

    <!-- Bootstrap CSS -->
    <link rel="stylesheet" href="https://stackpath.bootstrapcdn.com/bootstrap/4.3.1/css/bootstrap.min.css" integrity="sha384-ggOyR0iXCbMQv3Xipma34MD+dH/1fQ784/j6cY/iJTQUOhcWr7x9JvoRxT2MZw1T" crossorigin="anonymous">
    
    <!-- Font Awesome -->
    <script
      src="https://kit.fontawesome.com/6fb2d374d0.js"
      crossorigin="anonymous"
    ></script>

    <title>Hello, world!</title>
  </head>
  <body>
    <h1>Hello, world!</h1>

    <!-- Optional JavaScript -->
    <!-- jQuery first, then Popper.js, then Bootstrap JS -->
    <script src="https://code.jquery.com/jquery-3.3.1.slim.min.js" integrity="sha384-q8i/X+965DzO0rT7abK41JStQIAqVgRVzpbzo5smXKp4YfRvH+8abtTE1Pi6jizo" crossorigin="anonymous"></script>
    <script src="https://cdnjs.cloudflare.com/ajax/libs/popper.js/1.14.7/umd/popper.min.js" integrity="sha384-UO2eT0CpHqdSJQ6hJty5KVphtPhzWj9WO1clHTMGa3JDZwrnQq4sF86dIHNDz0W1" crossorigin="anonymous"></script>
    <script src="https://stackpath.bootstrapcdn.com/bootstrap/4.3.1/js/bootstrap.min.js" integrity="sha384-JjSmVgyd0p3pXB1rRibZUAYoIIy6OrQ6VrjIEaFf/nJGzIxFDsf4x0xIM+B07jRM" crossorigin="anonymous"></script>
  </body>
</html>
```

<br>

## 熟悉 Bootstrap

**Layout**

- [Overview](https://getbootstrap.com/docs/4.3/layout/overview/) --- `.container` `.container-fluid` `Responsive breakpoints`
- [Grid](https://getbootstrap.com/docs/4.3/layout/grid/)

**Content**

- [Typography](https://getbootstrap.com/docs/4.3/content/typography/)

**Components**

- [Navbar](https://getbootstrap.com/docs/4.3/components/navbar/)
- [Collapse](https://getbootstrap.com/docs/4.3/components/collapse/)
- [Dropdowns](https://getbootstrap.com/docs/4.3/components/dropdowns/)
- [Carousel](https://getbootstrap.com/docs/4.3/components/carousel/)
- [Buttons](https://getbootstrap.com/docs/4.3/components/buttons/)
- [Modal](https://getbootstrap.com/docs/4.3/components/modal/) - *Events

**Utilities**

- [Spacing](https://getbootstrap.com/docs/4.3/utilities/spacing/) - 調整間距
- [Colors](https://getbootstrap.com/docs/4.3/utilities/colors/) - 文字和背景色彩
- [Flex](https://getbootstrap.com/docs/4.3/utilities/flex/) - [圖解：CSS Flex 屬性一點也不難](https://wcc723.github.io/css/2017/07/21/css-flex/)

**Font Awesome**

- [Sizing Icons](https://fontawesome.com/how-to-use/on-the-web/styling/sizing-icons)

**HTML Tag**

- [header](https://www.w3schools.com/tags/tag_header.asp)
- [section](https://www.w3schools.com/tags/tag_section.asp)
- [small](https://www.w3schools.com/tags/tag_small.asp)
- [form](https://www.w3schools.com/tags/tag_form.asp)
- [iframe](https://www.w3schools.com/tags/tag_iframe.asp)
- [footer](https://www.w3schools.com/tags/tag_footer.asp)

<br>

### .container - 限制寬度

```
<nav class="navbar navbar-expand-lg navbar-dark bg-dark">
      <div class="container">
        <a class="navbar-brand" href="#">
```

<br>

### Carousel

因為圖片太大張不使用 `img` 

改用 `background-image: url()`

***自定義 class***

- `header-carousel-item` : 固定高度

- `bg-cover` : 限縮背景圖在這範圍內, 並且以中間內容為主呈現.

```
<div class="carousel-item header-carousel-item bg-cover" style="background-image: url(...)">
```

```
.header-carousel-item { height: 450px; }
.bg-cover {
	background-size: cover;
	background-position: center center;
}
```

<br>

### position: relative & absolue 用法

`section` 這層寫上 `position: relative`

內層就可以使用 `position: absolue` 來移動 (不佔空間)

`top: 0;` `bottom: 0;` 會隨著**自適應高度**張開

`justify-content-end` : 主軸線的推移至底部

`text-white` : 寬度 767px 以下時文字變白色

***自定義 class***

`text-md-dark` : 寬度 768px 以上時文字變 #333

```
 <section class="container-fluid py-5 bg-light text-white" style="position: relative">
        <div class="row">
          <div
            class="col-md-5 bg-cover"
            style="
                position: absolute; top: 0; bottom: 0;
                background-image: url(...)"
          ></div>
          <div class="container">
            <div class="row justify-content-end text-md-dark">
              <div class="col-md-7">
                <h3>歡迎來到六角餐廳</h3>
```

```
@media (min-width: 768px) {
	.text-md-dark { color: #333; }
}
```

<br>

### Flex

為了讓 `Font Awesome` 和 文字並排

在額外包一層 `.d-flex`

盡量不要寫在 `.col-md-6` 同一層

```
 <section class="py-5">
      <div class="container">
        <h2 class="text-center my-3 pb-5">如何這麼美味</h2>
        <div class="row">
          <div class="col-md-6">
            <div class="d-flex">
              <div class="mr-3 text-info">
                <i class="fas fa-award fa-5x"></i>
              </div>
              <div class="">
                <h3>美艷的食材</h3>
```

<br>

### Typography + flex-md-row-reverse

`flex-md-row-reverse` : 在寬度 768px 以上時, 將主軸線預設由左至右反轉, 才可以讓圖片佔滿右邊不留空隙 !

`z-index: 1;` : 設定權限才可以讓文字顯示於圖片前面 !

`text-truncate` : 會將超出的文字顯示成 ···

```
<section class="container-fluid bg-light py-5 text-white" style="position: relative;">
      <div class="row flex-md-row-reverse">
        <div class="container text-md-dark">
          <div class="row">
            <div class="col-md-7" style="z-index: 1;">
              <div class="container">
                <h2>讓快樂持續發生</h2>
```

<br>

### Google Map

開啟 Google Map 點選位置後

點擊 `分享` > `嵌入地圖` > `複製 HTML`

將 `width` 改為 `100%`

```
<iframe src="..." width="100%" height="450" frameborder="0" style="border:0;" allowfullscreen=""></iframe>
```

<br>

### Forms - Validation

瀏覽器預設方法驗證 `required` 

雖然不是所有瀏覽器都通用

但主流的瀏覽器都可以使用 !

```
<input
	type="text"
	class="form-control"
	id="username"
	placeholder="請輸入姓名"
	required
/>
```

<br>

驗證判斷樣式

在 `form` 加入 `class="needs-validation"` `novalidate`

```
<form action="" class="needs-validation" novalidate>
```

<br>

內容**有效**回饋

```
<div class="valid-feedback">
	Looks good!
</div>
```

<br>

內容**無效**回饋

```
<div class="invalid-feedback">
	請填入姓名 !!!
</div>
```

<br>

記得在 `</form>` 後面加上 `script`

```
<script>
// Example starter JavaScript for disabling form submissions if there are invalid fields
(function() {
  'use strict';
  window.addEventListener('load', function() {
    // Fetch all the forms we want to apply custom Bootstrap validation styles to
    var forms = document.getElementsByClassName('needs-validation');
    // Loop over them and prevent submission
    var validation = Array.prototype.filter.call(forms, function(form) {
      form.addEventListener('submit', function(event) {
        if (form.checkValidity() === false) {
          event.preventDefault();
          event.stopPropagation();
        }
        form.classList.add('was-validated');
      }, false);
    });
  }, false);
})();
</script>
```

<br>

### 巢狀 row col

使用這種巢狀方式用途

是用來避免內容過長 !

外層各占一半在裡面一層占 三分之二 的內容

雖然 `col` 會保留左右兩邊 `gutter` 空間 

但由於 `col` 是用 `padding` 去推左右兩邊空間

所以可以在這邊加上 `style="background-image: url(...)"`

```
<div class="row">
	<div class="col-md-6" style="background-image: url(...)">
		<div class="row">
			<div class="col-md-9">
				<small>...</small>
				<h3>...</h3>
				<p>...</p>
			</div>
		</div>
	</div>
</div>
```

<br>

### Modal

將 `data-toggle="modal"` `data-target="#loginModal"` 加入

```
<a href="#" class="btn btn-outline-primary mr-1" data-toggle="modal" data-target="#loginModal">登入</a>
```

<br>

把這段放在畫面的最下方

注意 id :

- `data-target="#loginModal"`
- `id="loginModal"`

```
<!-- Modal -->
<div class="modal fade" id="loginModal" tabindex="-1" role="dialog" aria-labelledby="exampleModalLabel" aria-hidden="true">
  <div class="modal-dialog" role="document">
    <div class="modal-content">
      <div class="modal-header">
        <h5 class="modal-title" id="exampleModalLabel">Modal title</h5>
        <button type="button" class="close" data-dismiss="modal" aria-label="Close">
          <span aria-hidden="true">&times;</span>
        </button>
      </div>
      <div class="modal-body">
        ...
      </div>
      <div class="modal-footer">
        <button type="button" class="btn btn-secondary" data-dismiss="modal">Close</button>
        <button type="button" class="btn btn-primary">Save changes</button>
      </div>
    </div>
  </div>
</div>
```

<br>

`data-dismiss="modal"` : 會將 modal 關閉

`data-toggle="modal"` `data-target="#registerModal"` : 會轉至註冊 modal

`class="mr-auto"` : 與右邊 button 產生距離

```
<a
	href="#"
	class="mr-auto"
	data-dismiss="modal"
	data-toggle="modal"
	data-target="#registerModal"
	>還沒有帳號嗎?<
/a>
```

<br>

### RegisterModal

***自定義 class***

`.modal-dialog-register` 將原本 `modal-dialog` `500px` 變寬

讓註冊頁面變好看

```
@media (min-width: 576px) {
	.modal-dialog-register {
		max-width: 700px;
	}
}
```

<br>

### 修改切換 modal 小 bug

在行動版時, 點選 `還沒有帳號嗎?` 轉至 `registerModal` 後捲軸無法往下 !

原因是在第一次點選 `登入` 時 

會在 `body` 加上 `class="modal-open"`

但在點選 `還沒有帳號嗎?` 切換時

`class="modal-open"` 被移除了 !!!

<br>

使用 `jQuery`

```
$(document).ready( function() {
	console.log('ready');
});
```

`console.log('ready');` : 檢測 ready 有沒有正確執行

<br>

要抓到這兩個連結

`<a href="#" class="mr-auto" data-dismiss="modal" data-toggle="modal" data-target="#loginModal">已經有帳號了?</a>`

`<a href="#" class="mr-auto" data-dismiss="modal" data-toggle="modal" data-target="#registerModal">還沒有帳號嗎?</a>`

共通點是 `a` `data-dismiss="modal"` `data-toggle="modal"`

使用 `$('a[data-dismiss="modal"][data-toggle="modal"]')` `.on`

`console.log('click');` : 檢測 有沒有成功

<br>

抓出 `data-target` 放入 變數 `target` 裡面

`var target = $(this).data('target');`

`console.log('target', target);` : 看抓出的是什麼

<br>

當點選抓出的 `target` ( `#registerModal` or `#loginModal` )

Events : `shown.bs.modal` 完全顯示 modal 後

觸發 `function()`

在 `body` 加入 Class `modal-open`

```
$(target).on('shown.bs.modal', function () {
	$('body').addClass('modal-open');
})
```

<br>

完整程式碼

```
<script>
	$(document).ready(function() {
	
		console.log('ready');
		
		$('a[data-dismiss="modal"][data-toggle="modal"]').on('click', function() {
		console.log('click');

		var target = $(this).data('target');
		console.log('target', target);

		$(target).on('shown.bs.modal', function () {
            $('body').addClass('modal-open');
			})
		})
	});
```
