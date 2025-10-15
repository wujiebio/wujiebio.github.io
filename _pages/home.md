---
title: "Brain Cell Atlas - Home"
layout: homelay
excerpt: "Brain Cell Atlas - Brain Data Centre: Facilitating Brain Disease Research with big data"
sitemap: true
permalink: /
---

<div style="text-align:center; margin-top:0; background-color:yellow;">
<a href="https://www.braincellatlas.org/index" style="color:#23265F; font-size:30px;">Click here to get access to Brain Cell Atlas web portal version 1.0</a>
</div>
<br/>
<br/>
<br/>

<div class="container">
<div class="row" style="display: flex; justify-content: space-between; width: 100%"> <!-- 两端对齐-->
<div class="col-lg-3 text-center custom-column">
<div class="img-circle card photo-card card-clickable" onclick="handleClick(this)">
<a href="#" onclick="showImage0('{{ site.url }}{{ site.baseurl }}/images/homePage/Adult.png'); return false">
<img src="{{ site.url }}{{ site.baseurl }}/images/homePage/adult-brain.png" class="rounded-circle" />
</a>
</div>
<div>
<p class="text-center" style="margin-top: 16px;">
<b style="font-size: 24px;">
<a href="#" onclick="showImage0('{{ site.url }}{{ site.baseurl }}/images/homePage/Adult.png'); return false">ADULT BRAIN</a>
</b>
</p>
</div>
</div>


<div class="col-lg-3 text-center custom-column">
<div class="img-circle card photo-card card-clickable" onclick="handleClick(this)">
<a href="#" onclick="showImage0('{{ site.url }}{{ site.baseurl }}/images/homePage/Fetal.png'); return false">
<img src="{{ site.url }}{{ site.baseurl }}/images/homePage/fetal-brain.png" class="rounded-circle" />
</a>
</div>
<div>
<p class="text-center" style="margin-top: 16px;">
<b style="font-size: 24px;">
<a href="#" onclick="showImage0('{{ site.url }}{{ site.baseurl }}/images/homePage/Fetal.png'); return false">FETAL BRAIN</a>
</b>
</p>
</div>
</div>


<div class="col-lg-3 text-center custom-column">
<div class="img-circle card photo-card card-clickable" onclick="handleClick(this)">
<a href="#" onclick="showImage0('{{ site.url }}{{ site.baseurl }}/images/homePage/Tumour.png'); return false">
<img src="{{ site.url }}{{ site.baseurl }}/images/homePage/tumour-brain.png" class="rounded-circle" />
</a>
</div>
<div>
<p class="text-center" style="margin-top: 16px;">
<b style="font-size: 24px;">
<a href="#" onclick="showImage0('{{ site.url }}{{ site.baseurl }}/images/homePage/Tumour.png'); return false">TUMOUR</a>
</b>
</p>
</div>
</div>

<div class="col-lg-3 text-center custom-column">
<div class="img-circle card photo-card card-clickable" onclick="handleClick(this)">
<a href="#" onclick="showImage0('{{ site.url }}{{ site.baseurl }}/images/homePage/Organoid.png'); return false">
<img src="{{ site.url }}{{ site.baseurl }}/images/homePage/drganoid-brain.png" class="rounded-circle" />
</a>
</div>
<div>
<p class="text-center" style="margin-top: 16px;">
<b style="font-size: 24px;">
<a href="#" onclick="showImage0('{{ site.url }}{{ site.baseurl }}/images/homePage/Organoid.png'); return false">ORGANOID</a>
</b>
</p>
</div>
</div>


<div class="col-lg-3 text-center custom-column">
<div class="img-circle card photo-card card-clickable" onclick="handleClick(this)">
<a href="#" onclick="showImage0('{{ site.url }}{{ site.baseurl }}/images/homePage/Mouse.png'); return false">
<img src="{{ site.url }}{{ site.baseurl }}/images/homePage/animal-brain.png" class="rounded-circle" />
</a>
</div>
<div>
<p class="text-center" style="margin-top: 16px;">
<b style="font-size: 24px;">
<a href="#" onclick="showImage0('{{ site.url }}{{ site.baseurl }}/images/homePage/Mouse.png'); return false">MOUSE BRAIN</a>
</b>
</p>
</div>
</div>

</div>
</div>





<br/><br/><br/>

<div class="container">
<div class="row" >
<div class="image-container">
<img id="photo" src="{{ site.url }}{{ site.baseurl }}/images/homePage/Adult.png" alt="Default Photo" style="max-height: 450px;">
</div>
</div>
</div>

<!-- <h3>Cite us </h3>
<p>Chen, Xinyue & Huang, Yin & Huang, Ziliang & Xu, Lahong & Huang, Liangfeng & Ye, Mingli & You, Renke & Zhang, Xuegong & Miao, Zhichao*. (2023). Brain Cell Atlas: An Integrative Ensemble of Cell Transcriptomes Across Human Brain Regions. 10.21203/rs.3.rs-3221500/v1.</p>
<br/> -->

<h3>Cite us </h3>
<div class="left-aligned" style="width: 100%;">
Xinyue Chen#, Yin Huang#, Liangfeng Huang#, Ziliang Huang#, Zhao-Zhe Hao#, Lahong Xu, Nana Xu, Zhi Li, Yonggao Mou, Mingli Ye, Renke You, Xuegong Zhang, Sheng Liu*, Zhichao Miao*. <br>
<strong style="color:#23265F;font-weight: bold">A brain cell atlas integrating single-cell transcriptomes across human brain regions. Nat Med (2024). https://doi.org/10.1038/s41591-024-03150-z.</strong><br>
<!-- <a> Unpublished</a> -->
</div>

<script>
  document.addEventListener('DOMContentLoaded', function() {
    var adultButton = document.querySelector('.col-lg-4:nth-child(1) .card-clickable');
    adultButton.click();
  });
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
</style>
<style>
    .photo-card {
/*         width: 350px;
        height: 350px; */
        border: 10px solid #ccc; 
        overflow: hidden;
        border-radius: 50%;
        position: relative;
        background-size: cover;
 /*        display: flex;  
        justify-content: right; /* 水平居中对齐 */
        /* align-items: right;  */
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
<script>
  var clickedCard = null;

  function handleClick(card) {
    if (clickedCard !== null) {
      clickedCard.classList.remove("clicked");
    }

    card.classList.add("clicked");
    clickedCard = card;
  }
</script>

<style>
    .custom-column {
        margin: 0 10px; /* 设置列之间的间距 */
        text-align: center
    }
</style>
