---
title: "Brain Cell Atlas - Database"
layout: textlay
excerpt: " The Databases in Brain Cell Atlas, GZNL-RDC. "
sitemap: true
permalink: /database/
---
<html lang="en">
<head>
<!--set sort order in table header begin-->
<meta http-equiv="Content-type" content="text/html; charset=utf-8">
  <meta name="viewport" content="width=device-width,initial-scale=1,user-scalable=no">
  <!-- <title>Ribozyme applications</title> -->
  <link rel="stylesheet" type="text/css" href="https://cdn.datatables.net/1.12.1/css/jquery.dataTables.min.css">
  <link rel="stylesheet" type="text/css" href="https://cdn.datatables.net/buttons/2.2.3/css/buttons.dataTables.min.css">
  <script src="https://cdnjs.cloudflare.com/ajax/libs/jquery/3.5.1/jquery.min.js"></script>
<!-- <script type="text/javascript" src="https://code.jquery.com/jquery-3.5.1.js"></script> -->
    <script type="text/javascript" src="https://cdn.datatables.net/1.12.1/js/jquery.dataTables.min.js"></script>
    <script type="text/javascript" src="https://cdn.datatables.net/buttons/2.2.3/js/dataTables.buttons.min.js"></script>
    <script type="text/javascript" src="https://cdnjs.cloudflare.com/ajax/libs/jszip/3.1.3/jszip.min.js"></script>
    <script type="text/javascript" src="https://cdnjs.cloudflare.com/ajax/libs/pdfmake/0.1.53/pdfmake.min.js"></script>
    <script type="text/javascript" src="https://cdnjs.cloudflare.com/ajax/libs/pdfmake/0.1.53/vfs_fonts.js"></script>
    <script type="text/javascript" src="https://cdn.datatables.net/buttons/2.2.3/js/buttons.html5.min.js"></script>
    <script type="text/javascript" src="https://cdn.datatables.net/buttons/2.2.3/js/buttons.print.min.js"></script>
   <script src="https://cdnjs.cloudflare.com/ajax/libs/plotly.js/3.0.3/plotly.min.js" integrity="sha512-OEXF/M4teW0Wh2kT1AzKLesQui+NH7J49H0peV/hXgq9SGIjjW2Blsq5/Pt/Wemw+oLwayZbfBPWyrYi/uCOBA==" crossorigin="anonymous" referrerpolicy="no-referrer"></script>
    <!-- <script src="https://cdn.plot.ly/plotly-latest.min.js"></script> -->
  <!--set sort order in table header finish-->
  <!-- <style>
    .header_box {
    border: none;
    background: #efefef;
    font-size:24px
  }
  h2{
    font-size:20px;
    font-weight: bold;
  }
/* Button Container Styles */
    .button-container {
      display: flex;
      justify-content: left;
      align-items: center;
      height: 50px;
      overflow:auto
    }
    /* Button Style */
    .button {
      display: block;
      padding: 10px;
      margin-right: 10px;
      text-align: center;
      background-color: #efefef;
      color: #005826;
      text-decoration: none;
      font-size: 16px;
      border: 1px solid #005826;
      border-radius: 5px;
    }
    /* Mouse Hover Style */
    .button:hover {
      background-color: #999;
      cursor: pointer;
    }
    /* 样式表格 */
    table {
        border: 2px solid #f8f8ff;
        border: 2px solid #767676;
		    border: 2px solid #767676;
		    border-radius: 5px;
		    background-color: #fff;
		    border-radius: 0;
        }
		  th {
        background-color: #719B71;
        background-color: #719B71;
        background-color: #005826;
        color: rgba(255,255,255,0.9);
		    cursor: pointer;
        }
		  td {
		    background-color: #ffffff;
		    background-color: #f9f9f9;
		    background-color: #f9f9f9;
		    }		
		  th, td {
		  padding: 10px 10px;
		}
    /* 隐藏所有 sheet */
    .sheet {
      display: none;
      overflow:auto
    }
    /* Style the search box */
  #searchBox {
    padding: 10px;
    font-size: 16px;
    border: 2px solid #ccc;
    border-radius: 4px;
    width: 300px;
  }
  /* Style the search box when it has focus */
  #searchBox:focus {
    outline: none;
    border-color: #2354C4;
  }
  /* Style the placeholder text */
  #searchBox::placeholder {
    font-size: 16px;
  }
  /* 搜索框和下载框水平布局 */
    .form-container {
      display: flex;
      align-items: center;
      overflow:auto
    }
    .form-container input {
      margin-right: 10px;
    }
    /* 下载框位置设置 */
    .form-container select {
      margin-left: auto;
      padding: 10px;
      font-size: 16px;
      border: 2px solid #ccc;
      border-radius: 4px;
      width: 300px;
    }
    .button.clicked {
    background-color: #999;
}

<!--   </style> -->
<style>
  .chart_container {
    display: flex;
    align-items: flex-start;
    flex-wrap: wrap;
    gap: 20px;
    justify-content: space-between;
  }
  .chart_box{
    flex: 1 1 calc(50% - 10px);
    min-width: 300px;
    margin-bottom: 20px;
    padding: 15px;
    border: 1px solid #e9ecef;
    border-radius: 12px;
    box-shadow: 0 2px 10px rgba(0, 0, 0, 0.05);
    background: white;
  }
  .chart_title{
    text-align: center;
    margin-bottom: 10px;
  }
  .chart_title h3 {
    margin: 0;
    color: #333;
    font-size: 18px;
  }
  .chart_graph{
    width: 100%;
    height: 300px;
    min-height: 250px;
  }
  
  /* Filter tags styles */
  .filter-tag {
    display: inline-flex;
    align-items: center;
    padding: 4px 8px;
    background: #f8f9fa;
    border: 1px solid #dee2e6;
    border-radius: 16px;
    font-size: 12px;
    color: #495057;
    gap: 6px;
  }
  
  .filter-tag-close {
    cursor: pointer;
    background: none;
    border: none;
    color: #6c757d;
    font-size: 14px;
    padding: 0;
    margin: 0;
    width: 16px;
    height: 16px;
    border-radius: 50%;
    display: flex;
    align-items: center;
    justify-content: center;
  }
  
  .filter-tag-close:hover {
    background: #dc3545;
    color: white;
  }
  
  /* Responsive design */
  @media (max-width: 768px) {
    .chart_container {
      flex-direction: column;
    }
    .chart_box {
      flex: 1 1 100%;
      min-width: unset;
    }
    .chart_graph {
      height: 250px;
    }
  }
  
  @media (max-width: 1200px) {
    .chart_box {
      flex: 1 1 calc(50% - 10px);
    }
  }
</style>
</head> 

<!-- <body onload="showSheet('sheet1')"> -->
<div class="chart_container">
   <div class="chart_box"> 
      <div class="chart_title">
        <h3>Species</h3>
      </div>
      <div id="chartSpecies" class="chart_graph"></div>
   </div>
   <div class="chart_box"> 
      <div class="chart_title">
        <h3>Year</h3>
      </div>
      <div id="chartYear" class="chart_graph"></div>
   </div>
   <div class="chart_box"> 
      <div class="chart_title">
        <h3>Tissue</h3>
      </div>
      <div id="chartTissue" class="chart_graph"></div>
   </div>
   <div class="chart_box"> 
      <div class="chart_title">
        <h3>Status</h3>
      </div>
      <div id="chartStatus" class="chart_graph"></div>
   </div>
</div>

<!-- Filter tags container -->
<div id="filterContainer" style="margin: 20px 0; display: none;">
  <div style="display: flex; align-items: center; flex-wrap: wrap; gap: 10px;">
    <span style="font-weight: bold; margin-right: 10px;">Applied Filters:</span>
    <div id="filterTags" style="display: flex; flex-wrap: wrap; gap: 8px;"></div>
    <button id="resetAllFilters" style="background: #dc3545; color: white; border: none; padding: 6px 12px; border-radius: 4px; cursor: pointer; font-size: 12px;">Reset All</button>
  </div>
</div>
<!-- 
<p class="header_box" >Detail information</p>

        
This section lists all the experimentally validated riboswitches. -->
<div style="text-align: left;">
<p>You can use keywords to search.</p>
<input type="text" id="searchBox" placeholder="Search by keyword..." onfocus="showAllSheets()" oninput="searchTables()"><br><br>
</div>
<div>
<p>You can download the tables by clicking on the five buttons below.</p>
<table id="cfttable" class="table table-hover table-bordered">
    <colgroup>
          <col style="width: 20%;">
          <col style="width: 5%;">
          <col style="width: 5%;">
          <col style="width: 5%;">
          <col style="width: 5%;">
          <col style="width: 20%;">
          <col style="width: 5%;">
          <col style="width: 10%;">
          <col style="width: 5%;">
          <col style="width: 10%;">
          <col style="width: 10%;">
          <col style="width: 10%;">
          <!-- <col style="width: 5%;"> -->
        </colgroup>
        <thead>
        <tr>
          <th onclick="sortTable(0)">Species</th>
          <th onclick="sortTable(1)">Atlas</th>
          <th onclick="sortTable(2)">Tissue</th>
          <th onclick="sortTable(3)">Status</th>
          <th onclick="sortTable(4)">Platform</th>
          <th onclick="sortTable(5)">Seq-type</th>
          <th onclick="sortTable(6)">Year</th>
          <th onclick="sortTable(7)">Accession</th>
          <th onclick="sortTable(8)">Link</th>
          <th onclick="sortTable(9)">Datasets</th>
          <th onclick="sortTable(10)">DOI</th>
          <th onclick="sortTable(11)">Download</th>
        </tr>
        </thead>
<tbody>
    {% for item in site.data.database_table  %}
         <tr> 
         <td name="td0">{{ item.Species }}</td>
         <td name="td1">{{ item.Atlas }}</td>
          <td name="td2">{{ item.Tissue }}</td>
          <td name="td3">{{ item.Status }}</td>
          <td name="td4">{{ item.Platform }}</td>
          <td name="td5">{{ item.Seq-type }}</td>
          <td name="td6">{{ item.Year }}</td>
          <td name="td7">{{ item.Accession}}</td>
          <td name="td8"><a href="{{item.Link}}" target="_blank" style="color:#23265F"><b>Link</b></a></td>
          <td name="td9">{{ item.Datasets}}</td>
          <td name="td10">{{ item.DOI }}</td>
          <td name="td11"><a href="{{item.Download}}" target="_blank" style="color:#23265F"><b>Raw&Processed Data</b></a></td>
          </tr>
          {% endfor %}       
   </tbody>
</table>
</div>                
<script> 
  var databaseData={{site.data.database_table | jsonify }}
  var tables = [];
  var currentSheet = 'sheet1';
  var activeFilters = {};
  var originalData = [];
  var chartInstances = {};
  var updateTimeout = null;
  
  // Color schemes for charts
  var colorSchemes = {
    species: ['#1f77b4', '#ff7f0e', '#2ca02c', '#d62728', '#9467bd', '#8c564b', '#e377c2', '#7f7f7f', '#bcbd22', '#17becf'],
    year: ['#3498db', '#e74c3c', '#2ecc71', '#f39c12', '#9b59b6', '#1abc9c', '#34495e', '#e67e22', '#95a5a6', '#f1c40f'],
    tissue: ['#FF6B6B', '#4ECDC4', '#45B7D1', '#96CEB4', '#FFEAA7', '#DDA0DD', '#98D8C8', '#F7DC6F', '#BB8FCE', '#85C1E9'],
    status: ['#FFA07A', '#20B2AA', '#87CEEB', '#DDA0DD', '#F0E68C', '#FFB6C1', '#87CEFA', '#98FB98', '#F5DEB3', '#D3D3D3']
  };
  
  $(document).ready(function() {
    $.noConflict();
    
    // Store original data for filtering
    originalData = databaseData.slice();
    
    // Initialize charts
    initializeCharts();
    
    // Initialize data tables
    tables.push($('#cfttable').DataTable({
      dom: 'Bfrtip',
      buttons: [
        {
          extend: 'copy',
          exportOptions: {
            columns: ':visible',
            format: {
              body: function (data, row, column, node) {
                // For Link column (index 8) and Download column (index 11), extract href from anchor tags
                if (column === 8 || column === 11) {
                  var $node = $(node);
                  var $link = $node.find('a');
                  return $link.length ? $link.attr('href') : data;
                }
                return data;
              }
            }
          }
        },
        {
          extend: 'csv',
          exportOptions: {
            columns: ':visible',
            format: {
              body: function (data, row, column, node) {
                // For Link column (index 8) and Download column (index 11), extract href from anchor tags
                if (column === 8 || column === 11) {
                  var $node = $(node);
                  var $link = $node.find('a');
                  return $link.length ? $link.attr('href') : data;
                }
                return data;
              }
            }
          }
        },
        {
          extend: 'excel',
          exportOptions: {
            columns: ':visible',
            format: {
              body: function (data, row, column, node) {
                // For Link column (index 8) and Download column (index 11), extract href from anchor tags
                if (column === 8 || column === 11) {
                  var $node = $(node);
                  var $link = $node.find('a');
                  return $link.length ? $link.attr('href') : data;
                }
                return data;
              }
            }
          }
        },
        {
          extend: 'pdf',
          exportOptions: {
            columns: ':visible',
            format: {
              body: function (data, row, column, node) {
                // For Link column (index 8) and Download column (index 11), extract href from anchor tags
                if (column === 8 || column === 11) {
                  var $node = $(node);
                  var $link = $node.find('a');
                  return $link.length ? $link.attr('href') : data;
                }
                return data;
              }
            }
          }
        },
        'print'
      ]
    }));
    tables.push($('#rnadetable').DataTable({
      dom: 'Bfrtip',
      buttons: [
        'copy', 'csv', 'excel', 'pdf', 'print'
      ]
    }));

    tables.push($('#rnapretable').DataTable({
      dom: 'Bfrtip',
      buttons: [
        'copy', 'csv', 'excel', 'pdf', 'print'
      ]
    }));
    tables.push($('#smtable').DataTable({
      dom: 'Bfrtip',
      buttons: [
        'copy', 'csv', 'excel', 'pdf', 'print'
      ]
    }));
    tables.push($('#eletable').DataTable({
      dom: 'Bfrtip',
      buttons: [
        'copy', 'csv', 'excel', 'pdf', 'print'
      ]
    }));

    tables.push($('#amintable').DataTable({
      dom: 'Bfrtip',
      buttons: [
        'copy', 'csv', 'excel', 'pdf', 'print'
      ]
    }));
    tables.push($('#sugtable').DataTable({
      dom: 'Bfrtip',
      buttons: [
        'copy', 'csv', 'excel', 'pdf', 'print'
      ]
    }));
    tables.push($('#tboxtable').DataTable({
      dom: 'Bfrtip',
      buttons: [
        'copy', 'csv', 'excel', 'pdf', 'print'
      ]
    }));
    tables.push($('#othtable').DataTable({
      dom: 'Bfrtip',
      buttons: [
        'copy', 'csv', 'excel', 'pdf', 'print'
      ]
    }));

    // Hide the search box for DataTables
      $('#cfttable_filter').css('display', 'none');
      $('#rnadetable_filter').css('display', 'none');
      $('#rnapretable_filter').css('display', 'none');
       $('#smtable_filter').css('display', 'none');
      $('#eletable_filter').css('display', 'none');
      $('#amintable_filter').css('display', 'none');
      $('#sugtable_filter').css('display', 'none');
      $('#tboxtable_filter').css('display', 'none');
      $('#othtable_filter').css('display', 'none');
      
      // Show the initial sheet (sheet1) and hide others
    showSheet('sheet1');//There is no node for sheet1 in DOM ,and an error will be reported.
    hideAllSheetsExcept('sheet1');
    <!-- If there are query parameters, the query table will be displayed -->
     const params = new URLSearchParams(window.location.search);
  const searchVal = params.get("search");
  if (searchVal) {
    document.getElementById("searchBox").value = searchVal;
   searchTables();
  }
  
  // Setup filter reset button
  $('#resetAllFilters').on('click', function() {
    resetAllFilters();
  });
  
  // Window resize handler for responsive charts
  $(window).on('resize', function() {
    Object.keys(chartInstances).forEach(function(chartId) {
      if (chartInstances[chartId]) {
        Plotly.Plots.resize(chartId);
      }
    });
  });
  });
 
  function sortTable(columnIndex) {
    // TODO: Add sorting logic based on the columnIndex
  }

  

function downloadExcel() {
  var selectElement = document.getElementById('downloadOptions');
  var selectedValue = selectElement.value;

  // Check if a valid option was selected
  if (selectedValue !== '') {
    // Create a temporary link element with the download URL
    var link = document.createElement('a');
    link.href = selectedValue;
    link.download = selectedValue.split('/').pop(); // Set the filename to the last part of the URL
    document.body.appendChild(link);

    // Trigger a click event on the link to start the download
    link.click();

    // Remove the link from the DOM
    document.body.removeChild(link);
  }
}
	
	
	function showSheet(sheetId) {
    // Hide the current sheet
    if (currentSheet) {
        var currentSheetElement = document.getElementById(currentSheet);
        if (currentSheetElement) {
            currentSheetElement.style.display = 'none';
        } else {
            console.warn('找不到当前sheet元素:', currentSheet);
        }
    }

    // Show the selected sheet
    var sheet = document.getElementById(sheetId);
    if (!sheet) {
        console.error('找不到ID为', sheetId, '的sheet元素');
        return; // 如果找不到元素，直接返回
    }
    
    sheet.style.display = 'block';

    // Update the current sheet
    currentSheet = sheetId;

    // Get all buttons
    var buttons = document.querySelectorAll('.button');

    // Remove clicked class from all buttons
    buttons.forEach(function(btn) {
        btn.classList.remove('clicked');
    });

    // Add clicked class to the clicked button using event.target
    event.target.classList.add('clicked');
}

  function hideAllSheetsExcept(sheetId) {
    var sheets = document.getElementsByClassName('sheet');
    for (var i = 0; i < sheets.length; i++) {
      var sheet = sheets[i];
      if (sheet.id !== sheetId) {
        sheet.style.display = 'none';
      }
    }
    }

    function showAllSheets() {
      var sheets = document.getElementsByClassName('sheet');
      for (var i = 0; i < sheets.length; i++) {
        sheets[i].style.display = 'block';
      }
    }

    function searchTables() {
      var keyword = $('#searchBox').val().toLowerCase();
      tables.forEach(function(table) {
        table.search(keyword).draw();
      });
      // Filter the sheets based on search results
    filterSheets();
  }

  function filterSheets() {
    var keyword = $('#searchBox').val().toLowerCase();
    var sheets = document.getElementsByClassName('sheet');
    for (var i = 0; i < sheets.length; i++) {
      var sheet = sheets[i];
      var table = tables[i];

      var displaySheet = false;

      table.rows().eq(0).each(function(index) {
        var row = table.row(index);
        var rowData = row.data().join(' ').toLowerCase();
        var display = rowData.includes(keyword) ? '' : 'none';
        row.nodes().to$().css('display', display);

        if (display !== 'none') {
          displaySheet = true;
        }
      });

      if (displaySheet) {
        $('#' + sheet.id).show();
      } else {
        $('#' + sheet.id).hide();
      }
    }
  }
  
  // Chart initialization and management functions
  function initializeCharts() {
    createSpeciesChart();
    createYearChart();
    createTissueChart();
    createStatusChart();
  }
  
  function createSpeciesChart() {
    var counts = {};
    originalData.forEach(function(item) {
      var species = item.Species || 'Unknown';
      counts[species] = (counts[species] || 0) + 1;
    });
    
    var sortedEntries = Object.entries(counts).sort((a, b) => b[1] - a[1]);
    var labels = sortedEntries.map(entry => entry[0]);
    var values = sortedEntries.map(entry => entry[1]);
    var colors = labels.map((_, i) => colorSchemes.species[i % colorSchemes.species.length]);
    
    var data = [{
      x: labels,
      y: values,
      type: 'bar',
      marker: {
        color: colors,
        line: { width: 0 }
      },
      hovertemplate: '<b>%{x}</b><br>Count: %{y}<extra></extra>'
    }];
    
    var layout = {
      title: false,
      margin: { l: 50, r: 20, t: 20, b: 100 },
      xaxis: { 
        tickangle: -45,
        automargin: true
      },
      yaxis: { title: 'Count' },
      plot_bgcolor: 'rgba(0,0,0,0)',
      paper_bgcolor: 'rgba(0,0,0,0)',
      font: { size: 12 }
    };
    
    var config = { 
      responsive: true, 
      displayModeBar: false 
    };
    
    Plotly.newPlot('chartSpecies', data, layout, config).then(function() {
      document.getElementById('chartSpecies').on('plotly_click', function(clickData) {
        var selectedSpecies = String(clickData.points[0].x); // Convert to string to match data format
        
        // Find the original color for this species
        var allSpecies = {};
        originalData.forEach(function(item) {
          var species = item.Species || 'Unknown';
          allSpecies[species] = (allSpecies[species] || 0) + 1;
        });
        var allSpeciesList = Object.keys(allSpecies).sort((a, b) => allSpecies[b] - allSpecies[a]);
        var originalIndex = allSpeciesList.indexOf(selectedSpecies);
        var originalColor = colorSchemes.species[originalIndex % colorSchemes.species.length];
        
        toggleFilter('Species', selectedSpecies, originalColor, 'chartSpecies');
      });
    });
    chartInstances['chartSpecies'] = true;
  }
  
  function createYearChart() {
    var counts = {};
    originalData.forEach(function(item) {
      var year = item.Year || 'Unknown';
      counts[year] = (counts[year] || 0) + 1;
    });
    
    var sortedEntries = Object.entries(counts).sort((a, b) => a[0].localeCompare(b[0]));
    var labels = sortedEntries.map(entry => entry[0]);
    var values = sortedEntries.map(entry => entry[1]);
    var colors = labels.map((_, i) => colorSchemes.year[i % colorSchemes.year.length]);
    
    var data = [{
      x: labels,
      y: values,
      type: 'bar',
      marker: {
        color: colors,
        line: { width: 0 }
      },
      hovertemplate: '<b>%{x}</b><br>Count: %{y}<extra></extra>'
    }];
    
    var layout = {
      title: false,
      margin: { l: 50, r: 20, t: 20, b: 60 },
      xaxis: { 
        title: 'Year',
        automargin: true
      },
      yaxis: { title: 'Count' },
      plot_bgcolor: 'rgba(0,0,0,0)',
      paper_bgcolor: 'rgba(0,0,0,0)',
      font: { size: 12 }
    };
    
    var config = { 
      responsive: true, 
      displayModeBar: false 
    };
    
    Plotly.newPlot('chartYear', data, layout, config).then(function() {
      document.getElementById('chartYear').on('plotly_click', function(clickData) {
        var selectedYear = String(clickData.points[0].x); // Convert to string to match data format
        
        // Find the original color for this year - use the same sorting as chart creation
        var allYears = {};
        originalData.forEach(function(item) {
          var year = item.Year || 'Unknown';
          allYears[year] = (allYears[year] || 0) + 1;
        });
        var sortedEntries = Object.entries(allYears).sort((a, b) => a[0].localeCompare(b[0]));
        var allYearsList = sortedEntries.map(entry => entry[0]);
        var originalIndex = allYearsList.indexOf(selectedYear);
        var originalColor = colorSchemes.year[originalIndex % colorSchemes.year.length];
        toggleFilter('Year', selectedYear, originalColor, 'chartYear');
      });
    });
    chartInstances['chartYear'] = true;
  }
  
  function createTissueChart() {
    var counts = {};
    originalData.forEach(function(item) {
      var tissue = item.Tissue || 'Unknown';
      counts[tissue] = (counts[tissue] || 0) + 1;
    });
    
    var sortedEntries = Object.entries(counts).sort((a, b) => b[1] - a[1]);
    var labels = sortedEntries.map(entry => entry[0]);
    var values = sortedEntries.map(entry => entry[1]);
    var colors = labels.map((_, i) => colorSchemes.tissue[i % colorSchemes.tissue.length]);
    
    // Truncate long labels for display
    var displayLabels = labels.map(function(label) {
      return label.length > 15 ? label.substring(0, 15) + '...' : label;
    });
    
    var data = [{
      labels: displayLabels,
      values: values,
      type: 'pie',
      hole: 0.4,  // 设置中心空洞，创建环饼图效果
      marker: {
        colors: colors,
        line: { width: 2, color: 'white' }
      },
      textinfo: 'percent',
      textposition: 'inside',
      hovertemplate: '<b>%{text}</b><br>Count: %{value}<br>Percentage: %{percent}<extra></extra>',
      text: labels, // 使用完整标签用于悬浮提示
      showlegend: true,
      textfont: { size: 10 },
      pull: labels.map(() => 0),
      // 添加自定义数据以便在点击事件中访问
      customdata: labels.map((label, i) => [label, colors[i]])
    }];
    
    var layout = {
      title: false,
      margin: { l: 20, r: 20, t: 20, b: 20 },
      plot_bgcolor: 'rgba(0,0,0,0)',
      paper_bgcolor: 'rgba(0,0,0,0)',
      font: { size: 10 },
      legend: {
        orientation: "v",
        x: 1.1,
        y: 0.5,
        font: { size: 10 },
        bgcolor: 'rgba(255,255,255,0.9)',
        bordercolor: '#ccc',
        borderwidth: 1
      }
    };
    
    var config = { 
      responsive: true, 
      displayModeBar: false 
    };
    
    Plotly.newPlot('chartTissue', data, layout, config).then(function() {
      document.getElementById('chartTissue').on('plotly_click', function(data) {
        var point = data.points[0];
        var pointIndex = point.pointIndex;
        var customData = point.customdata;
        
        // Get the selected value from the point label
        var selectedTissue = point.label;
        var selectedColor;
        
        // Handle the nested array structure - customData might be [Array(2), Array(2), ...]
        if (Array.isArray(customData) && Array.isArray(customData[0]) && customData[0].length >= 2) {
          // customData[0] contains [label, color] for the clicked segment
          selectedColor = customData[0][1];
        } else if (Array.isArray(customData) && customData.length >= 2) {
          // customData is [label, color] directly
          selectedColor = customData[1];
        } else {
          // Fallback: calculate color from original data
          var counts = {};
          originalData.forEach(function(item) {
            var tissue = item.Tissue || 'Unknown';
            counts[tissue] = (counts[tissue] || 0) + 1;
          });
          var sortedEntries = Object.entries(counts).sort((a, b) => b[1] - a[1]);
          var labels = sortedEntries.map(entry => entry[0]);
          var labelIndex = labels.indexOf(selectedTissue);
          selectedColor = colorSchemes.tissue[labelIndex % colorSchemes.tissue.length];
        }
        
        toggleFilter('Tissue', selectedTissue, selectedColor, 'chartTissue');
      });
    });
    chartInstances['chartTissue'] = true;
  }
  
  function createStatusChart() {
    var counts = {};
    originalData.forEach(function(item) {
      var status = item.Status || 'Unknown';
      counts[status] = (counts[status] || 0) + 1;
    });
    
    var sortedEntries = Object.entries(counts).sort((a, b) => b[1] - a[1]);
    var labels = sortedEntries.map(entry => entry[0]);
    var values = sortedEntries.map(entry => entry[1]);
    var colors = labels.map((_, i) => colorSchemes.status[i % colorSchemes.status.length]);
    
    // Truncate long labels for display
    var displayLabels = labels.map(function(label) {
      return label.length > 20 ? label.substring(0, 20) + '...' : label;
    });
    
    var data = [{
      labels: displayLabels,
      values: values,
      type: 'pie',
      hole: 0.4,  // 设置中心空洞，创建环饼图效果
      marker: {
        colors: colors,
        line: { width: 2, color: 'white' }
      },
      textinfo: 'percent',
      textposition: 'inside',
      hovertemplate: '<b>%{text}</b><br>Count: %{value}<br>Percentage: %{percent}<extra></extra>',
      text: labels, // 使用完整标签用于悬浮提示
      showlegend: true,
      textfont: { size: 10 },
      pull: labels.map(() => 0),
      // 添加自定义数据以便在点击事件中访问
      customdata: labels.map((label, i) => [label, colors[i]])
    }];
    
    var layout = {
      title: false,
      margin: { l: 20, r: 20, t: 20, b: 20 },
      plot_bgcolor: 'rgba(0,0,0,0)',
      paper_bgcolor: 'rgba(0,0,0,0)',
      font: { size: 10 },
      legend: {
        orientation: "v",
        x: 1.1,
        y: 0.5,
        font: { size: 10 },
        bgcolor: 'rgba(255,255,255,0.9)',
        bordercolor: '#ccc',
        borderwidth: 1
      }
    };
    
    var config = { 
      responsive: true, 
      displayModeBar: false 
    };
    
    Plotly.newPlot('chartStatus', data, layout, config).then(function() {
      document.getElementById('chartStatus').on('plotly_click', function(data) {
        var point = data.points[0];
        var pointIndex = point.pointIndex;
        var customData = point.customdata;
        
        // Get the selected value from the point label
        var selectedStatus = point.label;
        var selectedColor;
        
        // Handle the nested array structure - customData might be [Array(2), Array(2), ...]
        if (Array.isArray(customData) && Array.isArray(customData[0]) && customData[0].length >= 2) {
          // customData[0] contains [label, color] for the clicked segment
          selectedColor = customData[0][1];
        } else if (Array.isArray(customData) && customData.length >= 2) {
          // customData is [label, color] directly
          selectedColor = customData[1];
        } else {
          // Fallback: calculate color from original data
          var counts = {};
          originalData.forEach(function(item) {
            var status = item.Status || 'Unknown';
            counts[status] = (counts[status] || 0) + 1;
          });
          var sortedEntries = Object.entries(counts).sort((a, b) => b[1] - a[1]);
          var labels = sortedEntries.map(entry => entry[0]);
          var labelIndex = labels.indexOf(selectedStatus);
          selectedColor = colorSchemes.status[labelIndex % colorSchemes.status.length];
        }
        
        toggleFilter('Status', selectedStatus, selectedColor, 'chartStatus');
      });
    });
    chartInstances['chartStatus'] = true;
  }
  
  function toggleFilter(filterType, filterValue, color, sourceChartId) {
    var filterKey = filterType + '::' + filterValue;
    
    if (activeFilters[filterKey]) {
      // Remove filter
      delete activeFilters[filterKey];
    } else {
      // Add filter
      activeFilters[filterKey] = {
        type: filterType,
        value: filterValue,
        color: color
      };
    }
    
    // Update the current chart immediately to show visual feedback
    if (sourceChartId) {
      updateCurrentChartVisuals(sourceChartId, filterType);
    }
    
    // Update filter tags immediately (lightweight operation)
    updateFilterTags();
    
    // Debounce the heavy operations
    if (updateTimeout) {
      clearTimeout(updateTimeout);
    }
    
    updateTimeout = setTimeout(function() {
      // Update other charts asynchronously
      requestAnimationFrame(function() {
        updateChartVisuals(sourceChartId);
        // Update table data in next frame to avoid blocking
        requestAnimationFrame(function() {
          filterTableData();
        });
      });
    }, 50); // 50ms debounce
  }
  
  function updateCurrentChartVisuals(chartId, filterType) {
    var chart = document.getElementById(chartId);
    if (!chart || !chart.data) return;
    
    var data = chart.data[0];
    var update = {};
    
    if (chartId === 'chartSpecies' || chartId === 'chartYear') {
      // Handle bar charts
      var originalColors = filterType === 'Species' ? colorSchemes.species : colorSchemes.year;
      var colors = new Array(data.x.length);
      var lineWidths = new Array(data.x.length);
      var lineColors = new Array(data.x.length);
      
      for (var index = 0; index < data.x.length; index++) {
        var label = data.x[index];
        var filterKey = filterType + '::' + label;
        var originalColor = originalColors[index % originalColors.length];
        
        if (activeFilters[filterKey]) {
          // Make hollow - white fill with colored border
          colors[index] = 'rgba(255,255,255,0.9)';
          lineWidths[index] = 3;
          lineColors[index] = originalColor;
        } else {
          // Reset to original color
          colors[index] = originalColor;
          lineWidths[index] = 0;
          lineColors[index] = originalColor;
        }
      }
      
      update['marker.color'] = [colors];
      update['marker.line.width'] = [lineWidths];
      update['marker.line.color'] = [lineColors];
      
    } else if (chartId === 'chartTissue' || chartId === 'chartStatus') {
      // Handle pie charts
      var originalColors = filterType === 'Tissue' ? colorSchemes.tissue : colorSchemes.status;
      var labels = data.text || data.labels; // Get the full labels
      var colors = new Array(labels.length);
      var pullValues = new Array(labels.length);
      var lineColors = new Array(labels.length);
      var lineWidths = new Array(labels.length);
      var customData = new Array(labels.length);
      
      for (var index = 0; index < labels.length; index++) {
        var label = labels[index];
        var filterKey = filterType + '::' + label;
        var originalColor = originalColors[index % originalColors.length];
        
        // Update custom data
        customData[index] = [label, originalColor];
        
        if (activeFilters[filterKey]) {
          // Make hollow - white fill with colored border
          colors[index] = 'rgba(255,255,255,0.9)';
          pullValues[index] = 0.1; // Pull out selected segments
          lineColors[index] = originalColor;
          lineWidths[index] = 4;
        } else {
          // Reset to original color
          colors[index] = originalColor;
          pullValues[index] = 0;
          lineColors[index] = 'white';
          lineWidths[index] = 2;
        }
      }
      
      update = {
        'marker.colors': [colors],
        'pull': [pullValues],
        'marker.line.color': [lineColors],
        'marker.line.width': [lineWidths],
        'customdata': [customData]
      };
    }
    
    Plotly.restyle(chartId, update);
  }

  function getFilteredDataExcludingType(excludeType) {
    var filteredData = originalData;
    
    if (Object.keys(activeFilters).length > 0) {
      filteredData = originalData.filter(function(item) {
        // Group filters by type, excluding the specified type
        var filtersByType = {};
        Object.values(activeFilters).forEach(function(filter) {
          if (filter.type !== excludeType) {
            if (!filtersByType[filter.type]) {
              filtersByType[filter.type] = [];
            }
            filtersByType[filter.type].push(filter.value);
          }
        });
        
        // For each filter type, use OR logic within the type
        // For different filter types, use AND logic
        return Object.keys(filtersByType).every(function(filterType) {
          var valuesForType = filtersByType[filterType];
          return valuesForType.some(function(value) {
            return item[filterType] === value;
          });
        });
      });
    }
    
    return filteredData;
  }

  function updateChartVisuals(excludeChart) {
    var updates = [];
    
    // Collect all chart updates that need to be done
    if (excludeChart !== 'chartSpecies') {
      updates.push({id: 'chartSpecies', type: 'Species', isBar: true});
    }
    if (excludeChart !== 'chartYear') {
      updates.push({id: 'chartYear', type: 'Year', isBar: true});
    }
    if (excludeChart !== 'chartTissue') {
      updates.push({id: 'chartTissue', type: 'Tissue', isBar: false});
    }
    if (excludeChart !== 'chartStatus') {
      updates.push({id: 'chartStatus', type: 'Status', isBar: false});
    }
    
    // Process updates one by one with small delays to prevent blocking
    function processNextUpdate(index) {
      if (index >= updates.length) return;
      
      var update = updates[index];
      if (update.isBar) {
        updateBarChart(update.id, update.type);
      } else {
        updatePieChart(update.id, update.type);
      }
      
      // Process next update in next animation frame
      if (index < updates.length - 1) {
        requestAnimationFrame(function() {
          processNextUpdate(index + 1);
        });
      }
    }
    
    if (updates.length > 0) {
      processNextUpdate(0);
    }
  }
  
  function updateBarChart(chartId, filterType) {
    // Get filtered data excluding filters for this chart type
    var filteredData = getFilteredDataExcludingType(filterType);
    
    // Recalculate counts based on filtered data
    var counts = {};
    filteredData.forEach(function(item) {
      var value = item[filterType] || 'Unknown';
      counts[value] = (counts[value] || 0) + 1;
    });
    
    var sortedEntries = Object.entries(counts);
    if (filterType === 'Year') {
      sortedEntries.sort((a, b) => a[0].localeCompare(b[0]));
    } else {
      sortedEntries.sort((a, b) => b[1] - a[1]);
    }
    
    var labels = sortedEntries.map(entry => entry[0]);
    var values = sortedEntries.map(entry => entry[1]);
    var originalColors = filterType === 'Species' ? colorSchemes.species : colorSchemes.year;
    
    // Set colors and styles based on active filters
    var colors = new Array(labels.length);
    var lineWidths = new Array(labels.length);
    var lineColors = new Array(labels.length);
    
    for (var index = 0; index < labels.length; index++) {
      var label = labels[index];
      var filterKey = filterType + '::' + label;
      var originalColor = originalColors[index % originalColors.length];
      
      if (activeFilters[filterKey]) {
        // Make hollow - white fill with colored border
        colors[index] = 'rgba(255,255,255,0.9)';
        lineWidths[index] = 3;
        lineColors[index] = originalColor;
      } else {
        // Reset to original color
        colors[index] = originalColor;
        lineWidths[index] = 0;
        lineColors[index] = originalColor;
      }
    }
    
    var data = [{
      x: labels,
      y: values,
      type: 'bar',
      marker: {
        color: colors,
        line: { 
          width: lineWidths,
          color: lineColors
        }
      },
      hovertemplate: '<b>%{x}</b><br>Count: %{y}<extra></extra>'
    }];
    
    var layout = {
      title: false,
      margin: filterType === 'Species' ? { l: 50, r: 20, t: 20, b: 100 } : { l: 50, r: 20, t: 20, b: 60 },
      xaxis: { 
        tickangle: filterType === 'Species' ? -45 : 0,
        title: filterType === 'Year' ? 'Year' : '',
        automargin: true
      },
      yaxis: { title: 'Count' },
      plot_bgcolor: 'rgba(0,0,0,0)',
      paper_bgcolor: 'rgba(0,0,0,0)',
      font: { size: 12 }
    };
    
    var config = { 
      responsive: true, 
      displayModeBar: false 
    };
    
    Plotly.react(chartId, data, layout, config).then(function() {
      // Remove any existing click handlers to prevent multiple bindings
      document.getElementById(chartId).removeAllListeners('plotly_click');
      
      // Re-bind click event for bar charts
      document.getElementById(chartId).on('plotly_click', function(clickData) {
        var pointIndex = clickData.points[0].pointIndex;
        var selectedValue = String(clickData.points[0].x); // Convert to string to match data format
        
        // Find the original color for this value
        var originalColor;
        if (filterType === 'Species') {
          // For species, find the original index in the full data
          var allSpecies = {};
          originalData.forEach(function(item) {
            var species = item.Species || 'Unknown';
            allSpecies[species] = (allSpecies[species] || 0) + 1;
          });
          var allSpeciesList = Object.keys(allSpecies).sort((a, b) => allSpecies[b] - allSpecies[a]);
          var originalIndex = allSpeciesList.indexOf(selectedValue);
          originalColor = colorSchemes.species[originalIndex % colorSchemes.species.length];
        } else if (filterType === 'Year') {
          // For year, find the original index in the full data - use the same sorting as chart creation
          var allYears = {};
          originalData.forEach(function(item) {
            var year = item.Year || 'Unknown';
            allYears[year] = (allYears[year] || 0) + 1;
          });
          var sortedEntries = Object.entries(allYears).sort((a, b) => a[0].localeCompare(b[0]));
          var allYearsList = sortedEntries.map(entry => entry[0]);
          var originalIndex = allYearsList.indexOf(selectedValue);
          originalColor = colorSchemes.year[originalIndex % colorSchemes.year.length];
        } else {
          // Fallback to current color
          originalColor = originalColors[pointIndex % originalColors.length];
        }
        toggleFilter(filterType, selectedValue, originalColor, chartId);
      });
    });
  }
  
  function updatePieChart(chartId, filterType) {
    // Get filtered data excluding filters for this chart type
    var filteredData = getFilteredDataExcludingType(filterType);
    
    // Recalculate counts based on filtered data
    var counts = {};
    filteredData.forEach(function(item) {
      var value = item[filterType] || 'Unknown';
      counts[value] = (counts[value] || 0) + 1;
    });
    
    var sortedEntries = Object.entries(counts).sort((a, b) => b[1] - a[1]);
    var labels = sortedEntries.map(entry => entry[0]);
    var values = sortedEntries.map(entry => entry[1]);
    var originalColors = filterType === 'Tissue' ? colorSchemes.tissue : colorSchemes.status;
    
    // Truncate long labels for display
    var displayLabels = labels.map(function(label) {
      var maxLength = filterType === 'Status' ? 20 : 15;
      return label.length > maxLength ? label.substring(0, maxLength) + '...' : label;
    });
    
    // Set colors and styles based on active filters
    var colors = new Array(labels.length);
    var pullValues = new Array(labels.length);
    var lineColors = new Array(labels.length);
    var lineWidths = new Array(labels.length);
    var customData = new Array(labels.length);
    
    for (var index = 0; index < labels.length; index++) {
      var label = labels[index];
      var filterKey = filterType + '::' + label;
      var originalColor = originalColors[index % originalColors.length];
      
      // Update custom data
      customData[index] = [label, originalColor];
      
      if (activeFilters[filterKey]) {
        // Make hollow - white fill with colored border
        colors[index] = 'rgba(255,255,255,0.9)';
        pullValues[index] = 0.1; // Pull out selected segments
        lineColors[index] = originalColor;
        lineWidths[index] = 4;
      } else {
        // Reset to original color
        colors[index] = originalColor;
        pullValues[index] = 0;
        lineColors[index] = 'white';
        lineWidths[index] = 2;
      }
    }
    
    var data = [{
      labels: displayLabels,
      values: values,
      type: 'pie',
      hole: 0.4,
      marker: {
        colors: colors,
        line: { 
          width: lineWidths, 
          color: lineColors 
        }
      },
      textinfo: 'percent',
      textposition: 'inside',
      hovertemplate: '<b>%{text}</b><br>Count: %{value}<br>Percentage: %{percent}<extra></extra>',
      text: labels, // 使用完整标签用于悬浮提示
      showlegend: true,
      textfont: { size: 10 },
      pull: pullValues,
      customdata: customData
    }];
    
    var layout = {
      title: false,
      margin: { l: 20, r: 20, t: 20, b: 20 },
      plot_bgcolor: 'rgba(0,0,0,0)',
      paper_bgcolor: 'rgba(0,0,0,0)',
      font: { size: 10 },
      legend: {
        orientation: "v",
        x: 1.1,
        y: 0.5,
        font: { size: 10 },
        bgcolor: 'rgba(255,255,255,0.9)',
        bordercolor: '#ccc',
        borderwidth: 1
      }
    };
    
    var config = { 
      responsive: true, 
      displayModeBar: false 
    };
    
    Plotly.react(chartId, data, layout, config).then(function() {
      // Remove any existing click handlers to prevent multiple bindings
      document.getElementById(chartId).removeAllListeners('plotly_click');
      
      // Re-bind click event for pie charts
      document.getElementById(chartId).on('plotly_click', function(clickData) {
        var point = clickData.points[0];
        var pointIndex = point.pointIndex;
        var customData = point.customdata;
        
        // Get the selected value from the point label
        var selectedValue = point.label;
        var selectedColor;
        
        // Handle the nested array structure - customData might be [Array(2), Array(2), ...]
        if (Array.isArray(customData) && Array.isArray(customData[0]) && customData[0].length >= 2) {
          // customData[0] contains [label, color] for the clicked segment
          selectedColor = customData[0][1];
        } else if (Array.isArray(customData) && customData.length >= 2) {
          // customData is [label, color] directly
          selectedColor = customData[1];
        } else {
          // Fallback: calculate color from original data
          var counts = {};
          originalData.forEach(function(item) {
            var value = item[filterType] || 'Unknown';
            counts[value] = (counts[value] || 0) + 1;
          });
          var sortedEntries = Object.entries(counts).sort((a, b) => b[1] - a[1]);
          var labels = sortedEntries.map(entry => entry[0]);
          var labelIndex = labels.indexOf(selectedValue);
          var colorScheme = filterType === 'Tissue' ? colorSchemes.tissue : colorSchemes.status;
          selectedColor = colorScheme[labelIndex % colorScheme.length];
        }
        toggleFilter(filterType, selectedValue, selectedColor, chartId);
      });
    });
  }
  
  function updateFilterTags() {
    var container = document.getElementById('filterTags');
    var filterContainer = document.getElementById('filterContainer');
    
    container.innerHTML = '';
    
    if (Object.keys(activeFilters).length === 0) {
      filterContainer.style.display = 'none';
      return;
    }
    
    filterContainer.style.display = 'block';
    
    Object.keys(activeFilters).forEach(function(filterKey) {
      var filter = activeFilters[filterKey];
      var tag = document.createElement('div');
      tag.className = 'filter-tag';
      tag.style.setProperty('background-color', filter.color, 'important');
      tag.style.setProperty('color', 'white', 'important');
      tag.style.setProperty('border-color', filter.color, 'important');
      
      var text = document.createElement('span');
      text.textContent = filter.type + ': ' + filter.value;
      
      var closeBtn = document.createElement('button');
      closeBtn.className = 'filter-tag-close';
      closeBtn.innerHTML = '×';
      closeBtn.onclick = function() {
        toggleFilter(filter.type, filter.value, filter.color, null);
      };
      
      tag.appendChild(text);
      tag.appendChild(closeBtn);
      container.appendChild(tag);
    });
  }
  
  function resetAllFilters() {
    activeFilters = {};
    
    // Clear any pending updates
    if (updateTimeout) {
      clearTimeout(updateTimeout);
    }
    
    // Update filter tags immediately
    updateFilterTags();
    
    // Update charts and table asynchronously
    requestAnimationFrame(function() {
      updateChartVisuals(null);
      requestAnimationFrame(function() {
        filterTableData();
      });
    });
  }
  
  function filterTableData() {
    var filteredData = originalData;
    
    if (Object.keys(activeFilters).length > 0) {
      filteredData = originalData.filter(function(item) {
        // Group filters by type
        var filtersByType = {};
        Object.values(activeFilters).forEach(function(filter) {
          if (!filtersByType[filter.type]) {
            filtersByType[filter.type] = [];
          }
          filtersByType[filter.type].push(filter.value);
        });
        
        // For each filter type, use OR logic within the type
        // For different filter types, use AND logic
        return Object.keys(filtersByType).every(function(filterType) {
          var valuesForType = filtersByType[filterType];
          return valuesForType.some(function(value) {
            return item[filterType] === value;
          });
        });
      });
    }
    
    // Update the DataTable with filtered data
    if (tables[0]) {
      tables[0].clear();
      
      filteredData.forEach(function(item) {
        var linkCell = item.Link ? '<a href="' + item.Link + '" target="_blank" style="color:#23265F"><b>Link</b></a>' : '';
        var downloadCell = item.Download ? '<a href="' + item.Download + '" target="_blank" style="color:#23265F"><b>Raw&Processed Data</b></a>' : '';
        
        var row = [
          item.Species || '',
          item.Atlas || '',
          item.Tissue || '',
          item.Status || '',
          item.Platform || '',
          item['Seq-type'] || '',
          item.Year || '',
          item.Accession || '',
          linkCell,
          item.Datasets || '',
          item.DOI || '',
          downloadCell
        ];
        tables[0].row.add(row);
      });
      
      tables[0].draw();
    }
  }
  
  </script>      