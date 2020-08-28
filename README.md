# Graph_Com_Slider_
Script to perform network analysis and interactive visualization using Python libraries (NetworkX &amp; Bokeh)

Files in repository:

br_1.csv -> Data to visualize 

Slider_grafico_2 -> Script for network community detection with Girvan-Newmann algorithm and network visualization with
                    Python 3.6 libraries Numpy, NetworkX & Bokeh
                    
example_1.html -> Output Bokeh plot file of interactive network visualizer; filters edges depending on Edge Weight

<!DOCTYPE html>
<html lang="en">
  
  <head>
    
      <meta charset="utf-8">
      <title>Bokeh Plot</title>
      
      
        
          
        
        
          
        <script type="text/javascript" src="https://cdn.bokeh.org/bokeh/release/bokeh-2.1.1.min.js" integrity="sha384-kLr4fYcqcSpbuI95brIH3vnnYCquzzSxHPU6XGQCIkQRGJwhg0StNbj1eegrHs12" crossorigin="anonymous"></script>
        <script type="text/javascript" src="https://cdn.bokeh.org/bokeh/release/bokeh-widgets-2.1.1.min.js" integrity="sha384-xIGPmVtaOm+z0BqfSOMn4lOR6ciex448GIKG4eE61LsAvmGj48XcMQZtKcE/UXZe" crossorigin="anonymous"></script>
        <script type="text/javascript">
            Bokeh.set_log_level("info");
        </script>
        
      
      
    
  </head>
  
  
  <body>
    
      
        
          
          
            
              <div class="bk-root" id="df7ffde4-be05-45b5-87fd-9fdec98b5c86" data-root-id="7406"></div>
            
          
        
      
      
        <script type="application/json" id="7974">
          {"6c9f685f-4477-4469-9f31-4cd2be5694c3":{"roots":{"references":[{"attributes":{"children":[{"id":"7338"},{"id":"7405"}]},"id":"7406","type":"Column"},{"attributes":{"plot_height":500,"plot_width":900,"renderers":[{"id":"7342"}],"title":{"id":"7341"},"toolbar":{"id":"7372"},"x_range":{"id":"7336"},"x_scale":{"id":"7630"},"y_range":{"id":"7337"},"y_scale":{"id":"7629"}},"id":"7338","type":"Plot"},{"attributes":{"data_source":{"id":"7357"},"glyph":{"id":"7364"},"hover_glyph":{"id":"7395"},"muted_glyph":null,"selection_glyph":{"id":"7390"},"view":{"id":"7359"}},"id":"7358","type":"GlyphRenderer"},{"attributes":{"end":1.1,"start":-1.1},"id":"7337","type":"Range1d"},{"attributes":{"edge_renderer":{"id":"7358"},"inspection_policy":{"id":"7402"},"layout_provider":{"id":"7375"},"node_renderer":{"id":"7345"},"selection_policy":{"id":"7400"}},"id":"7342","type":"GraphRenderer"},{"attributes":{},"id":"7630","type":"LinearScale"},{"attributes":{"data":{"Weights":[41,30,53,88,68,29,55,52,49,10,49,80,3,74,83,31,77,44,74,29,56,52,59,80,51,17,78,51,51,80,75,48,65,61,25,61,5,47,55,19,30,66,54,19,80,19,72,50,51,14,26,53,9,17,5,8,75,28,31,44,23,69,23,7,16,53,24,21,16,25,7,65,53,65,88,68,80,43,24,72,2,50,67,16,40,79,73,16,82,23,89,68,71,69,36,67,62,60,15,42,85,4,71,86,27,72,55,83,28,67,47,71,87,61,37,57,43,48,16,67,74,16,82,64,53,51,45,57,44,63,38,58,66,46,4,60,38,55,61,16,47,2,33,42,11,20,56,41,11,62,13,62,35,41,69,85,39,28,72,3,53,69,19,42,86,77,19,90,26,87,70,74,77,22,15,56,41,61,7,37,75,78,6,60,16,67,70,92,39,18,66,45,63,9,36,92,72,9,78,20,81,62,82,2,26,12,22,3,40,19,42,38,14,23,45,13,67,37,54,41,16,29,43,34,37,28,39,18,3,73,81,29,63,60,72,29,75,43,78,79,57,6,4,55,2,1,2,38,6,1,1,5,63,39,56,41,57,32,59,45,55,66,44,25,68,58,80,23,69,44,72,80,61,24,9,18,67,26,22,18,27,9,30,59,26,42,60,46,63,37,69,9,78,16,76,59,80,18,70,36,77,87,78,25,22,18,27,9,28,83,67,65,29,38,19,71,70,68],"end":[1,2,3,4,5,6,8,9,10,11,12,13,14,15,16,17,18,19,20,21,22,23,24,25,26,2,3,4,5,6,8,9,10,11,12,13,14,15,16,17,18,19,20,21,22,23,24,25,26,3,4,5,6,8,9,10,12,13,14,15,16,17,18,19,20,21,22,23,24,25,26,4,5,6,8,9,10,11,12,13,14,15,16,17,18,19,20,21,22,23,24,25,26,5,6,8,9,10,11,12,13,14,15,16,17,18,19,20,21,22,23,24,25,26,6,8,9,10,11,12,13,14,15,16,17,18,19,20,21,22,23,24,25,26,7,8,9,10,11,12,13,14,15,16,17,18,19,20,21,22,23,24,25,26,9,10,11,12,13,14,15,16,17,18,19,20,21,22,23,24,25,26,10,11,12,13,15,16,17,18,19,20,21,22,23,24,25,26,11,12,13,15,16,17,18,19,20,21,22,23,24,25,26,12,13,15,16,18,19,20,22,24,25,26,13,14,15,16,17,18,19,20,21,22,23,24,25,26,14,15,16,17,18,19,20,21,22,23,24,25,26,15,16,17,18,19,20,21,22,23,24,25,16,17,18,19,20,21,22,23,24,25,26,17,18,19,20,21,22,23,24,25,26,18,19,20,21,22,23,24,25,26,19,20,21,22,23,24,25,26,20,21,22,23,24,25,26,21,22,23,24,25,26,22,23,24,25,26,23,24,25,26,24,25,26,25,26,26],"start":[0,0,0,0,0,0,0,0,0,0,0,0,0,0,0,0,0,0,0,0,0,0,0,0,0,1,1,1,1,1,1,1,1,1,1,1,1,1,1,1,1,1,1,1,1,1,1,1,1,2,2,2,2,2,2,2,2,2,2,2,2,2,2,2,2,2,2,2,2,2,2,3,3,3,3,3,3,3,3,3,3,3,3,3,3,3,3,3,3,3,3,3,3,4,4,4,4,4,4,4,4,4,4,4,4,4,4,4,4,4,4,4,4,4,5,5,5,5,5,5,5,5,5,5,5,5,5,5,5,5,5,5,5,5,6,6,6,6,6,6,6,6,6,6,6,6,6,6,6,6,6,6,6,6,8,8,8,8,8,8,8,8,8,8,8,8,8,8,8,8,8,8,9,9,9,9,9,9,9,9,9,9,9,9,9,9,9,9,10,10,10,10,10,10,10,10,10,10,10,10,10,10,10,11,11,11,11,11,11,11,11,11,11,11,12,12,12,12,12,12,12,12,12,12,12,12,12,12,13,13,13,13,13,13,13,13,13,13,13,13,13,14,14,14,14,14,14,14,14,14,14,14,15,15,15,15,15,15,15,15,15,15,15,16,16,16,16,16,16,16,16,16,16,17,17,17,17,17,17,17,17,17,18,18,18,18,18,18,18,18,19,19,19,19,19,19,19,20,20,20,20,20,20,21,21,21,21,21,22,22,22,22,23,23,23,24,24,25]},"selected":{"id":"7642"},"selection_policy":{"id":"7641"}},"id":"7357","type":"ColumnDataSource"},{"attributes":{"data":{"index":[0,1,2,3,4,5,6,7,8,9,10,11,12,13,14,15,16,17,18,19,20,21,22,23,24,25,26],"name":["A","B","C","D","E","F","G","H","I","J","K","L","M","N","N+","O","P","K","R","S","T","U","V","W","X","Y","Z"]},"selected":{"id":"7644"},"selection_policy":{"id":"7643"}},"id":"7344","type":"ColumnDataSource"},{"attributes":{"line_color":{"value":"#abdda4"},"line_width":{"value":5}},"id":"7395","type":"MultiLine"},{"attributes":{"fill_color":{"value":"blue"},"size":{"units":"screen","value":15}},"id":"7347","type":"Circle"},{"attributes":{"callback":null,"tooltips":[["Nodo","@name"]]},"id":"7369","type":"HoverTool"},{"attributes":{"line_alpha":{"value":0.8},"line_color":{"value":"#CCCCCC"}},"id":"7364","type":"MultiLine"},{"attributes":{"graph_layout":{"0":[0.5741222111625975,-0.6936578330941152],"1":[0.6693894168899376,0.6155999482994365],"10":[0.07967735656193846,0.9216562201114543],"11":[0.9036462780721253,-0.23790485890082083],"12":[-0.1647343257671386,-0.9794612312130251],"13":[-0.49353593594909784,0.7948442079233478],"14":[0.20262864263580774,-1.0],"15":[0.017815182733626075,-0.12812679687769563],"16":[0.012374414631024977,-0.09224073069498931],"17":[-0.2038625039949381,0.7580622134748903],"18":[-0.7239073877467542,-0.6405862489242073],"19":[-0.02184885097364843,-0.10217098663818346],"2":[0.47624219310478,0.8485349065733594],"20":[0.010715039795877927,-0.04131903302303426],"21":[-0.15107277099910085,0.7222934715392563],"22":[-0.018035544457565222,-0.0634446786026369],"23":[-0.7596590841692883,0.6437945325284475],"24":[0.04526099554807563,-0.04769668944374794],"25":[0.05551229188462873,-0.07751082712542737],"26":[0.054391791875435455,-0.1105809064994341],"3":[-0.8967393525652247,0.3325376824697817],"4":[-0.94043626888164,-0.0007194263325261396],"5":[-0.8710875192907697,-0.3321042410111875],"6":[-0.4562073645273659,-0.8412048291967006],"7":[0.9928267521176924,0.08647715458594792],"8":[0.7284363404445755,-0.7242635754329587],"9":[0.8780880018644087,0.3891925555047688]}},"id":"7375","type":"StaticLayoutProvider"},{"attributes":{"fill_color":{"value":"#abdda4"},"size":{"units":"screen","value":15}},"id":"7381","type":"Circle"},{"attributes":{"end":100,"format":"0[.]00","js_property_callbacks":{"change:value":[{"id":"7404"}]},"start":1,"title":"Umbral","value":1},"id":"7405","type":"Slider"},{"attributes":{"overlay":{"id":"7640"}},"id":"7371","type":"BoxSelectTool"},{"attributes":{"args":{"aristas":318,"datum":["A","B","C","D","E","F","G","H","I","J","K","L","M","N","N+","O","P","K","R","S","T","U","V","W","X","Y","Z"],"graph_setup":{"id":"7342"},"indices_actuales":[0,1,2,3,4,5,6,7,8,9,10,11,12,13,14,15,16,17,18,19,20,21,22,23,24,25,26],"nodos_destino_act":[1,2,3,4,5,6,8,9,10,11,12,13,14,15,16,17,18,19,20,21,22,23,24,25,26,2,3,4,5,6,8,9,10,11,12,13,14,15,16,17,18,19,20,21,22,23,24,25,26,3,4,5,6,8,9,10,12,13,14,15,16,17,18,19,20,21,22,23,24,25,26,4,5,6,8,9,10,11,12,13,14,15,16,17,18,19,20,21,22,23,24,25,26,5,6,8,9,10,11,12,13,14,15,16,17,18,19,20,21,22,23,24,25,26,6,8,9,10,11,12,13,14,15,16,17,18,19,20,21,22,23,24,25,26,7,8,9,10,11,12,13,14,15,16,17,18,19,20,21,22,23,24,25,26,9,10,11,12,13,14,15,16,17,18,19,20,21,22,23,24,25,26,10,11,12,13,15,16,17,18,19,20,21,22,23,24,25,26,11,12,13,15,16,17,18,19,20,21,22,23,24,25,26,12,13,15,16,18,19,20,22,24,25,26,13,14,15,16,17,18,19,20,21,22,23,24,25,26,14,15,16,17,18,19,20,21,22,23,24,25,26,15,16,17,18,19,20,21,22,23,24,25,16,17,18,19,20,21,22,23,24,25,26,17,18,19,20,21,22,23,24,25,26,18,19,20,21,22,23,24,25,26,19,20,21,22,23,24,25,26,20,21,22,23,24,25,26,21,22,23,24,25,26,22,23,24,25,26,23,24,25,26,24,25,26,25,26,26],"nodos_inicio_act":[0,0,0,0,0,0,0,0,0,0,0,0,0,0,0,0,0,0,0,0,0,0,0,0,0,1,1,1,1,1,1,1,1,1,1,1,1,1,1,1,1,1,1,1,1,1,1,1,1,2,2,2,2,2,2,2,2,2,2,2,2,2,2,2,2,2,2,2,2,2,2,3,3,3,3,3,3,3,3,3,3,3,3,3,3,3,3,3,3,3,3,3,3,4,4,4,4,4,4,4,4,4,4,4,4,4,4,4,4,4,4,4,4,4,5,5,5,5,5,5,5,5,5,5,5,5,5,5,5,5,5,5,5,5,6,6,6,6,6,6,6,6,6,6,6,6,6,6,6,6,6,6,6,6,8,8,8,8,8,8,8,8,8,8,8,8,8,8,8,8,8,8,9,9,9,9,9,9,9,9,9,9,9,9,9,9,9,9,10,10,10,10,10,10,10,10,10,10,10,10,10,10,10,11,11,11,11,11,11,11,11,11,11,11,12,12,12,12,12,12,12,12,12,12,12,12,12,12,13,13,13,13,13,13,13,13,13,13,13,13,13,14,14,14,14,14,14,14,14,14,14,14,15,15,15,15,15,15,15,15,15,15,15,16,16,16,16,16,16,16,16,16,16,17,17,17,17,17,17,17,17,17,18,18,18,18,18,18,18,18,19,19,19,19,19,19,19,20,20,20,20,20,20,21,21,21,21,21,22,22,22,22,23,23,23,24,24,25],"pesos_actuales":[41,30,53,88,68,29,55,52,49,10,49,80,3,74,83,31,77,44,74,29,56,52,59,80,51,17,78,51,51,80,75,48,65,61,25,61,5,47,55,19,30,66,54,19,80,19,72,50,51,14,26,53,9,17,5,8,75,28,31,44,23,69,23,7,16,53,24,21,16,25,7,65,53,65,88,68,80,43,24,72,2,50,67,16,40,79,73,16,82,23,89,68,71,69,36,67,62,60,15,42,85,4,71,86,27,72,55,83,28,67,47,71,87,61,37,57,43,48,16,67,74,16,82,64,53,51,45,57,44,63,38,58,66,46,4,60,38,55,61,16,47,2,33,42,11,20,56,41,11,62,13,62,35,41,69,85,39,28,72,3,53,69,19,42,86,77,19,90,26,87,70,74,77,22,15,56,41,61,7,37,75,78,6,60,16,67,70,92,39,18,66,45,63,9,36,92,72,9,78,20,81,62,82,2,26,12,22,3,40,19,42,38,14,23,45,13,67,37,54,41,16,29,43,34,37,28,39,18,3,73,81,29,63,60,72,29,75,43,78,79,57,6,4,55,2,1,2,38,6,1,1,5,63,39,56,41,57,32,59,45,55,66,44,25,68,58,80,23,69,44,72,80,61,24,9,18,67,26,22,18,27,9,30,59,26,42,60,46,63,37,69,9,78,16,76,59,80,18,70,36,77,87,78,25,22,18,27,9,28,83,67,65,29,38,19,71,70,68]},"code":"\n    \n    var datos_nodos = datum;\n    var f = cb_obj.value;\n    var n_nodos_inicio = [];\n    var n_nodos_destino = [];\n    var n_pesos = [];\n    var n_indices = [];\n\n    var n1 = nodos_inicio_act.slice();\n    var n2 = nodos_destino_act.slice();\n    var p1 = pesos_actuales.slice();\n    var limite = aristas;\n    var index_ = indices_actuales;\n\n    for (var i= 0; i &lt; limite; i++) {\n      if (p1[i] &gt; f) {\n        n_nodos_inicio.push(n1[i]);\n        n_nodos_destino.push(n2[i]);\n        n_pesos.push(p1[i]);\n      }\n    }\n\n    var new_data_edge = {'start': n_nodos_inicio, 'end': n_nodos_destino};\n    var new_data_nodes = {'index': index_};\n\n    graph_setup.edge_renderer.data_source.data = new_data_edge; \n    graph_setup.node_renderer.data_source.data = new_data_nodes;\n    graph_setup.node_renderer.data_source.data['name'] = datos_nodos;\n    \n"},"id":"7404","type":"CustomJS"},{"attributes":{},"id":"7402","type":"NodesAndLinkedEdges"},{"attributes":{"end":1.1,"start":-1.1},"id":"7336","type":"Range1d"},{"attributes":{"source":{"id":"7357"}},"id":"7359","type":"CDSView"},{"attributes":{"callback":null},"id":"7370","type":"TapTool"},{"attributes":{"active_drag":"auto","active_inspect":"auto","active_multi":null,"active_scroll":"auto","active_tap":"auto","tools":[{"id":"7369"},{"id":"7370"},{"id":"7371"}]},"id":"7372","type":"Toolbar"},{"attributes":{},"id":"7400","type":"NodesAndLinkedEdges"},{"attributes":{"fill_color":{"value":"#fdae61"},"size":{"units":"screen","value":15}},"id":"7376","type":"Circle"},{"attributes":{},"id":"7641","type":"UnionRenderers"},{"attributes":{"bottom_units":"screen","fill_alpha":0.5,"fill_color":"lightgrey","left_units":"screen","level":"overlay","line_alpha":1.0,"line_color":"black","line_dash":[4,4],"line_width":2,"right_units":"screen","top_units":"screen"},"id":"7640","type":"BoxAnnotation"},{"attributes":{},"id":"7643","type":"UnionRenderers"},{"attributes":{"line_color":{"value":"#fdae61"},"line_width":{"value":3}},"id":"7390","type":"MultiLine"},{"attributes":{},"id":"7644","type":"Selection"},{"attributes":{},"id":"7629","type":"LinearScale"},{"attributes":{"text":"br_1 Interaccion Slider"},"id":"7341","type":"Title"},{"attributes":{"source":{"id":"7344"}},"id":"7346","type":"CDSView"},{"attributes":{},"id":"7642","type":"Selection"},{"attributes":{"data_source":{"id":"7344"},"glyph":{"id":"7347"},"hover_glyph":{"id":"7381"},"muted_glyph":null,"selection_glyph":{"id":"7376"},"view":{"id":"7346"}},"id":"7345","type":"GlyphRenderer"}],"root_ids":["7406"]},"title":"Bokeh Application","version":"2.1.1"}}
        </script>
        <script type="text/javascript">
          (function() {
            var fn = function() {
              Bokeh.safely(function() {
                (function(root) {
                  function embed_document(root) {
                    
                  var docs_json = document.getElementById('7974').textContent;
                  var render_items = [{"docid":"6c9f685f-4477-4469-9f31-4cd2be5694c3","root_ids":["7406"],"roots":{"7406":"df7ffde4-be05-45b5-87fd-9fdec98b5c86"}}];
                  root.Bokeh.embed.embed_items(docs_json, render_items);
                
                  }
                  if (root.Bokeh !== undefined) {
                    embed_document(root);
                  } else {
                    var attempts = 0;
                    var timer = setInterval(function(root) {
                      if (root.Bokeh !== undefined) {
                        clearInterval(timer);
                        embed_document(root);
                      } else {
                        attempts++;
                        if (attempts > 100) {
                          clearInterval(timer);
                          console.log("Bokeh: ERROR: Unable to run BokehJS code because BokehJS library is missing");
                        }
                      }
                    }, 10, root)
                  }
                })(window);
              });
            };
            if (document.readyState != "loading") fn();
            else document.addEventListener("DOMContentLoaded", fn);
          })();
        </script>
    
  </body>
  
</html>
