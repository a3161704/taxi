# taxi

<!DOCTYPE html>

<meta charset="utf-8"/>
<html lang="en">
<head>
<script src="https://ajax.googleapis.com/ajax/libs/jquery/1.10.2/jquery.min.js"></script>
<link href="https://cdnjs.cloudflare.com/ajax/libs/nvd3/1.7.1/nv.d3.min.css" rel="stylesheet"/>
<script src="https://cdnjs.cloudflare.com/ajax/libs/d3/3.5.5/d3.min.js"></script>
<script src="https://cdnjs.cloudflare.com/ajax/libs/nvd3/1.7.1/nv.d3.min.js"></script>
</head>
<style>

body {
  font: 15px sans-serif;
}

</style>
<h2>各時段每小時平均人數</h2>
<div id="my_graphname"><svg style="width:800px;height:400px;"></svg></div>
<script>

    $(function(){


                data_my_graphname=[{"values": [{"x": "工作06-09", "y": 9.505162601626017}, {"x": "工作10-15", "y": 7.406422764227642}, {"x": "工作16-21", "y": 35.49368563685637}, {"x": "工作22-03", "y": 29.331138211382115}, {"x": "假日22-03", "y": 17.2675}, {"x": "假日06-15", "y": 8.289466666666666}, {"x": "假日16-21", "y": 19.08416666666667}, {"x": "每日04-05", "y": 17.30262295081967}], "key": "Serie 1", "yAxis": "1"}];


            nv.addGraph(function() {
        var chart = nv.models.discreteBarChart();

        chart.margin({top: 30, right: 60, bottom: 20, left: 60});

        var datum = data_my_graphname;



                    chart.yAxis
                .tickFormat(d3.format(',.0f'));

    
    

        



            d3.select('#my_graphname svg')
            .datum(datum)
            .transition().duration(500)
            .attr('width', 800)
            .attr('height', 400)
            .call(chart);

    
        });



        });
    </script>
<div id="ge_shi_duan_mei_xiao_shi_ping_jun_ren_shu"><svg style="width:800px;height:400px;"></svg></div>
<script>

    $(function(){


    data_ge_shi_duan_mei_xiao_shi_ping_jun_ren_shu=[{"values": [{"label": "A", "value": 9.505162601626017}, {"label": "B", "value": 7.406422764227642}, {"label": "C", "value": 35.49368563685637}, {"label": "D", "value": 29.331138211382115}, {"label": "E", "value": 17.2675}, {"label": "F", "value": 8.289466666666666}, {"label": "G", "value": 19.08416666666667}, {"label": "Other", "value": 17.30262295081967}], "key": "Serie 1"}];

    nv.addGraph(function() {
        var chart = nv.models.pieChart();
        chart.margin({top: 30, right: 60, bottom: 20, left: 60});
        var datum = data_ge_shi_duan_mei_xiao_shi_ping_jun_ren_shu[0].values;


    chart.tooltipContent(function(key, y, e, graph) {
          var x = String(key);
          var y =  String(y)  + ' %';

              tooltip_str = '<center><b>'+x+'</b></center>' + y;
              return tooltip_str;
              });
        chart.showLabels(true);

        chart.donut(false);

    chart.pie.valueFormat(d3.format('.1f'));
	
	chart.showLegend(true);
	
        var mycolor = new Array();
            mycolor[0] = "#5698c6";
            mycolor[1] = " #c2d5ee";
            mycolor[2] = "#fd9d48";
            mycolor[3] = "#ffcc9a";
            mycolor[4] = " #61b861";
            mycolor[5] = " #b2e7a7";
            mycolor[6] = " #e05d5e";
            mycolor[7] = "#ffb2b0";

        chart
            .x(function(d) { return d.label })
            .y(function(d) { return d.value });

        chart.width(800);

        chart.height(400);

        chart.color(mycolor);

            d3.select('#ge_shi_duan_mei_xiao_shi_ping_jun_ren_shu svg')
            .datum(datum)
            .transition().duration(500)
            .attr('width', 800)
            .attr('height', 400)
            .call(chart);


        });



        });
    </script>
</html>
