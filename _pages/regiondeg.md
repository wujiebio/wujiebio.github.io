---
title: "Brain Cell Atlas - RegionDEG"
layout: homelay
excerpt: "Brain Cell Atlas -- RegionDEG"
permalink: /regiondeg/
---
<!-- <b>The page is under maintenance</b> -->
<div class="container">
<!--b style="font-size: 24px; color: #BF5701">
ATLAS
</b-->
<!--div class="shadow p-3 mb-5 bg-white rounded row"-->
<p><b>Step1</b> Click below to select a target dataset for different analysis.</p>
<div class="row" style="display: flex; justify-content: space-between;"> <!-- 两端对齐-->
<div class="col-lg-3 text-center custom-column">
<div class="img-circle card photo-card card-clickable" onclick="handleClick('Adult',this)">
<img src="{{ site.url }}{{ site.baseurl }}/images/homePage/adult-brain.png" class="rounded-circle" />
</div>
<div>
<p class="text-center" style="margin-top: 16px;">
<b style="font-size: 24px; color: #23265F">
ADULT BRAIN
</b>
</p>
</div>
</div>

<div class="col-lg-3 text-center custom-column">
<div class="img-circle card photo-card card-clickable" onclick="handleClick('Fetal',this)">
<img src="{{ site.url }}{{ site.baseurl }}/images/homePage/fetal-brain.png" class="rounded-circle" />
</div>
<div>
<p class="text-center" style="margin-top: 16px;">
<b style="font-size: 24px; color: #23265F">
FETAL BRAIN
</b>
</p>
</div>
</div>
<div class="col-lg-3 text-center custom-column">
<div class="img-circle card photo-card card-clickable" onclick="handleClick('Tumour',this)">
<img src="{{ site.url }}{{ site.baseurl }}/images/homePage/tumour-brain.png" class="rounded-circle" />
</div>
<div>
<p class="text-center" style="margin-top: 16px;">
<b style="font-size: 24px; color: #23265F">
TUMOR
</b>
</p>
</div>
</div>
<div class="col-lg-3 text-center custom-column">
<div class="img-circle card photo-card card-clickable" onclick="handleClick('Organoid',this)">
<img src="{{ site.url }}{{ site.baseurl }}/images/homePage/drganoid-brain.png" class="rounded-circle" />
</div>
<div>
<p class="text-center" style="margin-top: 16px;">
<b style="font-size: 24px; color: #23265F">
ORGANOID
</b>
</p>
</div>
</div>

<!--div class="col-lg-3 text-center">
<div class="img-circle card photo-card card-clickable" onclick="handleClick('Tumour',this)">
<img src="{{ site.url }}{{ site.baseurl }}/images/homePage/airway.png" class="rounded-circle" />
</div>
<div>
<p class="text-center" style="margin-top: 16px;">
<b style="font-size: 24px; color: #BF5701">
ORGANOID
</b>
</p>
</div>
</div-->

</div>
</div>


<style>
    .custom-column {
        margin: 0 50px; /* 设置列之间的间距 */
    }
</style>


<script>
  function showImage0(photoName) {
    var photoElement = document.getElementById('photo');
    photoElement.src = photoName;
    photoElement.alt = photoName;
  }
</script>

<style>
  .image-container {
    max-width: 100%;
    max-height: 100%;
    background-color: none;
    justify-content: center;
    align-items: center;
    box-shadow: none;
  }
  
  .image-container img {
    width: 100%;
    height: 100%;
    object-fit: contain;
  }
    .photo-card {
        border: 10px solid #ccc; 
        overflow: hidden;
        border-radius: 50%;
        position: relative;
        background-size: cover;
    }
    .photo-card:hover img {
        transform: scale(1.1);
    }
    .photo-card img {
        display: block;
        width: 100%;
        height: 100%;
        object-fit: cover;
        transition: transform 0.3s;
    }
    .photo-card.clicked {
        border-color: #23265F;
    }
</style>



<br>
<div class="container">
<p><b>Step211</b> Select the target Region.</p>
  <b style="font-size: 24px; color: #23265F">Expression</b>
  <div id="imageIdContainer"></div>
  <br/>
  <b style="font-size: 24px; color: #23265F">Region</b>
  <br>
  <select id="selectBox1" style="width: 400px;" onchange="handleSelectChange();displaySelectedImage()" selectedIndex="0"></select>
  <br/>
  <!-- <button onclick="displaySelectedImage()">显示选择的照片</button> -->
  <div class="image-container">
  <img id="selectedImage" src="" alt="Selected Image">
</div>
</div>

<!-- <div id="imageIdContainer"></div> -->
<style>
  /* 设置固定宽度 */
  #selectBox1 {
    width: 400px; /* 这里可以根据需要调整宽度 */
    height: 38px
  }
  .image-container {
    max-width: 100%;
    max-height: 100%;
    background-color: none;
    justify-content: center;
    align-items: center;
    box-shadow: none;
  }
  .image-container img {
    width: 100%;
    height: 100%;
    object-fit: contain;
  }
  .container {
  /* background-color: #f0f0f0; */ /* 设置背景颜色为您想要的颜色值 */
  box-shadow: 0 0 15px grey;
  border-radius: 10px; /* 设置边框圆角的半径，可以根据需要进行调整 */
  padding: 10px; /* 可选：添加内边距以增加内容与边框之间的间距 */
}
  .imageIdContainer{
    box-shadow: 0 0 15px grey;
    border-radius: 10px; 
    padding: 10px; 
  }
</style>

<script>
  var selectedImageId = null;
  var selectedOptions = [];
  var selectedButton = null;
  var selectBox1 = document.getElementById('selectBox1');
  var originalOrder = true;
  var clickedCard = null;
  document.addEventListener('DOMContentLoaded', function() {
    // 使用setTimeout确保页面完全加载后再执行
    setTimeout(function() {
      // 默认选中第一个选项（Adult Brain）
      var adultButton = document.querySelector('.col-lg-3:first-child .card-clickable');
      if (adultButton) {
        console.log('找到Adult按钮，准备点击');
        adultButton.click();
      } else {
        console.log('未找到Adult按钮');
        // 备用方案：直接调用handleClick函数
        var firstCard = document.querySelector('.card-clickable');
        if (firstCard) {
          handleClick('Adult', firstCard);
        }
      }
    }, 100);
  });
  
  function handleClick(imageId,card) {
    if (clickedCard !== null) {
    clickedCard.classList.remove("clicked");
  }
    card.classList.add("clicked");
    clickedCard = card;
    selectedImageId = imageId;
    selectedOptions = [];

    fetch('{{ site.url }}{{ site.baseurl }}/js/genepage/RegionDEG.json')
      .then(response => response.json())
      .then(data => {
        var options = data[imageId];
        updateSelectBoxOptions('selectBox1', options);
        handleSelectChange(); // 确保选中第一个选项
        document.getElementById('imageIdContainer').textContent = 'Atlas: ' + imageId;
      })
      .catch(error => {
        console.error('Error:', error);
      });

  }
  function handleSelectChange() {
    var selectBox1 = document.getElementById('selectBox1');
    var option1 = selectBox1.options[selectBox1.selectedIndex].value;
    selectedOptions = [option1];
    displaySelectedImage();
  }

  function displaySelectedImage() {
  if (selectedImageId !== null && selectedOptions.length === 1) {
    var imageName = selectedImageId + '_' + encodeURIComponent(selectedOptions[0]) + '.png';
    var imagePath = 'https://data.braincellatlas.org/volcano/RegionDEG/' + imageName;
    // 在此处显示照片，例如：
    var imageElement = document.getElementById('selectedImage');
    imageElement.src = imagePath;
    console.log('Selected Image:', imagePath);
  } else {
    console.log('Please select an image and options.');
  }
}
  function updateSelectBoxOptions(selectBoxId, options) {
    var selectBox = document.getElementById(selectBoxId);
    selectBox.innerHTML = generateOptionsHtml(options);
    if (options.length > 0) {
        selectBox.value = options[0]; // 默认选中第一个选项
    }
  }
  function generateOptionsHtml(options) {
    var optionsHtml = '';
    for (var i = 0; i < options.length; i++) {
      optionsHtml += '<option value="' + options[i] + '">' + options[i] + '</option>';
    }
    return optionsHtml;
  }
</script>