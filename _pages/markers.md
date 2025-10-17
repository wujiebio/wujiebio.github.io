---
title: "Brain Cell Atlas - Markers"
layout: homelay
excerpt: "Brain Cell Atlas -- Markers"
permalink: /markers/
---
<!-- <b>The page is under maintenance</b> -->
<html>
<head>
	<meta http-equiv="Content-type" content="text/html; charset=utf-8">
	<meta name="viewport" content="width=device-width,initial-scale=1,user-scalable=no">
	<link rel="stylesheet" type="text/css" href="https://cdn.datatables.net/1.12.1/css/jquery.dataTables.min.css">
	<link rel="stylesheet" type="text/css" href="https://cdn.datatables.net/buttons/2.2.3/css/buttons.dataTables.min.css">
</head>
<body>
  <script type="text/javascript"  src="https://code.jquery.com/jquery-3.5.1.js"></script>
	<script type="text/javascript"  src="https://cdn.datatables.net/1.12.1/js/jquery.dataTables.min.js"></script>
	<script type="text/javascript"  src="https://cdn.datatables.net/buttons/2.2.3/js/dataTables.buttons.min.js"></script>
	<script type="text/javascript"  src="https://cdnjs.cloudflare.com/ajax/libs/jszip/3.1.3/jszip.min.js"></script>
	<script type="text/javascript"  src="https://cdnjs.cloudflare.com/ajax/libs/pdfmake/0.1.53/pdfmake.min.js"></script>
	<script type="text/javascript"  src="https://cdnjs.cloudflare.com/ajax/libs/pdfmake/0.1.53/vfs_fonts.js"></script>
	<script type="text/javascript" src="https://cdn.datatables.net/buttons/2.2.3/js/buttons.html5.min.js"></script>
	<script type="text/javascript"  src="https://cdn.datatables.net/buttons/2.2.3/js/buttons.print.min.js"></script>

    <style>
		th {
        background-color: #23265F;
        background-color: #23265F;
        background-color: #23265F;
        color: rgba(255,255,255,0.9);
		    cursor: pointer;
        }
	</style>

<div class="container">
<!--b style="font-size: 24px;">
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
<b style="font-size: 24px; color: #23265F;">
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
<b style="font-size: 24px; color: #23265F;">
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
<b style="font-size: 24px; color: #23265F;">
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
<b style="font-size: 24px; color: #23265F;">
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
<b style="font-size: 24px;">
ORGANOID
</b>
</p>
</div>
</div-->

</div>
</div>
<br/>
<div class="container">
<p><b>Step2</b> Click the buttons to show the differentially expressed genes (DEGs) of the target Brain Region or the target Cell type.</p>
  <button id="buttonA" onclick="changeOrder('A')">By Region</button>
  <button id="buttonB" onclick="changeOrder('B')">By Cell type</button>
</div>
  <br/>

<div class="container">
<p><b>Step3</b> Select the target Cell type/Region to show the DEGs.</p>
  <p id="sentence"></p>
  
  <!-- 第一层选择 -->
  <div id="firstLevelContainer">
    <p><b id="firstLevelLabel">Select Category:</b></p>
    <div id="firstLevelOptions" class="selection-grid"></div>
  </div>
  
  <!-- 第二层选择 -->
  <div id="secondLevelContainer" style="display: none;">
    <p><b id="secondLevelLabel">Select Item:</b></p>
    <div id="secondLevelOptions" class="selection-grid"></div>
  </div>
  
  <button type="button" class="btn btn-primary btn-sm" style="text-transform: capitalize; margin-top: 20px;" onclick="toggleContent();displaySelectedImage();displaySelectedTable();">Markers</button>
</div>
<br/>
<div id="contentContainer" style="display: none;">
<div class="container">
<div class="image-container">
<b>Result1</b> Volcano Plot.
<img id="selectedImage" src="" alt="Selected Image">
</div>
</div>
<br/>
<div class="container">
<b>Result2</b> The table of DEGs.
<div id="csvTableContainer" style="max-height: 500px; overflow-y: auto;"></div>
</div>
</div>
<script>
jQuery( document ).ready(function( $ ) {
        $(document).ready( function () {
        $.noConflict();
        var table = $('#mytable').DataTable();
        });
})
</script>

<div class="container">
<p id="clickMessageContainer" style="display: block;">Please click</p>
</div>


<!-- <div class="container">
<table id="myTable" class="display table table-striped table-bordered" cellspacing="0" width="100%">
<thead>
  <tr>
    <th>Year</th>
    <th>Author</th>
    <th>Title</th>
    <th>Ribozyme name</th>
    <th>Description</th>
    <th>Journal</th>
  </tr>
</thead>
<tbody>
  <tr>
    <td>2004</td>
    <td>Adams, P. L., M. R. Stahley, A. B. Kosek, J. Wang and S. A. Strobel </td>
    <td>Crystal structure of a self-splicing group I intron with both exons.</td>
    <td><a href="https://www.ribocentre.org/docs/groupI.html"  target="_blank" ><b> Group I self-splicing intron</b></a></td>
    <td>Crystal structure of <em>Azoarcus</em> group I intron with both exons</td>
    <td ><a href="https://www.ncbi.nlm.nih.gov/pubmed/15175762"  target="_blank" ><b> Nature 430 (6995): 45-50.</b></a></td>
  </tr>
  <tr>
    <td>1989</td>
    <td>Flor, P. J., J. B. Flanegan and T. R. Cech </td>
    <td>A conserved base pair within helix P4 of the <em>Tetrahymena</em> ribozyme helps to form the tertiary structure required for self-splicing.</td>
    <td><a href="https://www.ribocentre.org/docs/groupI.html"  target="_blank" ><b> Group I self-splicing intron</b></a></td>
    <td>The conserved base pair C109-G212 in P4 contributes to the tertiary structure required for self-splicing</td>
    <td ><a href="https://www.ncbi.nlm.nih.gov/pubmed/2684642"  target="_blank" ><b> EMBO J 8 (11): 3391-9.</b></a></td>
  </tr>
  <tr>
    <td>1982</td>
    <td>Kruger, K., P. J. Grabowski, A. J. Zaug, J. Sands, D. E. Gottschling and T. R. Cech </td>
    <td>Self-splicing RNA: autoexcision and autocyclization of the ribosomal RNA intervening sequence of <em>Tetrahymena</em>.</td>
    <td><a href="https://www.ribocentre.org/docs/groupI.html"  target="_blank" ><b> Group I self-splicing intron</b></a></td>
    <td>Discovery</td>
    <td ><a href="https://www.ncbi.nlm.nih.gov/pubmed/6297754"  target="_blank" ><b> Cell 31 (1): 147-57.</b></a></td>
  </tr>
  <tr>
    <td>1982</td>
    <td>Davies, R. W., R. B. Waring, J. A. Ray, T. A. Brown and C. Scazzocchio </td>
    <td>Making ends meet: a model for RNA splicing in fungal mitochondria.</td>
    <td><a href="https://www.ribocentre.org/docs/groupI.html"  target="_blank" ><b> Group I self-splicing intron</b></a></td>
    <td>Determination of shared secondary structure</td>
    <td ><a href="https://www.ncbi.nlm.nih.gov/pubmed/6757759"  target="_blank" ><b> Nature 300 (5894): 719-24.</b></a></td>
  </tr>
  <tr>
    <td>1986</td>
    <td>Zaug, A. J. and T. R. Cech </td>
    <td>The intervening sequence RNA of <em>Tetrahymena</em> is an enzyme.</td>
    <td><a href="https://www.ribocentre.org/docs/groupI.html"  target="_blank" ><b> Group I self-splicing intron</b></a></td>
    <td>The intervening sequence RNA of <em>Tetrahymena</em> is an enzyme</td>
    <td ><a href="https://www.ncbi.nlm.nih.gov/pubmed/3941911"  target="_blank" ><b> Science 231 (4737): 470-5.</b></a></td>
  </tr>
  <tr>
    <td>1988</td>
    <td>Price, J. V. and T. R. Cech </td>
    <td>Determinants of the 3' splice site for self-splicing of the <em>Tetrahymena</em> pre-rRNA.</td>
    <td><a href="https://www.ribocentre.org/docs/groupI.html"  target="_blank" ><b> Group I self-splicing intron</b></a></td>
    <td>ωG is closely related to the choice of 3' splice site</td>
    <td ><a href="https://www.ncbi.nlm.nih.gov/pubmed/3209068"  target="_blank" ><b> Genes Dev 2 (11): 1439-47.</b></a></td>
  </tr>
  <tr>
    <td>1990</td>
    <td>Michel, F. and E. Westhof </td>
    <td>Modelling of the three-dimensional architecture of group I catalytic introns based on comparative sequence analysis.</td>
    <td><a href="https://www.ribocentre.org/docs/groupI.html"  target="_blank" ><b> Group I self-splicing intron</b></a></td>
    <td>3D models of  group I intron based on comparative sequence analysis</td>
    <td ><a href="https://www.ncbi.nlm.nih.gov/pubmed/2258934"  target="_blank" ><b> J Mol Biol 216 (3): 585-610.</b></a></td>
  </tr>
  <tr>
    <td>1996</td>
    <td>Cate, J. H., A. R. Gooding, E. Podell, K. Zhou, B. L. Golden, C. E. Kundrot, T. R. Cech and J. A. Doudna </td>
    <td>Crystal structure of a group I ribozyme domain: principles of RNA packing.</td>
    <td><a href="https://www.ribocentre.org/docs/groupI.html"  target="_blank" ><b> Group I self-splicing intron</b></a></td>
    <td>Crystal structure of <em>Tetrahymena</em> P4-P6 domain</td>
    <td ><a href="https://www.ncbi.nlm.nih.gov/pubmed/8781224"  target="_blank" ><b> Science 273 (5282): 1678-85.</b></a></td>
  </tr>
</tbody>
</table>
 -->
<style>
    .custom-column {
        margin: 0 50px; /* 设置列之间的间距 */
    }
</style>
<style>
  #csvTableContainer {
    max-height: 500px;
    overflow-y: auto;
  }

  /* 将表格头部固定 */
  #csvTableContainer thead {
    position: sticky;
    top: 0;
    background-color: white;
  }
</style>







<style>
  .active {
    background-color: #23265F; 
    color: white;
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
/*   .table-container {
    max-height: 500px; 
    overflow-y: auto;
  } */
</style>
<script type="text/javascript"  src="https://code.jquery.com/jquery-3.5.1.js"></script>
<script type="text/javascript"  src="https://cdn.datatables.net/1.12.1/js/jquery.dataTables.min.js"></script>
<script type="text/javascript"  src="https://cdn.datatables.net/buttons/2.2.3/js/dataTables.buttons.min.js"></script>
<script type="text/javascript"  src="https://cdnjs.cloudflare.com/ajax/libs/jszip/3.1.3/jszip.min.js"></script>
<script type="text/javascript"  src="https://cdnjs.cloudflare.com/ajax/libs/pdfmake/0.1.53/pdfmake.min.js"></script>
<script type="text/javascript"  src="https://cdnjs.cloudflare.com/ajax/libs/pdfmake/0.1.53/vfs_fonts.js"></script>
<script type="text/javascript" src="https://cdn.datatables.net/buttons/2.2.3/js/buttons.html5.min.js"></script>
<script type="text/javascript"  src="https://cdn.datatables.net/buttons/2.2.3/js/buttons.print.min.js"></script>
<div id="csvTableContainer"></div>
<script>
  var imageLoaded = false; // 添加一个全局变量用于跟踪图片加载状态
  var selectedImageId = null;
  var selectedOptions = [];
  var selectedButton = null;
  var originalOrder = true;
  var clickedCard = null;
  var firstLevelSelected = null;
  var secondLevelSelected = null;
  var currentDataset = null;
  // document.addEventListener('DOMContentLoaded', function() {
  //   var adultButton = document.querySelector('.col-lg-3:nth-child(1) .card-clickable');
  //   adultButton.click();
  // });
  function handleClick(imageId,card) {
    if (clickedCard !== null) {
    clickedCard.classList.remove("clicked");
  }
    card.classList.add("clicked");
    clickedCard = card;
    selectedImageId = imageId;
    selectedOptions = [];
    firstLevelSelected = null;
    secondLevelSelected = null;
    
    // 根据Step2选择的按钮类型加载相应数据文件
    var dataFile = '';
    if (selectedButton === 'A') {
      dataFile = 'region.json';  // By Region
    } else if (selectedButton === 'B') {
      dataFile = 'cellType.json';  // By Cell type
    }
    
    if (dataFile) {
      fetch('{{ site.url }}{{ site.baseurl }}/js/genepage/' + dataFile)
      .then(response => response.json())
      .then(data => {
          // 根据Step1选择的imageId获取对应的数据集
          currentDataset = data[imageId];  // 例如：data['Adult'] 或 data['Fetal']
          if (currentDataset) {
            // 获取当前数据集的所有keys（第一层选择）
            var keys = Object.keys(currentDataset);
            displayFirstLevelOptions(keys, selectedButton === 'A' ? 'regions' : 'cellTypes');
            // 隐藏第二层选择
            document.getElementById('secondLevelContainer').style.display = 'none';
          }
      })
      .catch(error => {
          console.error('Error loading data from ' + dataFile + ':', error);
        });
    }
    resetDisplay();
  }
  function handleSelectChange() {
    // 这个函数现在由新的选择界面处理
    // selectedOptions 已经在 selectFirstLevel 和 selectSecondLevel 中更新
    console.log('Current selection:', selectedOptions);
  }
  function resetDisplay() {
      var contentContainer = document.getElementById('contentContainer');
      var clickMessageContainer = document.getElementById('clickMessageContainer');
      contentContainer.style.display = 'none';
      clickMessageContainer.style.display = 'block';
    }
function displaySelectedImage() {
  if (selectedImageId !== null && selectedOptions.length === 2 && selectedOptions[0] && selectedOptions[1]) {
    var imageName;
    if (selectedButton === 'A') {
      imageName = selectedImageId + '_' + encodeURIComponent(selectedOptions[0]) + '_' + encodeURIComponent(selectedOptions[1]) + '.png';
    var imagePath = 'https://data.braincellatlas.org/volcano/VolcanoByRegion/' + imageName;
    } else if (selectedButton === 'B') {
      imageName = selectedImageId + '_' + encodeURIComponent(selectedOptions[1]) + '_' + encodeURIComponent(selectedOptions[0]) + '.png';
    var imagePath = 'https://data.braincellatlas.org/volcano/VolcanoByCellType/' + imageName;
    }
    console.log('Image path:', imagePath); // 调试信息
    /* var imagePath = '{{ site.url }}{{ site.baseurl }}/images/markerPage/volcano/' + imageName; */
    // 在此处显示照片，例如：
    var imageElement = document.getElementById('selectedImage');
    if (imageElement) {
      imageElement.onload = function() {
        // 图片加载成功时，清除错误消息
        var errorMessage = document.getElementById('errorMessage');
        if (errorMessage) {
          errorMessage.remove();
        }
        imageLoaded = true; // 图片加载成功
      };
      // 处理图片加载错误
      imageElement.onerror = function() {
        console.error('Failed to load image:', imagePath);
        imageElement.src = ''; // 清空src属性
        imageElement.alt = '';
        // 显示错误消息
        var errorMessage = document.getElementById('errorMessage');
        if (!errorMessage) {
          errorMessage = document.createElement('div');
          errorMessage.id = 'errorMessage';
          errorMessage.textContent = 'No figure to show';
          errorMessage.style.textAlign = 'center';
          imageElement.parentNode.insertBefore(errorMessage, imageElement.nextSibling);
        }
        imageLoaded = false; // 图片加载失败
      };
    imageElement.src = imagePath;
    imageElement.style.width = '500px';  // 设置宽度
    imageElement.style.height = 'auto';  // 高度自动调整
    // 设置图片居中
    imageElement.style.display = 'block';
    imageElement.style.margin = '0 auto';
    console.log('Selected Image:', imagePath);
  } else {
    console.error('Element with id "selectedImage" not found.');
  }
  } else {
    console.log('Please select an image and options.');
    // 当没有图片展示时，隐藏表格并显示 "No table" 消息
    hideTableAndShowMessage();
  }
}
function hideTableAndShowMessage() {
  var tableContainer = document.getElementById('csvTableContainer');
  tableContainer.innerHTML = ''; // 清空表格内容
  // 显示 "No table" 消息
  var noTableMessage = document.getElementById('noTableMessage');
  if (!noTableMessage) {
    noTableMessage = document.createElement('div');
    noTableMessage.id = 'noTableMessage';
    noTableMessage.textContent = 'No table to show';
    noTableMessage.style.textAlign = 'center';
    tableContainer.appendChild(noTableMessage);
  }
}
// function sortTable(columnIndex) {
//     var table = document.getElementById("your-table-id"); // 替换为你的表格的ID
//     var rows = Array.from(table.rows).slice(1); // 去掉表头，获取行数组 
//     // 根据指定的列索引进行排序
//     rows.sort(function(rowA, rowB) {
//         var cellA = rowA.cells[columnIndex].textContent.trim();
//         var cellB = rowB.cells[columnIndex].textContent.trim();
//         return cellA.localeCompare(cellB, "zh");
//     });
//     // 将排序后的行重新添加到表格中
//     rows.forEach(function(row) {
//         table.appendChild(row);
//     });
// }
// jQuery( document ).ready(function( $ ) {
//         $(document).ready( function () {
//         $.noConflict();
//         var table = $('#mytable').DataTable();
//         });
// })
function displaySelectedTable() {
  clearTableAndMessage();
  // 不再完全依赖imageLoaded状态，即使图片加载失败也尝试加载表格
  // if (!imageLoaded) {
  //   console.log('No image to show.');
  //   hideTableAndShowMessage();
  //   return;
  // }
  if (selectedImageId !== null && selectedOptions.length === 2 && selectedOptions[0] && selectedOptions[1]) {
    var tableName;
    var tablePath;
    if (selectedButton === 'A') {
      tableName = selectedImageId + '_' + encodeURIComponent(selectedOptions[0]) + '_' + encodeURIComponent(selectedOptions[1]) + '_cell_type.csv';
      tablePath = 'https://data.braincellatlas.org/markersByRegion/' + tableName;
    } else if (selectedButton === 'B') {
      tableName = selectedImageId + '_' + encodeURIComponent(selectedOptions[1]) + '_' + encodeURIComponent(selectedOptions[0]) + '_cell_type.csv';
      tablePath = 'https://data.braincellatlas.org/markersByCellType/' + tableName;
    } else {
      console.log('Please select an image and options.');
      hideTableAndShowMessage(); // 结束函数的执行，并显示 "No table" 消息
      return; // 结束函数的执行
    }
    console.log('Table Path:', tablePath);
    
    // 显示 loading 效果
    showTableLoading();
    
    var xhr = new XMLHttpRequest();
    xhr.open('GET', tablePath, true);
    xhr.onreadystatechange = function() {
      if (xhr.readyState === 4) {
        if (xhr.status === 200) {
          var csvData = xhr.responseText;
          console.log('CSV Data:', csvData);
          // 移除图片错误检查，允许表格独立显示
          // var errorMessage = document.getElementById('errorMessage');
          // if (errorMessage && errorMessage.textContent === 'No figure to show') {
          //   hideTableAndShowMessage(); // 当没有图片展示时，隐藏表格并显示 "No table" 消息
          //   return; // 结束函数的执行
          // }
          
          // 隐藏 loading 效果
          hideTableLoading();
          
          var tableContainer = document.getElementById('csvTableContainer');
          // 解析 CSV 数据
          var rows = csvData.split('\n');
          var tableHtml = '<table id="mytable" class="mytable table table-striped table-bordered" cellspacing="0" width="100%">';
          var headerHtml = `<thead>
          <tr>
              <th>genes</th>
              <th>avg_log2FC</th>
              <th>p_val</th>
              <th>p_val_adj</th>
              <th>pct.1</th>
              <th>pct.2</th>
          </tr>
          </thead>
          <tbody>`;
          tableHtml += headerHtml;
          for (var i = 1; i < rows.length; i++) {
            var cells = rows[i].split(',');
            tableHtml += '<tr>';
            for (var j = 0; j < cells.length; j++) {
                // 去掉每个单元格内容的引号
                var cellContent = cells[j].replace(/^"(.*)"$/, '$1');
                tableHtml += '<td>' + cellContent + '</td>';
            }
            tableHtml += '</tr>';
          }
          tableHtml += `</tbody>
          </table>`;
          // 清除 "No table" 消息
          var noTableMessage = document.getElementById('noTableMessage');
          if (noTableMessage) {
            noTableMessage.remove();
          }
          tableContainer.innerHTML = tableHtml;
          // 初始化表格并按第二列排序
          initializeDataTable();
        } else {
          // 处理请求失败的情况
          console.error('Failed to load table data. Status:', xhr.status, 'Response:', xhr.responseText);
          // 隐藏 loading 效果
          hideTableLoading();
          hideTableAndShowMessage();
        }
      }
    };
    xhr.send();
  } else {
    console.log('Please select an image and options.');
    hideTableAndShowMessage(); // 结束函数的执行，并显示 "No table" 消息
  }
}
jQuery( document ).ready(function( $ ) {
        $(document).ready( function () {
        $.noConflict();
        var table = $('#mytable').DataTable();
        });
})
function initializeDataTable() {
  jQuery(document).ready(function($) {
    $.noConflict();
    $('#mytable').DataTable({
      "order": [[1, "asc"]] // 默认按第二列（索引1）升序排序
    });
  });
}
function clearTableAndMessage() {
  // 清除表格内容
  var tableContainer = document.getElementById('csvTableContainer');
  tableContainer.innerHTML = '';
  // 显示 "No table" 消息
  var noTableMessage = document.getElementById('noTableMessage');
  if (!noTableMessage) {
    noTableMessage = document.createElement('div');
    noTableMessage.id = 'noTableMessage';
    noTableMessage.textContent = 'No table to show';
    noTableMessage.style.textAlign = 'center';
    tableContainer.appendChild(noTableMessage);
  }
}

// 显示表格加载效果
function showTableLoading() {
  var tableContainer = document.getElementById('csvTableContainer');
  tableContainer.innerHTML = '';
  
  var loadingContainer = document.createElement('div');
  loadingContainer.className = 'loading-container';
  loadingContainer.id = 'tableLoadingContainer';
  
  var spinner = document.createElement('div');
  spinner.className = 'loading-spinner';
  
  var loadingText = document.createElement('div');
  loadingText.className = 'loading-text';
  loadingText.textContent = 'loading...';
  
  loadingContainer.appendChild(spinner);
  loadingContainer.appendChild(loadingText);
  tableContainer.appendChild(loadingContainer);
}

// 隐藏表格加载效果
function hideTableLoading() {
  var loadingContainer = document.getElementById('tableLoadingContainer');
  if (loadingContainer) {
    loadingContainer.remove();
  }
}
  // 显示第一层选择选项
  function displayFirstLevelOptions(options, type) {
    var container = document.getElementById('firstLevelOptions');
    var firstLevelLabel = document.getElementById('firstLevelLabel');
    var secondLevelLabel = document.getElementById('secondLevelLabel');
    
    // 更新标签文本
    if (selectedButton === 'A') {
      // By Region
      firstLevelLabel.textContent = 'Select Region:';
      secondLevelLabel.textContent = 'Select Cell Type:';
    } else if (selectedButton === 'B') {
      // By Cell type
      firstLevelLabel.textContent = 'Select Cell Type:';
      secondLevelLabel.textContent = 'Select Region:';
    }
    
    container.innerHTML = '';
    
    options.forEach(function(option, index) {
      var item = document.createElement('div');
      
      // 判断当前显示的是什么类型的选项
      var currentType = selectedButton === 'A' ? 'region' : 'celltype';
      
      // 根据类型决定显示方式
      if (currentType === 'celltype') {
        // Cell Type 使用图片显示（卡片式）
        item.className = 'selection-item-card';
        
        // 创建图标容器
        var iconDiv = document.createElement('div');
        iconDiv.className = 'selection-icon';
        iconDiv.innerHTML = getIconForOption(option, 'celltype');
        
        // 创建文字标签
        var labelDiv = document.createElement('div');
        labelDiv.className = 'selection-label';
        labelDiv.textContent = option;
        
        item.appendChild(iconDiv);
        item.appendChild(labelDiv);
      } else {
        // Region 使用方框显示
        item.className = 'selection-item';
        item.textContent = option;
      }
      
      item.onclick = function() {
        selectFirstLevel(option, item);
      };
      
      container.appendChild(item);
      
      // 默认选中第一个选项
      if (index === 0) {
        setTimeout(function() {
          selectFirstLevel(option, item);
        }, 100);
      }
    });
  }
  
  // 获取选项对应的图标
  function getIconForOption(option, type) {
    if (type === 'celltype') {
      // Cell Type 始终使用图片显示
      var imagePath = '{{ site.url }}{{ site.baseurl }}/assets/celltype/' + encodeURIComponent(option) + '.png';
      
      return '<div style="width: 60px; height: 60px; border-radius: 50%; background-color: #f5f5f5; display: flex; align-items: center; justify-content: center; overflow: hidden; position: relative;">' + 
             '<img src="' + imagePath + '" alt="' + option + '" style="width: 100%; height: 100%; object-fit: contain;" onerror="this.style.display=\'none\'; this.parentNode.innerHTML=\'' + option.substring(0, 2).toUpperCase() + '\';" />' +
             '</div>';
    } else {
      // Region 始终使用方框形式显示（文字缩写）
      return '<div style="width: 60px; height: 60px; border-radius: 50%; background-color: #f5f5f5; display: flex; align-items: center; justify-content: center; font-weight: bold; font-size: 14px; color: #333;">' + 
             option.substring(0, 2).toUpperCase() +
             '</div>';
    }
  }

  // 显示第二层选择选项
  function displaySecondLevelOptions(options) {
    var container = document.getElementById('secondLevelOptions');
    container.innerHTML = '';
    
    // 判断第二层显示的是什么类型
    var secondLevelType = selectedButton === 'A' ? 'celltype' : 'region';
    
    options.forEach(function(option, index) {
      var item = document.createElement('div');
      
      // 根据类型决定显示方式
      if (secondLevelType === 'celltype') {
        // Cell Type 使用图片显示（卡片式）
        item.className = 'selection-item-card';
        
        // 创建图标容器
        var iconDiv = document.createElement('div');
        iconDiv.className = 'selection-icon';
        iconDiv.innerHTML = getIconForOption(option, 'celltype');
        
        // 创建文字标签
        var labelDiv = document.createElement('div');
        labelDiv.className = 'selection-label';
        labelDiv.textContent = option;
        
        item.appendChild(iconDiv);
        item.appendChild(labelDiv);
      } else {
        // Region 使用方框显示
        item.className = 'selection-item';
        item.textContent = option;
      }
      
      item.onclick = function() {
        selectSecondLevel(option, item);
      };
      container.appendChild(item);
      
      // 默认选中第一个选项
      if (index === 0) {
        setTimeout(function() {
          selectSecondLevel(option, item);
        }, 150);
      }
    });
    
    // 显示第二层容器
    document.getElementById('secondLevelContainer').style.display = 'block';
  }
  
  // 选择第一层选项
  function selectFirstLevel(option, element) {
    // 清除之前的选择（需要处理两种类型的选择项）
    var cardItems = document.querySelectorAll('#firstLevelOptions .selection-item-card');
    var normalItems = document.querySelectorAll('#firstLevelOptions .selection-item');
    
    cardItems.forEach(function(item) {
      item.classList.remove('selected');
    });
    normalItems.forEach(function(item) {
      item.classList.remove('selected');
    });
    
    // 选择当前项
    element.classList.add('selected');
    firstLevelSelected = option;
    
    // 显示第二层选项
    if (currentDataset && currentDataset[option]) {
      displaySecondLevelOptions(currentDataset[option]);
    }
    
    // 重置第二层选择
    secondLevelSelected = null;
    selectedOptions = [firstLevelSelected, secondLevelSelected];
  }
  
  // 选择第二层选项
  function selectSecondLevel(option, element) {
    // 清除之前的选择（需要处理两种类型的选择项）
    var cardItems = document.querySelectorAll('#secondLevelOptions .selection-item-card');
    var normalItems = document.querySelectorAll('#secondLevelOptions .selection-item');
    
    cardItems.forEach(function(item) {
      item.classList.remove('selected');
    });
    normalItems.forEach(function(item) {
      item.classList.remove('selected');
    });
    
    // 选择当前项
    element.classList.add('selected');
    secondLevelSelected = option;
    
    // 更新selectedOptions
    selectedOptions = [firstLevelSelected, secondLevelSelected];
  }
  
  function updateSelectBoxOptions(selectBoxId, options) {
    // 这个函数保留以防其他地方还在使用
    console.log('updateSelectBoxOptions is deprecated, using new selection interface');
  }
  function generateOptionsHtml(options) {
    // 这个函数保留以防其他地方还在使用
    return '';
  }
document.addEventListener('DOMContentLoaded', function() {
    var buttonA = document.getElementById('buttonA');
    var buttonB = document.getElementById('buttonB');
    buttonA.click();
    // 设置按钮 A 为选中状态
    buttonA.classList.add('active');
    buttonB.classList.remove('active');
  });
  var activeButton = null;
  function changeOrder(button) {
    var sentenceElement = document.getElementById("sentence");
    var buttonA = document.getElementById('buttonA');
    var buttonB = document.getElementById('buttonB');
    if (button === 'A') {
      buttonA.classList.add('active');
      buttonB.classList.remove('active');
      activeButton = buttonA;
      sentenceElement.innerHTML = 'Search for <b>differentially expressed genes (DEGs)</b> of selected cell type compared to others in the selected respiratory system region.';
      selectedButton = button;
      originalOrder = true;
      resetSelectBoxes();
      // 如果已经选择了数据集，重新加载对应数据
      if (selectedImageId && clickedCard) {
        handleClick(selectedImageId, clickedCard);
      }
    } else if (button === 'B') {
      buttonA.classList.remove('active');
      buttonB.classList.add('active');
      activeButton = buttonB;
      sentenceElement.innerHTML = 'Search for <b>differentially expressed genes (DEGs)</b> of selected respiratory system region compared to others in the selected cell type.';
      selectedButton = button;
      originalOrder = false;
      resetSelectBoxes();
      resetDisplay();
      // 如果已经选择了数据集，重新加载对应数据
      if (selectedImageId && clickedCard) {
        handleClick(selectedImageId, clickedCard);
      }
    }
 }   
  function resetSelectBoxes() {
    // 清空选择界面
    document.getElementById('firstLevelOptions').innerHTML = '';
    document.getElementById('secondLevelOptions').innerHTML = '';
    document.getElementById('secondLevelContainer').style.display = 'none';
    firstLevelSelected = null;
    secondLevelSelected = null;
    selectedOptions = [];
    currentDataset = null;
  }
  function toggleContent() {
    var contentContainer = document.getElementById('contentContainer');
    var clickMessageContainer = document.getElementById('clickMessageContainer');
    // 只显示内容，不再切换隐藏
    contentContainer.style.display = 'block';
    clickMessageContainer.style.display = 'none';
  }


</script>

<script>
  $(document).ready( function () {
    $.noConflict();
    var table = $('#mytable').DataTable();
} );
</script>

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
  .container {
  /* background-color: #f0f0f0; */ /* 设置背景颜色为您想要的颜色值 */
  box-shadow: 0 0 15px grey;
  border-radius: 10px; /* 设置边框圆角的半径，可以根据需要进行调整 */
  padding: 10px; /* 可选：添加内边距以增加内容与边框之间的间距 */
}
  #buttonA, #buttonB {
      font-size: 17px; /* Increase font size */
      /* padding: 15px 30px; /* Increase padding */
      margin: 5px; /*Add some margin*/
      width: 150px; /*Set button width  */
      height: 38px; /* Set button height */
      /* cursor: pointer;
      border: none;
      background-color: #23265F; /* Change background color */
      /* color: white; Change text color */
      /* border-radius: 5px; Add border radius  */
    }
    /* #buttonA:hover, #buttonB:hover {
      background-color: #23265F; Change background color on hover */
    /* } */
</style>
<style>
    .photo-card {
/*         width: 200px;
        height: 200px; */
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
</body>
<style>
    .btn-primary {
      font-weight: normal; /* 确保文本不加粗 */
      font-size: 17px;    /* 设置文本字体大小 */
    }
    
    /* 选择网格样式 */
    .selection-grid {
      display: flex;
      flex-wrap: wrap;
      gap: 15px;
      margin: 20px 0;
    }
    
    /* 卡片式选择项（第一层） */
    .selection-item-card {
      display: flex;
      flex-direction: column;
      align-items: center;
      padding: 15px;
      border: none;
      border-radius: 12px;
      background-color: transparent;
      cursor: pointer;
      transition: all 0.3s ease;
      min-width: 120px;
      max-width: 140px;
    }
    
    .selection-item-card:hover {
      transform: translateY(-2px);
    }
    
    .selection-item-card.selected {
      /* 选中状态不改变背景 */
    }
    
    .selection-icon {
      margin-bottom: 10px;
    }
    
    /* 选中状态的圆形图标边框 */
    .selection-item-card.selected .selection-icon > div {
      border: 3px solid #23265F !important;
    }
    
    .selection-label {
      font-size: 12px;
      font-weight: 500;
      text-align: center;
      color: #333;
      line-height: 1.2;
    }
    
    .selection-item-card.selected .selection-label {
      color: #23265F;
      font-weight: 600;
    }
    
    /* 普通选择项（第二层） */
    .selection-item {
      padding: 10px 15px;
      border: 2px solid #ccc;
      border-radius: 8px;
      background-color: #f9f9f9;
      cursor: pointer;
      transition: all 0.3s ease;
      font-size: 14px;
      text-align: center;
      min-width: 120px;
    }
    
    .selection-item:hover {
      border-color: #23265F;
      background-color: #e8e8e8;
    }
    
    .selection-item.selected {
      border-color: #23265F;
      background-color: #23265F;
      color: white;
      font-weight: bold;
    }
    
    #firstLevelContainer, #secondLevelContainer {
      margin: 20px 0;
      padding: 15px;
      border: 1px solid #ddd;
      border-radius: 8px;
      background-color: #fafafa;
    }
    
    /* Loading 效果样式 */
    .loading-container {
      display: flex;
      flex-direction: column;
      align-items: center;
      justify-content: center;
      padding: 40px;
      text-align: center;
    }
    
    .loading-spinner {
      width: 40px;
      height: 40px;
      border: 4px solid #f3f3f3;
      border-top: 4px solid #23265F;
      border-radius: 50%;
      animation: spin 1s linear infinite;
      margin-bottom: 15px;
    }
    
    @keyframes spin {
      0% { transform: rotate(0deg); }
      100% { transform: rotate(360deg); }
    }
    
    .loading-text {
      color: #666;
      font-size: 16px;
      font-weight: 500;
    }
  </style>