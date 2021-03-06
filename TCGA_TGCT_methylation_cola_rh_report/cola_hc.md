cola Report for Hierarchical Partitioning - 'TCGA_TGCT_methylation'
==================

**Date**: 2021-07-22 16:18:33 CEST, **cola version**: 1.9.4

----------------------------------------------------------------

<style type='text/css'>

body, td, th {
   font-family: Arial,Helvetica,sans-serif;
   background-color: white;
   font-size: 13px;
  max-width: 800px;
  margin: auto;
  margin-left:210px;
  padding: 0px 10px 0px 10px;
  border-left: 1px solid #EEEEEE;
  line-height: 150%;
}

tt, code, pre {
   font-family: 'DejaVu Sans Mono', 'Droid Sans Mono', 'Lucida Console', Consolas, Monaco, 

monospace;
}

h1 {
   font-size:2.2em;
}

h2 {
   font-size:1.8em;
}

h3 {
   font-size:1.4em;
}

h4 {
   font-size:1.0em;
}

h5 {
   font-size:0.9em;
}

h6 {
   font-size:0.8em;
}

a {
  text-decoration: none;
  color: #0366d6;
}

a:hover {
  text-decoration: underline;
}

a:visited {
   color: #0366d6;
}

pre, img {
  max-width: 100%;
}
pre {
  overflow-x: auto;
}
pre code {
   display: block; padding: 0.5em;
}

code {
  font-size: 92%;
  border: 1px solid #ccc;
}

code[class] {
  background-color: #F8F8F8;
}

table, td, th {
  border: 1px solid #ccc;
}

blockquote {
   color:#666666;
   margin:0;
   padding-left: 1em;
   border-left: 0.5em #EEE solid;
}

hr {
   height: 0px;
   border-bottom: none;
   border-top-width: thin;
   border-top-style: dotted;
   border-top-color: #999999;
}

@media print {
   * {
      background: transparent !important;
      color: black !important;
      filter:none !important;
      -ms-filter: none !important;
   }

   body {
      font-size:12pt;
      max-width:100%;
   }

   a, a:visited {
      text-decoration: underline;
   }

   hr {
      visibility: hidden;
      page-break-before: always;
   }

   pre, blockquote {
      padding-right: 1em;
      page-break-inside: avoid;
   }

   tr, img {
      page-break-inside: avoid;
   }

   img {
      max-width: 100% !important;
   }

   @page :left {
      margin: 15mm 20mm 15mm 10mm;
   }

   @page :right {
      margin: 15mm 10mm 15mm 20mm;
   }

   p, h2, h3 {
      orphans: 3; widows: 3;
   }

   h2, h3 {
      page-break-after: avoid;
   }
}
</style>




## Summary



First the variable is renamed to `res_rh`.


```r
res_rh = rh
```



The partition hierarchy and all available functions which can be applied to `res_rh` object.


```r
res_rh
```

```
#> A 'HierarchicalPartition' object with 4 combinations of top-value methods and partitioning methods.
#>   On a matrix with 376225 rows and 156 columns.
#>   Performed in total 40600 partitions.
#>   There are 21 groups under the following parameters:
#>     - min_samples: 6
#>     - mean_silhouette_cutoff: 0.9
#>     - min_n_signatures: 1000 (signatures are selected based on:)
#>       - fdr_cutoff: 0.05
#>       - group_diff: 0.25
#> 
#> Hierarchy of the partition:
#>   0, 156 cols
#>   |-- 01, 51 cols, 7052 signatures
#>   |   |-- 011, 24 cols, 432 signatures (c)
#>   |   |-- 012, 16 cols, 9534 signatures
#>   |   |   |-- 0121, 7 cols (b)
#>   |   |   |-- 0122, 7 cols (b)
#>   |   |   `-- 0123, 2 cols (b)
#>   |   `-- 013, 11 cols (b)
#>   |-- 02, 82 cols, 18548 signatures
#>   |   |-- 021, 19 cols, 994 signatures (c)
#>   |   |-- 022, 35 cols, 52459 signatures
#>   |   |   |-- 0221, 11 cols (b)
#>   |   |   |-- 0222, 5 cols (b)
#>   |   |   |-- 0223, 13 cols, 128 signatures (c)
#>   |   |   `-- 0224, 6 cols (b)
#>   |   |-- 023, 14 cols, 66872 signatures
#>   |   |   |-- 0231, 5 cols (b)
#>   |   |   |-- 0232, 2 cols (b)
#>   |   |   |-- 0233, 4 cols (b)
#>   |   |   `-- 0234, 3 cols (b)
#>   |   `-- 024, 14 cols, 5127 signatures
#>   |       |-- 0241, 5 cols (b)
#>   |       |-- 0242, 5 cols (b)
#>   |       `-- 0243, 4 cols (b)
#>   `-- 03, 23 cols, 2846 signatures
#>       |-- 031, 8 cols (b)
#>       |-- 032, 7 cols (b)
#>       |-- 033, 5 cols (b)
#>       `-- 034, 3 cols (b)
#> Stop reason:
#>   b) Subgroup had too few columns.
#>   c) There were too few signatures.
#> 
#> Following methods can be applied to this 'HierarchicalPartition' object:
#>  [1] "all_leaves"            "all_nodes"             "cola_report"           "collect_classes"      
#>  [5] "colnames"              "compare_signatures"    "dimension_reduction"   "functional_enrichment"
#>  [9] "get_anno_col"          "get_anno"              "get_children_nodes"    "get_classes"          
#> [13] "get_matrix"            "get_signatures"        "is_leaf_node"          "max_depth"            
#> [17] "merge_node"            "ncol"                  "node_info"             "node_level"           
#> [21] "nrow"                  "rownames"              "show"                  "split_node"           
#> [25] "suggest_best_k"        "test_to_known_factors" "top_rows_heatmap"      "top_rows_overlap"     
#> 
#> You can get result for a single node by e.g. object["01"]
```

The call of `hierarchical_partition()` was:


```
#> hierarchical_partition(data = mat, top_n = 1000, top_value_method = c("SD", "ATC"), 
#>     partition_method = c("kmeans", "skmeans"), subset = 500, group_diff = 0.25, min_n_signatures = 1000, 
#>     filter_fun = function(mat) {
#>         s = rowSds(mat)
#>         order(-s)[1:30000]
#>     }, max_k = 8, scale_rows = FALSE, cores = 4)
```

Dimension of the input matrix:


```r
mat = get_matrix(res_rh)
dim(mat)
```

```
#> [1] 376225    156
```

All the methods that were tried:


```r
res_rh@param$combination_method
```

```
#> [[1]]
#> [1] "SD"     "kmeans"
#> 
#> [[2]]
#> [1] "ATC"    "kmeans"
#> 
#> [[3]]
#> [1] "SD"      "skmeans"
#> 
#> [[4]]
#> [1] "ATC"     "skmeans"
```

### Density distribution

The density distribution for each sample is visualized as one column in the following heatmap.
The clustering is based on the distance which is the Kolmogorov-Smirnov statistic between two distributions.




```r
library(ComplexHeatmap)
densityHeatmap(mat, ylab = "value", cluster_columns = TRUE, show_column_names = FALSE,
    mc.cores = 1)
```

![plot of chunk density-heatmap](figure_cola/density-heatmap-1.png)



Some values about the hierarchy:


```r
all_nodes(res_rh)
```

```
#>  [1] "0"    "01"   "011"  "012"  "0121" "0122" "0123" "013"  "02"   "021"  "022"  "0221" "0222"
#> [14] "0223" "0224" "023"  "0231" "0232" "0233" "0234" "024"  "0241" "0242" "0243" "03"   "031" 
#> [27] "032"  "033"  "034"
```

```r
all_leaves(res_rh)
```

```
#>  [1] "011"  "0121" "0122" "0123" "013"  "021"  "0221" "0222" "0223" "0224" "0231" "0232" "0233"
#> [14] "0234" "0241" "0242" "0243" "031"  "032"  "033"  "034"
```

```r
node_info(res_rh)
```

```
#>      id best_method depth best_k n_columns n_signatures p_signatures is_leaf
#> 1     0  SD:skmeans     1      3       156       191928      0.51014   FALSE
#> 2    01  SD:skmeans     2      3        51         7052      0.01874   FALSE
#> 3   011  ATC:kmeans     3      2        24          432      0.00115    TRUE
#> 4   012  ATC:kmeans     3      3        16         9534      0.02534   FALSE
#> 5  0121 not applied     4     NA         7           NA           NA    TRUE
#> 6  0122 not applied     4     NA         7           NA           NA    TRUE
#> 7  0123 not applied     4     NA         2           NA           NA    TRUE
#> 8   013 not applied     3     NA        11           NA           NA    TRUE
#> 9    02 ATC:skmeans     2      4        82        18548      0.04930   FALSE
#> 10  021 ATC:skmeans     3      2        19          994      0.00264    TRUE
#> 11  022   SD:kmeans     3      4        35        52459      0.13944   FALSE
#> 12 0221 not applied     4     NA        11           NA           NA    TRUE
#> 13 0222 not applied     4     NA         5           NA           NA    TRUE
#> 14 0223  ATC:kmeans     4      2        13          128      0.00034    TRUE
#> 15 0224 not applied     4     NA         6           NA           NA    TRUE
#> 16  023   SD:kmeans     3      4        14        66872      0.17774   FALSE
#> 17 0231 not applied     4     NA         5           NA           NA    TRUE
#> 18 0232 not applied     4     NA         2           NA           NA    TRUE
#> 19 0233 not applied     4     NA         4           NA           NA    TRUE
#> 20 0234 not applied     4     NA         3           NA           NA    TRUE
#> 21  024 ATC:skmeans     3      3        14         5127      0.01363   FALSE
#> 22 0241 not applied     4     NA         5           NA           NA    TRUE
#> 23 0242 not applied     4     NA         5           NA           NA    TRUE
#> 24 0243 not applied     4     NA         4           NA           NA    TRUE
#> 25   03  ATC:kmeans     2      4        23         2846      0.00756   FALSE
#> 26  031 not applied     3     NA         8           NA           NA    TRUE
#> 27  032 not applied     3     NA         7           NA           NA    TRUE
#> 28  033 not applied     3     NA         5           NA           NA    TRUE
#> 29  034 not applied     3     NA         3           NA           NA    TRUE
```

In the output from `node_info()`, there are the following columns:

- `id`: The node id.
- `best_method`: The best method selected.
- `depth`: Depth of the node in the hierarchy.
- `best_k`: Best number of groups of the partition on that node.
- `n_columns`: Number of columns in the submatrix.
- `n_signatures`: Number of signatures with the `best_k`.
- `p_signatures`: Proportion of hte signatures in total number of rows in the matrix.
- `is_leaf`: Whether the node is a leaf.

Labels of nodes are encoded in a special way. The number of digits
correspond to the depth of the node in the hierarchy and the value of the
digits correspond to the index of the subgroup in the current node, E.g. a label
of ???012??? means the node is the second subgroup of the partition which is the
first subgroup of the root node.

### Suggest the best k



Following table shows the best `k` (number of partitions) for each node in the
partition hierarchy. Clicking on the node name in the table goes to the
corresponding section for the partitioning on that node.

[The cola vignette](https://jokergoo.github.io/cola_vignettes/cola.html#toc_13)
explains the definition of the metrics used for determining the best
number of partitions.



```r
suggest_best_k(res_rh)
```


|Node                |Best method                                         |Is leaf   |Best k |1-PAC |Mean silhouette |Concordance | #samples|   |
|:-------------------|:---------------------------------------------------|:---------|:------|:-----|:---------------|:-----------|--------:|:--|
|[Node0](#Node0)     |SD:skmeans                                          |          |4      |1.00  |0.99            |0.99        |      156|** |
|[Node01](#Node01)   |SD:skmeans                                          |          |3      |1.00  |0.98            |0.99        |       51|** |
|Node011-leaf        |ATC:kmeans                                          |??? (&#99;) |6      |0.96  |0.92            |0.95        |       24|** |
|[Node012](#Node012) |ATC:kmeans                                          |          |3      |1.00  |0.97            |0.97        |       16|** |
|Node0121-leaf       |<span style='color:grey;'><i>not applied</i></span> |??? (b)     |       |      |                |            |        7|   |
|Node0122-leaf       |<span style='color:grey;'><i>not applied</i></span> |??? (b)     |       |      |                |            |        7|   |
|Node0123-leaf       |<span style='color:grey;'><i>not applied</i></span> |??? (b)     |       |      |                |            |        2|   |
|Node013-leaf        |<span style='color:grey;'><i>not applied</i></span> |??? (b)     |       |      |                |            |       11|   |
|[Node02](#Node02)   |ATC:skmeans                                         |          |6      |0.92  |0.82            |0.93        |       82|*  |
|Node021-leaf        |ATC:skmeans                                         |??? (&#99;) |2      |0.95  |0.95            |0.96        |       19|*  |
|[Node022](#Node022) |SD:kmeans                                           |          |2      |1.00  |1.00            |1.00        |       35|** |
|Node0221-leaf       |<span style='color:grey;'><i>not applied</i></span> |??? (b)     |       |      |                |            |       11|   |
|Node0222-leaf       |<span style='color:grey;'><i>not applied</i></span> |??? (b)     |       |      |                |            |        5|   |
|Node0223-leaf       |ATC:kmeans                                          |??? (&#99;) |8      |0.92  |0.41            |0.78        |       13|*  |
|Node0224-leaf       |<span style='color:grey;'><i>not applied</i></span> |??? (b)     |       |      |                |            |        6|   |
|[Node023](#Node023) |SD:kmeans                                           |          |5      |0.95  |0.89            |0.95        |       14|*  |
|Node0231-leaf       |<span style='color:grey;'><i>not applied</i></span> |??? (b)     |       |      |                |            |        5|   |
|Node0232-leaf       |<span style='color:grey;'><i>not applied</i></span> |??? (b)     |       |      |                |            |        2|   |
|Node0233-leaf       |<span style='color:grey;'><i>not applied</i></span> |??? (b)     |       |      |                |            |        4|   |
|Node0234-leaf       |<span style='color:grey;'><i>not applied</i></span> |??? (b)     |       |      |                |            |        3|   |
|[Node024](#Node024) |ATC:skmeans                                         |          |3      |1.00  |0.98            |0.99        |       14|** |
|Node0241-leaf       |<span style='color:grey;'><i>not applied</i></span> |??? (b)     |       |      |                |            |        5|   |
|Node0242-leaf       |<span style='color:grey;'><i>not applied</i></span> |??? (b)     |       |      |                |            |        5|   |
|Node0243-leaf       |<span style='color:grey;'><i>not applied</i></span> |??? (b)     |       |      |                |            |        4|   |
|[Node03](#Node03)   |ATC:kmeans                                          |          |4      |0.94  |0.96            |0.96        |       23|*  |
|Node031-leaf        |<span style='color:grey;'><i>not applied</i></span> |??? (b)     |       |      |                |            |        8|   |
|Node032-leaf        |<span style='color:grey;'><i>not applied</i></span> |??? (b)     |       |      |                |            |        7|   |
|Node033-leaf        |<span style='color:grey;'><i>not applied</i></span> |??? (b)     |       |      |                |            |        5|   |
|Node034-leaf        |<span style='color:grey;'><i>not applied</i></span> |??? (b)     |       |      |                |            |        3|   |


Stop reason: b) Subgroup had too few columns. c) There were too few signatures. 

\*\*: 1-PAC > 0.95, \*: 1-PAC > 0.9


### Partition hierarchy

The nodes of the hierarchy can be merged by setting the `merge_node` parameters. Here we 
control the hierarchy with the `min_n_signatures` parameter. The value of `min_n_signatures` is
from `node_info()`.





<style type='text/css'>



.ui-helper-hidden {
	display: none;
}
.ui-helper-hidden-accessible {
	border: 0;
	clip: rect(0 0 0 0);
	height: 1px;
	margin: -1px;
	overflow: hidden;
	padding: 0;
	position: absolute;
	width: 1px;
}
.ui-helper-reset {
	margin: 0;
	padding: 0;
	border: 0;
	outline: 0;
	line-height: 1.3;
	text-decoration: none;
	font-size: 100%;
	list-style: none;
}
.ui-helper-clearfix:before,
.ui-helper-clearfix:after {
	content: "";
	display: table;
	border-collapse: collapse;
}
.ui-helper-clearfix:after {
	clear: both;
}
.ui-helper-zfix {
	width: 100%;
	height: 100%;
	top: 0;
	left: 0;
	position: absolute;
	opacity: 0;
	filter:Alpha(Opacity=0); 
}

.ui-front {
	z-index: 100;
}



.ui-state-disabled {
	cursor: default !important;
	pointer-events: none;
}



.ui-icon {
	display: inline-block;
	vertical-align: middle;
	margin-top: -.25em;
	position: relative;
	text-indent: -99999px;
	overflow: hidden;
	background-repeat: no-repeat;
}

.ui-widget-icon-block {
	left: 50%;
	margin-left: -8px;
	display: block;
}




.ui-widget-overlay {
	position: fixed;
	top: 0;
	left: 0;
	width: 100%;
	height: 100%;
}
.ui-accordion .ui-accordion-header {
	display: block;
	cursor: pointer;
	position: relative;
	margin: 2px 0 0 0;
	padding: .5em .5em .5em .7em;
	font-size: 100%;
}
.ui-accordion .ui-accordion-content {
	padding: 1em 2.2em;
	border-top: 0;
	overflow: auto;
}
.ui-autocomplete {
	position: absolute;
	top: 0;
	left: 0;
	cursor: default;
}
.ui-menu {
	list-style: none;
	padding: 0;
	margin: 0;
	display: block;
	outline: 0;
}
.ui-menu .ui-menu {
	position: absolute;
}
.ui-menu .ui-menu-item {
	margin: 0;
	cursor: pointer;
	
	list-style-image: url("data:image/gif;base64,R0lGODlhAQABAIAAAAAAAP///yH5BAEAAAAALAAAAAABAAEAAAIBRAA7");
}
.ui-menu .ui-menu-item-wrapper {
	position: relative;
	padding: 3px 1em 3px .4em;
}
.ui-menu .ui-menu-divider {
	margin: 5px 0;
	height: 0;
	font-size: 0;
	line-height: 0;
	border-width: 1px 0 0 0;
}
.ui-menu .ui-state-focus,
.ui-menu .ui-state-active {
	margin: -1px;
}


.ui-menu-icons {
	position: relative;
}
.ui-menu-icons .ui-menu-item-wrapper {
	padding-left: 2em;
}


.ui-menu .ui-icon {
	position: absolute;
	top: 0;
	bottom: 0;
	left: .2em;
	margin: auto 0;
}


.ui-menu .ui-menu-icon {
	left: auto;
	right: 0;
}
.ui-button {
	padding: .4em 1em;
	display: inline-block;
	position: relative;
	line-height: normal;
	margin-right: .1em;
	cursor: pointer;
	vertical-align: middle;
	text-align: center;
	-webkit-user-select: none;
	-moz-user-select: none;
	-ms-user-select: none;
	user-select: none;

	
	overflow: visible;
}

.ui-button,
.ui-button:link,
.ui-button:visited,
.ui-button:hover,
.ui-button:active {
	text-decoration: none;
}


.ui-button-icon-only {
	width: 2em;
	box-sizing: border-box;
	text-indent: -9999px;
	white-space: nowrap;
}


input.ui-button.ui-button-icon-only {
	text-indent: 0;
}


.ui-button-icon-only .ui-icon {
	position: absolute;
	top: 50%;
	left: 50%;
	margin-top: -8px;
	margin-left: -8px;
}

.ui-button.ui-icon-notext .ui-icon {
	padding: 0;
	width: 2.1em;
	height: 2.1em;
	text-indent: -9999px;
	white-space: nowrap;

}

input.ui-button.ui-icon-notext .ui-icon {
	width: auto;
	height: auto;
	text-indent: 0;
	white-space: normal;
	padding: .4em 1em;
}



input.ui-button::-moz-focus-inner,
button.ui-button::-moz-focus-inner {
	border: 0;
	padding: 0;
}
.ui-controlgroup {
	vertical-align: middle;
	display: inline-block;
}
.ui-controlgroup > .ui-controlgroup-item {
	float: left;
	margin-left: 0;
	margin-right: 0;
}
.ui-controlgroup > .ui-controlgroup-item:focus,
.ui-controlgroup > .ui-controlgroup-item.ui-visual-focus {
	z-index: 9999;
}
.ui-controlgroup-vertical > .ui-controlgroup-item {
	display: block;
	float: none;
	width: 100%;
	margin-top: 0;
	margin-bottom: 0;
	text-align: left;
}
.ui-controlgroup-vertical .ui-controlgroup-item {
	box-sizing: border-box;
}
.ui-controlgroup .ui-controlgroup-label {
	padding: .4em 1em;
}
.ui-controlgroup .ui-controlgroup-label span {
	font-size: 80%;
}
.ui-controlgroup-horizontal .ui-controlgroup-label + .ui-controlgroup-item {
	border-left: none;
}
.ui-controlgroup-vertical .ui-controlgroup-label + .ui-controlgroup-item {
	border-top: none;
}
.ui-controlgroup-horizontal .ui-controlgroup-label.ui-widget-content {
	border-right: none;
}
.ui-controlgroup-vertical .ui-controlgroup-label.ui-widget-content {
	border-bottom: none;
}


.ui-controlgroup-vertical .ui-spinner-input {

	
	width: 75%;
	width: calc( 100% - 2.4em );
}
.ui-controlgroup-vertical .ui-spinner .ui-spinner-up {
	border-top-style: solid;
}

.ui-checkboxradio-label .ui-icon-background {
	box-shadow: inset 1px 1px 1px #ccc;
	border-radius: .12em;
	border: none;
}
.ui-checkboxradio-radio-label .ui-icon-background {
	width: 16px;
	height: 16px;
	border-radius: 1em;
	overflow: visible;
	border: none;
}
.ui-checkboxradio-radio-label.ui-checkboxradio-checked .ui-icon,
.ui-checkboxradio-radio-label.ui-checkboxradio-checked:hover .ui-icon {
	background-image: none;
	width: 8px;
	height: 8px;
	border-width: 4px;
	border-style: solid;
}
.ui-checkboxradio-disabled {
	pointer-events: none;
}
.ui-datepicker {
	width: 17em;
	padding: .2em .2em 0;
	display: none;
}
.ui-datepicker .ui-datepicker-header {
	position: relative;
	padding: .2em 0;
}
.ui-datepicker .ui-datepicker-prev,
.ui-datepicker .ui-datepicker-next {
	position: absolute;
	top: 2px;
	width: 1.8em;
	height: 1.8em;
}
.ui-datepicker .ui-datepicker-prev-hover,
.ui-datepicker .ui-datepicker-next-hover {
	top: 1px;
}
.ui-datepicker .ui-datepicker-prev {
	left: 2px;
}
.ui-datepicker .ui-datepicker-next {
	right: 2px;
}
.ui-datepicker .ui-datepicker-prev-hover {
	left: 1px;
}
.ui-datepicker .ui-datepicker-next-hover {
	right: 1px;
}
.ui-datepicker .ui-datepicker-prev span,
.ui-datepicker .ui-datepicker-next span {
	display: block;
	position: absolute;
	left: 50%;
	margin-left: -8px;
	top: 50%;
	margin-top: -8px;
}
.ui-datepicker .ui-datepicker-title {
	margin: 0 2.3em;
	line-height: 1.8em;
	text-align: center;
}
.ui-datepicker .ui-datepicker-title select {
	font-size: 1em;
	margin: 1px 0;
}
.ui-datepicker select.ui-datepicker-month,
.ui-datepicker select.ui-datepicker-year {
	width: 45%;
}
.ui-datepicker table {
	width: 100%;
	font-size: .9em;
	border-collapse: collapse;
	margin: 0 0 .4em;
}
.ui-datepicker th {
	padding: .7em .3em;
	text-align: center;
	font-weight: bold;
	border: 0;
}
.ui-datepicker td {
	border: 0;
	padding: 1px;
}
.ui-datepicker td span,
.ui-datepicker td a {
	display: block;
	padding: .2em;
	text-align: right;
	text-decoration: none;
}
.ui-datepicker .ui-datepicker-buttonpane {
	background-image: none;
	margin: .7em 0 0 0;
	padding: 0 .2em;
	border-left: 0;
	border-right: 0;
	border-bottom: 0;
}
.ui-datepicker .ui-datepicker-buttonpane button {
	float: right;
	margin: .5em .2em .4em;
	cursor: pointer;
	padding: .2em .6em .3em .6em;
	width: auto;
	overflow: visible;
}
.ui-datepicker .ui-datepicker-buttonpane button.ui-datepicker-current {
	float: left;
}


.ui-datepicker.ui-datepicker-multi {
	width: auto;
}
.ui-datepicker-multi .ui-datepicker-group {
	float: left;
}
.ui-datepicker-multi .ui-datepicker-group table {
	width: 95%;
	margin: 0 auto .4em;
}
.ui-datepicker-multi-2 .ui-datepicker-group {
	width: 50%;
}
.ui-datepicker-multi-3 .ui-datepicker-group {
	width: 33.3%;
}
.ui-datepicker-multi-4 .ui-datepicker-group {
	width: 25%;
}
.ui-datepicker-multi .ui-datepicker-group-last .ui-datepicker-header,
.ui-datepicker-multi .ui-datepicker-group-middle .ui-datepicker-header {
	border-left-width: 0;
}
.ui-datepicker-multi .ui-datepicker-buttonpane {
	clear: left;
}
.ui-datepicker-row-break {
	clear: both;
	width: 100%;
	font-size: 0;
}


.ui-datepicker-rtl {
	direction: rtl;
}
.ui-datepicker-rtl .ui-datepicker-prev {
	right: 2px;
	left: auto;
}
.ui-datepicker-rtl .ui-datepicker-next {
	left: 2px;
	right: auto;
}
.ui-datepicker-rtl .ui-datepicker-prev:hover {
	right: 1px;
	left: auto;
}
.ui-datepicker-rtl .ui-datepicker-next:hover {
	left: 1px;
	right: auto;
}
.ui-datepicker-rtl .ui-datepicker-buttonpane {
	clear: right;
}
.ui-datepicker-rtl .ui-datepicker-buttonpane button {
	float: left;
}
.ui-datepicker-rtl .ui-datepicker-buttonpane button.ui-datepicker-current,
.ui-datepicker-rtl .ui-datepicker-group {
	float: right;
}
.ui-datepicker-rtl .ui-datepicker-group-last .ui-datepicker-header,
.ui-datepicker-rtl .ui-datepicker-group-middle .ui-datepicker-header {
	border-right-width: 0;
	border-left-width: 1px;
}


.ui-datepicker .ui-icon {
	display: block;
	text-indent: -99999px;
	overflow: hidden;
	background-repeat: no-repeat;
	left: .5em;
	top: .3em;
}
.ui-dialog {
	position: absolute;
	top: 0;
	left: 0;
	padding: .2em;
	outline: 0;
}
.ui-dialog .ui-dialog-titlebar {
	padding: .4em 1em;
	position: relative;
}
.ui-dialog .ui-dialog-title {
	float: left;
	margin: .1em 0;
	white-space: nowrap;
	width: 90%;
	overflow: hidden;
	text-overflow: ellipsis;
}
.ui-dialog .ui-dialog-titlebar-close {
	position: absolute;
	right: .3em;
	top: 50%;
	width: 20px;
	margin: -10px 0 0 0;
	padding: 1px;
	height: 20px;
}
.ui-dialog .ui-dialog-content {
	position: relative;
	border: 0;
	padding: .5em 1em;
	background: none;
	overflow: auto;
}
.ui-dialog .ui-dialog-buttonpane {
	text-align: left;
	border-width: 1px 0 0 0;
	background-image: none;
	margin-top: .5em;
	padding: .3em 1em .5em .4em;
}
.ui-dialog .ui-dialog-buttonpane .ui-dialog-buttonset {
	float: right;
}
.ui-dialog .ui-dialog-buttonpane button {
	margin: .5em .4em .5em 0;
	cursor: pointer;
}
.ui-dialog .ui-resizable-n {
	height: 2px;
	top: 0;
}
.ui-dialog .ui-resizable-e {
	width: 2px;
	right: 0;
}
.ui-dialog .ui-resizable-s {
	height: 2px;
	bottom: 0;
}
.ui-dialog .ui-resizable-w {
	width: 2px;
	left: 0;
}
.ui-dialog .ui-resizable-se,
.ui-dialog .ui-resizable-sw,
.ui-dialog .ui-resizable-ne,
.ui-dialog .ui-resizable-nw {
	width: 7px;
	height: 7px;
}
.ui-dialog .ui-resizable-se {
	right: 0;
	bottom: 0;
}
.ui-dialog .ui-resizable-sw {
	left: 0;
	bottom: 0;
}
.ui-dialog .ui-resizable-ne {
	right: 0;
	top: 0;
}
.ui-dialog .ui-resizable-nw {
	left: 0;
	top: 0;
}
.ui-draggable .ui-dialog-titlebar {
	cursor: move;
}
.ui-draggable-handle {
	-ms-touch-action: none;
	touch-action: none;
}
.ui-resizable {
	position: relative;
}
.ui-resizable-handle {
	position: absolute;
	font-size: 0.1px;
	display: block;
	-ms-touch-action: none;
	touch-action: none;
}
.ui-resizable-disabled .ui-resizable-handle,
.ui-resizable-autohide .ui-resizable-handle {
	display: none;
}
.ui-resizable-n {
	cursor: n-resize;
	height: 7px;
	width: 100%;
	top: -5px;
	left: 0;
}
.ui-resizable-s {
	cursor: s-resize;
	height: 7px;
	width: 100%;
	bottom: -5px;
	left: 0;
}
.ui-resizable-e {
	cursor: e-resize;
	width: 7px;
	right: -5px;
	top: 0;
	height: 100%;
}
.ui-resizable-w {
	cursor: w-resize;
	width: 7px;
	left: -5px;
	top: 0;
	height: 100%;
}
.ui-resizable-se {
	cursor: se-resize;
	width: 12px;
	height: 12px;
	right: 1px;
	bottom: 1px;
}
.ui-resizable-sw {
	cursor: sw-resize;
	width: 9px;
	height: 9px;
	left: -5px;
	bottom: -5px;
}
.ui-resizable-nw {
	cursor: nw-resize;
	width: 9px;
	height: 9px;
	left: -5px;
	top: -5px;
}
.ui-resizable-ne {
	cursor: ne-resize;
	width: 9px;
	height: 9px;
	right: -5px;
	top: -5px;
}
.ui-progressbar {
	height: 2em;
	text-align: left;
	overflow: hidden;
}
.ui-progressbar .ui-progressbar-value {
	margin: -1px;
	height: 100%;
}
.ui-progressbar .ui-progressbar-overlay {
	background: url("data:image/gif;base64,R0lGODlhKAAoAIABAAAAAP///yH/C05FVFNDQVBFMi4wAwEAAAAh+QQJAQABACwAAAAAKAAoAAACkYwNqXrdC52DS06a7MFZI+4FHBCKoDeWKXqymPqGqxvJrXZbMx7Ttc+w9XgU2FB3lOyQRWET2IFGiU9m1frDVpxZZc6bfHwv4c1YXP6k1Vdy292Fb6UkuvFtXpvWSzA+HycXJHUXiGYIiMg2R6W459gnWGfHNdjIqDWVqemH2ekpObkpOlppWUqZiqr6edqqWQAAIfkECQEAAQAsAAAAACgAKAAAApSMgZnGfaqcg1E2uuzDmmHUBR8Qil95hiPKqWn3aqtLsS18y7G1SzNeowWBENtQd+T1JktP05nzPTdJZlR6vUxNWWjV+vUWhWNkWFwxl9VpZRedYcflIOLafaa28XdsH/ynlcc1uPVDZxQIR0K25+cICCmoqCe5mGhZOfeYSUh5yJcJyrkZWWpaR8doJ2o4NYq62lAAACH5BAkBAAEALAAAAAAoACgAAAKVDI4Yy22ZnINRNqosw0Bv7i1gyHUkFj7oSaWlu3ovC8GxNso5fluz3qLVhBVeT/Lz7ZTHyxL5dDalQWPVOsQWtRnuwXaFTj9jVVh8pma9JjZ4zYSj5ZOyma7uuolffh+IR5aW97cHuBUXKGKXlKjn+DiHWMcYJah4N0lYCMlJOXipGRr5qdgoSTrqWSq6WFl2ypoaUAAAIfkECQEAAQAsAAAAACgAKAAAApaEb6HLgd/iO7FNWtcFWe+ufODGjRfoiJ2akShbueb0wtI50zm02pbvwfWEMWBQ1zKGlLIhskiEPm9R6vRXxV4ZzWT2yHOGpWMyorblKlNp8HmHEb/lCXjcW7bmtXP8Xt229OVWR1fod2eWqNfHuMjXCPkIGNileOiImVmCOEmoSfn3yXlJWmoHGhqp6ilYuWYpmTqKUgAAIfkECQEAAQAsAAAAACgAKAAAApiEH6kb58biQ3FNWtMFWW3eNVcojuFGfqnZqSebuS06w5V80/X02pKe8zFwP6EFWOT1lDFk8rGERh1TTNOocQ61Hm4Xm2VexUHpzjymViHrFbiELsefVrn6XKfnt2Q9G/+Xdie499XHd2g4h7ioOGhXGJboGAnXSBnoBwKYyfioubZJ2Hn0RuRZaflZOil56Zp6iioKSXpUAAAh+QQJAQABACwAAAAAKAAoAAACkoQRqRvnxuI7kU1a1UU5bd5tnSeOZXhmn5lWK3qNTWvRdQxP8qvaC+/yaYQzXO7BMvaUEmJRd3TsiMAgswmNYrSgZdYrTX6tSHGZO73ezuAw2uxuQ+BbeZfMxsexY35+/Qe4J1inV0g4x3WHuMhIl2jXOKT2Q+VU5fgoSUI52VfZyfkJGkha6jmY+aaYdirq+lQAACH5BAkBAAEALAAAAAAoACgAAAKWBIKpYe0L3YNKToqswUlvznigd4wiR4KhZrKt9Upqip61i9E3vMvxRdHlbEFiEXfk9YARYxOZZD6VQ2pUunBmtRXo1Lf8hMVVcNl8JafV38aM2/Fu5V16Bn63r6xt97j09+MXSFi4BniGFae3hzbH9+hYBzkpuUh5aZmHuanZOZgIuvbGiNeomCnaxxap2upaCZsq+1kAACH5BAkBAAEALAAAAAAoACgAAAKXjI8By5zf4kOxTVrXNVlv1X0d8IGZGKLnNpYtm8Lr9cqVeuOSvfOW79D9aDHizNhDJidFZhNydEahOaDH6nomtJjp1tutKoNWkvA6JqfRVLHU/QUfau9l2x7G54d1fl995xcIGAdXqMfBNadoYrhH+Mg2KBlpVpbluCiXmMnZ2Sh4GBqJ+ckIOqqJ6LmKSllZmsoq6wpQAAAh+QQJAQABACwAAAAAKAAoAAAClYx/oLvoxuJDkU1a1YUZbJ59nSd2ZXhWqbRa2/gF8Gu2DY3iqs7yrq+xBYEkYvFSM8aSSObE+ZgRl1BHFZNr7pRCavZ5BW2142hY3AN/zWtsmf12p9XxxFl2lpLn1rseztfXZjdIWIf2s5dItwjYKBgo9yg5pHgzJXTEeGlZuenpyPmpGQoKOWkYmSpaSnqKileI2FAAACH5BAkBAAEALAAAAAAoACgAAAKVjB+gu+jG4kORTVrVhRlsnn2dJ3ZleFaptFrb+CXmO9OozeL5VfP99HvAWhpiUdcwkpBH3825AwYdU8xTqlLGhtCosArKMpvfa1mMRae9VvWZfeB2XfPkeLmm18lUcBj+p5dnN8jXZ3YIGEhYuOUn45aoCDkp16hl5IjYJvjWKcnoGQpqyPlpOhr3aElaqrq56Bq7VAAAOw==");
	height: 100%;
	filter: alpha(opacity=25); 
	opacity: 0.25;
}
.ui-progressbar-indeterminate .ui-progressbar-value {
	background-image: none;
}
.ui-selectable {
	-ms-touch-action: none;
	touch-action: none;
}
.ui-selectable-helper {
	position: absolute;
	z-index: 100;
	border: 1px dotted black;
}
.ui-selectmenu-menu {
	padding: 0;
	margin: 0;
	position: absolute;
	top: 0;
	left: 0;
	display: none;
}
.ui-selectmenu-menu .ui-menu {
	overflow: auto;
	overflow-x: hidden;
	padding-bottom: 1px;
}
.ui-selectmenu-menu .ui-menu .ui-selectmenu-optgroup {
	font-size: 1em;
	font-weight: bold;
	line-height: 1.5;
	padding: 2px 0.4em;
	margin: 0.5em 0 0 0;
	height: auto;
	border: 0;
}
.ui-selectmenu-open {
	display: block;
}
.ui-selectmenu-text {
	display: block;
	margin-right: 20px;
	overflow: hidden;
	text-overflow: ellipsis;
}
.ui-selectmenu-button.ui-button {
	text-align: left;
	white-space: nowrap;
	width: 14em;
}
.ui-selectmenu-icon.ui-icon {
	float: right;
	margin-top: 0;
}
.ui-slider {
	position: relative;
	text-align: left;
}
.ui-slider .ui-slider-handle {
	position: absolute;
	z-index: 2;
	width: 1.2em;
	height: 1.2em;
	cursor: default;
	-ms-touch-action: none;
	touch-action: none;
}
.ui-slider .ui-slider-range {
	position: absolute;
	z-index: 1;
	font-size: .7em;
	display: block;
	border: 0;
	background-position: 0 0;
}


.ui-slider.ui-state-disabled .ui-slider-handle,
.ui-slider.ui-state-disabled .ui-slider-range {
	filter: inherit;
}

.ui-slider-horizontal {
	height: .8em;
}
.ui-slider-horizontal .ui-slider-handle {
	top: -.3em;
	margin-left: -.6em;
}
.ui-slider-horizontal .ui-slider-range {
	top: 0;
	height: 100%;
}
.ui-slider-horizontal .ui-slider-range-min {
	left: 0;
}
.ui-slider-horizontal .ui-slider-range-max {
	right: 0;
}

.ui-slider-vertical {
	width: .8em;
	height: 100px;
}
.ui-slider-vertical .ui-slider-handle {
	left: -.3em;
	margin-left: 0;
	margin-bottom: -.6em;
}
.ui-slider-vertical .ui-slider-range {
	left: 0;
	width: 100%;
}
.ui-slider-vertical .ui-slider-range-min {
	bottom: 0;
}
.ui-slider-vertical .ui-slider-range-max {
	top: 0;
}
.ui-sortable-handle {
	-ms-touch-action: none;
	touch-action: none;
}
.ui-spinner {
	position: relative;
	display: inline-block;
	overflow: hidden;
	padding: 0;
	vertical-align: middle;
}
.ui-spinner-input {
	border: none;
	background: none;
	color: inherit;
	padding: .222em 0;
	margin: .2em 0;
	vertical-align: middle;
	margin-left: .4em;
	margin-right: 2em;
}
.ui-spinner-button {
	width: 1.6em;
	height: 50%;
	font-size: .5em;
	padding: 0;
	margin: 0;
	text-align: center;
	position: absolute;
	cursor: default;
	display: block;
	overflow: hidden;
	right: 0;
}

.ui-spinner a.ui-spinner-button {
	border-top-style: none;
	border-bottom-style: none;
	border-right-style: none;
}
.ui-spinner-up {
	top: 0;
}
.ui-spinner-down {
	bottom: 0;
}
.ui-tabs {
	position: relative;
	padding: .2em;
}
.ui-tabs .ui-tabs-nav {
	margin: 0;
	padding: .2em .2em 0;
}
.ui-tabs .ui-tabs-nav li {
	list-style: none;
	float: left;
	position: relative;
	top: 0;
	margin: 1px .2em 0 0;
	border-bottom-width: 0;
	padding: 0;
	white-space: nowrap;
}
.ui-tabs .ui-tabs-nav .ui-tabs-anchor {
	float: left;
	padding: .5em 1em;
	text-decoration: none;
}
.ui-tabs .ui-tabs-nav li.ui-tabs-active {
	margin-bottom: -1px;
	padding-bottom: 1px;
}
.ui-tabs .ui-tabs-nav li.ui-tabs-active .ui-tabs-anchor,
.ui-tabs .ui-tabs-nav li.ui-state-disabled .ui-tabs-anchor,
.ui-tabs .ui-tabs-nav li.ui-tabs-loading .ui-tabs-anchor {
	cursor: text;
}
.ui-tabs-collapsible .ui-tabs-nav li.ui-tabs-active .ui-tabs-anchor {
	cursor: pointer;
}
.ui-tabs .ui-tabs-panel {
	display: block;
	border-width: 0;
	padding: 1em 1.4em;
	background: none;
}
.ui-tooltip {
	padding: 8px;
	position: absolute;
	z-index: 9999;
	max-width: 300px;
}
body .ui-tooltip {
	border-width: 2px;
}

.ui-widget {
	font-family: Arial,Helvetica,sans-serif;
	font-size: 1em;
}
.ui-widget .ui-widget {
	font-size: 1em;
}
.ui-widget input,
.ui-widget select,
.ui-widget textarea,
.ui-widget button {
	font-family: Arial,Helvetica,sans-serif;
	font-size: 1em;
}
.ui-widget.ui-widget-content {
	border: 1px solid #c5c5c5;
}
.ui-widget-content {
	border: 1px solid #dddddd;
	background: #ffffff;
	color: #333333;
}
.ui-widget-content a {
	color: #333333;
}
.ui-widget-header {
	border: 1px solid #dddddd;
	background: #e9e9e9;
	color: #333333;
	font-weight: bold;
}
.ui-widget-header a {
	color: #333333;
}


.ui-state-default,
.ui-widget-content .ui-state-default,
.ui-widget-header .ui-state-default,
.ui-button,


html .ui-button.ui-state-disabled:hover,
html .ui-button.ui-state-disabled:active {
	border: 1px solid #c5c5c5;
	background: #f6f6f6;
	font-weight: normal;
	color: #454545;
}
.ui-state-default a,
.ui-state-default a:link,
.ui-state-default a:visited,
a.ui-button,
a:link.ui-button,
a:visited.ui-button,
.ui-button {
	color: #454545;
	text-decoration: none;
}
.ui-state-hover,
.ui-widget-content .ui-state-hover,
.ui-widget-header .ui-state-hover,
.ui-state-focus,
.ui-widget-content .ui-state-focus,
.ui-widget-header .ui-state-focus,
.ui-button:hover,
.ui-button:focus {
	border: 1px solid #cccccc;
	background: #ededed;
	font-weight: normal;
	color: #2b2b2b;
}
.ui-state-hover a,
.ui-state-hover a:hover,
.ui-state-hover a:link,
.ui-state-hover a:visited,
.ui-state-focus a,
.ui-state-focus a:hover,
.ui-state-focus a:link,
.ui-state-focus a:visited,
a.ui-button:hover,
a.ui-button:focus {
	color: #2b2b2b;
	text-decoration: none;
}

.ui-visual-focus {
	box-shadow: 0 0 3px 1px rgb(94, 158, 214);
}
.ui-state-active,
.ui-widget-content .ui-state-active,
.ui-widget-header .ui-state-active,
a.ui-button:active,
.ui-button:active,
.ui-button.ui-state-active:hover {
	border: 1px solid #003eff;
	background: #007fff;
	font-weight: normal;
	color: #ffffff;
}
.ui-icon-background,
.ui-state-active .ui-icon-background {
	border: #003eff;
	background-color: #ffffff;
}
.ui-state-active a,
.ui-state-active a:link,
.ui-state-active a:visited {
	color: #ffffff;
	text-decoration: none;
}


.ui-state-highlight,
.ui-widget-content .ui-state-highlight,
.ui-widget-header .ui-state-highlight {
	border: 1px solid #dad55e;
	background: #fffa90;
	color: #777620;
}
.ui-state-checked {
	border: 1px solid #dad55e;
	background: #fffa90;
}
.ui-state-highlight a,
.ui-widget-content .ui-state-highlight a,
.ui-widget-header .ui-state-highlight a {
	color: #777620;
}
.ui-state-error,
.ui-widget-content .ui-state-error,
.ui-widget-header .ui-state-error {
	border: 1px solid #f1a899;
	background: #fddfdf;
	color: #5f3f3f;
}
.ui-state-error a,
.ui-widget-content .ui-state-error a,
.ui-widget-header .ui-state-error a {
	color: #5f3f3f;
}
.ui-state-error-text,
.ui-widget-content .ui-state-error-text,
.ui-widget-header .ui-state-error-text {
	color: #5f3f3f;
}
.ui-priority-primary,
.ui-widget-content .ui-priority-primary,
.ui-widget-header .ui-priority-primary {
	font-weight: bold;
}
.ui-priority-secondary,
.ui-widget-content .ui-priority-secondary,
.ui-widget-header .ui-priority-secondary {
	opacity: .7;
	filter:Alpha(Opacity=70); 
	font-weight: normal;
}
.ui-state-disabled,
.ui-widget-content .ui-state-disabled,
.ui-widget-header .ui-state-disabled {
	opacity: .35;
	filter:Alpha(Opacity=35); 
	background-image: none;
}
.ui-state-disabled .ui-icon {
	filter:Alpha(Opacity=35); 
}




.ui-icon {
	width: 16px;
	height: 16px;
}
.ui-icon,
.ui-widget-content .ui-icon {
	background-image: url("images/ui-icons_444444_256x240.png");
}
.ui-widget-header .ui-icon {
	background-image: url("images/ui-icons_444444_256x240.png");
}
.ui-state-hover .ui-icon,
.ui-state-focus .ui-icon,
.ui-button:hover .ui-icon,
.ui-button:focus .ui-icon {
	background-image: url("images/ui-icons_555555_256x240.png");
}
.ui-state-active .ui-icon,
.ui-button:active .ui-icon {
	background-image: url("images/ui-icons_ffffff_256x240.png");
}
.ui-state-highlight .ui-icon,
.ui-button .ui-state-highlight.ui-icon {
	background-image: url("images/ui-icons_777620_256x240.png");
}
.ui-state-error .ui-icon,
.ui-state-error-text .ui-icon {
	background-image: url("images/ui-icons_cc0000_256x240.png");
}
.ui-button .ui-icon {
	background-image: url("images/ui-icons_777777_256x240.png");
}


.ui-icon-blank { background-position: 16px 16px; }
.ui-icon-caret-1-n { background-position: 0 0; }
.ui-icon-caret-1-ne { background-position: -16px 0; }
.ui-icon-caret-1-e { background-position: -32px 0; }
.ui-icon-caret-1-se { background-position: -48px 0; }
.ui-icon-caret-1-s { background-position: -65px 0; }
.ui-icon-caret-1-sw { background-position: -80px 0; }
.ui-icon-caret-1-w { background-position: -96px 0; }
.ui-icon-caret-1-nw { background-position: -112px 0; }
.ui-icon-caret-2-n-s { background-position: -128px 0; }
.ui-icon-caret-2-e-w { background-position: -144px 0; }
.ui-icon-triangle-1-n { background-position: 0 -16px; }
.ui-icon-triangle-1-ne { background-position: -16px -16px; }
.ui-icon-triangle-1-e { background-position: -32px -16px; }
.ui-icon-triangle-1-se { background-position: -48px -16px; }
.ui-icon-triangle-1-s { background-position: -65px -16px; }
.ui-icon-triangle-1-sw { background-position: -80px -16px; }
.ui-icon-triangle-1-w { background-position: -96px -16px; }
.ui-icon-triangle-1-nw { background-position: -112px -16px; }
.ui-icon-triangle-2-n-s { background-position: -128px -16px; }
.ui-icon-triangle-2-e-w { background-position: -144px -16px; }
.ui-icon-arrow-1-n { background-position: 0 -32px; }
.ui-icon-arrow-1-ne { background-position: -16px -32px; }
.ui-icon-arrow-1-e { background-position: -32px -32px; }
.ui-icon-arrow-1-se { background-position: -48px -32px; }
.ui-icon-arrow-1-s { background-position: -65px -32px; }
.ui-icon-arrow-1-sw { background-position: -80px -32px; }
.ui-icon-arrow-1-w { background-position: -96px -32px; }
.ui-icon-arrow-1-nw { background-position: -112px -32px; }
.ui-icon-arrow-2-n-s { background-position: -128px -32px; }
.ui-icon-arrow-2-ne-sw { background-position: -144px -32px; }
.ui-icon-arrow-2-e-w { background-position: -160px -32px; }
.ui-icon-arrow-2-se-nw { background-position: -176px -32px; }
.ui-icon-arrowstop-1-n { background-position: -192px -32px; }
.ui-icon-arrowstop-1-e { background-position: -208px -32px; }
.ui-icon-arrowstop-1-s { background-position: -224px -32px; }
.ui-icon-arrowstop-1-w { background-position: -240px -32px; }
.ui-icon-arrowthick-1-n { background-position: 1px -48px; }
.ui-icon-arrowthick-1-ne { background-position: -16px -48px; }
.ui-icon-arrowthick-1-e { background-position: -32px -48px; }
.ui-icon-arrowthick-1-se { background-position: -48px -48px; }
.ui-icon-arrowthick-1-s { background-position: -64px -48px; }
.ui-icon-arrowthick-1-sw { background-position: -80px -48px; }
.ui-icon-arrowthick-1-w { background-position: -96px -48px; }
.ui-icon-arrowthick-1-nw { background-position: -112px -48px; }
.ui-icon-arrowthick-2-n-s { background-position: -128px -48px; }
.ui-icon-arrowthick-2-ne-sw { background-position: -144px -48px; }
.ui-icon-arrowthick-2-e-w { background-position: -160px -48px; }
.ui-icon-arrowthick-2-se-nw { background-position: -176px -48px; }
.ui-icon-arrowthickstop-1-n { background-position: -192px -48px; }
.ui-icon-arrowthickstop-1-e { background-position: -208px -48px; }
.ui-icon-arrowthickstop-1-s { background-position: -224px -48px; }
.ui-icon-arrowthickstop-1-w { background-position: -240px -48px; }
.ui-icon-arrowreturnthick-1-w { background-position: 0 -64px; }
.ui-icon-arrowreturnthick-1-n { background-position: -16px -64px; }
.ui-icon-arrowreturnthick-1-e { background-position: -32px -64px; }
.ui-icon-arrowreturnthick-1-s { background-position: -48px -64px; }
.ui-icon-arrowreturn-1-w { background-position: -64px -64px; }
.ui-icon-arrowreturn-1-n { background-position: -80px -64px; }
.ui-icon-arrowreturn-1-e { background-position: -96px -64px; }
.ui-icon-arrowreturn-1-s { background-position: -112px -64px; }
.ui-icon-arrowrefresh-1-w { background-position: -128px -64px; }
.ui-icon-arrowrefresh-1-n { background-position: -144px -64px; }
.ui-icon-arrowrefresh-1-e { background-position: -160px -64px; }
.ui-icon-arrowrefresh-1-s { background-position: -176px -64px; }
.ui-icon-arrow-4 { background-position: 0 -80px; }
.ui-icon-arrow-4-diag { background-position: -16px -80px; }
.ui-icon-extlink { background-position: -32px -80px; }
.ui-icon-newwin { background-position: -48px -80px; }
.ui-icon-refresh { background-position: -64px -80px; }
.ui-icon-shuffle { background-position: -80px -80px; }
.ui-icon-transfer-e-w { background-position: -96px -80px; }
.ui-icon-transferthick-e-w { background-position: -112px -80px; }
.ui-icon-folder-collapsed { background-position: 0 -96px; }
.ui-icon-folder-open { background-position: -16px -96px; }
.ui-icon-document { background-position: -32px -96px; }
.ui-icon-document-b { background-position: -48px -96px; }
.ui-icon-note { background-position: -64px -96px; }
.ui-icon-mail-closed { background-position: -80px -96px; }
.ui-icon-mail-open { background-position: -96px -96px; }
.ui-icon-suitcase { background-position: -112px -96px; }
.ui-icon-comment { background-position: -128px -96px; }
.ui-icon-person { background-position: -144px -96px; }
.ui-icon-print { background-position: -160px -96px; }
.ui-icon-trash { background-position: -176px -96px; }
.ui-icon-locked { background-position: -192px -96px; }
.ui-icon-unlocked { background-position: -208px -96px; }
.ui-icon-bookmark { background-position: -224px -96px; }
.ui-icon-tag { background-position: -240px -96px; }
.ui-icon-home { background-position: 0 -112px; }
.ui-icon-flag { background-position: -16px -112px; }
.ui-icon-calendar { background-position: -32px -112px; }
.ui-icon-cart { background-position: -48px -112px; }
.ui-icon-pencil { background-position: -64px -112px; }
.ui-icon-clock { background-position: -80px -112px; }
.ui-icon-disk { background-position: -96px -112px; }
.ui-icon-calculator { background-position: -112px -112px; }
.ui-icon-zoomin { background-position: -128px -112px; }
.ui-icon-zoomout { background-position: -144px -112px; }
.ui-icon-search { background-position: -160px -112px; }
.ui-icon-wrench { background-position: -176px -112px; }
.ui-icon-gear { background-position: -192px -112px; }
.ui-icon-heart { background-position: -208px -112px; }
.ui-icon-star { background-position: -224px -112px; }
.ui-icon-link { background-position: -240px -112px; }
.ui-icon-cancel { background-position: 0 -128px; }
.ui-icon-plus { background-position: -16px -128px; }
.ui-icon-plusthick { background-position: -32px -128px; }
.ui-icon-minus { background-position: -48px -128px; }
.ui-icon-minusthick { background-position: -64px -128px; }
.ui-icon-close { background-position: -80px -128px; }
.ui-icon-closethick { background-position: -96px -128px; }
.ui-icon-key { background-position: -112px -128px; }
.ui-icon-lightbulb { background-position: -128px -128px; }
.ui-icon-scissors { background-position: -144px -128px; }
.ui-icon-clipboard { background-position: -160px -128px; }
.ui-icon-copy { background-position: -176px -128px; }
.ui-icon-contact { background-position: -192px -128px; }
.ui-icon-image { background-position: -208px -128px; }
.ui-icon-video { background-position: -224px -128px; }
.ui-icon-script { background-position: -240px -128px; }
.ui-icon-alert { background-position: 0 -144px; }
.ui-icon-info { background-position: -16px -144px; }
.ui-icon-notice { background-position: -32px -144px; }
.ui-icon-help { background-position: -48px -144px; }
.ui-icon-check { background-position: -64px -144px; }
.ui-icon-bullet { background-position: -80px -144px; }
.ui-icon-radio-on { background-position: -96px -144px; }
.ui-icon-radio-off { background-position: -112px -144px; }
.ui-icon-pin-w { background-position: -128px -144px; }
.ui-icon-pin-s { background-position: -144px -144px; }
.ui-icon-play { background-position: 0 -160px; }
.ui-icon-pause { background-position: -16px -160px; }
.ui-icon-seek-next { background-position: -32px -160px; }
.ui-icon-seek-prev { background-position: -48px -160px; }
.ui-icon-seek-end { background-position: -64px -160px; }
.ui-icon-seek-start { background-position: -80px -160px; }

.ui-icon-seek-first { background-position: -80px -160px; }
.ui-icon-stop { background-position: -96px -160px; }
.ui-icon-eject { background-position: -112px -160px; }
.ui-icon-volume-off { background-position: -128px -160px; }
.ui-icon-volume-on { background-position: -144px -160px; }
.ui-icon-power { background-position: 0 -176px; }
.ui-icon-signal-diag { background-position: -16px -176px; }
.ui-icon-signal { background-position: -32px -176px; }
.ui-icon-battery-0 { background-position: -48px -176px; }
.ui-icon-battery-1 { background-position: -64px -176px; }
.ui-icon-battery-2 { background-position: -80px -176px; }
.ui-icon-battery-3 { background-position: -96px -176px; }
.ui-icon-circle-plus { background-position: 0 -192px; }
.ui-icon-circle-minus { background-position: -16px -192px; }
.ui-icon-circle-close { background-position: -32px -192px; }
.ui-icon-circle-triangle-e { background-position: -48px -192px; }
.ui-icon-circle-triangle-s { background-position: -64px -192px; }
.ui-icon-circle-triangle-w { background-position: -80px -192px; }
.ui-icon-circle-triangle-n { background-position: -96px -192px; }
.ui-icon-circle-arrow-e { background-position: -112px -192px; }
.ui-icon-circle-arrow-s { background-position: -128px -192px; }
.ui-icon-circle-arrow-w { background-position: -144px -192px; }
.ui-icon-circle-arrow-n { background-position: -160px -192px; }
.ui-icon-circle-zoomin { background-position: -176px -192px; }
.ui-icon-circle-zoomout { background-position: -192px -192px; }
.ui-icon-circle-check { background-position: -208px -192px; }
.ui-icon-circlesmall-plus { background-position: 0 -208px; }
.ui-icon-circlesmall-minus { background-position: -16px -208px; }
.ui-icon-circlesmall-close { background-position: -32px -208px; }
.ui-icon-squaresmall-plus { background-position: -48px -208px; }
.ui-icon-squaresmall-minus { background-position: -64px -208px; }
.ui-icon-squaresmall-close { background-position: -80px -208px; }
.ui-icon-grip-dotted-vertical { background-position: 0 -224px; }
.ui-icon-grip-dotted-horizontal { background-position: -16px -224px; }
.ui-icon-grip-solid-vertical { background-position: -32px -224px; }
.ui-icon-grip-solid-horizontal { background-position: -48px -224px; }
.ui-icon-gripsmall-diagonal-se { background-position: -64px -224px; }
.ui-icon-grip-diagonal-se { background-position: -80px -224px; }





.ui-corner-all,
.ui-corner-top,
.ui-corner-left,
.ui-corner-tl {
	border-top-left-radius: 3px;
}
.ui-corner-all,
.ui-corner-top,
.ui-corner-right,
.ui-corner-tr {
	border-top-right-radius: 3px;
}
.ui-corner-all,
.ui-corner-bottom,
.ui-corner-left,
.ui-corner-bl {
	border-bottom-left-radius: 3px;
}
.ui-corner-all,
.ui-corner-bottom,
.ui-corner-right,
.ui-corner-br {
	border-bottom-right-radius: 3px;
}


.ui-widget-overlay {
	background: #aaaaaa;
	opacity: .3;
	filter: Alpha(Opacity=30); 
}
.ui-widget-shadow {
	-webkit-box-shadow: 0px 0px 5px #666666;
	box-shadow: 0px 0px 5px #666666;
} 
</style>
<script src='js/jquery-1.12.4.js'></script>
<script src='js/jquery-ui.js'></script>

<script>
$( function() {
	$( '#tabs-collect-classes-from-hierarchical-partition' ).tabs();
} );
</script>
<div id='tabs-collect-classes-from-hierarchical-partition'>
<ul>
<li><a href='#tab-collect-classes-from-hierarchical-partition-1'>n_signatures ??? 2846</a></li>
<li><a href='#tab-collect-classes-from-hierarchical-partition-2'>n_signatures ??? 5127</a></li>
<li><a href='#tab-collect-classes-from-hierarchical-partition-3'>n_signatures ??? 7052</a></li>
<li><a href='#tab-collect-classes-from-hierarchical-partition-4'>n_signatures ??? 9534</a></li>
<li><a href='#tab-collect-classes-from-hierarchical-partition-5'>n_signatures ??? 18548</a></li>
<li><a href='#tab-collect-classes-from-hierarchical-partition-6'>n_signatures ??? 52459</a></li>
<li><a href='#tab-collect-classes-from-hierarchical-partition-7'>n_signatures ??? 66872</a></li>
<li><a href='#tab-collect-classes-from-hierarchical-partition-8'>n_signatures ??? 191928</a></li>
</ul>
<div id='tab-collect-classes-from-hierarchical-partition-1'>
<pre><code class="r">collect_classes(res_rh, merge_node = merge_node_param(min_n_signatures = 2846))
</code></pre>

<p><img src="figure_cola/tab-collect-classes-from-hierarchical-partition-1-1.png" alt="plot of chunk tab-collect-classes-from-hierarchical-partition-1"/></p>

</div>
<div id='tab-collect-classes-from-hierarchical-partition-2'>
<pre><code class="r">collect_classes(res_rh, merge_node = merge_node_param(min_n_signatures = 5127))
</code></pre>

<p><img src="figure_cola/tab-collect-classes-from-hierarchical-partition-2-1.png" alt="plot of chunk tab-collect-classes-from-hierarchical-partition-2"/></p>

</div>
<div id='tab-collect-classes-from-hierarchical-partition-3'>
<pre><code class="r">collect_classes(res_rh, merge_node = merge_node_param(min_n_signatures = 7052))
</code></pre>

<p><img src="figure_cola/tab-collect-classes-from-hierarchical-partition-3-1.png" alt="plot of chunk tab-collect-classes-from-hierarchical-partition-3"/></p>

</div>
<div id='tab-collect-classes-from-hierarchical-partition-4'>
<pre><code class="r">collect_classes(res_rh, merge_node = merge_node_param(min_n_signatures = 9534))
</code></pre>

<p><img src="figure_cola/tab-collect-classes-from-hierarchical-partition-4-1.png" alt="plot of chunk tab-collect-classes-from-hierarchical-partition-4"/></p>

</div>
<div id='tab-collect-classes-from-hierarchical-partition-5'>
<pre><code class="r">collect_classes(res_rh, merge_node = merge_node_param(min_n_signatures = 18548))
</code></pre>

<p><img src="figure_cola/tab-collect-classes-from-hierarchical-partition-5-1.png" alt="plot of chunk tab-collect-classes-from-hierarchical-partition-5"/></p>

</div>
<div id='tab-collect-classes-from-hierarchical-partition-6'>
<pre><code class="r">collect_classes(res_rh, merge_node = merge_node_param(min_n_signatures = 52459))
</code></pre>

<p><img src="figure_cola/tab-collect-classes-from-hierarchical-partition-6-1.png" alt="plot of chunk tab-collect-classes-from-hierarchical-partition-6"/></p>

</div>
<div id='tab-collect-classes-from-hierarchical-partition-7'>
<pre><code class="r">collect_classes(res_rh, merge_node = merge_node_param(min_n_signatures = 66872))
</code></pre>

<p><img src="figure_cola/tab-collect-classes-from-hierarchical-partition-7-1.png" alt="plot of chunk tab-collect-classes-from-hierarchical-partition-7"/></p>

</div>
<div id='tab-collect-classes-from-hierarchical-partition-8'>
<pre><code class="r">collect_classes(res_rh, merge_node = merge_node_param(min_n_signatures = 191928))
</code></pre>

<p><img src="figure_cola/tab-collect-classes-from-hierarchical-partition-8-1.png" alt="plot of chunk tab-collect-classes-from-hierarchical-partition-8"/></p>

</div>
</div>

Following shows the table of the partitions (You need to click the **show/hide
code output** link to see it).


<script>
$( function() {
	$( '#tabs-get-classes-from-hierarchical-partition' ).tabs();
} );
</script>
<div id='tabs-get-classes-from-hierarchical-partition'>
<ul>
<li><a href='#tab-get-classes-from-hierarchical-partition-1'>n_signatures ??? 2846</a></li>
<li><a href='#tab-get-classes-from-hierarchical-partition-2'>n_signatures ??? 5127</a></li>
<li><a href='#tab-get-classes-from-hierarchical-partition-3'>n_signatures ??? 7052</a></li>
<li><a href='#tab-get-classes-from-hierarchical-partition-4'>n_signatures ??? 9534</a></li>
<li><a href='#tab-get-classes-from-hierarchical-partition-5'>n_signatures ??? 18548</a></li>
<li><a href='#tab-get-classes-from-hierarchical-partition-6'>n_signatures ??? 52459</a></li>
<li><a href='#tab-get-classes-from-hierarchical-partition-7'>n_signatures ??? 66872</a></li>
<li><a href='#tab-get-classes-from-hierarchical-partition-8'>n_signatures ??? 191928</a></li>
</ul>

<div id='tab-get-classes-from-hierarchical-partition-1'>
<p><a id='tab-get-classes-from-hierarchical-partition-1-a' style='color:#0366d6' href='#'>show/hide code output</a></p>
<pre><code class="r">get_classes(res_rh, merge_node = merge_node_param(min_n_signatures = 2846))
</code></pre>

<pre><code>#&gt; TCGA.XE.A8H4.01 TCGA.2G.AAF1.01 TCGA.W4.A7U4.01 TCGA.2G.AAGO.01 TCGA.VF.A8AC.01 TCGA.2G.AALX.01 
#&gt;           &quot;011&quot;           &quot;011&quot;          &quot;0243&quot;          &quot;0243&quot;           &quot;011&quot;          &quot;0221&quot; 
#&gt; TCGA.2G.AAGK.01 TCGA.2G.AAGG.01 TCGA.2G.AAGP.01 TCGA.2G.AAKM.01 TCGA.ZM.AA0E.01 TCGA.XE.A9SE.01 
#&gt;           &quot;021&quot;          &quot;0223&quot;          &quot;0231&quot;          &quot;0243&quot;           &quot;011&quot;           &quot;013&quot; 
#&gt; TCGA.2G.AAKO.05 TCGA.2G.AAFY.01 TCGA.XE.AANI.01 TCGA.YU.AA4L.01 TCGA.2G.AAGI.05 TCGA.XE.AANV.01 
#&gt;           &quot;011&quot;           &quot;021&quot;          &quot;0221&quot;          &quot;0222&quot;           &quot;011&quot;           &quot;032&quot; 
#&gt; TCGA.YU.A90S.01 TCGA.XY.A89B.01 TCGA.ZM.AA05.01 TCGA.2G.AAHA.01 TCGA.2G.AAH2.01 TCGA.2G.AAG6.01 
#&gt;           &quot;011&quot;           &quot;011&quot;           &quot;011&quot;           &quot;032&quot;          &quot;0223&quot;          &quot;0221&quot; 
#&gt; TCGA.2G.AAG0.01 TCGA.WZ.A7V3.01 TCGA.2G.AALO.01 TCGA.ZM.AA0F.01 TCGA.XE.A8H5.01 TCGA.XE.AANJ.01 
#&gt;           &quot;021&quot;           &quot;034&quot;          &quot;0223&quot;           &quot;011&quot;           &quot;031&quot;          &quot;0122&quot; 
#&gt; TCGA.YU.A94I.01 TCGA.SO.A8JP.01 TCGA.2G.AAM4.01 TCGA.WZ.A7V5.01 TCGA.YU.A90Y.01 TCGA.2G.AALZ.01 
#&gt;          &quot;0222&quot;           &quot;031&quot;           &quot;021&quot;           &quot;011&quot;          &quot;0233&quot;          &quot;0221&quot; 
#&gt; TCGA.WZ.A8D5.01 TCGA.2G.AAGA.01 TCGA.2G.AALY.01 TCGA.2G.AAKG.01 TCGA.2G.AAL5.01 TCGA.YU.A94D.01 
#&gt;           &quot;011&quot;          &quot;0241&quot;          &quot;0234&quot;          &quot;0233&quot;          &quot;0224&quot;          &quot;0224&quot; 
#&gt; TCGA.XE.AAOL.01 TCGA.SN.A84X.01 TCGA.2G.AAHC.01 TCGA.2G.AAHT.01 TCGA.2G.AALT.01 TCGA.2G.AAM2.01 
#&gt;           &quot;031&quot;          &quot;0232&quot;           &quot;013&quot;           &quot;032&quot;          &quot;0223&quot;          &quot;0242&quot; 
#&gt; TCGA.2G.AAFH.01 TCGA.2G.AAFI.01 TCGA.2G.AAHN.01 TCGA.2G.AAGT.01 TCGA.YU.A90W.01 TCGA.2G.AAGJ.01 
#&gt;           &quot;013&quot;           &quot;021&quot;           &quot;011&quot;          &quot;0222&quot;           &quot;034&quot;           &quot;021&quot; 
#&gt; TCGA.2G.AAGV.01 TCGA.XE.A8H1.01 TCGA.2G.AAFJ.01 TCGA.2G.AAG5.01 TCGA.X3.A8G4.01 TCGA.2G.AAGY.01 
#&gt;          &quot;0223&quot;           &quot;021&quot;          &quot;0221&quot;          &quot;0221&quot;          &quot;0233&quot;          &quot;0221&quot; 
#&gt; TCGA.2G.AAG8.01 TCGA.S6.A8JW.01 TCGA.2G.AAEW.01 TCGA.2G.AAFO.01 TCGA.YU.A912.01 TCGA.2G.AAM3.01 
#&gt;           &quot;021&quot;           &quot;033&quot;           &quot;032&quot;           &quot;021&quot;           &quot;033&quot;          &quot;0223&quot; 
#&gt; TCGA.VF.A8A8.01 TCGA.SN.A84W.01 TCGA.XE.AAO4.01 TCGA.ZM.AA0N.01 TCGA.VF.A8AE.01 TCGA.2G.AAFZ.01 
#&gt;          &quot;0242&quot;          &quot;0221&quot;           &quot;011&quot;           &quot;013&quot;           &quot;013&quot;          &quot;0221&quot; 
#&gt; TCGA.2G.AAGM.01 TCGA.2G.AAKH.01 TCGA.2G.AAF6.01 TCGA.4K.AA1I.01 TCGA.2G.AAFL.01 TCGA.XY.A9T9.01 
#&gt;          &quot;0224&quot;           &quot;021&quot;          &quot;0122&quot;           &quot;011&quot;           &quot;021&quot;          &quot;0121&quot; 
#&gt; TCGA.WZ.A7V4.01 TCGA.S6.A8JX.01 TCGA.2G.AAHL.01 TCGA.4K.AA1H.01 TCGA.ZM.AA06.01 TCGA.VF.A8A9.01 
#&gt;           &quot;011&quot;           &quot;031&quot;           &quot;034&quot;           &quot;011&quot;          &quot;0122&quot;           &quot;013&quot; 
#&gt; TCGA.4K.AA1G.01 TCGA.2G.AAFE.01 TCGA.ZM.AA0H.01 TCGA.2G.AAKG.05 TCGA.ZM.AA0B.01 TCGA.2G.AALP.01 
#&gt;           &quot;033&quot;           &quot;032&quot;           &quot;011&quot;          &quot;0231&quot;          &quot;0121&quot;           &quot;021&quot; 
#&gt; TCGA.YU.A90P.01 TCGA.2G.AAGS.01 TCGA.W4.A7U3.01 TCGA.SN.A6IS.01 TCGA.2G.AAGF.01 TCGA.2G.AAGE.01 
#&gt;           &quot;021&quot;          &quot;0234&quot;          &quot;0223&quot;          &quot;0122&quot;           &quot;021&quot;           &quot;021&quot; 
#&gt; TCGA.2G.AAGY.05 TCGA.2G.AAKL.01 TCGA.2G.AAF8.01 TCGA.2G.AALW.01 TCGA.XE.AAOB.01 TCGA.2G.AAF4.01 
#&gt;           &quot;031&quot;          &quot;0241&quot;           &quot;013&quot;          &quot;0223&quot;          &quot;0231&quot;          &quot;0121&quot; 
#&gt; TCGA.XE.AAOC.01 TCGA.XE.AANR.01 TCGA.2G.AAFG.05 TCGA.2G.AALS.01 TCGA.2G.AAG3.01 TCGA.2G.AALN.01 
#&gt;          &quot;0221&quot;          &quot;0232&quot;           &quot;013&quot;          &quot;0231&quot;          &quot;0223&quot;          &quot;0234&quot; 
#&gt; TCGA.ZM.AA0D.01 TCGA.2G.AAG9.01 TCGA.2G.AAGC.01 TCGA.2X.A9D6.01 TCGA.4K.AAAL.01 TCGA.SN.A84Y.01 
#&gt;           &quot;011&quot;           &quot;032&quot;          &quot;0233&quot;           &quot;011&quot;           &quot;032&quot;          &quot;0241&quot; 
#&gt; TCGA.VF.A8AA.01 TCGA.2G.AAH3.01 TCGA.YU.A90Q.01 TCGA.2G.AAKO.01 TCGA.2G.AAGZ.01 TCGA.VF.A8AB.01 
#&gt;           &quot;011&quot;          &quot;0122&quot;           &quot;031&quot;           &quot;011&quot;          &quot;0231&quot;           &quot;013&quot; 
#&gt; TCGA.2G.AALF.01 TCGA.2G.AAL7.01 TCGA.2G.AALQ.01 TCGA.2G.AAFN.01 TCGA.2G.AAFG.01 TCGA.2G.AAGN.01 
#&gt;          &quot;0222&quot;          &quot;0243&quot;          &quot;0224&quot;          &quot;0241&quot;           &quot;013&quot;           &quot;021&quot; 
#&gt; TCGA.XE.AAOD.01 TCGA.XE.AAOF.01 TCGA.XY.A8S3.01 TCGA.2G.AAFV.01 TCGA.2G.AAHP.05 TCGA.2G.AAH4.01 
#&gt;           &quot;013&quot;           &quot;011&quot;           &quot;021&quot;          &quot;0222&quot;           &quot;011&quot;          &quot;0221&quot; 
#&gt; TCGA.XE.AAO3.01 TCGA.SB.A76C.01 TCGA.2G.AAHG.01 TCGA.XE.AAO6.01 TCGA.SB.A6J6.01 TCGA.YU.AA61.01 
#&gt;          &quot;0123&quot;           &quot;033&quot;           &quot;033&quot;          &quot;0122&quot;          &quot;0121&quot;          &quot;0223&quot; 
#&gt; TCGA.2G.AAG7.01 TCGA.XY.A8S2.01 TCGA.2G.AAEX.01 TCGA.2G.AAH0.01 TCGA.2G.AAKD.01 TCGA.VF.A8AD.01 
#&gt;          &quot;0242&quot;          &quot;0241&quot;          &quot;0121&quot;          &quot;0121&quot;          &quot;0242&quot;           &quot;021&quot; 
#&gt; TCGA.2G.AALR.01 TCGA.2G.AAFM.01 TCGA.2G.AALG.01 TCGA.XE.AAOJ.01 TCGA.2G.AAGI.01 TCGA.W4.A7U2.01 
#&gt;          &quot;0224&quot;           &quot;021&quot;          &quot;0223&quot;          &quot;0224&quot;          &quot;0223&quot;          &quot;0122&quot; 
#&gt; TCGA.S6.A8JY.01 TCGA.2G.AAH8.01 TCGA.2G.AAHP.01 TCGA.2G.AAGW.01 TCGA.2X.A9D5.01 TCGA.2G.AAGX.01 
#&gt;           &quot;031&quot;           &quot;031&quot;          &quot;0123&quot;          &quot;0242&quot;          &quot;0121&quot;          &quot;0223&quot;
</code></pre>

<script>
$('#tab-get-classes-from-hierarchical-partition-1-a').parent().next().next().hide();
$('#tab-get-classes-from-hierarchical-partition-1-a').click(function(){
  $('#tab-get-classes-from-hierarchical-partition-1-a').parent().next().next().toggle();
  return(false);
});
</script>
</div>

<div id='tab-get-classes-from-hierarchical-partition-2'>
<p><a id='tab-get-classes-from-hierarchical-partition-2-a' style='color:#0366d6' href='#'>show/hide code output</a></p>
<pre><code class="r">get_classes(res_rh, merge_node = merge_node_param(min_n_signatures = 5127))
</code></pre>

<pre><code>#&gt; TCGA.XE.A8H4.01 TCGA.2G.AAF1.01 TCGA.W4.A7U4.01 TCGA.2G.AAGO.01 TCGA.VF.A8AC.01 TCGA.2G.AALX.01 
#&gt;           &quot;011&quot;           &quot;011&quot;          &quot;0243&quot;          &quot;0243&quot;           &quot;011&quot;          &quot;0221&quot; 
#&gt; TCGA.2G.AAGK.01 TCGA.2G.AAGG.01 TCGA.2G.AAGP.01 TCGA.2G.AAKM.01 TCGA.ZM.AA0E.01 TCGA.XE.A9SE.01 
#&gt;           &quot;021&quot;          &quot;0223&quot;          &quot;0231&quot;          &quot;0243&quot;           &quot;011&quot;           &quot;013&quot; 
#&gt; TCGA.2G.AAKO.05 TCGA.2G.AAFY.01 TCGA.XE.AANI.01 TCGA.YU.AA4L.01 TCGA.2G.AAGI.05 TCGA.XE.AANV.01 
#&gt;           &quot;011&quot;           &quot;021&quot;          &quot;0221&quot;          &quot;0222&quot;           &quot;011&quot;            &quot;03&quot; 
#&gt; TCGA.YU.A90S.01 TCGA.XY.A89B.01 TCGA.ZM.AA05.01 TCGA.2G.AAHA.01 TCGA.2G.AAH2.01 TCGA.2G.AAG6.01 
#&gt;           &quot;011&quot;           &quot;011&quot;           &quot;011&quot;            &quot;03&quot;          &quot;0223&quot;          &quot;0221&quot; 
#&gt; TCGA.2G.AAG0.01 TCGA.WZ.A7V3.01 TCGA.2G.AALO.01 TCGA.ZM.AA0F.01 TCGA.XE.A8H5.01 TCGA.XE.AANJ.01 
#&gt;           &quot;021&quot;            &quot;03&quot;          &quot;0223&quot;           &quot;011&quot;            &quot;03&quot;          &quot;0122&quot; 
#&gt; TCGA.YU.A94I.01 TCGA.SO.A8JP.01 TCGA.2G.AAM4.01 TCGA.WZ.A7V5.01 TCGA.YU.A90Y.01 TCGA.2G.AALZ.01 
#&gt;          &quot;0222&quot;            &quot;03&quot;           &quot;021&quot;           &quot;011&quot;          &quot;0233&quot;          &quot;0221&quot; 
#&gt; TCGA.WZ.A8D5.01 TCGA.2G.AAGA.01 TCGA.2G.AALY.01 TCGA.2G.AAKG.01 TCGA.2G.AAL5.01 TCGA.YU.A94D.01 
#&gt;           &quot;011&quot;          &quot;0241&quot;          &quot;0234&quot;          &quot;0233&quot;          &quot;0224&quot;          &quot;0224&quot; 
#&gt; TCGA.XE.AAOL.01 TCGA.SN.A84X.01 TCGA.2G.AAHC.01 TCGA.2G.AAHT.01 TCGA.2G.AALT.01 TCGA.2G.AAM2.01 
#&gt;            &quot;03&quot;          &quot;0232&quot;           &quot;013&quot;            &quot;03&quot;          &quot;0223&quot;          &quot;0242&quot; 
#&gt; TCGA.2G.AAFH.01 TCGA.2G.AAFI.01 TCGA.2G.AAHN.01 TCGA.2G.AAGT.01 TCGA.YU.A90W.01 TCGA.2G.AAGJ.01 
#&gt;           &quot;013&quot;           &quot;021&quot;           &quot;011&quot;          &quot;0222&quot;            &quot;03&quot;           &quot;021&quot; 
#&gt; TCGA.2G.AAGV.01 TCGA.XE.A8H1.01 TCGA.2G.AAFJ.01 TCGA.2G.AAG5.01 TCGA.X3.A8G4.01 TCGA.2G.AAGY.01 
#&gt;          &quot;0223&quot;           &quot;021&quot;          &quot;0221&quot;          &quot;0221&quot;          &quot;0233&quot;          &quot;0221&quot; 
#&gt; TCGA.2G.AAG8.01 TCGA.S6.A8JW.01 TCGA.2G.AAEW.01 TCGA.2G.AAFO.01 TCGA.YU.A912.01 TCGA.2G.AAM3.01 
#&gt;           &quot;021&quot;            &quot;03&quot;            &quot;03&quot;           &quot;021&quot;            &quot;03&quot;          &quot;0223&quot; 
#&gt; TCGA.VF.A8A8.01 TCGA.SN.A84W.01 TCGA.XE.AAO4.01 TCGA.ZM.AA0N.01 TCGA.VF.A8AE.01 TCGA.2G.AAFZ.01 
#&gt;          &quot;0242&quot;          &quot;0221&quot;           &quot;011&quot;           &quot;013&quot;           &quot;013&quot;          &quot;0221&quot; 
#&gt; TCGA.2G.AAGM.01 TCGA.2G.AAKH.01 TCGA.2G.AAF6.01 TCGA.4K.AA1I.01 TCGA.2G.AAFL.01 TCGA.XY.A9T9.01 
#&gt;          &quot;0224&quot;           &quot;021&quot;          &quot;0122&quot;           &quot;011&quot;           &quot;021&quot;          &quot;0121&quot; 
#&gt; TCGA.WZ.A7V4.01 TCGA.S6.A8JX.01 TCGA.2G.AAHL.01 TCGA.4K.AA1H.01 TCGA.ZM.AA06.01 TCGA.VF.A8A9.01 
#&gt;           &quot;011&quot;            &quot;03&quot;            &quot;03&quot;           &quot;011&quot;          &quot;0122&quot;           &quot;013&quot; 
#&gt; TCGA.4K.AA1G.01 TCGA.2G.AAFE.01 TCGA.ZM.AA0H.01 TCGA.2G.AAKG.05 TCGA.ZM.AA0B.01 TCGA.2G.AALP.01 
#&gt;            &quot;03&quot;            &quot;03&quot;           &quot;011&quot;          &quot;0231&quot;          &quot;0121&quot;           &quot;021&quot; 
#&gt; TCGA.YU.A90P.01 TCGA.2G.AAGS.01 TCGA.W4.A7U3.01 TCGA.SN.A6IS.01 TCGA.2G.AAGF.01 TCGA.2G.AAGE.01 
#&gt;           &quot;021&quot;          &quot;0234&quot;          &quot;0223&quot;          &quot;0122&quot;           &quot;021&quot;           &quot;021&quot; 
#&gt; TCGA.2G.AAGY.05 TCGA.2G.AAKL.01 TCGA.2G.AAF8.01 TCGA.2G.AALW.01 TCGA.XE.AAOB.01 TCGA.2G.AAF4.01 
#&gt;            &quot;03&quot;          &quot;0241&quot;           &quot;013&quot;          &quot;0223&quot;          &quot;0231&quot;          &quot;0121&quot; 
#&gt; TCGA.XE.AAOC.01 TCGA.XE.AANR.01 TCGA.2G.AAFG.05 TCGA.2G.AALS.01 TCGA.2G.AAG3.01 TCGA.2G.AALN.01 
#&gt;          &quot;0221&quot;          &quot;0232&quot;           &quot;013&quot;          &quot;0231&quot;          &quot;0223&quot;          &quot;0234&quot; 
#&gt; TCGA.ZM.AA0D.01 TCGA.2G.AAG9.01 TCGA.2G.AAGC.01 TCGA.2X.A9D6.01 TCGA.4K.AAAL.01 TCGA.SN.A84Y.01 
#&gt;           &quot;011&quot;            &quot;03&quot;          &quot;0233&quot;           &quot;011&quot;            &quot;03&quot;          &quot;0241&quot; 
#&gt; TCGA.VF.A8AA.01 TCGA.2G.AAH3.01 TCGA.YU.A90Q.01 TCGA.2G.AAKO.01 TCGA.2G.AAGZ.01 TCGA.VF.A8AB.01 
#&gt;           &quot;011&quot;          &quot;0122&quot;            &quot;03&quot;           &quot;011&quot;          &quot;0231&quot;           &quot;013&quot; 
#&gt; TCGA.2G.AALF.01 TCGA.2G.AAL7.01 TCGA.2G.AALQ.01 TCGA.2G.AAFN.01 TCGA.2G.AAFG.01 TCGA.2G.AAGN.01 
#&gt;          &quot;0222&quot;          &quot;0243&quot;          &quot;0224&quot;          &quot;0241&quot;           &quot;013&quot;           &quot;021&quot; 
#&gt; TCGA.XE.AAOD.01 TCGA.XE.AAOF.01 TCGA.XY.A8S3.01 TCGA.2G.AAFV.01 TCGA.2G.AAHP.05 TCGA.2G.AAH4.01 
#&gt;           &quot;013&quot;           &quot;011&quot;           &quot;021&quot;          &quot;0222&quot;           &quot;011&quot;          &quot;0221&quot; 
#&gt; TCGA.XE.AAO3.01 TCGA.SB.A76C.01 TCGA.2G.AAHG.01 TCGA.XE.AAO6.01 TCGA.SB.A6J6.01 TCGA.YU.AA61.01 
#&gt;          &quot;0123&quot;            &quot;03&quot;            &quot;03&quot;          &quot;0122&quot;          &quot;0121&quot;          &quot;0223&quot; 
#&gt; TCGA.2G.AAG7.01 TCGA.XY.A8S2.01 TCGA.2G.AAEX.01 TCGA.2G.AAH0.01 TCGA.2G.AAKD.01 TCGA.VF.A8AD.01 
#&gt;          &quot;0242&quot;          &quot;0241&quot;          &quot;0121&quot;          &quot;0121&quot;          &quot;0242&quot;           &quot;021&quot; 
#&gt; TCGA.2G.AALR.01 TCGA.2G.AAFM.01 TCGA.2G.AALG.01 TCGA.XE.AAOJ.01 TCGA.2G.AAGI.01 TCGA.W4.A7U2.01 
#&gt;          &quot;0224&quot;           &quot;021&quot;          &quot;0223&quot;          &quot;0224&quot;          &quot;0223&quot;          &quot;0122&quot; 
#&gt; TCGA.S6.A8JY.01 TCGA.2G.AAH8.01 TCGA.2G.AAHP.01 TCGA.2G.AAGW.01 TCGA.2X.A9D5.01 TCGA.2G.AAGX.01 
#&gt;            &quot;03&quot;            &quot;03&quot;          &quot;0123&quot;          &quot;0242&quot;          &quot;0121&quot;          &quot;0223&quot;
</code></pre>

<script>
$('#tab-get-classes-from-hierarchical-partition-2-a').parent().next().next().hide();
$('#tab-get-classes-from-hierarchical-partition-2-a').click(function(){
  $('#tab-get-classes-from-hierarchical-partition-2-a').parent().next().next().toggle();
  return(false);
});
</script>
</div>

<div id='tab-get-classes-from-hierarchical-partition-3'>
<p><a id='tab-get-classes-from-hierarchical-partition-3-a' style='color:#0366d6' href='#'>show/hide code output</a></p>
<pre><code class="r">get_classes(res_rh, merge_node = merge_node_param(min_n_signatures = 7052))
</code></pre>

<pre><code>#&gt; TCGA.XE.A8H4.01 TCGA.2G.AAF1.01 TCGA.W4.A7U4.01 TCGA.2G.AAGO.01 TCGA.VF.A8AC.01 TCGA.2G.AALX.01 
#&gt;           &quot;011&quot;           &quot;011&quot;           &quot;024&quot;           &quot;024&quot;           &quot;011&quot;          &quot;0221&quot; 
#&gt; TCGA.2G.AAGK.01 TCGA.2G.AAGG.01 TCGA.2G.AAGP.01 TCGA.2G.AAKM.01 TCGA.ZM.AA0E.01 TCGA.XE.A9SE.01 
#&gt;           &quot;021&quot;          &quot;0223&quot;          &quot;0231&quot;           &quot;024&quot;           &quot;011&quot;           &quot;013&quot; 
#&gt; TCGA.2G.AAKO.05 TCGA.2G.AAFY.01 TCGA.XE.AANI.01 TCGA.YU.AA4L.01 TCGA.2G.AAGI.05 TCGA.XE.AANV.01 
#&gt;           &quot;011&quot;           &quot;021&quot;          &quot;0221&quot;          &quot;0222&quot;           &quot;011&quot;            &quot;03&quot; 
#&gt; TCGA.YU.A90S.01 TCGA.XY.A89B.01 TCGA.ZM.AA05.01 TCGA.2G.AAHA.01 TCGA.2G.AAH2.01 TCGA.2G.AAG6.01 
#&gt;           &quot;011&quot;           &quot;011&quot;           &quot;011&quot;            &quot;03&quot;          &quot;0223&quot;          &quot;0221&quot; 
#&gt; TCGA.2G.AAG0.01 TCGA.WZ.A7V3.01 TCGA.2G.AALO.01 TCGA.ZM.AA0F.01 TCGA.XE.A8H5.01 TCGA.XE.AANJ.01 
#&gt;           &quot;021&quot;            &quot;03&quot;          &quot;0223&quot;           &quot;011&quot;            &quot;03&quot;          &quot;0122&quot; 
#&gt; TCGA.YU.A94I.01 TCGA.SO.A8JP.01 TCGA.2G.AAM4.01 TCGA.WZ.A7V5.01 TCGA.YU.A90Y.01 TCGA.2G.AALZ.01 
#&gt;          &quot;0222&quot;            &quot;03&quot;           &quot;021&quot;           &quot;011&quot;          &quot;0233&quot;          &quot;0221&quot; 
#&gt; TCGA.WZ.A8D5.01 TCGA.2G.AAGA.01 TCGA.2G.AALY.01 TCGA.2G.AAKG.01 TCGA.2G.AAL5.01 TCGA.YU.A94D.01 
#&gt;           &quot;011&quot;           &quot;024&quot;          &quot;0234&quot;          &quot;0233&quot;          &quot;0224&quot;          &quot;0224&quot; 
#&gt; TCGA.XE.AAOL.01 TCGA.SN.A84X.01 TCGA.2G.AAHC.01 TCGA.2G.AAHT.01 TCGA.2G.AALT.01 TCGA.2G.AAM2.01 
#&gt;            &quot;03&quot;          &quot;0232&quot;           &quot;013&quot;            &quot;03&quot;          &quot;0223&quot;           &quot;024&quot; 
#&gt; TCGA.2G.AAFH.01 TCGA.2G.AAFI.01 TCGA.2G.AAHN.01 TCGA.2G.AAGT.01 TCGA.YU.A90W.01 TCGA.2G.AAGJ.01 
#&gt;           &quot;013&quot;           &quot;021&quot;           &quot;011&quot;          &quot;0222&quot;            &quot;03&quot;           &quot;021&quot; 
#&gt; TCGA.2G.AAGV.01 TCGA.XE.A8H1.01 TCGA.2G.AAFJ.01 TCGA.2G.AAG5.01 TCGA.X3.A8G4.01 TCGA.2G.AAGY.01 
#&gt;          &quot;0223&quot;           &quot;021&quot;          &quot;0221&quot;          &quot;0221&quot;          &quot;0233&quot;          &quot;0221&quot; 
#&gt; TCGA.2G.AAG8.01 TCGA.S6.A8JW.01 TCGA.2G.AAEW.01 TCGA.2G.AAFO.01 TCGA.YU.A912.01 TCGA.2G.AAM3.01 
#&gt;           &quot;021&quot;            &quot;03&quot;            &quot;03&quot;           &quot;021&quot;            &quot;03&quot;          &quot;0223&quot; 
#&gt; TCGA.VF.A8A8.01 TCGA.SN.A84W.01 TCGA.XE.AAO4.01 TCGA.ZM.AA0N.01 TCGA.VF.A8AE.01 TCGA.2G.AAFZ.01 
#&gt;           &quot;024&quot;          &quot;0221&quot;           &quot;011&quot;           &quot;013&quot;           &quot;013&quot;          &quot;0221&quot; 
#&gt; TCGA.2G.AAGM.01 TCGA.2G.AAKH.01 TCGA.2G.AAF6.01 TCGA.4K.AA1I.01 TCGA.2G.AAFL.01 TCGA.XY.A9T9.01 
#&gt;          &quot;0224&quot;           &quot;021&quot;          &quot;0122&quot;           &quot;011&quot;           &quot;021&quot;          &quot;0121&quot; 
#&gt; TCGA.WZ.A7V4.01 TCGA.S6.A8JX.01 TCGA.2G.AAHL.01 TCGA.4K.AA1H.01 TCGA.ZM.AA06.01 TCGA.VF.A8A9.01 
#&gt;           &quot;011&quot;            &quot;03&quot;            &quot;03&quot;           &quot;011&quot;          &quot;0122&quot;           &quot;013&quot; 
#&gt; TCGA.4K.AA1G.01 TCGA.2G.AAFE.01 TCGA.ZM.AA0H.01 TCGA.2G.AAKG.05 TCGA.ZM.AA0B.01 TCGA.2G.AALP.01 
#&gt;            &quot;03&quot;            &quot;03&quot;           &quot;011&quot;          &quot;0231&quot;          &quot;0121&quot;           &quot;021&quot; 
#&gt; TCGA.YU.A90P.01 TCGA.2G.AAGS.01 TCGA.W4.A7U3.01 TCGA.SN.A6IS.01 TCGA.2G.AAGF.01 TCGA.2G.AAGE.01 
#&gt;           &quot;021&quot;          &quot;0234&quot;          &quot;0223&quot;          &quot;0122&quot;           &quot;021&quot;           &quot;021&quot; 
#&gt; TCGA.2G.AAGY.05 TCGA.2G.AAKL.01 TCGA.2G.AAF8.01 TCGA.2G.AALW.01 TCGA.XE.AAOB.01 TCGA.2G.AAF4.01 
#&gt;            &quot;03&quot;           &quot;024&quot;           &quot;013&quot;          &quot;0223&quot;          &quot;0231&quot;          &quot;0121&quot; 
#&gt; TCGA.XE.AAOC.01 TCGA.XE.AANR.01 TCGA.2G.AAFG.05 TCGA.2G.AALS.01 TCGA.2G.AAG3.01 TCGA.2G.AALN.01 
#&gt;          &quot;0221&quot;          &quot;0232&quot;           &quot;013&quot;          &quot;0231&quot;          &quot;0223&quot;          &quot;0234&quot; 
#&gt; TCGA.ZM.AA0D.01 TCGA.2G.AAG9.01 TCGA.2G.AAGC.01 TCGA.2X.A9D6.01 TCGA.4K.AAAL.01 TCGA.SN.A84Y.01 
#&gt;           &quot;011&quot;            &quot;03&quot;          &quot;0233&quot;           &quot;011&quot;            &quot;03&quot;           &quot;024&quot; 
#&gt; TCGA.VF.A8AA.01 TCGA.2G.AAH3.01 TCGA.YU.A90Q.01 TCGA.2G.AAKO.01 TCGA.2G.AAGZ.01 TCGA.VF.A8AB.01 
#&gt;           &quot;011&quot;          &quot;0122&quot;            &quot;03&quot;           &quot;011&quot;          &quot;0231&quot;           &quot;013&quot; 
#&gt; TCGA.2G.AALF.01 TCGA.2G.AAL7.01 TCGA.2G.AALQ.01 TCGA.2G.AAFN.01 TCGA.2G.AAFG.01 TCGA.2G.AAGN.01 
#&gt;          &quot;0222&quot;           &quot;024&quot;          &quot;0224&quot;           &quot;024&quot;           &quot;013&quot;           &quot;021&quot; 
#&gt; TCGA.XE.AAOD.01 TCGA.XE.AAOF.01 TCGA.XY.A8S3.01 TCGA.2G.AAFV.01 TCGA.2G.AAHP.05 TCGA.2G.AAH4.01 
#&gt;           &quot;013&quot;           &quot;011&quot;           &quot;021&quot;          &quot;0222&quot;           &quot;011&quot;          &quot;0221&quot; 
#&gt; TCGA.XE.AAO3.01 TCGA.SB.A76C.01 TCGA.2G.AAHG.01 TCGA.XE.AAO6.01 TCGA.SB.A6J6.01 TCGA.YU.AA61.01 
#&gt;          &quot;0123&quot;            &quot;03&quot;            &quot;03&quot;          &quot;0122&quot;          &quot;0121&quot;          &quot;0223&quot; 
#&gt; TCGA.2G.AAG7.01 TCGA.XY.A8S2.01 TCGA.2G.AAEX.01 TCGA.2G.AAH0.01 TCGA.2G.AAKD.01 TCGA.VF.A8AD.01 
#&gt;           &quot;024&quot;           &quot;024&quot;          &quot;0121&quot;          &quot;0121&quot;           &quot;024&quot;           &quot;021&quot; 
#&gt; TCGA.2G.AALR.01 TCGA.2G.AAFM.01 TCGA.2G.AALG.01 TCGA.XE.AAOJ.01 TCGA.2G.AAGI.01 TCGA.W4.A7U2.01 
#&gt;          &quot;0224&quot;           &quot;021&quot;          &quot;0223&quot;          &quot;0224&quot;          &quot;0223&quot;          &quot;0122&quot; 
#&gt; TCGA.S6.A8JY.01 TCGA.2G.AAH8.01 TCGA.2G.AAHP.01 TCGA.2G.AAGW.01 TCGA.2X.A9D5.01 TCGA.2G.AAGX.01 
#&gt;            &quot;03&quot;            &quot;03&quot;          &quot;0123&quot;           &quot;024&quot;          &quot;0121&quot;          &quot;0223&quot;
</code></pre>

<script>
$('#tab-get-classes-from-hierarchical-partition-3-a').parent().next().next().hide();
$('#tab-get-classes-from-hierarchical-partition-3-a').click(function(){
  $('#tab-get-classes-from-hierarchical-partition-3-a').parent().next().next().toggle();
  return(false);
});
</script>
</div>

<div id='tab-get-classes-from-hierarchical-partition-4'>
<p><a id='tab-get-classes-from-hierarchical-partition-4-a' style='color:#0366d6' href='#'>show/hide code output</a></p>
<pre><code class="r">get_classes(res_rh, merge_node = merge_node_param(min_n_signatures = 9534))
</code></pre>

<pre><code>#&gt; TCGA.XE.A8H4.01 TCGA.2G.AAF1.01 TCGA.W4.A7U4.01 TCGA.2G.AAGO.01 TCGA.VF.A8AC.01 TCGA.2G.AALX.01 
#&gt;            &quot;01&quot;            &quot;01&quot;           &quot;024&quot;           &quot;024&quot;            &quot;01&quot;          &quot;0221&quot; 
#&gt; TCGA.2G.AAGK.01 TCGA.2G.AAGG.01 TCGA.2G.AAGP.01 TCGA.2G.AAKM.01 TCGA.ZM.AA0E.01 TCGA.XE.A9SE.01 
#&gt;           &quot;021&quot;          &quot;0223&quot;          &quot;0231&quot;           &quot;024&quot;            &quot;01&quot;            &quot;01&quot; 
#&gt; TCGA.2G.AAKO.05 TCGA.2G.AAFY.01 TCGA.XE.AANI.01 TCGA.YU.AA4L.01 TCGA.2G.AAGI.05 TCGA.XE.AANV.01 
#&gt;            &quot;01&quot;           &quot;021&quot;          &quot;0221&quot;          &quot;0222&quot;            &quot;01&quot;            &quot;03&quot; 
#&gt; TCGA.YU.A90S.01 TCGA.XY.A89B.01 TCGA.ZM.AA05.01 TCGA.2G.AAHA.01 TCGA.2G.AAH2.01 TCGA.2G.AAG6.01 
#&gt;            &quot;01&quot;            &quot;01&quot;            &quot;01&quot;            &quot;03&quot;          &quot;0223&quot;          &quot;0221&quot; 
#&gt; TCGA.2G.AAG0.01 TCGA.WZ.A7V3.01 TCGA.2G.AALO.01 TCGA.ZM.AA0F.01 TCGA.XE.A8H5.01 TCGA.XE.AANJ.01 
#&gt;           &quot;021&quot;            &quot;03&quot;          &quot;0223&quot;            &quot;01&quot;            &quot;03&quot;            &quot;01&quot; 
#&gt; TCGA.YU.A94I.01 TCGA.SO.A8JP.01 TCGA.2G.AAM4.01 TCGA.WZ.A7V5.01 TCGA.YU.A90Y.01 TCGA.2G.AALZ.01 
#&gt;          &quot;0222&quot;            &quot;03&quot;           &quot;021&quot;            &quot;01&quot;          &quot;0233&quot;          &quot;0221&quot; 
#&gt; TCGA.WZ.A8D5.01 TCGA.2G.AAGA.01 TCGA.2G.AALY.01 TCGA.2G.AAKG.01 TCGA.2G.AAL5.01 TCGA.YU.A94D.01 
#&gt;            &quot;01&quot;           &quot;024&quot;          &quot;0234&quot;          &quot;0233&quot;          &quot;0224&quot;          &quot;0224&quot; 
#&gt; TCGA.XE.AAOL.01 TCGA.SN.A84X.01 TCGA.2G.AAHC.01 TCGA.2G.AAHT.01 TCGA.2G.AALT.01 TCGA.2G.AAM2.01 
#&gt;            &quot;03&quot;          &quot;0232&quot;            &quot;01&quot;            &quot;03&quot;          &quot;0223&quot;           &quot;024&quot; 
#&gt; TCGA.2G.AAFH.01 TCGA.2G.AAFI.01 TCGA.2G.AAHN.01 TCGA.2G.AAGT.01 TCGA.YU.A90W.01 TCGA.2G.AAGJ.01 
#&gt;            &quot;01&quot;           &quot;021&quot;            &quot;01&quot;          &quot;0222&quot;            &quot;03&quot;           &quot;021&quot; 
#&gt; TCGA.2G.AAGV.01 TCGA.XE.A8H1.01 TCGA.2G.AAFJ.01 TCGA.2G.AAG5.01 TCGA.X3.A8G4.01 TCGA.2G.AAGY.01 
#&gt;          &quot;0223&quot;           &quot;021&quot;          &quot;0221&quot;          &quot;0221&quot;          &quot;0233&quot;          &quot;0221&quot; 
#&gt; TCGA.2G.AAG8.01 TCGA.S6.A8JW.01 TCGA.2G.AAEW.01 TCGA.2G.AAFO.01 TCGA.YU.A912.01 TCGA.2G.AAM3.01 
#&gt;           &quot;021&quot;            &quot;03&quot;            &quot;03&quot;           &quot;021&quot;            &quot;03&quot;          &quot;0223&quot; 
#&gt; TCGA.VF.A8A8.01 TCGA.SN.A84W.01 TCGA.XE.AAO4.01 TCGA.ZM.AA0N.01 TCGA.VF.A8AE.01 TCGA.2G.AAFZ.01 
#&gt;           &quot;024&quot;          &quot;0221&quot;            &quot;01&quot;            &quot;01&quot;            &quot;01&quot;          &quot;0221&quot; 
#&gt; TCGA.2G.AAGM.01 TCGA.2G.AAKH.01 TCGA.2G.AAF6.01 TCGA.4K.AA1I.01 TCGA.2G.AAFL.01 TCGA.XY.A9T9.01 
#&gt;          &quot;0224&quot;           &quot;021&quot;            &quot;01&quot;            &quot;01&quot;           &quot;021&quot;            &quot;01&quot; 
#&gt; TCGA.WZ.A7V4.01 TCGA.S6.A8JX.01 TCGA.2G.AAHL.01 TCGA.4K.AA1H.01 TCGA.ZM.AA06.01 TCGA.VF.A8A9.01 
#&gt;            &quot;01&quot;            &quot;03&quot;            &quot;03&quot;            &quot;01&quot;            &quot;01&quot;            &quot;01&quot; 
#&gt; TCGA.4K.AA1G.01 TCGA.2G.AAFE.01 TCGA.ZM.AA0H.01 TCGA.2G.AAKG.05 TCGA.ZM.AA0B.01 TCGA.2G.AALP.01 
#&gt;            &quot;03&quot;            &quot;03&quot;            &quot;01&quot;          &quot;0231&quot;            &quot;01&quot;           &quot;021&quot; 
#&gt; TCGA.YU.A90P.01 TCGA.2G.AAGS.01 TCGA.W4.A7U3.01 TCGA.SN.A6IS.01 TCGA.2G.AAGF.01 TCGA.2G.AAGE.01 
#&gt;           &quot;021&quot;          &quot;0234&quot;          &quot;0223&quot;            &quot;01&quot;           &quot;021&quot;           &quot;021&quot; 
#&gt; TCGA.2G.AAGY.05 TCGA.2G.AAKL.01 TCGA.2G.AAF8.01 TCGA.2G.AALW.01 TCGA.XE.AAOB.01 TCGA.2G.AAF4.01 
#&gt;            &quot;03&quot;           &quot;024&quot;            &quot;01&quot;          &quot;0223&quot;          &quot;0231&quot;            &quot;01&quot; 
#&gt; TCGA.XE.AAOC.01 TCGA.XE.AANR.01 TCGA.2G.AAFG.05 TCGA.2G.AALS.01 TCGA.2G.AAG3.01 TCGA.2G.AALN.01 
#&gt;          &quot;0221&quot;          &quot;0232&quot;            &quot;01&quot;          &quot;0231&quot;          &quot;0223&quot;          &quot;0234&quot; 
#&gt; TCGA.ZM.AA0D.01 TCGA.2G.AAG9.01 TCGA.2G.AAGC.01 TCGA.2X.A9D6.01 TCGA.4K.AAAL.01 TCGA.SN.A84Y.01 
#&gt;            &quot;01&quot;            &quot;03&quot;          &quot;0233&quot;            &quot;01&quot;            &quot;03&quot;           &quot;024&quot; 
#&gt; TCGA.VF.A8AA.01 TCGA.2G.AAH3.01 TCGA.YU.A90Q.01 TCGA.2G.AAKO.01 TCGA.2G.AAGZ.01 TCGA.VF.A8AB.01 
#&gt;            &quot;01&quot;            &quot;01&quot;            &quot;03&quot;            &quot;01&quot;          &quot;0231&quot;            &quot;01&quot; 
#&gt; TCGA.2G.AALF.01 TCGA.2G.AAL7.01 TCGA.2G.AALQ.01 TCGA.2G.AAFN.01 TCGA.2G.AAFG.01 TCGA.2G.AAGN.01 
#&gt;          &quot;0222&quot;           &quot;024&quot;          &quot;0224&quot;           &quot;024&quot;            &quot;01&quot;           &quot;021&quot; 
#&gt; TCGA.XE.AAOD.01 TCGA.XE.AAOF.01 TCGA.XY.A8S3.01 TCGA.2G.AAFV.01 TCGA.2G.AAHP.05 TCGA.2G.AAH4.01 
#&gt;            &quot;01&quot;            &quot;01&quot;           &quot;021&quot;          &quot;0222&quot;            &quot;01&quot;          &quot;0221&quot; 
#&gt; TCGA.XE.AAO3.01 TCGA.SB.A76C.01 TCGA.2G.AAHG.01 TCGA.XE.AAO6.01 TCGA.SB.A6J6.01 TCGA.YU.AA61.01 
#&gt;            &quot;01&quot;            &quot;03&quot;            &quot;03&quot;            &quot;01&quot;            &quot;01&quot;          &quot;0223&quot; 
#&gt; TCGA.2G.AAG7.01 TCGA.XY.A8S2.01 TCGA.2G.AAEX.01 TCGA.2G.AAH0.01 TCGA.2G.AAKD.01 TCGA.VF.A8AD.01 
#&gt;           &quot;024&quot;           &quot;024&quot;            &quot;01&quot;            &quot;01&quot;           &quot;024&quot;           &quot;021&quot; 
#&gt; TCGA.2G.AALR.01 TCGA.2G.AAFM.01 TCGA.2G.AALG.01 TCGA.XE.AAOJ.01 TCGA.2G.AAGI.01 TCGA.W4.A7U2.01 
#&gt;          &quot;0224&quot;           &quot;021&quot;          &quot;0223&quot;          &quot;0224&quot;          &quot;0223&quot;            &quot;01&quot; 
#&gt; TCGA.S6.A8JY.01 TCGA.2G.AAH8.01 TCGA.2G.AAHP.01 TCGA.2G.AAGW.01 TCGA.2X.A9D5.01 TCGA.2G.AAGX.01 
#&gt;            &quot;03&quot;            &quot;03&quot;            &quot;01&quot;           &quot;024&quot;            &quot;01&quot;          &quot;0223&quot;
</code></pre>

<script>
$('#tab-get-classes-from-hierarchical-partition-4-a').parent().next().next().hide();
$('#tab-get-classes-from-hierarchical-partition-4-a').click(function(){
  $('#tab-get-classes-from-hierarchical-partition-4-a').parent().next().next().toggle();
  return(false);
});
</script>
</div>

<div id='tab-get-classes-from-hierarchical-partition-5'>
<p><a id='tab-get-classes-from-hierarchical-partition-5-a' style='color:#0366d6' href='#'>show/hide code output</a></p>
<pre><code class="r">get_classes(res_rh, merge_node = merge_node_param(min_n_signatures = 18548))
</code></pre>

<pre><code>#&gt; TCGA.XE.A8H4.01 TCGA.2G.AAF1.01 TCGA.W4.A7U4.01 TCGA.2G.AAGO.01 TCGA.VF.A8AC.01 TCGA.2G.AALX.01 
#&gt;            &quot;01&quot;            &quot;01&quot;           &quot;024&quot;           &quot;024&quot;            &quot;01&quot;          &quot;0221&quot; 
#&gt; TCGA.2G.AAGK.01 TCGA.2G.AAGG.01 TCGA.2G.AAGP.01 TCGA.2G.AAKM.01 TCGA.ZM.AA0E.01 TCGA.XE.A9SE.01 
#&gt;           &quot;021&quot;          &quot;0223&quot;          &quot;0231&quot;           &quot;024&quot;            &quot;01&quot;            &quot;01&quot; 
#&gt; TCGA.2G.AAKO.05 TCGA.2G.AAFY.01 TCGA.XE.AANI.01 TCGA.YU.AA4L.01 TCGA.2G.AAGI.05 TCGA.XE.AANV.01 
#&gt;            &quot;01&quot;           &quot;021&quot;          &quot;0221&quot;          &quot;0222&quot;            &quot;01&quot;            &quot;03&quot; 
#&gt; TCGA.YU.A90S.01 TCGA.XY.A89B.01 TCGA.ZM.AA05.01 TCGA.2G.AAHA.01 TCGA.2G.AAH2.01 TCGA.2G.AAG6.01 
#&gt;            &quot;01&quot;            &quot;01&quot;            &quot;01&quot;            &quot;03&quot;          &quot;0223&quot;          &quot;0221&quot; 
#&gt; TCGA.2G.AAG0.01 TCGA.WZ.A7V3.01 TCGA.2G.AALO.01 TCGA.ZM.AA0F.01 TCGA.XE.A8H5.01 TCGA.XE.AANJ.01 
#&gt;           &quot;021&quot;            &quot;03&quot;          &quot;0223&quot;            &quot;01&quot;            &quot;03&quot;            &quot;01&quot; 
#&gt; TCGA.YU.A94I.01 TCGA.SO.A8JP.01 TCGA.2G.AAM4.01 TCGA.WZ.A7V5.01 TCGA.YU.A90Y.01 TCGA.2G.AALZ.01 
#&gt;          &quot;0222&quot;            &quot;03&quot;           &quot;021&quot;            &quot;01&quot;          &quot;0233&quot;          &quot;0221&quot; 
#&gt; TCGA.WZ.A8D5.01 TCGA.2G.AAGA.01 TCGA.2G.AALY.01 TCGA.2G.AAKG.01 TCGA.2G.AAL5.01 TCGA.YU.A94D.01 
#&gt;            &quot;01&quot;           &quot;024&quot;          &quot;0234&quot;          &quot;0233&quot;          &quot;0224&quot;          &quot;0224&quot; 
#&gt; TCGA.XE.AAOL.01 TCGA.SN.A84X.01 TCGA.2G.AAHC.01 TCGA.2G.AAHT.01 TCGA.2G.AALT.01 TCGA.2G.AAM2.01 
#&gt;            &quot;03&quot;          &quot;0232&quot;            &quot;01&quot;            &quot;03&quot;          &quot;0223&quot;           &quot;024&quot; 
#&gt; TCGA.2G.AAFH.01 TCGA.2G.AAFI.01 TCGA.2G.AAHN.01 TCGA.2G.AAGT.01 TCGA.YU.A90W.01 TCGA.2G.AAGJ.01 
#&gt;            &quot;01&quot;           &quot;021&quot;            &quot;01&quot;          &quot;0222&quot;            &quot;03&quot;           &quot;021&quot; 
#&gt; TCGA.2G.AAGV.01 TCGA.XE.A8H1.01 TCGA.2G.AAFJ.01 TCGA.2G.AAG5.01 TCGA.X3.A8G4.01 TCGA.2G.AAGY.01 
#&gt;          &quot;0223&quot;           &quot;021&quot;          &quot;0221&quot;          &quot;0221&quot;          &quot;0233&quot;          &quot;0221&quot; 
#&gt; TCGA.2G.AAG8.01 TCGA.S6.A8JW.01 TCGA.2G.AAEW.01 TCGA.2G.AAFO.01 TCGA.YU.A912.01 TCGA.2G.AAM3.01 
#&gt;           &quot;021&quot;            &quot;03&quot;            &quot;03&quot;           &quot;021&quot;            &quot;03&quot;          &quot;0223&quot; 
#&gt; TCGA.VF.A8A8.01 TCGA.SN.A84W.01 TCGA.XE.AAO4.01 TCGA.ZM.AA0N.01 TCGA.VF.A8AE.01 TCGA.2G.AAFZ.01 
#&gt;           &quot;024&quot;          &quot;0221&quot;            &quot;01&quot;            &quot;01&quot;            &quot;01&quot;          &quot;0221&quot; 
#&gt; TCGA.2G.AAGM.01 TCGA.2G.AAKH.01 TCGA.2G.AAF6.01 TCGA.4K.AA1I.01 TCGA.2G.AAFL.01 TCGA.XY.A9T9.01 
#&gt;          &quot;0224&quot;           &quot;021&quot;            &quot;01&quot;            &quot;01&quot;           &quot;021&quot;            &quot;01&quot; 
#&gt; TCGA.WZ.A7V4.01 TCGA.S6.A8JX.01 TCGA.2G.AAHL.01 TCGA.4K.AA1H.01 TCGA.ZM.AA06.01 TCGA.VF.A8A9.01 
#&gt;            &quot;01&quot;            &quot;03&quot;            &quot;03&quot;            &quot;01&quot;            &quot;01&quot;            &quot;01&quot; 
#&gt; TCGA.4K.AA1G.01 TCGA.2G.AAFE.01 TCGA.ZM.AA0H.01 TCGA.2G.AAKG.05 TCGA.ZM.AA0B.01 TCGA.2G.AALP.01 
#&gt;            &quot;03&quot;            &quot;03&quot;            &quot;01&quot;          &quot;0231&quot;            &quot;01&quot;           &quot;021&quot; 
#&gt; TCGA.YU.A90P.01 TCGA.2G.AAGS.01 TCGA.W4.A7U3.01 TCGA.SN.A6IS.01 TCGA.2G.AAGF.01 TCGA.2G.AAGE.01 
#&gt;           &quot;021&quot;          &quot;0234&quot;          &quot;0223&quot;            &quot;01&quot;           &quot;021&quot;           &quot;021&quot; 
#&gt; TCGA.2G.AAGY.05 TCGA.2G.AAKL.01 TCGA.2G.AAF8.01 TCGA.2G.AALW.01 TCGA.XE.AAOB.01 TCGA.2G.AAF4.01 
#&gt;            &quot;03&quot;           &quot;024&quot;            &quot;01&quot;          &quot;0223&quot;          &quot;0231&quot;            &quot;01&quot; 
#&gt; TCGA.XE.AAOC.01 TCGA.XE.AANR.01 TCGA.2G.AAFG.05 TCGA.2G.AALS.01 TCGA.2G.AAG3.01 TCGA.2G.AALN.01 
#&gt;          &quot;0221&quot;          &quot;0232&quot;            &quot;01&quot;          &quot;0231&quot;          &quot;0223&quot;          &quot;0234&quot; 
#&gt; TCGA.ZM.AA0D.01 TCGA.2G.AAG9.01 TCGA.2G.AAGC.01 TCGA.2X.A9D6.01 TCGA.4K.AAAL.01 TCGA.SN.A84Y.01 
#&gt;            &quot;01&quot;            &quot;03&quot;          &quot;0233&quot;            &quot;01&quot;            &quot;03&quot;           &quot;024&quot; 
#&gt; TCGA.VF.A8AA.01 TCGA.2G.AAH3.01 TCGA.YU.A90Q.01 TCGA.2G.AAKO.01 TCGA.2G.AAGZ.01 TCGA.VF.A8AB.01 
#&gt;            &quot;01&quot;            &quot;01&quot;            &quot;03&quot;            &quot;01&quot;          &quot;0231&quot;            &quot;01&quot; 
#&gt; TCGA.2G.AALF.01 TCGA.2G.AAL7.01 TCGA.2G.AALQ.01 TCGA.2G.AAFN.01 TCGA.2G.AAFG.01 TCGA.2G.AAGN.01 
#&gt;          &quot;0222&quot;           &quot;024&quot;          &quot;0224&quot;           &quot;024&quot;            &quot;01&quot;           &quot;021&quot; 
#&gt; TCGA.XE.AAOD.01 TCGA.XE.AAOF.01 TCGA.XY.A8S3.01 TCGA.2G.AAFV.01 TCGA.2G.AAHP.05 TCGA.2G.AAH4.01 
#&gt;            &quot;01&quot;            &quot;01&quot;           &quot;021&quot;          &quot;0222&quot;            &quot;01&quot;          &quot;0221&quot; 
#&gt; TCGA.XE.AAO3.01 TCGA.SB.A76C.01 TCGA.2G.AAHG.01 TCGA.XE.AAO6.01 TCGA.SB.A6J6.01 TCGA.YU.AA61.01 
#&gt;            &quot;01&quot;            &quot;03&quot;            &quot;03&quot;            &quot;01&quot;            &quot;01&quot;          &quot;0223&quot; 
#&gt; TCGA.2G.AAG7.01 TCGA.XY.A8S2.01 TCGA.2G.AAEX.01 TCGA.2G.AAH0.01 TCGA.2G.AAKD.01 TCGA.VF.A8AD.01 
#&gt;           &quot;024&quot;           &quot;024&quot;            &quot;01&quot;            &quot;01&quot;           &quot;024&quot;           &quot;021&quot; 
#&gt; TCGA.2G.AALR.01 TCGA.2G.AAFM.01 TCGA.2G.AALG.01 TCGA.XE.AAOJ.01 TCGA.2G.AAGI.01 TCGA.W4.A7U2.01 
#&gt;          &quot;0224&quot;           &quot;021&quot;          &quot;0223&quot;          &quot;0224&quot;          &quot;0223&quot;            &quot;01&quot; 
#&gt; TCGA.S6.A8JY.01 TCGA.2G.AAH8.01 TCGA.2G.AAHP.01 TCGA.2G.AAGW.01 TCGA.2X.A9D5.01 TCGA.2G.AAGX.01 
#&gt;            &quot;03&quot;            &quot;03&quot;            &quot;01&quot;           &quot;024&quot;            &quot;01&quot;          &quot;0223&quot;
</code></pre>

<script>
$('#tab-get-classes-from-hierarchical-partition-5-a').parent().next().next().hide();
$('#tab-get-classes-from-hierarchical-partition-5-a').click(function(){
  $('#tab-get-classes-from-hierarchical-partition-5-a').parent().next().next().toggle();
  return(false);
});
</script>
</div>

<div id='tab-get-classes-from-hierarchical-partition-6'>
<p><a id='tab-get-classes-from-hierarchical-partition-6-a' style='color:#0366d6' href='#'>show/hide code output</a></p>
<pre><code class="r">get_classes(res_rh, merge_node = merge_node_param(min_n_signatures = 52459))
</code></pre>

<pre><code>#&gt; TCGA.XE.A8H4.01 TCGA.2G.AAF1.01 TCGA.W4.A7U4.01 TCGA.2G.AAGO.01 TCGA.VF.A8AC.01 TCGA.2G.AALX.01 
#&gt;            &quot;01&quot;            &quot;01&quot;            &quot;02&quot;            &quot;02&quot;            &quot;01&quot;            &quot;02&quot; 
#&gt; TCGA.2G.AAGK.01 TCGA.2G.AAGG.01 TCGA.2G.AAGP.01 TCGA.2G.AAKM.01 TCGA.ZM.AA0E.01 TCGA.XE.A9SE.01 
#&gt;            &quot;02&quot;            &quot;02&quot;            &quot;02&quot;            &quot;02&quot;            &quot;01&quot;            &quot;01&quot; 
#&gt; TCGA.2G.AAKO.05 TCGA.2G.AAFY.01 TCGA.XE.AANI.01 TCGA.YU.AA4L.01 TCGA.2G.AAGI.05 TCGA.XE.AANV.01 
#&gt;            &quot;01&quot;            &quot;02&quot;            &quot;02&quot;            &quot;02&quot;            &quot;01&quot;            &quot;03&quot; 
#&gt; TCGA.YU.A90S.01 TCGA.XY.A89B.01 TCGA.ZM.AA05.01 TCGA.2G.AAHA.01 TCGA.2G.AAH2.01 TCGA.2G.AAG6.01 
#&gt;            &quot;01&quot;            &quot;01&quot;            &quot;01&quot;            &quot;03&quot;            &quot;02&quot;            &quot;02&quot; 
#&gt; TCGA.2G.AAG0.01 TCGA.WZ.A7V3.01 TCGA.2G.AALO.01 TCGA.ZM.AA0F.01 TCGA.XE.A8H5.01 TCGA.XE.AANJ.01 
#&gt;            &quot;02&quot;            &quot;03&quot;            &quot;02&quot;            &quot;01&quot;            &quot;03&quot;            &quot;01&quot; 
#&gt; TCGA.YU.A94I.01 TCGA.SO.A8JP.01 TCGA.2G.AAM4.01 TCGA.WZ.A7V5.01 TCGA.YU.A90Y.01 TCGA.2G.AALZ.01 
#&gt;            &quot;02&quot;            &quot;03&quot;            &quot;02&quot;            &quot;01&quot;            &quot;02&quot;            &quot;02&quot; 
#&gt; TCGA.WZ.A8D5.01 TCGA.2G.AAGA.01 TCGA.2G.AALY.01 TCGA.2G.AAKG.01 TCGA.2G.AAL5.01 TCGA.YU.A94D.01 
#&gt;            &quot;01&quot;            &quot;02&quot;            &quot;02&quot;            &quot;02&quot;            &quot;02&quot;            &quot;02&quot; 
#&gt; TCGA.XE.AAOL.01 TCGA.SN.A84X.01 TCGA.2G.AAHC.01 TCGA.2G.AAHT.01 TCGA.2G.AALT.01 TCGA.2G.AAM2.01 
#&gt;            &quot;03&quot;            &quot;02&quot;            &quot;01&quot;            &quot;03&quot;            &quot;02&quot;            &quot;02&quot; 
#&gt; TCGA.2G.AAFH.01 TCGA.2G.AAFI.01 TCGA.2G.AAHN.01 TCGA.2G.AAGT.01 TCGA.YU.A90W.01 TCGA.2G.AAGJ.01 
#&gt;            &quot;01&quot;            &quot;02&quot;            &quot;01&quot;            &quot;02&quot;            &quot;03&quot;            &quot;02&quot; 
#&gt; TCGA.2G.AAGV.01 TCGA.XE.A8H1.01 TCGA.2G.AAFJ.01 TCGA.2G.AAG5.01 TCGA.X3.A8G4.01 TCGA.2G.AAGY.01 
#&gt;            &quot;02&quot;            &quot;02&quot;            &quot;02&quot;            &quot;02&quot;            &quot;02&quot;            &quot;02&quot; 
#&gt; TCGA.2G.AAG8.01 TCGA.S6.A8JW.01 TCGA.2G.AAEW.01 TCGA.2G.AAFO.01 TCGA.YU.A912.01 TCGA.2G.AAM3.01 
#&gt;            &quot;02&quot;            &quot;03&quot;            &quot;03&quot;            &quot;02&quot;            &quot;03&quot;            &quot;02&quot; 
#&gt; TCGA.VF.A8A8.01 TCGA.SN.A84W.01 TCGA.XE.AAO4.01 TCGA.ZM.AA0N.01 TCGA.VF.A8AE.01 TCGA.2G.AAFZ.01 
#&gt;            &quot;02&quot;            &quot;02&quot;            &quot;01&quot;            &quot;01&quot;            &quot;01&quot;            &quot;02&quot; 
#&gt; TCGA.2G.AAGM.01 TCGA.2G.AAKH.01 TCGA.2G.AAF6.01 TCGA.4K.AA1I.01 TCGA.2G.AAFL.01 TCGA.XY.A9T9.01 
#&gt;            &quot;02&quot;            &quot;02&quot;            &quot;01&quot;            &quot;01&quot;            &quot;02&quot;            &quot;01&quot; 
#&gt; TCGA.WZ.A7V4.01 TCGA.S6.A8JX.01 TCGA.2G.AAHL.01 TCGA.4K.AA1H.01 TCGA.ZM.AA06.01 TCGA.VF.A8A9.01 
#&gt;            &quot;01&quot;            &quot;03&quot;            &quot;03&quot;            &quot;01&quot;            &quot;01&quot;            &quot;01&quot; 
#&gt; TCGA.4K.AA1G.01 TCGA.2G.AAFE.01 TCGA.ZM.AA0H.01 TCGA.2G.AAKG.05 TCGA.ZM.AA0B.01 TCGA.2G.AALP.01 
#&gt;            &quot;03&quot;            &quot;03&quot;            &quot;01&quot;            &quot;02&quot;            &quot;01&quot;            &quot;02&quot; 
#&gt; TCGA.YU.A90P.01 TCGA.2G.AAGS.01 TCGA.W4.A7U3.01 TCGA.SN.A6IS.01 TCGA.2G.AAGF.01 TCGA.2G.AAGE.01 
#&gt;            &quot;02&quot;            &quot;02&quot;            &quot;02&quot;            &quot;01&quot;            &quot;02&quot;            &quot;02&quot; 
#&gt; TCGA.2G.AAGY.05 TCGA.2G.AAKL.01 TCGA.2G.AAF8.01 TCGA.2G.AALW.01 TCGA.XE.AAOB.01 TCGA.2G.AAF4.01 
#&gt;            &quot;03&quot;            &quot;02&quot;            &quot;01&quot;            &quot;02&quot;            &quot;02&quot;            &quot;01&quot; 
#&gt; TCGA.XE.AAOC.01 TCGA.XE.AANR.01 TCGA.2G.AAFG.05 TCGA.2G.AALS.01 TCGA.2G.AAG3.01 TCGA.2G.AALN.01 
#&gt;            &quot;02&quot;            &quot;02&quot;            &quot;01&quot;            &quot;02&quot;            &quot;02&quot;            &quot;02&quot; 
#&gt; TCGA.ZM.AA0D.01 TCGA.2G.AAG9.01 TCGA.2G.AAGC.01 TCGA.2X.A9D6.01 TCGA.4K.AAAL.01 TCGA.SN.A84Y.01 
#&gt;            &quot;01&quot;            &quot;03&quot;            &quot;02&quot;            &quot;01&quot;            &quot;03&quot;            &quot;02&quot; 
#&gt; TCGA.VF.A8AA.01 TCGA.2G.AAH3.01 TCGA.YU.A90Q.01 TCGA.2G.AAKO.01 TCGA.2G.AAGZ.01 TCGA.VF.A8AB.01 
#&gt;            &quot;01&quot;            &quot;01&quot;            &quot;03&quot;            &quot;01&quot;            &quot;02&quot;            &quot;01&quot; 
#&gt; TCGA.2G.AALF.01 TCGA.2G.AAL7.01 TCGA.2G.AALQ.01 TCGA.2G.AAFN.01 TCGA.2G.AAFG.01 TCGA.2G.AAGN.01 
#&gt;            &quot;02&quot;            &quot;02&quot;            &quot;02&quot;            &quot;02&quot;            &quot;01&quot;            &quot;02&quot; 
#&gt; TCGA.XE.AAOD.01 TCGA.XE.AAOF.01 TCGA.XY.A8S3.01 TCGA.2G.AAFV.01 TCGA.2G.AAHP.05 TCGA.2G.AAH4.01 
#&gt;            &quot;01&quot;            &quot;01&quot;            &quot;02&quot;            &quot;02&quot;            &quot;01&quot;            &quot;02&quot; 
#&gt; TCGA.XE.AAO3.01 TCGA.SB.A76C.01 TCGA.2G.AAHG.01 TCGA.XE.AAO6.01 TCGA.SB.A6J6.01 TCGA.YU.AA61.01 
#&gt;            &quot;01&quot;            &quot;03&quot;            &quot;03&quot;            &quot;01&quot;            &quot;01&quot;            &quot;02&quot; 
#&gt; TCGA.2G.AAG7.01 TCGA.XY.A8S2.01 TCGA.2G.AAEX.01 TCGA.2G.AAH0.01 TCGA.2G.AAKD.01 TCGA.VF.A8AD.01 
#&gt;            &quot;02&quot;            &quot;02&quot;            &quot;01&quot;            &quot;01&quot;            &quot;02&quot;            &quot;02&quot; 
#&gt; TCGA.2G.AALR.01 TCGA.2G.AAFM.01 TCGA.2G.AALG.01 TCGA.XE.AAOJ.01 TCGA.2G.AAGI.01 TCGA.W4.A7U2.01 
#&gt;            &quot;02&quot;            &quot;02&quot;            &quot;02&quot;            &quot;02&quot;            &quot;02&quot;            &quot;01&quot; 
#&gt; TCGA.S6.A8JY.01 TCGA.2G.AAH8.01 TCGA.2G.AAHP.01 TCGA.2G.AAGW.01 TCGA.2X.A9D5.01 TCGA.2G.AAGX.01 
#&gt;            &quot;03&quot;            &quot;03&quot;            &quot;01&quot;            &quot;02&quot;            &quot;01&quot;            &quot;02&quot;
</code></pre>

<script>
$('#tab-get-classes-from-hierarchical-partition-6-a').parent().next().next().hide();
$('#tab-get-classes-from-hierarchical-partition-6-a').click(function(){
  $('#tab-get-classes-from-hierarchical-partition-6-a').parent().next().next().toggle();
  return(false);
});
</script>
</div>

<div id='tab-get-classes-from-hierarchical-partition-7'>
<p><a id='tab-get-classes-from-hierarchical-partition-7-a' style='color:#0366d6' href='#'>show/hide code output</a></p>
<pre><code class="r">get_classes(res_rh, merge_node = merge_node_param(min_n_signatures = 66872))
</code></pre>

<pre><code>#&gt; TCGA.XE.A8H4.01 TCGA.2G.AAF1.01 TCGA.W4.A7U4.01 TCGA.2G.AAGO.01 TCGA.VF.A8AC.01 TCGA.2G.AALX.01 
#&gt;            &quot;01&quot;            &quot;01&quot;            &quot;02&quot;            &quot;02&quot;            &quot;01&quot;            &quot;02&quot; 
#&gt; TCGA.2G.AAGK.01 TCGA.2G.AAGG.01 TCGA.2G.AAGP.01 TCGA.2G.AAKM.01 TCGA.ZM.AA0E.01 TCGA.XE.A9SE.01 
#&gt;            &quot;02&quot;            &quot;02&quot;            &quot;02&quot;            &quot;02&quot;            &quot;01&quot;            &quot;01&quot; 
#&gt; TCGA.2G.AAKO.05 TCGA.2G.AAFY.01 TCGA.XE.AANI.01 TCGA.YU.AA4L.01 TCGA.2G.AAGI.05 TCGA.XE.AANV.01 
#&gt;            &quot;01&quot;            &quot;02&quot;            &quot;02&quot;            &quot;02&quot;            &quot;01&quot;            &quot;03&quot; 
#&gt; TCGA.YU.A90S.01 TCGA.XY.A89B.01 TCGA.ZM.AA05.01 TCGA.2G.AAHA.01 TCGA.2G.AAH2.01 TCGA.2G.AAG6.01 
#&gt;            &quot;01&quot;            &quot;01&quot;            &quot;01&quot;            &quot;03&quot;            &quot;02&quot;            &quot;02&quot; 
#&gt; TCGA.2G.AAG0.01 TCGA.WZ.A7V3.01 TCGA.2G.AALO.01 TCGA.ZM.AA0F.01 TCGA.XE.A8H5.01 TCGA.XE.AANJ.01 
#&gt;            &quot;02&quot;            &quot;03&quot;            &quot;02&quot;            &quot;01&quot;            &quot;03&quot;            &quot;01&quot; 
#&gt; TCGA.YU.A94I.01 TCGA.SO.A8JP.01 TCGA.2G.AAM4.01 TCGA.WZ.A7V5.01 TCGA.YU.A90Y.01 TCGA.2G.AALZ.01 
#&gt;            &quot;02&quot;            &quot;03&quot;            &quot;02&quot;            &quot;01&quot;            &quot;02&quot;            &quot;02&quot; 
#&gt; TCGA.WZ.A8D5.01 TCGA.2G.AAGA.01 TCGA.2G.AALY.01 TCGA.2G.AAKG.01 TCGA.2G.AAL5.01 TCGA.YU.A94D.01 
#&gt;            &quot;01&quot;            &quot;02&quot;            &quot;02&quot;            &quot;02&quot;            &quot;02&quot;            &quot;02&quot; 
#&gt; TCGA.XE.AAOL.01 TCGA.SN.A84X.01 TCGA.2G.AAHC.01 TCGA.2G.AAHT.01 TCGA.2G.AALT.01 TCGA.2G.AAM2.01 
#&gt;            &quot;03&quot;            &quot;02&quot;            &quot;01&quot;            &quot;03&quot;            &quot;02&quot;            &quot;02&quot; 
#&gt; TCGA.2G.AAFH.01 TCGA.2G.AAFI.01 TCGA.2G.AAHN.01 TCGA.2G.AAGT.01 TCGA.YU.A90W.01 TCGA.2G.AAGJ.01 
#&gt;            &quot;01&quot;            &quot;02&quot;            &quot;01&quot;            &quot;02&quot;            &quot;03&quot;            &quot;02&quot; 
#&gt; TCGA.2G.AAGV.01 TCGA.XE.A8H1.01 TCGA.2G.AAFJ.01 TCGA.2G.AAG5.01 TCGA.X3.A8G4.01 TCGA.2G.AAGY.01 
#&gt;            &quot;02&quot;            &quot;02&quot;            &quot;02&quot;            &quot;02&quot;            &quot;02&quot;            &quot;02&quot; 
#&gt; TCGA.2G.AAG8.01 TCGA.S6.A8JW.01 TCGA.2G.AAEW.01 TCGA.2G.AAFO.01 TCGA.YU.A912.01 TCGA.2G.AAM3.01 
#&gt;            &quot;02&quot;            &quot;03&quot;            &quot;03&quot;            &quot;02&quot;            &quot;03&quot;            &quot;02&quot; 
#&gt; TCGA.VF.A8A8.01 TCGA.SN.A84W.01 TCGA.XE.AAO4.01 TCGA.ZM.AA0N.01 TCGA.VF.A8AE.01 TCGA.2G.AAFZ.01 
#&gt;            &quot;02&quot;            &quot;02&quot;            &quot;01&quot;            &quot;01&quot;            &quot;01&quot;            &quot;02&quot; 
#&gt; TCGA.2G.AAGM.01 TCGA.2G.AAKH.01 TCGA.2G.AAF6.01 TCGA.4K.AA1I.01 TCGA.2G.AAFL.01 TCGA.XY.A9T9.01 
#&gt;            &quot;02&quot;            &quot;02&quot;            &quot;01&quot;            &quot;01&quot;            &quot;02&quot;            &quot;01&quot; 
#&gt; TCGA.WZ.A7V4.01 TCGA.S6.A8JX.01 TCGA.2G.AAHL.01 TCGA.4K.AA1H.01 TCGA.ZM.AA06.01 TCGA.VF.A8A9.01 
#&gt;            &quot;01&quot;            &quot;03&quot;            &quot;03&quot;            &quot;01&quot;            &quot;01&quot;            &quot;01&quot; 
#&gt; TCGA.4K.AA1G.01 TCGA.2G.AAFE.01 TCGA.ZM.AA0H.01 TCGA.2G.AAKG.05 TCGA.ZM.AA0B.01 TCGA.2G.AALP.01 
#&gt;            &quot;03&quot;            &quot;03&quot;            &quot;01&quot;            &quot;02&quot;            &quot;01&quot;            &quot;02&quot; 
#&gt; TCGA.YU.A90P.01 TCGA.2G.AAGS.01 TCGA.W4.A7U3.01 TCGA.SN.A6IS.01 TCGA.2G.AAGF.01 TCGA.2G.AAGE.01 
#&gt;            &quot;02&quot;            &quot;02&quot;            &quot;02&quot;            &quot;01&quot;            &quot;02&quot;            &quot;02&quot; 
#&gt; TCGA.2G.AAGY.05 TCGA.2G.AAKL.01 TCGA.2G.AAF8.01 TCGA.2G.AALW.01 TCGA.XE.AAOB.01 TCGA.2G.AAF4.01 
#&gt;            &quot;03&quot;            &quot;02&quot;            &quot;01&quot;            &quot;02&quot;            &quot;02&quot;            &quot;01&quot; 
#&gt; TCGA.XE.AAOC.01 TCGA.XE.AANR.01 TCGA.2G.AAFG.05 TCGA.2G.AALS.01 TCGA.2G.AAG3.01 TCGA.2G.AALN.01 
#&gt;            &quot;02&quot;            &quot;02&quot;            &quot;01&quot;            &quot;02&quot;            &quot;02&quot;            &quot;02&quot; 
#&gt; TCGA.ZM.AA0D.01 TCGA.2G.AAG9.01 TCGA.2G.AAGC.01 TCGA.2X.A9D6.01 TCGA.4K.AAAL.01 TCGA.SN.A84Y.01 
#&gt;            &quot;01&quot;            &quot;03&quot;            &quot;02&quot;            &quot;01&quot;            &quot;03&quot;            &quot;02&quot; 
#&gt; TCGA.VF.A8AA.01 TCGA.2G.AAH3.01 TCGA.YU.A90Q.01 TCGA.2G.AAKO.01 TCGA.2G.AAGZ.01 TCGA.VF.A8AB.01 
#&gt;            &quot;01&quot;            &quot;01&quot;            &quot;03&quot;            &quot;01&quot;            &quot;02&quot;            &quot;01&quot; 
#&gt; TCGA.2G.AALF.01 TCGA.2G.AAL7.01 TCGA.2G.AALQ.01 TCGA.2G.AAFN.01 TCGA.2G.AAFG.01 TCGA.2G.AAGN.01 
#&gt;            &quot;02&quot;            &quot;02&quot;            &quot;02&quot;            &quot;02&quot;            &quot;01&quot;            &quot;02&quot; 
#&gt; TCGA.XE.AAOD.01 TCGA.XE.AAOF.01 TCGA.XY.A8S3.01 TCGA.2G.AAFV.01 TCGA.2G.AAHP.05 TCGA.2G.AAH4.01 
#&gt;            &quot;01&quot;            &quot;01&quot;            &quot;02&quot;            &quot;02&quot;            &quot;01&quot;            &quot;02&quot; 
#&gt; TCGA.XE.AAO3.01 TCGA.SB.A76C.01 TCGA.2G.AAHG.01 TCGA.XE.AAO6.01 TCGA.SB.A6J6.01 TCGA.YU.AA61.01 
#&gt;            &quot;01&quot;            &quot;03&quot;            &quot;03&quot;            &quot;01&quot;            &quot;01&quot;            &quot;02&quot; 
#&gt; TCGA.2G.AAG7.01 TCGA.XY.A8S2.01 TCGA.2G.AAEX.01 TCGA.2G.AAH0.01 TCGA.2G.AAKD.01 TCGA.VF.A8AD.01 
#&gt;            &quot;02&quot;            &quot;02&quot;            &quot;01&quot;            &quot;01&quot;            &quot;02&quot;            &quot;02&quot; 
#&gt; TCGA.2G.AALR.01 TCGA.2G.AAFM.01 TCGA.2G.AALG.01 TCGA.XE.AAOJ.01 TCGA.2G.AAGI.01 TCGA.W4.A7U2.01 
#&gt;            &quot;02&quot;            &quot;02&quot;            &quot;02&quot;            &quot;02&quot;            &quot;02&quot;            &quot;01&quot; 
#&gt; TCGA.S6.A8JY.01 TCGA.2G.AAH8.01 TCGA.2G.AAHP.01 TCGA.2G.AAGW.01 TCGA.2X.A9D5.01 TCGA.2G.AAGX.01 
#&gt;            &quot;03&quot;            &quot;03&quot;            &quot;01&quot;            &quot;02&quot;            &quot;01&quot;            &quot;02&quot;
</code></pre>

<script>
$('#tab-get-classes-from-hierarchical-partition-7-a').parent().next().next().hide();
$('#tab-get-classes-from-hierarchical-partition-7-a').click(function(){
  $('#tab-get-classes-from-hierarchical-partition-7-a').parent().next().next().toggle();
  return(false);
});
</script>
</div>

<div id='tab-get-classes-from-hierarchical-partition-8'>
<p><a id='tab-get-classes-from-hierarchical-partition-8-a' style='color:#0366d6' href='#'>show/hide code output</a></p>
<pre><code class="r">get_classes(res_rh, merge_node = merge_node_param(min_n_signatures = 191928))
</code></pre>

<pre><code>#&gt; TCGA.XE.A8H4.01 TCGA.2G.AAF1.01 TCGA.W4.A7U4.01 TCGA.2G.AAGO.01 TCGA.VF.A8AC.01 TCGA.2G.AALX.01 
#&gt;            &quot;01&quot;            &quot;01&quot;            &quot;02&quot;            &quot;02&quot;            &quot;01&quot;            &quot;02&quot; 
#&gt; TCGA.2G.AAGK.01 TCGA.2G.AAGG.01 TCGA.2G.AAGP.01 TCGA.2G.AAKM.01 TCGA.ZM.AA0E.01 TCGA.XE.A9SE.01 
#&gt;            &quot;02&quot;            &quot;02&quot;            &quot;02&quot;            &quot;02&quot;            &quot;01&quot;            &quot;01&quot; 
#&gt; TCGA.2G.AAKO.05 TCGA.2G.AAFY.01 TCGA.XE.AANI.01 TCGA.YU.AA4L.01 TCGA.2G.AAGI.05 TCGA.XE.AANV.01 
#&gt;            &quot;01&quot;            &quot;02&quot;            &quot;02&quot;            &quot;02&quot;            &quot;01&quot;            &quot;03&quot; 
#&gt; TCGA.YU.A90S.01 TCGA.XY.A89B.01 TCGA.ZM.AA05.01 TCGA.2G.AAHA.01 TCGA.2G.AAH2.01 TCGA.2G.AAG6.01 
#&gt;            &quot;01&quot;            &quot;01&quot;            &quot;01&quot;            &quot;03&quot;            &quot;02&quot;            &quot;02&quot; 
#&gt; TCGA.2G.AAG0.01 TCGA.WZ.A7V3.01 TCGA.2G.AALO.01 TCGA.ZM.AA0F.01 TCGA.XE.A8H5.01 TCGA.XE.AANJ.01 
#&gt;            &quot;02&quot;            &quot;03&quot;            &quot;02&quot;            &quot;01&quot;            &quot;03&quot;            &quot;01&quot; 
#&gt; TCGA.YU.A94I.01 TCGA.SO.A8JP.01 TCGA.2G.AAM4.01 TCGA.WZ.A7V5.01 TCGA.YU.A90Y.01 TCGA.2G.AALZ.01 
#&gt;            &quot;02&quot;            &quot;03&quot;            &quot;02&quot;            &quot;01&quot;            &quot;02&quot;            &quot;02&quot; 
#&gt; TCGA.WZ.A8D5.01 TCGA.2G.AAGA.01 TCGA.2G.AALY.01 TCGA.2G.AAKG.01 TCGA.2G.AAL5.01 TCGA.YU.A94D.01 
#&gt;            &quot;01&quot;            &quot;02&quot;            &quot;02&quot;            &quot;02&quot;            &quot;02&quot;            &quot;02&quot; 
#&gt; TCGA.XE.AAOL.01 TCGA.SN.A84X.01 TCGA.2G.AAHC.01 TCGA.2G.AAHT.01 TCGA.2G.AALT.01 TCGA.2G.AAM2.01 
#&gt;            &quot;03&quot;            &quot;02&quot;            &quot;01&quot;            &quot;03&quot;            &quot;02&quot;            &quot;02&quot; 
#&gt; TCGA.2G.AAFH.01 TCGA.2G.AAFI.01 TCGA.2G.AAHN.01 TCGA.2G.AAGT.01 TCGA.YU.A90W.01 TCGA.2G.AAGJ.01 
#&gt;            &quot;01&quot;            &quot;02&quot;            &quot;01&quot;            &quot;02&quot;            &quot;03&quot;            &quot;02&quot; 
#&gt; TCGA.2G.AAGV.01 TCGA.XE.A8H1.01 TCGA.2G.AAFJ.01 TCGA.2G.AAG5.01 TCGA.X3.A8G4.01 TCGA.2G.AAGY.01 
#&gt;            &quot;02&quot;            &quot;02&quot;            &quot;02&quot;            &quot;02&quot;            &quot;02&quot;            &quot;02&quot; 
#&gt; TCGA.2G.AAG8.01 TCGA.S6.A8JW.01 TCGA.2G.AAEW.01 TCGA.2G.AAFO.01 TCGA.YU.A912.01 TCGA.2G.AAM3.01 
#&gt;            &quot;02&quot;            &quot;03&quot;            &quot;03&quot;            &quot;02&quot;            &quot;03&quot;            &quot;02&quot; 
#&gt; TCGA.VF.A8A8.01 TCGA.SN.A84W.01 TCGA.XE.AAO4.01 TCGA.ZM.AA0N.01 TCGA.VF.A8AE.01 TCGA.2G.AAFZ.01 
#&gt;            &quot;02&quot;            &quot;02&quot;            &quot;01&quot;            &quot;01&quot;            &quot;01&quot;            &quot;02&quot; 
#&gt; TCGA.2G.AAGM.01 TCGA.2G.AAKH.01 TCGA.2G.AAF6.01 TCGA.4K.AA1I.01 TCGA.2G.AAFL.01 TCGA.XY.A9T9.01 
#&gt;            &quot;02&quot;            &quot;02&quot;            &quot;01&quot;            &quot;01&quot;            &quot;02&quot;            &quot;01&quot; 
#&gt; TCGA.WZ.A7V4.01 TCGA.S6.A8JX.01 TCGA.2G.AAHL.01 TCGA.4K.AA1H.01 TCGA.ZM.AA06.01 TCGA.VF.A8A9.01 
#&gt;            &quot;01&quot;            &quot;03&quot;            &quot;03&quot;            &quot;01&quot;            &quot;01&quot;            &quot;01&quot; 
#&gt; TCGA.4K.AA1G.01 TCGA.2G.AAFE.01 TCGA.ZM.AA0H.01 TCGA.2G.AAKG.05 TCGA.ZM.AA0B.01 TCGA.2G.AALP.01 
#&gt;            &quot;03&quot;            &quot;03&quot;            &quot;01&quot;            &quot;02&quot;            &quot;01&quot;            &quot;02&quot; 
#&gt; TCGA.YU.A90P.01 TCGA.2G.AAGS.01 TCGA.W4.A7U3.01 TCGA.SN.A6IS.01 TCGA.2G.AAGF.01 TCGA.2G.AAGE.01 
#&gt;            &quot;02&quot;            &quot;02&quot;            &quot;02&quot;            &quot;01&quot;            &quot;02&quot;            &quot;02&quot; 
#&gt; TCGA.2G.AAGY.05 TCGA.2G.AAKL.01 TCGA.2G.AAF8.01 TCGA.2G.AALW.01 TCGA.XE.AAOB.01 TCGA.2G.AAF4.01 
#&gt;            &quot;03&quot;            &quot;02&quot;            &quot;01&quot;            &quot;02&quot;            &quot;02&quot;            &quot;01&quot; 
#&gt; TCGA.XE.AAOC.01 TCGA.XE.AANR.01 TCGA.2G.AAFG.05 TCGA.2G.AALS.01 TCGA.2G.AAG3.01 TCGA.2G.AALN.01 
#&gt;            &quot;02&quot;            &quot;02&quot;            &quot;01&quot;            &quot;02&quot;            &quot;02&quot;            &quot;02&quot; 
#&gt; TCGA.ZM.AA0D.01 TCGA.2G.AAG9.01 TCGA.2G.AAGC.01 TCGA.2X.A9D6.01 TCGA.4K.AAAL.01 TCGA.SN.A84Y.01 
#&gt;            &quot;01&quot;            &quot;03&quot;            &quot;02&quot;            &quot;01&quot;            &quot;03&quot;            &quot;02&quot; 
#&gt; TCGA.VF.A8AA.01 TCGA.2G.AAH3.01 TCGA.YU.A90Q.01 TCGA.2G.AAKO.01 TCGA.2G.AAGZ.01 TCGA.VF.A8AB.01 
#&gt;            &quot;01&quot;            &quot;01&quot;            &quot;03&quot;            &quot;01&quot;            &quot;02&quot;            &quot;01&quot; 
#&gt; TCGA.2G.AALF.01 TCGA.2G.AAL7.01 TCGA.2G.AALQ.01 TCGA.2G.AAFN.01 TCGA.2G.AAFG.01 TCGA.2G.AAGN.01 
#&gt;            &quot;02&quot;            &quot;02&quot;            &quot;02&quot;            &quot;02&quot;            &quot;01&quot;            &quot;02&quot; 
#&gt; TCGA.XE.AAOD.01 TCGA.XE.AAOF.01 TCGA.XY.A8S3.01 TCGA.2G.AAFV.01 TCGA.2G.AAHP.05 TCGA.2G.AAH4.01 
#&gt;            &quot;01&quot;            &quot;01&quot;            &quot;02&quot;            &quot;02&quot;            &quot;01&quot;            &quot;02&quot; 
#&gt; TCGA.XE.AAO3.01 TCGA.SB.A76C.01 TCGA.2G.AAHG.01 TCGA.XE.AAO6.01 TCGA.SB.A6J6.01 TCGA.YU.AA61.01 
#&gt;            &quot;01&quot;            &quot;03&quot;            &quot;03&quot;            &quot;01&quot;            &quot;01&quot;            &quot;02&quot; 
#&gt; TCGA.2G.AAG7.01 TCGA.XY.A8S2.01 TCGA.2G.AAEX.01 TCGA.2G.AAH0.01 TCGA.2G.AAKD.01 TCGA.VF.A8AD.01 
#&gt;            &quot;02&quot;            &quot;02&quot;            &quot;01&quot;            &quot;01&quot;            &quot;02&quot;            &quot;02&quot; 
#&gt; TCGA.2G.AALR.01 TCGA.2G.AAFM.01 TCGA.2G.AALG.01 TCGA.XE.AAOJ.01 TCGA.2G.AAGI.01 TCGA.W4.A7U2.01 
#&gt;            &quot;02&quot;            &quot;02&quot;            &quot;02&quot;            &quot;02&quot;            &quot;02&quot;            &quot;01&quot; 
#&gt; TCGA.S6.A8JY.01 TCGA.2G.AAH8.01 TCGA.2G.AAHP.01 TCGA.2G.AAGW.01 TCGA.2X.A9D5.01 TCGA.2G.AAGX.01 
#&gt;            &quot;03&quot;            &quot;03&quot;            &quot;01&quot;            &quot;02&quot;            &quot;01&quot;            &quot;02&quot;
</code></pre>

<script>
$('#tab-get-classes-from-hierarchical-partition-8-a').parent().next().next().hide();
$('#tab-get-classes-from-hierarchical-partition-8-a').click(function(){
  $('#tab-get-classes-from-hierarchical-partition-8-a').parent().next().next().toggle();
  return(false);
});
</script>
</div>
</div>



### Top rows heatmap

Heatmaps of the top rows:





```r
top_rows_heatmap(res_rh)
```

![plot of chunk top-rows-heatmap](figure_cola/top-rows-heatmap-1.png)

```
#> Error in h(simpleError(msg, call)) : 
#>   error in evaluating the argument 'object' in selecting a method for function 'draw': no applicable method for 'height' applied to an object of class "list"
```

Top rows on each node:


```r
top_rows_overlap(res_rh, method = "upset")
```

![plot of chunk top-rows-overlap](figure_cola/top-rows-overlap-1.png)


### UMAP plot

UMAP plot which shows how samples are separated.




<script>
$( function() {
	$( '#tabs-dimension-reduction-by-depth' ).tabs();
} );
</script>
<div id='tabs-dimension-reduction-by-depth'>
<ul>
<li><a href='#tab-dimension-reduction-by-depth-1'>n_signatures ??? 2846</a></li>
<li><a href='#tab-dimension-reduction-by-depth-2'>n_signatures ??? 5127</a></li>
<li><a href='#tab-dimension-reduction-by-depth-3'>n_signatures ??? 7052</a></li>
<li><a href='#tab-dimension-reduction-by-depth-4'>n_signatures ??? 9534</a></li>
<li><a href='#tab-dimension-reduction-by-depth-5'>n_signatures ??? 18548</a></li>
<li><a href='#tab-dimension-reduction-by-depth-6'>n_signatures ??? 52459</a></li>
<li><a href='#tab-dimension-reduction-by-depth-7'>n_signatures ??? 66872</a></li>
<li><a href='#tab-dimension-reduction-by-depth-8'>n_signatures ??? 191928</a></li>
</ul>
<div id='tab-dimension-reduction-by-depth-1'>
<pre><code class="r">par(mfrow = c(1, 2))
dimension_reduction(res_rh, merge_node = merge_node_param(min_n_signatures = 2846),
    method = &quot;UMAP&quot;, top_value_method = &quot;SD&quot;, top_n = 40000, scale_rows = FALSE)
dimension_reduction(res_rh, merge_node = merge_node_param(min_n_signatures = 2846),
    method = &quot;UMAP&quot;, top_value_method = &quot;ATC&quot;, top_n = 40000, scale_rows = TRUE)
</code></pre>

<p><img src="figure_cola/tab-dimension-reduction-by-depth-1-1.png" title="plot of chunk tab-dimension-reduction-by-depth-1" alt="plot of chunk tab-dimension-reduction-by-depth-1" width="100%" /></p>

</div>
<div id='tab-dimension-reduction-by-depth-2'>
<pre><code class="r">par(mfrow = c(1, 2))
dimension_reduction(res_rh, merge_node = merge_node_param(min_n_signatures = 5127),
    method = &quot;UMAP&quot;, top_value_method = &quot;SD&quot;, top_n = 40000, scale_rows = FALSE)
dimension_reduction(res_rh, merge_node = merge_node_param(min_n_signatures = 5127),
    method = &quot;UMAP&quot;, top_value_method = &quot;ATC&quot;, top_n = 40000, scale_rows = TRUE)
</code></pre>

<p><img src="figure_cola/tab-dimension-reduction-by-depth-2-1.png" title="plot of chunk tab-dimension-reduction-by-depth-2" alt="plot of chunk tab-dimension-reduction-by-depth-2" width="100%" /></p>

</div>
<div id='tab-dimension-reduction-by-depth-3'>
<pre><code class="r">par(mfrow = c(1, 2))
dimension_reduction(res_rh, merge_node = merge_node_param(min_n_signatures = 7052),
    method = &quot;UMAP&quot;, top_value_method = &quot;SD&quot;, top_n = 40000, scale_rows = FALSE)
dimension_reduction(res_rh, merge_node = merge_node_param(min_n_signatures = 7052),
    method = &quot;UMAP&quot;, top_value_method = &quot;ATC&quot;, top_n = 40000, scale_rows = TRUE)
</code></pre>

<p><img src="figure_cola/tab-dimension-reduction-by-depth-3-1.png" title="plot of chunk tab-dimension-reduction-by-depth-3" alt="plot of chunk tab-dimension-reduction-by-depth-3" width="100%" /></p>

</div>
<div id='tab-dimension-reduction-by-depth-4'>
<pre><code class="r">par(mfrow = c(1, 2))
dimension_reduction(res_rh, merge_node = merge_node_param(min_n_signatures = 9534),
    method = &quot;UMAP&quot;, top_value_method = &quot;SD&quot;, top_n = 40000, scale_rows = FALSE)
dimension_reduction(res_rh, merge_node = merge_node_param(min_n_signatures = 9534),
    method = &quot;UMAP&quot;, top_value_method = &quot;ATC&quot;, top_n = 40000, scale_rows = TRUE)
</code></pre>

<p><img src="figure_cola/tab-dimension-reduction-by-depth-4-1.png" title="plot of chunk tab-dimension-reduction-by-depth-4" alt="plot of chunk tab-dimension-reduction-by-depth-4" width="100%" /></p>

</div>
<div id='tab-dimension-reduction-by-depth-5'>
<pre><code class="r">par(mfrow = c(1, 2))
dimension_reduction(res_rh, merge_node = merge_node_param(min_n_signatures = 18548),
    method = &quot;UMAP&quot;, top_value_method = &quot;SD&quot;, top_n = 40000, scale_rows = FALSE)
dimension_reduction(res_rh, merge_node = merge_node_param(min_n_signatures = 18548),
    method = &quot;UMAP&quot;, top_value_method = &quot;ATC&quot;, top_n = 40000, scale_rows = TRUE)
</code></pre>

<p><img src="figure_cola/tab-dimension-reduction-by-depth-5-1.png" title="plot of chunk tab-dimension-reduction-by-depth-5" alt="plot of chunk tab-dimension-reduction-by-depth-5" width="100%" /></p>

</div>
<div id='tab-dimension-reduction-by-depth-6'>
<pre><code class="r">par(mfrow = c(1, 2))
dimension_reduction(res_rh, merge_node = merge_node_param(min_n_signatures = 52459),
    method = &quot;UMAP&quot;, top_value_method = &quot;SD&quot;, top_n = 40000, scale_rows = FALSE)
dimension_reduction(res_rh, merge_node = merge_node_param(min_n_signatures = 52459),
    method = &quot;UMAP&quot;, top_value_method = &quot;ATC&quot;, top_n = 40000, scale_rows = TRUE)
</code></pre>

<p><img src="figure_cola/tab-dimension-reduction-by-depth-6-1.png" title="plot of chunk tab-dimension-reduction-by-depth-6" alt="plot of chunk tab-dimension-reduction-by-depth-6" width="100%" /></p>

</div>
<div id='tab-dimension-reduction-by-depth-7'>
<pre><code class="r">par(mfrow = c(1, 2))
dimension_reduction(res_rh, merge_node = merge_node_param(min_n_signatures = 66872),
    method = &quot;UMAP&quot;, top_value_method = &quot;SD&quot;, top_n = 40000, scale_rows = FALSE)
dimension_reduction(res_rh, merge_node = merge_node_param(min_n_signatures = 66872),
    method = &quot;UMAP&quot;, top_value_method = &quot;ATC&quot;, top_n = 40000, scale_rows = TRUE)
</code></pre>

<p><img src="figure_cola/tab-dimension-reduction-by-depth-7-1.png" title="plot of chunk tab-dimension-reduction-by-depth-7" alt="plot of chunk tab-dimension-reduction-by-depth-7" width="100%" /></p>

</div>
<div id='tab-dimension-reduction-by-depth-8'>
<pre><code class="r">par(mfrow = c(1, 2))
dimension_reduction(res_rh, merge_node = merge_node_param(min_n_signatures = 191928),
    method = &quot;UMAP&quot;, top_value_method = &quot;SD&quot;, top_n = 40000, scale_rows = FALSE)
dimension_reduction(res_rh, merge_node = merge_node_param(min_n_signatures = 191928),
    method = &quot;UMAP&quot;, top_value_method = &quot;ATC&quot;, top_n = 40000, scale_rows = TRUE)
</code></pre>

<p><img src="figure_cola/tab-dimension-reduction-by-depth-8-1.png" title="plot of chunk tab-dimension-reduction-by-depth-8" alt="plot of chunk tab-dimension-reduction-by-depth-8" width="100%" /></p>

</div>
</div>




### Signature heatmap

Signatures on the heatmap are the union of all signatures found on every node
on the hierarchy. The number of k-means on rows are automatically selected by the function.




<script>
$( function() {
	$( '#tabs-get-signatures-from-hierarchical-partition' ).tabs();
} );
</script>
<div id='tabs-get-signatures-from-hierarchical-partition'>
<ul>
<li><a href='#tab-get-signatures-from-hierarchical-partition-1'>n_signatures ??? 2846</a></li>
<li><a href='#tab-get-signatures-from-hierarchical-partition-2'>n_signatures ??? 5127</a></li>
<li><a href='#tab-get-signatures-from-hierarchical-partition-3'>n_signatures ??? 7052</a></li>
<li><a href='#tab-get-signatures-from-hierarchical-partition-4'>n_signatures ??? 9534</a></li>
<li><a href='#tab-get-signatures-from-hierarchical-partition-5'>n_signatures ??? 18548</a></li>
<li><a href='#tab-get-signatures-from-hierarchical-partition-6'>n_signatures ??? 52459</a></li>
<li><a href='#tab-get-signatures-from-hierarchical-partition-7'>n_signatures ??? 66872</a></li>
<li><a href='#tab-get-signatures-from-hierarchical-partition-8'>n_signatures ??? 191928</a></li>
</ul>
<div id='tab-get-signatures-from-hierarchical-partition-1'>
<pre><code class="r">get_signatures(res_rh, merge_node = merge_node_param(min_n_signatures = 2846))
</code></pre>

<p><img src="figure_cola/tab-get-signatures-from-hierarchical-partition-1-1.png" alt="plot of chunk tab-get-signatures-from-hierarchical-partition-1"/></p>

</div>
<div id='tab-get-signatures-from-hierarchical-partition-2'>
<pre><code class="r">get_signatures(res_rh, merge_node = merge_node_param(min_n_signatures = 5127))
</code></pre>

<p><img src="figure_cola/tab-get-signatures-from-hierarchical-partition-2-1.png" alt="plot of chunk tab-get-signatures-from-hierarchical-partition-2"/></p>

</div>
<div id='tab-get-signatures-from-hierarchical-partition-3'>
<pre><code class="r">get_signatures(res_rh, merge_node = merge_node_param(min_n_signatures = 7052))
</code></pre>

<p><img src="figure_cola/tab-get-signatures-from-hierarchical-partition-3-1.png" alt="plot of chunk tab-get-signatures-from-hierarchical-partition-3"/></p>

</div>
<div id='tab-get-signatures-from-hierarchical-partition-4'>
<pre><code class="r">get_signatures(res_rh, merge_node = merge_node_param(min_n_signatures = 9534))
</code></pre>

<p><img src="figure_cola/tab-get-signatures-from-hierarchical-partition-4-1.png" alt="plot of chunk tab-get-signatures-from-hierarchical-partition-4"/></p>

</div>
<div id='tab-get-signatures-from-hierarchical-partition-5'>
<pre><code class="r">get_signatures(res_rh, merge_node = merge_node_param(min_n_signatures = 18548))
</code></pre>

<p><img src="figure_cola/tab-get-signatures-from-hierarchical-partition-5-1.png" alt="plot of chunk tab-get-signatures-from-hierarchical-partition-5"/></p>

</div>
<div id='tab-get-signatures-from-hierarchical-partition-6'>
<pre><code class="r">get_signatures(res_rh, merge_node = merge_node_param(min_n_signatures = 52459))
</code></pre>

<p><img src="figure_cola/tab-get-signatures-from-hierarchical-partition-6-1.png" alt="plot of chunk tab-get-signatures-from-hierarchical-partition-6"/></p>

</div>
<div id='tab-get-signatures-from-hierarchical-partition-7'>
<pre><code class="r">get_signatures(res_rh, merge_node = merge_node_param(min_n_signatures = 66872))
</code></pre>

<p><img src="figure_cola/tab-get-signatures-from-hierarchical-partition-7-1.png" alt="plot of chunk tab-get-signatures-from-hierarchical-partition-7"/></p>

</div>
<div id='tab-get-signatures-from-hierarchical-partition-8'>
<pre><code class="r">get_signatures(res_rh, merge_node = merge_node_param(min_n_signatures = 191928))
</code></pre>

<p><img src="figure_cola/tab-get-signatures-from-hierarchical-partition-8-1.png" alt="plot of chunk tab-get-signatures-from-hierarchical-partition-8"/></p>

</div>
</div>




Compare signatures from different nodes:


```r
compare_signatures(res_rh, verbose = FALSE)
```

![plot of chunk unnamed-chunk-24](figure_cola/unnamed-chunk-24-1.png)

If there are too many signatures, `top_signatures = ...` can be set to only show the 
signatures with the highest FDRs. Note it only works on every node and the final signatures
are the union of all signatures of all nodes.


```r
# code only for demonstration
# e.g. to show the top 500 most significant rows on each node.
tb = get_signature(res_rh, top_signatures = 500)
```


## Results for each node


---------------------------------------------------




### Node0


Child nodes: 
                [Node01](#Node01)
        ,
                [Node02](#Node02)
        ,
                [Node03](#Node03)
        .







The object with results only for a single top-value method and a single partitioning method 
can be extracted as:

```r
res = res_rh["0"]
```

A summary of `res` and all the functions that can be applied to it:

```r
res
```

```
#> A 'ConsensusPartition' object with k = 2, 3, 4, 5, 6, 7, 8.
#>   On a matrix with 30000 rows and 156 columns.
#>   Top rows (1000) are extracted by 'SD' method.
#>   Subgroups are detected by 'skmeans' method.
#>   Performed in total 350 partitions by row resampling.
#>   Best k for subgroups seems to be 4.
#> 
#> Following methods can be applied to this 'ConsensusPartition' object:
#>  [1] "cola_report"             "collect_classes"         "collect_plots"          
#>  [4] "collect_stats"           "colnames"                "compare_partitions"     
#>  [7] "compare_signatures"      "consensus_heatmap"       "dimension_reduction"    
#> [10] "functional_enrichment"   "get_anno_col"            "get_anno"               
#> [13] "get_classes"             "get_consensus"           "get_matrix"             
#> [16] "get_membership"          "get_param"               "get_signatures"         
#> [19] "get_stats"               "is_best_k"               "is_stable_k"            
#> [22] "membership_heatmap"      "ncol"                    "nrow"                   
#> [25] "plot_ecdf"               "predict_classes"         "rownames"               
#> [28] "select_partition_number" "show"                    "suggest_best_k"         
#> [31] "test_to_known_factors"   "top_rows_heatmap"
```

`collect_plots()` function collects all the plots made from `res` for all `k` (number of subgroups)
into one single page to provide an easy and fast comparison between different `k`.

```r
collect_plots(res)
```

![plot of chunk node-0-collect-plots](figure_cola/node-0-collect-plots-1.png)

The plots are:

- The first row: a plot of the eCDF (empirical cumulative distribution
  function) curves of the consensus matrix for each `k` and the heatmap of
  predicted classes for each `k`.
- The second row: heatmaps of the consensus matrix for each `k`.
- The third row: heatmaps of the membership matrix for each `k`.
- The fouth row: heatmaps of the signatures for each `k`.

All the plots in panels can be made by individual functions and they are
plotted later in this section.

`select_partition_number()` produces several plots showing different
statistics for choosing "optimized" `k`. There are following statistics:

- eCDF curves of the consensus matrix for each `k`;
- 1-PAC. [The PAC score](https://en.wikipedia.org/wiki/Consensus_clustering#Over-interpretation_potential_of_consensus_clustering)
  measures the proportion of the ambiguous subgrouping.
- Mean silhouette score.
- Concordance. The mean probability of fiting the consensus subgroup labels in all
  partitions.
- Area increased. Denote $A_k$ as the area under the eCDF curve for current
  `k`, the area increased is defined as $A_k - A_{k-1}$.
- Rand index. The percent of pairs of samples that are both in a same cluster
  or both are not in a same cluster in the partition of k and k-1.
- Jaccard index. The ratio of pairs of samples are both in a same cluster in
  the partition of k and k-1 and the pairs of samples are both in a same
  cluster in the partition k or k-1.

The detailed explanations of these statistics can be found in [the _cola_
vignette](https://jokergoo.github.io/cola_vignettes/cola.html#toc_13).

Generally speaking, higher 1-PAC score, higher mean silhouette score or higher
concordance corresponds to better partition. Rand index and Jaccard index
measure how similar the current partition is compared to partition with `k-1`.
If they are too similar, we won't accept `k` is better than `k-1`.

```r
select_partition_number(res)
```

![plot of chunk node-0-select-partition-number](figure_cola/node-0-select-partition-number-1.png)

The numeric values for all these statistics can be obtained by `get_stats()`.

```r
get_stats(res)
```

```
#>   k 1-PAC mean_silhouette concordance area_increased  Rand Jaccard
#> 2 2 1.000           0.983       0.994         0.5007 0.499   0.499
#> 3 3 0.941           0.952       0.972         0.1964 0.894   0.789
#> 4 4 1.000           0.987       0.994         0.0882 0.943   0.859
#> 5 5 0.816           0.836       0.902         0.0584 0.993   0.981
#> 6 6 0.796           0.747       0.838         0.0463 0.987   0.964
#> 7 7 0.772           0.792       0.837         0.0800 0.863   0.596
#> 8 8 0.790           0.773       0.859         0.0265 0.984   0.922
```

`suggest_best_k()` suggests the best $k$ based on these statistics. The rules are as follows:

- All $k$ with Jaccard index larger than 0.95 are removed because increasing
  $k$ does not provide enough extra information. If all $k$ are removed, it is
  marked as no subgroup is detected.
- For all $k$ with 1-PAC score larger than 0.9, the maximal $k$ is taken as
  the best $k$, and other $k$ are marked as optional $k$.
- If it does not fit the second rule. The $k$ with the maximal vote of the
  highest 1-PAC score, highest mean silhouette, and highest concordance is
  taken as the best $k$.

```r
suggest_best_k(res)
```

```
#> [1] 4
#> attr(,"optional")
#> [1] 2 3
```

There is also optional best $k$ = 2 3 that is worth to check.

Following is the table of the partitions (You need to click the **show/hide
code output** link to see it). The membership matrix (columns with name `p*`)
is inferred by
[`clue::cl_consensus()`](https://www.rdocumentation.org/link/cl_consensus?package=clue)
function with the `SE` method. Basically the value in the membership matrix
represents the probability to belong to a certain group. The finall subgroup
label for an item is determined with the group with highest probability it
belongs to.

In `get_classes()` function, the entropy is calculated from the membership
matrix and the silhouette score is calculated from the consensus matrix.



<script>
$( function() {
	$( '#tabs-node-0-get-classes' ).tabs();
} );
</script>
<div id='tabs-node-0-get-classes'>
<ul>
<li><a href='#tab-node-0-get-classes-1'>k = 2</a></li>
<li><a href='#tab-node-0-get-classes-2'>k = 3</a></li>
<li><a href='#tab-node-0-get-classes-3'>k = 4</a></li>
<li><a href='#tab-node-0-get-classes-4'>k = 5</a></li>
<li><a href='#tab-node-0-get-classes-5'>k = 6</a></li>
<li><a href='#tab-node-0-get-classes-6'>k = 7</a></li>
<li><a href='#tab-node-0-get-classes-7'>k = 8</a></li>
</ul>

<div id='tab-node-0-get-classes-1'>
<p><a id='tab-node-0-get-classes-1-a' style='color:#0366d6' href='#'>show/hide code output</a></p>
<pre><code class="r">cbind(get_classes(res, k = 2), get_membership(res, k = 2))
</code></pre>

<pre><code>#&gt;                 class entropy silhouette   p1   p2
#&gt; TCGA.XE.A8H4.01     1   0.000      0.987 1.00 0.00
#&gt; TCGA.2G.AAF1.01     1   0.000      0.987 1.00 0.00
#&gt; TCGA.W4.A7U4.01     2   0.000      1.000 0.00 1.00
#&gt; TCGA.2G.AAGO.01     2   0.000      1.000 0.00 1.00
#&gt; TCGA.VF.A8AC.01     1   0.000      0.987 1.00 0.00
#&gt; TCGA.2G.AALX.01     2   0.000      1.000 0.00 1.00
#&gt; TCGA.2G.AAGK.01     2   0.000      1.000 0.00 1.00
#&gt; TCGA.2G.AAGG.01     2   0.000      1.000 0.00 1.00
#&gt; TCGA.2G.AAGP.01     2   0.000      1.000 0.00 1.00
#&gt; TCGA.2G.AAKM.01     2   0.000      1.000 0.00 1.00
#&gt; TCGA.ZM.AA0E.01     1   0.000      0.987 1.00 0.00
#&gt; TCGA.XE.A9SE.01     1   0.242      0.947 0.96 0.04
#&gt; TCGA.2G.AAKO.05     1   0.000      0.987 1.00 0.00
#&gt; TCGA.2G.AAFY.01     2   0.000      1.000 0.00 1.00
#&gt; TCGA.XE.AANI.01     2   0.000      1.000 0.00 1.00
#&gt; TCGA.YU.AA4L.01     2   0.000      1.000 0.00 1.00
#&gt; TCGA.2G.AAGI.05     1   0.000      0.987 1.00 0.00
#&gt; TCGA.XE.AANV.01     1   0.000      0.987 1.00 0.00
#&gt; TCGA.YU.A90S.01     1   0.000      0.987 1.00 0.00
#&gt; TCGA.XY.A89B.01     1   0.000      0.987 1.00 0.00
#&gt; TCGA.ZM.AA05.01     1   0.000      0.987 1.00 0.00
#&gt; TCGA.2G.AAHA.01     1   0.000      0.987 1.00 0.00
#&gt; TCGA.2G.AAH2.01     2   0.000      1.000 0.00 1.00
#&gt; TCGA.2G.AAG6.01     2   0.000      1.000 0.00 1.00
#&gt; TCGA.2G.AAG0.01     2   0.000      1.000 0.00 1.00
#&gt; TCGA.WZ.A7V3.01     1   0.000      0.987 1.00 0.00
#&gt; TCGA.2G.AALO.01     2   0.000      1.000 0.00 1.00
#&gt; TCGA.ZM.AA0F.01     1   0.000      0.987 1.00 0.00
#&gt; TCGA.XE.A8H5.01     1   0.000      0.987 1.00 0.00
#&gt; TCGA.XE.AANJ.01     1   0.000      0.987 1.00 0.00
#&gt; TCGA.YU.A94I.01     2   0.000      1.000 0.00 1.00
#&gt; TCGA.SO.A8JP.01     1   0.000      0.987 1.00 0.00
#&gt; TCGA.2G.AAM4.01     2   0.000      1.000 0.00 1.00
#&gt; TCGA.WZ.A7V5.01     1   0.000      0.987 1.00 0.00
#&gt; TCGA.YU.A90Y.01     2   0.000      1.000 0.00 1.00
#&gt; TCGA.2G.AALZ.01     2   0.000      1.000 0.00 1.00
#&gt; TCGA.WZ.A8D5.01     1   0.000      0.987 1.00 0.00
#&gt; TCGA.2G.AAGA.01     2   0.000      1.000 0.00 1.00
#&gt; TCGA.2G.AALY.01     2   0.000      1.000 0.00 1.00
#&gt; TCGA.2G.AAKG.01     2   0.000      1.000 0.00 1.00
#&gt; TCGA.2G.AAL5.01     2   0.000      1.000 0.00 1.00
#&gt; TCGA.YU.A94D.01     2   0.000      1.000 0.00 1.00
#&gt; TCGA.XE.AAOL.01     1   0.000      0.987 1.00 0.00
#&gt; TCGA.SN.A84X.01     2   0.000      1.000 0.00 1.00
#&gt; TCGA.2G.AAHC.01     1   0.000      0.987 1.00 0.00
#&gt; TCGA.2G.AAHT.01     1   0.000      0.987 1.00 0.00
#&gt; TCGA.2G.AALT.01     2   0.000      1.000 0.00 1.00
#&gt; TCGA.2G.AAM2.01     2   0.000      1.000 0.00 1.00
#&gt; TCGA.2G.AAFH.01     1   0.000      0.987 1.00 0.00
#&gt; TCGA.2G.AAFI.01     2   0.000      1.000 0.00 1.00
#&gt; TCGA.2G.AAHN.01     1   0.000      0.987 1.00 0.00
#&gt; TCGA.2G.AAGT.01     2   0.000      1.000 0.00 1.00
#&gt; TCGA.YU.A90W.01     1   0.000      0.987 1.00 0.00
#&gt; TCGA.2G.AAGJ.01     2   0.000      1.000 0.00 1.00
#&gt; TCGA.2G.AAGV.01     2   0.000      1.000 0.00 1.00
#&gt; TCGA.XE.A8H1.01     2   0.000      1.000 0.00 1.00
#&gt; TCGA.2G.AAFJ.01     2   0.000      1.000 0.00 1.00
#&gt; TCGA.2G.AAG5.01     2   0.000      1.000 0.00 1.00
#&gt; TCGA.X3.A8G4.01     2   0.000      1.000 0.00 1.00
#&gt; TCGA.2G.AAGY.01     2   0.000      1.000 0.00 1.00
#&gt; TCGA.2G.AAG8.01     2   0.000      1.000 0.00 1.00
#&gt; TCGA.S6.A8JW.01     1   0.000      0.987 1.00 0.00
#&gt; TCGA.2G.AAEW.01     1   0.000      0.987 1.00 0.00
#&gt; TCGA.2G.AAFO.01     2   0.000      1.000 0.00 1.00
#&gt; TCGA.YU.A912.01     1   0.000      0.987 1.00 0.00
#&gt; TCGA.2G.AAM3.01     2   0.000      1.000 0.00 1.00
#&gt; TCGA.VF.A8A8.01     2   0.000      1.000 0.00 1.00
#&gt; TCGA.SN.A84W.01     2   0.000      1.000 0.00 1.00
#&gt; TCGA.XE.AAO4.01     1   0.000      0.987 1.00 0.00
#&gt; TCGA.ZM.AA0N.01     1   0.000      0.987 1.00 0.00
#&gt; TCGA.VF.A8AE.01     1   0.000      0.987 1.00 0.00
#&gt; TCGA.2G.AAFZ.01     2   0.000      1.000 0.00 1.00
#&gt; TCGA.2G.AAGM.01     2   0.000      1.000 0.00 1.00
#&gt; TCGA.2G.AAKH.01     2   0.000      1.000 0.00 1.00
#&gt; TCGA.2G.AAF6.01     1   0.000      0.987 1.00 0.00
#&gt; TCGA.4K.AA1I.01     1   0.000      0.987 1.00 0.00
#&gt; TCGA.2G.AAFL.01     2   0.000      1.000 0.00 1.00
#&gt; TCGA.XY.A9T9.01     1   0.000      0.987 1.00 0.00
#&gt; TCGA.WZ.A7V4.01     1   0.000      0.987 1.00 0.00
#&gt; TCGA.S6.A8JX.01     1   0.000      0.987 1.00 0.00
#&gt; TCGA.2G.AAHL.01     1   0.000      0.987 1.00 0.00
#&gt; TCGA.4K.AA1H.01     1   0.000      0.987 1.00 0.00
#&gt; TCGA.ZM.AA06.01     1   0.000      0.987 1.00 0.00
#&gt; TCGA.VF.A8A9.01     1   0.000      0.987 1.00 0.00
#&gt; TCGA.4K.AA1G.01     1   0.000      0.987 1.00 0.00
#&gt; TCGA.2G.AAFE.01     1   0.000      0.987 1.00 0.00
#&gt; TCGA.ZM.AA0H.01     1   0.000      0.987 1.00 0.00
#&gt; TCGA.2G.AAKG.05     2   0.000      1.000 0.00 1.00
#&gt; TCGA.ZM.AA0B.01     1   0.000      0.987 1.00 0.00
#&gt; TCGA.2G.AALP.01     2   0.000      1.000 0.00 1.00
#&gt; TCGA.YU.A90P.01     2   0.000      1.000 0.00 1.00
#&gt; TCGA.2G.AAGS.01     2   0.000      1.000 0.00 1.00
#&gt; TCGA.W4.A7U3.01     2   0.000      1.000 0.00 1.00
#&gt; TCGA.SN.A6IS.01     1   0.000      0.987 1.00 0.00
#&gt; TCGA.2G.AAGF.01     2   0.000      1.000 0.00 1.00
#&gt; TCGA.2G.AAGE.01     2   0.000      1.000 0.00 1.00
#&gt; TCGA.2G.AAGY.05     1   0.000      0.987 1.00 0.00
#&gt; TCGA.2G.AAKL.01     2   0.000      1.000 0.00 1.00
#&gt; TCGA.2G.AAF8.01     2   0.000      1.000 0.00 1.00
#&gt; TCGA.2G.AALW.01     2   0.000      1.000 0.00 1.00
#&gt; TCGA.XE.AAOB.01     2   0.000      1.000 0.00 1.00
#&gt; TCGA.2G.AAF4.01     1   0.000      0.987 1.00 0.00
#&gt; TCGA.XE.AAOC.01     2   0.000      1.000 0.00 1.00
#&gt; TCGA.XE.AANR.01     2   0.000      1.000 0.00 1.00
#&gt; TCGA.2G.AAFG.05     1   0.000      0.987 1.00 0.00
#&gt; TCGA.2G.AALS.01     2   0.000      1.000 0.00 1.00
#&gt; TCGA.2G.AAG3.01     2   0.000      1.000 0.00 1.00
#&gt; TCGA.2G.AALN.01     2   0.000      1.000 0.00 1.00
#&gt; TCGA.ZM.AA0D.01     1   0.000      0.987 1.00 0.00
#&gt; TCGA.2G.AAG9.01     1   0.000      0.987 1.00 0.00
#&gt; TCGA.2G.AAGC.01     2   0.000      1.000 0.00 1.00
#&gt; TCGA.2X.A9D6.01     1   0.000      0.987 1.00 0.00
#&gt; TCGA.4K.AAAL.01     1   0.000      0.987 1.00 0.00
#&gt; TCGA.SN.A84Y.01     2   0.000      1.000 0.00 1.00
#&gt; TCGA.VF.A8AA.01     1   0.000      0.987 1.00 0.00
#&gt; TCGA.2G.AAH3.01     1   0.990      0.226 0.56 0.44
#&gt; TCGA.YU.A90Q.01     1   0.000      0.987 1.00 0.00
#&gt; TCGA.2G.AAKO.01     1   0.000      0.987 1.00 0.00
#&gt; TCGA.2G.AAGZ.01     2   0.000      1.000 0.00 1.00
#&gt; TCGA.VF.A8AB.01     1   0.995      0.161 0.54 0.46
#&gt; TCGA.2G.AALF.01     2   0.000      1.000 0.00 1.00
#&gt; TCGA.2G.AAL7.01     2   0.000      1.000 0.00 1.00
#&gt; TCGA.2G.AALQ.01     2   0.000      1.000 0.00 1.00
#&gt; TCGA.2G.AAFN.01     2   0.000      1.000 0.00 1.00
#&gt; TCGA.2G.AAFG.01     1   0.000      0.987 1.00 0.00
#&gt; TCGA.2G.AAGN.01     2   0.000      1.000 0.00 1.00
#&gt; TCGA.XE.AAOD.01     1   0.000      0.987 1.00 0.00
#&gt; TCGA.XE.AAOF.01     1   0.000      0.987 1.00 0.00
#&gt; TCGA.XY.A8S3.01     2   0.000      1.000 0.00 1.00
#&gt; TCGA.2G.AAFV.01     2   0.000      1.000 0.00 1.00
#&gt; TCGA.2G.AAHP.05     1   0.000      0.987 1.00 0.00
#&gt; TCGA.2G.AAH4.01     2   0.000      1.000 0.00 1.00
#&gt; TCGA.XE.AAO3.01     1   0.000      0.987 1.00 0.00
#&gt; TCGA.SB.A76C.01     1   0.000      0.987 1.00 0.00
#&gt; TCGA.2G.AAHG.01     1   0.000      0.987 1.00 0.00
#&gt; TCGA.XE.AAO6.01     1   0.000      0.987 1.00 0.00
#&gt; TCGA.SB.A6J6.01     1   0.000      0.987 1.00 0.00
#&gt; TCGA.YU.AA61.01     2   0.000      1.000 0.00 1.00
#&gt; TCGA.2G.AAG7.01     2   0.000      1.000 0.00 1.00
#&gt; TCGA.XY.A8S2.01     2   0.000      1.000 0.00 1.00
#&gt; TCGA.2G.AAEX.01     1   0.000      0.987 1.00 0.00
#&gt; TCGA.2G.AAH0.01     1   0.000      0.987 1.00 0.00
#&gt; TCGA.2G.AAKD.01     2   0.000      1.000 0.00 1.00
#&gt; TCGA.VF.A8AD.01     2   0.000      1.000 0.00 1.00
#&gt; TCGA.2G.AALR.01     2   0.000      1.000 0.00 1.00
#&gt; TCGA.2G.AAFM.01     2   0.000      1.000 0.00 1.00
#&gt; TCGA.2G.AALG.01     2   0.000      1.000 0.00 1.00
#&gt; TCGA.XE.AAOJ.01     2   0.000      1.000 0.00 1.00
#&gt; TCGA.2G.AAGI.01     2   0.000      1.000 0.00 1.00
#&gt; TCGA.W4.A7U2.01     1   0.000      0.987 1.00 0.00
#&gt; TCGA.S6.A8JY.01     1   0.000      0.987 1.00 0.00
#&gt; TCGA.2G.AAH8.01     1   0.000      0.987 1.00 0.00
#&gt; TCGA.2G.AAHP.01     1   0.000      0.987 1.00 0.00
#&gt; TCGA.2G.AAGW.01     2   0.000      1.000 0.00 1.00
#&gt; TCGA.2X.A9D5.01     1   0.000      0.987 1.00 0.00
#&gt; TCGA.2G.AAGX.01     2   0.000      1.000 0.00 1.00
</code></pre>

<script>
$('#tab-node-0-get-classes-1-a').parent().next().next().hide();
$('#tab-node-0-get-classes-1-a').click(function(){
  $('#tab-node-0-get-classes-1-a').parent().next().next().toggle();
  return(false);
});
</script>
</div>

<div id='tab-node-0-get-classes-2'>
<p><a id='tab-node-0-get-classes-2-a' style='color:#0366d6' href='#'>show/hide code output</a></p>
<pre><code class="r">cbind(get_classes(res, k = 3), get_membership(res, k = 3))
</code></pre>

<pre><code>#&gt;                 class entropy silhouette   p1   p2   p3
#&gt; TCGA.XE.A8H4.01     1   0.207      0.934 0.94 0.00 0.06
#&gt; TCGA.2G.AAF1.01     1   0.207      0.934 0.94 0.00 0.06
#&gt; TCGA.W4.A7U4.01     2   0.000      1.000 0.00 1.00 0.00
#&gt; TCGA.2G.AAGO.01     2   0.000      1.000 0.00 1.00 0.00
#&gt; TCGA.VF.A8AC.01     1   0.207      0.934 0.94 0.00 0.06
#&gt; TCGA.2G.AALX.01     2   0.000      1.000 0.00 1.00 0.00
#&gt; TCGA.2G.AAGK.01     2   0.000      1.000 0.00 1.00 0.00
#&gt; TCGA.2G.AAGG.01     2   0.000      1.000 0.00 1.00 0.00
#&gt; TCGA.2G.AAGP.01     2   0.000      1.000 0.00 1.00 0.00
#&gt; TCGA.2G.AAKM.01     2   0.000      1.000 0.00 1.00 0.00
#&gt; TCGA.ZM.AA0E.01     1   0.207      0.934 0.94 0.00 0.06
#&gt; TCGA.XE.A9SE.01     1   0.000      0.923 1.00 0.00 0.00
#&gt; TCGA.2G.AAKO.05     1   0.207      0.934 0.94 0.00 0.06
#&gt; TCGA.2G.AAFY.01     2   0.000      1.000 0.00 1.00 0.00
#&gt; TCGA.XE.AANI.01     2   0.000      1.000 0.00 1.00 0.00
#&gt; TCGA.YU.AA4L.01     2   0.000      1.000 0.00 1.00 0.00
#&gt; TCGA.2G.AAGI.05     1   0.207      0.934 0.94 0.00 0.06
#&gt; TCGA.XE.AANV.01     3   0.000      0.952 0.00 0.00 1.00
#&gt; TCGA.YU.A90S.01     1   0.207      0.934 0.94 0.00 0.06
#&gt; TCGA.XY.A89B.01     1   0.207      0.934 0.94 0.00 0.06
#&gt; TCGA.ZM.AA05.01     1   0.207      0.934 0.94 0.00 0.06
#&gt; TCGA.2G.AAHA.01     3   0.000      0.952 0.00 0.00 1.00
#&gt; TCGA.2G.AAH2.01     2   0.000      1.000 0.00 1.00 0.00
#&gt; TCGA.2G.AAG6.01     2   0.000      1.000 0.00 1.00 0.00
#&gt; TCGA.2G.AAG0.01     2   0.000      1.000 0.00 1.00 0.00
#&gt; TCGA.WZ.A7V3.01     3   0.000      0.952 0.00 0.00 1.00
#&gt; TCGA.2G.AALO.01     2   0.000      1.000 0.00 1.00 0.00
#&gt; TCGA.ZM.AA0F.01     1   0.207      0.934 0.94 0.00 0.06
#&gt; TCGA.XE.A8H5.01     3   0.000      0.952 0.00 0.00 1.00
#&gt; TCGA.XE.AANJ.01     1   0.334      0.865 0.88 0.00 0.12
#&gt; TCGA.YU.A94I.01     2   0.000      1.000 0.00 1.00 0.00
#&gt; TCGA.SO.A8JP.01     3   0.000      0.952 0.00 0.00 1.00
#&gt; TCGA.2G.AAM4.01     2   0.000      1.000 0.00 1.00 0.00
#&gt; TCGA.WZ.A7V5.01     1   0.207      0.934 0.94 0.00 0.06
#&gt; TCGA.YU.A90Y.01     2   0.000      1.000 0.00 1.00 0.00
#&gt; TCGA.2G.AALZ.01     2   0.000      1.000 0.00 1.00 0.00
#&gt; TCGA.WZ.A8D5.01     1   0.207      0.934 0.94 0.00 0.06
#&gt; TCGA.2G.AAGA.01     2   0.000      1.000 0.00 1.00 0.00
#&gt; TCGA.2G.AALY.01     2   0.000      1.000 0.00 1.00 0.00
#&gt; TCGA.2G.AAKG.01     2   0.000      1.000 0.00 1.00 0.00
#&gt; TCGA.2G.AAL5.01     2   0.000      1.000 0.00 1.00 0.00
#&gt; TCGA.YU.A94D.01     2   0.000      1.000 0.00 1.00 0.00
#&gt; TCGA.XE.AAOL.01     3   0.000      0.952 0.00 0.00 1.00
#&gt; TCGA.SN.A84X.01     2   0.000      1.000 0.00 1.00 0.00
#&gt; TCGA.2G.AAHC.01     1   0.000      0.923 1.00 0.00 0.00
#&gt; TCGA.2G.AAHT.01     3   0.000      0.952 0.00 0.00 1.00
#&gt; TCGA.2G.AALT.01     2   0.000      1.000 0.00 1.00 0.00
#&gt; TCGA.2G.AAM2.01     2   0.000      1.000 0.00 1.00 0.00
#&gt; TCGA.2G.AAFH.01     1   0.000      0.923 1.00 0.00 0.00
#&gt; TCGA.2G.AAFI.01     2   0.000      1.000 0.00 1.00 0.00
#&gt; TCGA.2G.AAHN.01     1   0.207      0.934 0.94 0.00 0.06
#&gt; TCGA.2G.AAGT.01     2   0.000      1.000 0.00 1.00 0.00
#&gt; TCGA.YU.A90W.01     3   0.000      0.952 0.00 0.00 1.00
#&gt; TCGA.2G.AAGJ.01     2   0.000      1.000 0.00 1.00 0.00
#&gt; TCGA.2G.AAGV.01     2   0.000      1.000 0.00 1.00 0.00
#&gt; TCGA.XE.A8H1.01     2   0.000      1.000 0.00 1.00 0.00
#&gt; TCGA.2G.AAFJ.01     2   0.000      1.000 0.00 1.00 0.00
#&gt; TCGA.2G.AAG5.01     2   0.000      1.000 0.00 1.00 0.00
#&gt; TCGA.X3.A8G4.01     2   0.000      1.000 0.00 1.00 0.00
#&gt; TCGA.2G.AAGY.01     2   0.000      1.000 0.00 1.00 0.00
#&gt; TCGA.2G.AAG8.01     2   0.000      1.000 0.00 1.00 0.00
#&gt; TCGA.S6.A8JW.01     3   0.000      0.952 0.00 0.00 1.00
#&gt; TCGA.2G.AAEW.01     3   0.619      0.237 0.42 0.00 0.58
#&gt; TCGA.2G.AAFO.01     2   0.000      1.000 0.00 1.00 0.00
#&gt; TCGA.YU.A912.01     3   0.000      0.952 0.00 0.00 1.00
#&gt; TCGA.2G.AAM3.01     2   0.000      1.000 0.00 1.00 0.00
#&gt; TCGA.VF.A8A8.01     2   0.000      1.000 0.00 1.00 0.00
#&gt; TCGA.SN.A84W.01     2   0.000      1.000 0.00 1.00 0.00
#&gt; TCGA.XE.AAO4.01     1   0.502      0.741 0.76 0.00 0.24
#&gt; TCGA.ZM.AA0N.01     1   0.000      0.923 1.00 0.00 0.00
#&gt; TCGA.VF.A8AE.01     1   0.207      0.934 0.94 0.00 0.06
#&gt; TCGA.2G.AAFZ.01     2   0.000      1.000 0.00 1.00 0.00
#&gt; TCGA.2G.AAGM.01     2   0.000      1.000 0.00 1.00 0.00
#&gt; TCGA.2G.AAKH.01     2   0.000      1.000 0.00 1.00 0.00
#&gt; TCGA.2G.AAF6.01     1   0.334      0.865 0.88 0.00 0.12
#&gt; TCGA.4K.AA1I.01     1   0.207      0.934 0.94 0.00 0.06
#&gt; TCGA.2G.AAFL.01     2   0.000      1.000 0.00 1.00 0.00
#&gt; TCGA.XY.A9T9.01     1   0.000      0.923 1.00 0.00 0.00
#&gt; TCGA.WZ.A7V4.01     1   0.207      0.934 0.94 0.00 0.06
#&gt; TCGA.S6.A8JX.01     3   0.000      0.952 0.00 0.00 1.00
#&gt; TCGA.2G.AAHL.01     3   0.000      0.952 0.00 0.00 1.00
#&gt; TCGA.4K.AA1H.01     1   0.207      0.934 0.94 0.00 0.06
#&gt; TCGA.ZM.AA06.01     1   0.334      0.865 0.88 0.00 0.12
#&gt; TCGA.VF.A8A9.01     1   0.000      0.923 1.00 0.00 0.00
#&gt; TCGA.4K.AA1G.01     3   0.000      0.952 0.00 0.00 1.00
#&gt; TCGA.2G.AAFE.01     3   0.000      0.952 0.00 0.00 1.00
#&gt; TCGA.ZM.AA0H.01     1   0.207      0.934 0.94 0.00 0.06
#&gt; TCGA.2G.AAKG.05     2   0.000      1.000 0.00 1.00 0.00
#&gt; TCGA.ZM.AA0B.01     1   0.000      0.923 1.00 0.00 0.00
#&gt; TCGA.2G.AALP.01     2   0.000      1.000 0.00 1.00 0.00
#&gt; TCGA.YU.A90P.01     2   0.000      1.000 0.00 1.00 0.00
#&gt; TCGA.2G.AAGS.01     2   0.000      1.000 0.00 1.00 0.00
#&gt; TCGA.W4.A7U3.01     2   0.000      1.000 0.00 1.00 0.00
#&gt; TCGA.SN.A6IS.01     1   0.296      0.880 0.90 0.00 0.10
#&gt; TCGA.2G.AAGF.01     2   0.000      1.000 0.00 1.00 0.00
#&gt; TCGA.2G.AAGE.01     2   0.000      1.000 0.00 1.00 0.00
#&gt; TCGA.2G.AAGY.05     3   0.000      0.952 0.00 0.00 1.00
#&gt; TCGA.2G.AAKL.01     2   0.000      1.000 0.00 1.00 0.00
#&gt; TCGA.2G.AAF8.01     1   0.400      0.742 0.84 0.16 0.00
#&gt; TCGA.2G.AALW.01     2   0.000      1.000 0.00 1.00 0.00
#&gt; TCGA.XE.AAOB.01     2   0.000      1.000 0.00 1.00 0.00
#&gt; TCGA.2G.AAF4.01     1   0.334      0.865 0.88 0.00 0.12
#&gt; TCGA.XE.AAOC.01     2   0.000      1.000 0.00 1.00 0.00
#&gt; TCGA.XE.AANR.01     2   0.000      1.000 0.00 1.00 0.00
#&gt; TCGA.2G.AAFG.05     1   0.000      0.923 1.00 0.00 0.00
#&gt; TCGA.2G.AALS.01     2   0.000      1.000 0.00 1.00 0.00
#&gt; TCGA.2G.AAG3.01     2   0.000      1.000 0.00 1.00 0.00
#&gt; TCGA.2G.AALN.01     2   0.000      1.000 0.00 1.00 0.00
#&gt; TCGA.ZM.AA0D.01     1   0.207      0.934 0.94 0.00 0.06
#&gt; TCGA.2G.AAG9.01     3   0.000      0.952 0.00 0.00 1.00
#&gt; TCGA.2G.AAGC.01     2   0.000      1.000 0.00 1.00 0.00
#&gt; TCGA.2X.A9D6.01     1   0.207      0.934 0.94 0.00 0.06
#&gt; TCGA.4K.AAAL.01     3   0.619      0.138 0.42 0.00 0.58
#&gt; TCGA.SN.A84Y.01     2   0.000      1.000 0.00 1.00 0.00
#&gt; TCGA.VF.A8AA.01     1   0.207      0.934 0.94 0.00 0.06
#&gt; TCGA.2G.AAH3.01     1   0.400      0.742 0.84 0.16 0.00
#&gt; TCGA.YU.A90Q.01     3   0.000      0.952 0.00 0.00 1.00
#&gt; TCGA.2G.AAKO.01     1   0.207      0.934 0.94 0.00 0.06
#&gt; TCGA.2G.AAGZ.01     2   0.000      1.000 0.00 1.00 0.00
#&gt; TCGA.VF.A8AB.01     1   0.000      0.923 1.00 0.00 0.00
#&gt; TCGA.2G.AALF.01     2   0.000      1.000 0.00 1.00 0.00
#&gt; TCGA.2G.AAL7.01     2   0.000      1.000 0.00 1.00 0.00
#&gt; TCGA.2G.AALQ.01     2   0.000      1.000 0.00 1.00 0.00
#&gt; TCGA.2G.AAFN.01     2   0.000      1.000 0.00 1.00 0.00
#&gt; TCGA.2G.AAFG.01     1   0.000      0.923 1.00 0.00 0.00
#&gt; TCGA.2G.AAGN.01     2   0.000      1.000 0.00 1.00 0.00
#&gt; TCGA.XE.AAOD.01     1   0.000      0.923 1.00 0.00 0.00
#&gt; TCGA.XE.AAOF.01     1   0.207      0.934 0.94 0.00 0.06
#&gt; TCGA.XY.A8S3.01     2   0.000      1.000 0.00 1.00 0.00
#&gt; TCGA.2G.AAFV.01     2   0.000      1.000 0.00 1.00 0.00
#&gt; TCGA.2G.AAHP.05     1   0.207      0.934 0.94 0.00 0.06
#&gt; TCGA.2G.AAH4.01     2   0.000      1.000 0.00 1.00 0.00
#&gt; TCGA.XE.AAO3.01     1   0.334      0.865 0.88 0.00 0.12
#&gt; TCGA.SB.A76C.01     3   0.000      0.952 0.00 0.00 1.00
#&gt; TCGA.2G.AAHG.01     3   0.207      0.898 0.06 0.00 0.94
#&gt; TCGA.XE.AAO6.01     1   0.296      0.880 0.90 0.00 0.10
#&gt; TCGA.SB.A6J6.01     1   0.000      0.923 1.00 0.00 0.00
#&gt; TCGA.YU.AA61.01     2   0.000      1.000 0.00 1.00 0.00
#&gt; TCGA.2G.AAG7.01     2   0.000      1.000 0.00 1.00 0.00
#&gt; TCGA.XY.A8S2.01     2   0.000      1.000 0.00 1.00 0.00
#&gt; TCGA.2G.AAEX.01     1   0.296      0.880 0.90 0.00 0.10
#&gt; TCGA.2G.AAH0.01     1   0.334      0.865 0.88 0.00 0.12
#&gt; TCGA.2G.AAKD.01     2   0.000      1.000 0.00 1.00 0.00
#&gt; TCGA.VF.A8AD.01     2   0.000      1.000 0.00 1.00 0.00
#&gt; TCGA.2G.AALR.01     2   0.000      1.000 0.00 1.00 0.00
#&gt; TCGA.2G.AAFM.01     2   0.000      1.000 0.00 1.00 0.00
#&gt; TCGA.2G.AALG.01     2   0.000      1.000 0.00 1.00 0.00
#&gt; TCGA.XE.AAOJ.01     2   0.000      1.000 0.00 1.00 0.00
#&gt; TCGA.2G.AAGI.01     2   0.000      1.000 0.00 1.00 0.00
#&gt; TCGA.W4.A7U2.01     1   0.334      0.865 0.88 0.00 0.12
#&gt; TCGA.S6.A8JY.01     3   0.207      0.898 0.06 0.00 0.94
#&gt; TCGA.2G.AAH8.01     3   0.000      0.952 0.00 0.00 1.00
#&gt; TCGA.2G.AAHP.01     1   0.334      0.865 0.88 0.00 0.12
#&gt; TCGA.2G.AAGW.01     2   0.000      1.000 0.00 1.00 0.00
#&gt; TCGA.2X.A9D5.01     1   0.296      0.917 0.90 0.00 0.10
#&gt; TCGA.2G.AAGX.01     2   0.000      1.000 0.00 1.00 0.00
</code></pre>

<script>
$('#tab-node-0-get-classes-2-a').parent().next().next().hide();
$('#tab-node-0-get-classes-2-a').click(function(){
  $('#tab-node-0-get-classes-2-a').parent().next().next().toggle();
  return(false);
});
</script>
</div>

<div id='tab-node-0-get-classes-3'>
<p><a id='tab-node-0-get-classes-3-a' style='color:#0366d6' href='#'>show/hide code output</a></p>
<pre><code class="r">cbind(get_classes(res, k = 4), get_membership(res, k = 4))
</code></pre>

<pre><code>#&gt;                 class entropy silhouette   p1   p2   p3   p4
#&gt; TCGA.XE.A8H4.01     1  0.0000      0.987 1.00 0.00 0.00 0.00
#&gt; TCGA.2G.AAF1.01     1  0.0000      0.987 1.00 0.00 0.00 0.00
#&gt; TCGA.W4.A7U4.01     2  0.0000      0.999 0.00 1.00 0.00 0.00
#&gt; TCGA.2G.AAGO.01     2  0.0000      0.999 0.00 1.00 0.00 0.00
#&gt; TCGA.VF.A8AC.01     1  0.0000      0.987 1.00 0.00 0.00 0.00
#&gt; TCGA.2G.AALX.01     2  0.0000      0.999 0.00 1.00 0.00 0.00
#&gt; TCGA.2G.AAGK.01     2  0.0000      0.999 0.00 1.00 0.00 0.00
#&gt; TCGA.2G.AAGG.01     2  0.0000      0.999 0.00 1.00 0.00 0.00
#&gt; TCGA.2G.AAGP.01     2  0.0000      0.999 0.00 1.00 0.00 0.00
#&gt; TCGA.2G.AAKM.01     2  0.0000      0.999 0.00 1.00 0.00 0.00
#&gt; TCGA.ZM.AA0E.01     1  0.0000      0.987 1.00 0.00 0.00 0.00
#&gt; TCGA.XE.A9SE.01     4  0.0000      0.999 0.00 0.00 0.00 1.00
#&gt; TCGA.2G.AAKO.05     1  0.0000      0.987 1.00 0.00 0.00 0.00
#&gt; TCGA.2G.AAFY.01     2  0.0000      0.999 0.00 1.00 0.00 0.00
#&gt; TCGA.XE.AANI.01     2  0.0000      0.999 0.00 1.00 0.00 0.00
#&gt; TCGA.YU.AA4L.01     2  0.0000      0.999 0.00 1.00 0.00 0.00
#&gt; TCGA.2G.AAGI.05     1  0.0000      0.987 1.00 0.00 0.00 0.00
#&gt; TCGA.XE.AANV.01     3  0.0000      0.977 0.00 0.00 1.00 0.00
#&gt; TCGA.YU.A90S.01     1  0.0000      0.987 1.00 0.00 0.00 0.00
#&gt; TCGA.XY.A89B.01     1  0.0000      0.987 1.00 0.00 0.00 0.00
#&gt; TCGA.ZM.AA05.01     1  0.0000      0.987 1.00 0.00 0.00 0.00
#&gt; TCGA.2G.AAHA.01     3  0.0707      0.960 0.02 0.00 0.98 0.00
#&gt; TCGA.2G.AAH2.01     2  0.0000      0.999 0.00 1.00 0.00 0.00
#&gt; TCGA.2G.AAG6.01     2  0.0000      0.999 0.00 1.00 0.00 0.00
#&gt; TCGA.2G.AAG0.01     2  0.0000      0.999 0.00 1.00 0.00 0.00
#&gt; TCGA.WZ.A7V3.01     3  0.0000      0.977 0.00 0.00 1.00 0.00
#&gt; TCGA.2G.AALO.01     2  0.0000      0.999 0.00 1.00 0.00 0.00
#&gt; TCGA.ZM.AA0F.01     1  0.0000      0.987 1.00 0.00 0.00 0.00
#&gt; TCGA.XE.A8H5.01     3  0.0000      0.977 0.00 0.00 1.00 0.00
#&gt; TCGA.XE.AANJ.01     4  0.0000      0.999 0.00 0.00 0.00 1.00
#&gt; TCGA.YU.A94I.01     2  0.0000      0.999 0.00 1.00 0.00 0.00
#&gt; TCGA.SO.A8JP.01     3  0.0000      0.977 0.00 0.00 1.00 0.00
#&gt; TCGA.2G.AAM4.01     2  0.0000      0.999 0.00 1.00 0.00 0.00
#&gt; TCGA.WZ.A7V5.01     1  0.0000      0.987 1.00 0.00 0.00 0.00
#&gt; TCGA.YU.A90Y.01     2  0.0000      0.999 0.00 1.00 0.00 0.00
#&gt; TCGA.2G.AALZ.01     2  0.0000      0.999 0.00 1.00 0.00 0.00
#&gt; TCGA.WZ.A8D5.01     1  0.0000      0.987 1.00 0.00 0.00 0.00
#&gt; TCGA.2G.AAGA.01     2  0.0000      0.999 0.00 1.00 0.00 0.00
#&gt; TCGA.2G.AALY.01     2  0.0000      0.999 0.00 1.00 0.00 0.00
#&gt; TCGA.2G.AAKG.01     2  0.0000      0.999 0.00 1.00 0.00 0.00
#&gt; TCGA.2G.AAL5.01     2  0.0000      0.999 0.00 1.00 0.00 0.00
#&gt; TCGA.YU.A94D.01     2  0.0000      0.999 0.00 1.00 0.00 0.00
#&gt; TCGA.XE.AAOL.01     3  0.0000      0.977 0.00 0.00 1.00 0.00
#&gt; TCGA.SN.A84X.01     2  0.0000      0.999 0.00 1.00 0.00 0.00
#&gt; TCGA.2G.AAHC.01     1  0.3172      0.810 0.84 0.00 0.00 0.16
#&gt; TCGA.2G.AAHT.01     3  0.0000      0.977 0.00 0.00 1.00 0.00
#&gt; TCGA.2G.AALT.01     2  0.0000      0.999 0.00 1.00 0.00 0.00
#&gt; TCGA.2G.AAM2.01     2  0.0000      0.999 0.00 1.00 0.00 0.00
#&gt; TCGA.2G.AAFH.01     4  0.0000      0.999 0.00 0.00 0.00 1.00
#&gt; TCGA.2G.AAFI.01     2  0.0000      0.999 0.00 1.00 0.00 0.00
#&gt; TCGA.2G.AAHN.01     1  0.0000      0.987 1.00 0.00 0.00 0.00
#&gt; TCGA.2G.AAGT.01     2  0.0000      0.999 0.00 1.00 0.00 0.00
#&gt; TCGA.YU.A90W.01     3  0.0000      0.977 0.00 0.00 1.00 0.00
#&gt; TCGA.2G.AAGJ.01     2  0.0000      0.999 0.00 1.00 0.00 0.00
#&gt; TCGA.2G.AAGV.01     2  0.0000      0.999 0.00 1.00 0.00 0.00
#&gt; TCGA.XE.A8H1.01     2  0.0000      0.999 0.00 1.00 0.00 0.00
#&gt; TCGA.2G.AAFJ.01     2  0.0000      0.999 0.00 1.00 0.00 0.00
#&gt; TCGA.2G.AAG5.01     2  0.0000      0.999 0.00 1.00 0.00 0.00
#&gt; TCGA.X3.A8G4.01     2  0.0000      0.999 0.00 1.00 0.00 0.00
#&gt; TCGA.2G.AAGY.01     2  0.0000      0.999 0.00 1.00 0.00 0.00
#&gt; TCGA.2G.AAG8.01     2  0.0000      0.999 0.00 1.00 0.00 0.00
#&gt; TCGA.S6.A8JW.01     3  0.0000      0.977 0.00 0.00 1.00 0.00
#&gt; TCGA.2G.AAEW.01     1  0.3172      0.811 0.84 0.00 0.16 0.00
#&gt; TCGA.2G.AAFO.01     2  0.0000      0.999 0.00 1.00 0.00 0.00
#&gt; TCGA.YU.A912.01     3  0.0000      0.977 0.00 0.00 1.00 0.00
#&gt; TCGA.2G.AAM3.01     2  0.0000      0.999 0.00 1.00 0.00 0.00
#&gt; TCGA.VF.A8A8.01     2  0.0000      0.999 0.00 1.00 0.00 0.00
#&gt; TCGA.SN.A84W.01     2  0.0000      0.999 0.00 1.00 0.00 0.00
#&gt; TCGA.XE.AAO4.01     1  0.0707      0.970 0.98 0.00 0.02 0.00
#&gt; TCGA.ZM.AA0N.01     4  0.0000      0.999 0.00 0.00 0.00 1.00
#&gt; TCGA.VF.A8AE.01     1  0.0000      0.987 1.00 0.00 0.00 0.00
#&gt; TCGA.2G.AAFZ.01     2  0.0000      0.999 0.00 1.00 0.00 0.00
#&gt; TCGA.2G.AAGM.01     2  0.0000      0.999 0.00 1.00 0.00 0.00
#&gt; TCGA.2G.AAKH.01     2  0.0000      0.999 0.00 1.00 0.00 0.00
#&gt; TCGA.2G.AAF6.01     4  0.0000      0.999 0.00 0.00 0.00 1.00
#&gt; TCGA.4K.AA1I.01     1  0.0000      0.987 1.00 0.00 0.00 0.00
#&gt; TCGA.2G.AAFL.01     2  0.0000      0.999 0.00 1.00 0.00 0.00
#&gt; TCGA.XY.A9T9.01     4  0.0707      0.977 0.02 0.00 0.00 0.98
#&gt; TCGA.WZ.A7V4.01     1  0.0000      0.987 1.00 0.00 0.00 0.00
#&gt; TCGA.S6.A8JX.01     3  0.0000      0.977 0.00 0.00 1.00 0.00
#&gt; TCGA.2G.AAHL.01     3  0.0000      0.977 0.00 0.00 1.00 0.00
#&gt; TCGA.4K.AA1H.01     1  0.0000      0.987 1.00 0.00 0.00 0.00
#&gt; TCGA.ZM.AA06.01     4  0.0000      0.999 0.00 0.00 0.00 1.00
#&gt; TCGA.VF.A8A9.01     4  0.0000      0.999 0.00 0.00 0.00 1.00
#&gt; TCGA.4K.AA1G.01     3  0.0000      0.977 0.00 0.00 1.00 0.00
#&gt; TCGA.2G.AAFE.01     3  0.0000      0.977 0.00 0.00 1.00 0.00
#&gt; TCGA.ZM.AA0H.01     1  0.0000      0.987 1.00 0.00 0.00 0.00
#&gt; TCGA.2G.AAKG.05     2  0.0000      0.999 0.00 1.00 0.00 0.00
#&gt; TCGA.ZM.AA0B.01     4  0.0000      0.999 0.00 0.00 0.00 1.00
#&gt; TCGA.2G.AALP.01     2  0.0000      0.999 0.00 1.00 0.00 0.00
#&gt; TCGA.YU.A90P.01     2  0.0000      0.999 0.00 1.00 0.00 0.00
#&gt; TCGA.2G.AAGS.01     2  0.0000      0.999 0.00 1.00 0.00 0.00
#&gt; TCGA.W4.A7U3.01     2  0.0000      0.999 0.00 1.00 0.00 0.00
#&gt; TCGA.SN.A6IS.01     4  0.0000      0.999 0.00 0.00 0.00 1.00
#&gt; TCGA.2G.AAGF.01     2  0.0000      0.999 0.00 1.00 0.00 0.00
#&gt; TCGA.2G.AAGE.01     2  0.0000      0.999 0.00 1.00 0.00 0.00
#&gt; TCGA.2G.AAGY.05     3  0.0000      0.977 0.00 0.00 1.00 0.00
#&gt; TCGA.2G.AAKL.01     2  0.0000      0.999 0.00 1.00 0.00 0.00
#&gt; TCGA.2G.AAF8.01     4  0.0000      0.999 0.00 0.00 0.00 1.00
#&gt; TCGA.2G.AALW.01     2  0.0000      0.999 0.00 1.00 0.00 0.00
#&gt; TCGA.XE.AAOB.01     2  0.0000      0.999 0.00 1.00 0.00 0.00
#&gt; TCGA.2G.AAF4.01     4  0.0000      0.999 0.00 0.00 0.00 1.00
#&gt; TCGA.XE.AAOC.01     2  0.0000      0.999 0.00 1.00 0.00 0.00
#&gt; TCGA.XE.AANR.01     2  0.2011      0.913 0.00 0.92 0.00 0.08
#&gt; TCGA.2G.AAFG.05     1  0.0000      0.987 1.00 0.00 0.00 0.00
#&gt; TCGA.2G.AALS.01     2  0.0000      0.999 0.00 1.00 0.00 0.00
#&gt; TCGA.2G.AAG3.01     2  0.0000      0.999 0.00 1.00 0.00 0.00
#&gt; TCGA.2G.AALN.01     2  0.0000      0.999 0.00 1.00 0.00 0.00
#&gt; TCGA.ZM.AA0D.01     1  0.0000      0.987 1.00 0.00 0.00 0.00
#&gt; TCGA.2G.AAG9.01     3  0.0000      0.977 0.00 0.00 1.00 0.00
#&gt; TCGA.2G.AAGC.01     2  0.0000      0.999 0.00 1.00 0.00 0.00
#&gt; TCGA.2X.A9D6.01     1  0.0000      0.987 1.00 0.00 0.00 0.00
#&gt; TCGA.4K.AAAL.01     3  0.5512      0.544 0.04 0.00 0.66 0.30
#&gt; TCGA.SN.A84Y.01     2  0.0000      0.999 0.00 1.00 0.00 0.00
#&gt; TCGA.VF.A8AA.01     1  0.0000      0.987 1.00 0.00 0.00 0.00
#&gt; TCGA.2G.AAH3.01     4  0.0000      0.999 0.00 0.00 0.00 1.00
#&gt; TCGA.YU.A90Q.01     3  0.0000      0.977 0.00 0.00 1.00 0.00
#&gt; TCGA.2G.AAKO.01     1  0.0000      0.987 1.00 0.00 0.00 0.00
#&gt; TCGA.2G.AAGZ.01     2  0.0000      0.999 0.00 1.00 0.00 0.00
#&gt; TCGA.VF.A8AB.01     4  0.0000      0.999 0.00 0.00 0.00 1.00
#&gt; TCGA.2G.AALF.01     2  0.0000      0.999 0.00 1.00 0.00 0.00
#&gt; TCGA.2G.AAL7.01     2  0.0000      0.999 0.00 1.00 0.00 0.00
#&gt; TCGA.2G.AALQ.01     2  0.0000      0.999 0.00 1.00 0.00 0.00
#&gt; TCGA.2G.AAFN.01     2  0.0000      0.999 0.00 1.00 0.00 0.00
#&gt; TCGA.2G.AAFG.01     4  0.0000      0.999 0.00 0.00 0.00 1.00
#&gt; TCGA.2G.AAGN.01     2  0.0000      0.999 0.00 1.00 0.00 0.00
#&gt; TCGA.XE.AAOD.01     1  0.0000      0.987 1.00 0.00 0.00 0.00
#&gt; TCGA.XE.AAOF.01     1  0.0000      0.987 1.00 0.00 0.00 0.00
#&gt; TCGA.XY.A8S3.01     2  0.0000      0.999 0.00 1.00 0.00 0.00
#&gt; TCGA.2G.AAFV.01     2  0.0000      0.999 0.00 1.00 0.00 0.00
#&gt; TCGA.2G.AAHP.05     1  0.0000      0.987 1.00 0.00 0.00 0.00
#&gt; TCGA.2G.AAH4.01     2  0.0000      0.999 0.00 1.00 0.00 0.00
#&gt; TCGA.XE.AAO3.01     4  0.0000      0.999 0.00 0.00 0.00 1.00
#&gt; TCGA.SB.A76C.01     3  0.0000      0.977 0.00 0.00 1.00 0.00
#&gt; TCGA.2G.AAHG.01     3  0.2345      0.886 0.00 0.00 0.90 0.10
#&gt; TCGA.XE.AAO6.01     4  0.0000      0.999 0.00 0.00 0.00 1.00
#&gt; TCGA.SB.A6J6.01     4  0.0000      0.999 0.00 0.00 0.00 1.00
#&gt; TCGA.YU.AA61.01     2  0.0000      0.999 0.00 1.00 0.00 0.00
#&gt; TCGA.2G.AAG7.01     2  0.0000      0.999 0.00 1.00 0.00 0.00
#&gt; TCGA.XY.A8S2.01     2  0.0000      0.999 0.00 1.00 0.00 0.00
#&gt; TCGA.2G.AAEX.01     4  0.0000      0.999 0.00 0.00 0.00 1.00
#&gt; TCGA.2G.AAH0.01     4  0.0000      0.999 0.00 0.00 0.00 1.00
#&gt; TCGA.2G.AAKD.01     2  0.0000      0.999 0.00 1.00 0.00 0.00
#&gt; TCGA.VF.A8AD.01     2  0.0000      0.999 0.00 1.00 0.00 0.00
#&gt; TCGA.2G.AALR.01     2  0.0000      0.999 0.00 1.00 0.00 0.00
#&gt; TCGA.2G.AAFM.01     2  0.0000      0.999 0.00 1.00 0.00 0.00
#&gt; TCGA.2G.AALG.01     2  0.0000      0.999 0.00 1.00 0.00 0.00
#&gt; TCGA.XE.AAOJ.01     2  0.0000      0.999 0.00 1.00 0.00 0.00
#&gt; TCGA.2G.AAGI.01     2  0.0000      0.999 0.00 1.00 0.00 0.00
#&gt; TCGA.W4.A7U2.01     4  0.0000      0.999 0.00 0.00 0.00 1.00
#&gt; TCGA.S6.A8JY.01     3  0.1211      0.945 0.00 0.00 0.96 0.04
#&gt; TCGA.2G.AAH8.01     3  0.0000      0.977 0.00 0.00 1.00 0.00
#&gt; TCGA.2G.AAHP.01     4  0.0000      0.999 0.00 0.00 0.00 1.00
#&gt; TCGA.2G.AAGW.01     2  0.0000      0.999 0.00 1.00 0.00 0.00
#&gt; TCGA.2X.A9D5.01     1  0.1211      0.952 0.96 0.00 0.04 0.00
#&gt; TCGA.2G.AAGX.01     2  0.0000      0.999 0.00 1.00 0.00 0.00
</code></pre>

<script>
$('#tab-node-0-get-classes-3-a').parent().next().next().hide();
$('#tab-node-0-get-classes-3-a').click(function(){
  $('#tab-node-0-get-classes-3-a').parent().next().next().toggle();
  return(false);
});
</script>
</div>

<div id='tab-node-0-get-classes-4'>
<p><a id='tab-node-0-get-classes-4-a' style='color:#0366d6' href='#'>show/hide code output</a></p>
<pre><code class="r">cbind(get_classes(res, k = 5), get_membership(res, k = 5))
</code></pre>

<pre><code>#&gt;                 class entropy silhouette   p1   p2   p3   p4   p5
#&gt; TCGA.XE.A8H4.01     1  0.0000      0.923 1.00 0.00 0.00 0.00 0.00
#&gt; TCGA.2G.AAF1.01     1  0.0000      0.923 1.00 0.00 0.00 0.00 0.00
#&gt; TCGA.W4.A7U4.01     2  0.3109      0.758 0.00 0.80 0.00 0.00 0.20
#&gt; TCGA.2G.AAGO.01     2  0.3109      0.758 0.00 0.80 0.00 0.00 0.20
#&gt; TCGA.VF.A8AC.01     1  0.1410      0.917 0.94 0.00 0.00 0.00 0.06
#&gt; TCGA.2G.AALX.01     2  0.0000      0.858 0.00 1.00 0.00 0.00 0.00
#&gt; TCGA.2G.AAGK.01     2  0.3109      0.758 0.00 0.80 0.00 0.00 0.20
#&gt; TCGA.2G.AAGG.01     2  0.0000      0.858 0.00 1.00 0.00 0.00 0.00
#&gt; TCGA.2G.AAGP.01     2  0.3109      0.758 0.00 0.80 0.00 0.00 0.20
#&gt; TCGA.2G.AAKM.01     2  0.3109      0.758 0.00 0.80 0.00 0.00 0.20
#&gt; TCGA.ZM.AA0E.01     1  0.2280      0.902 0.88 0.00 0.00 0.00 0.12
#&gt; TCGA.XE.A9SE.01     4  0.4060      0.723 0.00 0.00 0.00 0.64 0.36
#&gt; TCGA.2G.AAKO.05     1  0.0000      0.923 1.00 0.00 0.00 0.00 0.00
#&gt; TCGA.2G.AAFY.01     2  0.3109      0.758 0.00 0.80 0.00 0.00 0.20
#&gt; TCGA.XE.AANI.01     2  0.0000      0.858 0.00 1.00 0.00 0.00 0.00
#&gt; TCGA.YU.AA4L.01     2  0.0000      0.858 0.00 1.00 0.00 0.00 0.00
#&gt; TCGA.2G.AAGI.05     1  0.1410      0.917 0.94 0.00 0.00 0.00 0.06
#&gt; TCGA.XE.AANV.01     3  0.2732      0.863 0.00 0.00 0.84 0.00 0.16
#&gt; TCGA.YU.A90S.01     1  0.0000      0.923 1.00 0.00 0.00 0.00 0.00
#&gt; TCGA.XY.A89B.01     1  0.2280      0.903 0.88 0.00 0.00 0.00 0.12
#&gt; TCGA.ZM.AA05.01     1  0.1732      0.914 0.92 0.00 0.00 0.00 0.08
#&gt; TCGA.2G.AAHA.01     3  0.2516      0.870 0.00 0.00 0.86 0.00 0.14
#&gt; TCGA.2G.AAH2.01     2  0.0000      0.858 0.00 1.00 0.00 0.00 0.00
#&gt; TCGA.2G.AAG6.01     2  0.0000      0.858 0.00 1.00 0.00 0.00 0.00
#&gt; TCGA.2G.AAG0.01     2  0.3109      0.758 0.00 0.80 0.00 0.00 0.20
#&gt; TCGA.WZ.A7V3.01     3  0.1216      0.897 0.00 0.00 0.96 0.02 0.02
#&gt; TCGA.2G.AALO.01     2  0.0000      0.858 0.00 1.00 0.00 0.00 0.00
#&gt; TCGA.ZM.AA0F.01     1  0.0000      0.923 1.00 0.00 0.00 0.00 0.00
#&gt; TCGA.XE.A8H5.01     3  0.1410      0.893 0.00 0.00 0.94 0.00 0.06
#&gt; TCGA.XE.AANJ.01     4  0.1043      0.895 0.00 0.00 0.00 0.96 0.04
#&gt; TCGA.YU.A94I.01     2  0.0000      0.858 0.00 1.00 0.00 0.00 0.00
#&gt; TCGA.SO.A8JP.01     3  0.2280      0.887 0.00 0.00 0.88 0.00 0.12
#&gt; TCGA.2G.AAM4.01     2  0.0000      0.858 0.00 1.00 0.00 0.00 0.00
#&gt; TCGA.WZ.A7V5.01     1  0.2516      0.894 0.86 0.00 0.00 0.00 0.14
#&gt; TCGA.YU.A90Y.01     2  0.3109      0.758 0.00 0.80 0.00 0.00 0.20
#&gt; TCGA.2G.AALZ.01     2  0.0000      0.858 0.00 1.00 0.00 0.00 0.00
#&gt; TCGA.WZ.A8D5.01     1  0.2516      0.894 0.86 0.00 0.00 0.00 0.14
#&gt; TCGA.2G.AAGA.01     2  0.3109      0.758 0.00 0.80 0.00 0.00 0.20
#&gt; TCGA.2G.AALY.01     2  0.0000      0.858 0.00 1.00 0.00 0.00 0.00
#&gt; TCGA.2G.AAKG.01     2  0.3109      0.758 0.00 0.80 0.00 0.00 0.20
#&gt; TCGA.2G.AAL5.01     2  0.0000      0.858 0.00 1.00 0.00 0.00 0.00
#&gt; TCGA.YU.A94D.01     2  0.0000      0.858 0.00 1.00 0.00 0.00 0.00
#&gt; TCGA.XE.AAOL.01     3  0.2020      0.889 0.00 0.00 0.90 0.00 0.10
#&gt; TCGA.SN.A84X.01     2  0.0000      0.858 0.00 1.00 0.00 0.00 0.00
#&gt; TCGA.2G.AAHC.01     1  0.4644      0.524 0.68 0.00 0.00 0.28 0.04
#&gt; TCGA.2G.AAHT.01     3  0.2020      0.886 0.00 0.00 0.90 0.00 0.10
#&gt; TCGA.2G.AALT.01     2  0.0000      0.858 0.00 1.00 0.00 0.00 0.00
#&gt; TCGA.2G.AAM2.01     2  0.0000      0.858 0.00 1.00 0.00 0.00 0.00
#&gt; TCGA.2G.AAFH.01     4  0.2280      0.881 0.00 0.00 0.00 0.88 0.12
#&gt; TCGA.2G.AAFI.01     2  0.3109      0.758 0.00 0.80 0.00 0.00 0.20
#&gt; TCGA.2G.AAHN.01     1  0.0000      0.923 1.00 0.00 0.00 0.00 0.00
#&gt; TCGA.2G.AAGT.01     2  0.0000      0.858 0.00 1.00 0.00 0.00 0.00
#&gt; TCGA.YU.A90W.01     3  0.2012      0.889 0.00 0.00 0.92 0.02 0.06
#&gt; TCGA.2G.AAGJ.01     2  0.3109      0.758 0.00 0.80 0.00 0.00 0.20
#&gt; TCGA.2G.AAGV.01     2  0.0000      0.858 0.00 1.00 0.00 0.00 0.00
#&gt; TCGA.XE.A8H1.01     2  0.3109      0.758 0.00 0.80 0.00 0.00 0.20
#&gt; TCGA.2G.AAFJ.01     2  0.0000      0.858 0.00 1.00 0.00 0.00 0.00
#&gt; TCGA.2G.AAG5.01     2  0.0000      0.858 0.00 1.00 0.00 0.00 0.00
#&gt; TCGA.X3.A8G4.01     2  0.2280      0.801 0.00 0.88 0.00 0.00 0.12
#&gt; TCGA.2G.AAGY.01     2  0.0000      0.858 0.00 1.00 0.00 0.00 0.00
#&gt; TCGA.2G.AAG8.01     2  0.3109      0.758 0.00 0.80 0.00 0.00 0.20
#&gt; TCGA.S6.A8JW.01     3  0.2020      0.889 0.00 0.00 0.90 0.00 0.10
#&gt; TCGA.2G.AAEW.01     1  0.5444      0.687 0.66 0.00 0.16 0.00 0.18
#&gt; TCGA.2G.AAFO.01     2  0.3109      0.758 0.00 0.80 0.00 0.00 0.20
#&gt; TCGA.YU.A912.01     3  0.2020      0.886 0.00 0.00 0.90 0.00 0.10
#&gt; TCGA.2G.AAM3.01     2  0.0000      0.858 0.00 1.00 0.00 0.00 0.00
#&gt; TCGA.VF.A8A8.01     2  0.0000      0.858 0.00 1.00 0.00 0.00 0.00
#&gt; TCGA.SN.A84W.01     2  0.0000      0.858 0.00 1.00 0.00 0.00 0.00
#&gt; TCGA.XE.AAO4.01     1  0.4075      0.834 0.78 0.00 0.06 0.00 0.16
#&gt; TCGA.ZM.AA0N.01     4  0.2020      0.891 0.00 0.00 0.00 0.90 0.10
#&gt; TCGA.VF.A8AE.01     1  0.0000      0.923 1.00 0.00 0.00 0.00 0.00
#&gt; TCGA.2G.AAFZ.01     2  0.0000      0.858 0.00 1.00 0.00 0.00 0.00
#&gt; TCGA.2G.AAGM.01     2  0.0000      0.858 0.00 1.00 0.00 0.00 0.00
#&gt; TCGA.2G.AAKH.01     2  0.3109      0.758 0.00 0.80 0.00 0.00 0.20
#&gt; TCGA.2G.AAF6.01     4  0.1043      0.888 0.00 0.00 0.00 0.96 0.04
#&gt; TCGA.4K.AA1I.01     1  0.0000      0.923 1.00 0.00 0.00 0.00 0.00
#&gt; TCGA.2G.AAFL.01     2  0.3109      0.758 0.00 0.80 0.00 0.00 0.20
#&gt; TCGA.XY.A9T9.01     4  0.0609      0.899 0.00 0.00 0.00 0.98 0.02
#&gt; TCGA.WZ.A7V4.01     1  0.0000      0.923 1.00 0.00 0.00 0.00 0.00
#&gt; TCGA.S6.A8JX.01     3  0.2280      0.884 0.00 0.00 0.88 0.00 0.12
#&gt; TCGA.2G.AAHL.01     3  0.2020      0.886 0.00 0.00 0.90 0.00 0.10
#&gt; TCGA.4K.AA1H.01     1  0.0000      0.923 1.00 0.00 0.00 0.00 0.00
#&gt; TCGA.ZM.AA06.01     4  0.0609      0.896 0.00 0.00 0.00 0.98 0.02
#&gt; TCGA.VF.A8A9.01     4  0.2020      0.891 0.00 0.00 0.00 0.90 0.10
#&gt; TCGA.4K.AA1G.01     3  0.2020      0.896 0.00 0.00 0.90 0.00 0.10
#&gt; TCGA.2G.AAFE.01     3  0.1732      0.889 0.00 0.00 0.92 0.00 0.08
#&gt; TCGA.ZM.AA0H.01     1  0.2516      0.894 0.86 0.00 0.00 0.00 0.14
#&gt; TCGA.2G.AAKG.05     2  0.3109      0.758 0.00 0.80 0.00 0.00 0.20
#&gt; TCGA.ZM.AA0B.01     4  0.2020      0.891 0.00 0.00 0.00 0.90 0.10
#&gt; TCGA.2G.AALP.01     2  0.0000      0.858 0.00 1.00 0.00 0.00 0.00
#&gt; TCGA.YU.A90P.01     2  0.3109      0.758 0.00 0.80 0.00 0.00 0.20
#&gt; TCGA.2G.AAGS.01     2  0.0000      0.858 0.00 1.00 0.00 0.00 0.00
#&gt; TCGA.W4.A7U3.01     2  0.0000      0.858 0.00 1.00 0.00 0.00 0.00
#&gt; TCGA.SN.A6IS.01     4  0.1043      0.895 0.00 0.00 0.00 0.96 0.04
#&gt; TCGA.2G.AAGF.01     2  0.0000      0.858 0.00 1.00 0.00 0.00 0.00
#&gt; TCGA.2G.AAGE.01     2  0.0609      0.849 0.00 0.98 0.00 0.00 0.02
#&gt; TCGA.2G.AAGY.05     3  0.1043      0.895 0.00 0.00 0.96 0.00 0.04
#&gt; TCGA.2G.AAKL.01     2  0.3109      0.758 0.00 0.80 0.00 0.00 0.20
#&gt; TCGA.2G.AAF8.01     4  0.4126      0.719 0.00 0.00 0.00 0.62 0.38
#&gt; TCGA.2G.AALW.01     2  0.0000      0.858 0.00 1.00 0.00 0.00 0.00
#&gt; TCGA.XE.AAOB.01     2  0.3109      0.758 0.00 0.80 0.00 0.00 0.20
#&gt; TCGA.2G.AAF4.01     4  0.0609      0.896 0.00 0.00 0.00 0.98 0.02
#&gt; TCGA.XE.AAOC.01     2  0.0000      0.858 0.00 1.00 0.00 0.00 0.00
#&gt; TCGA.XE.AANR.01     5  0.5659      0.000 0.00 0.32 0.00 0.10 0.58
#&gt; TCGA.2G.AAFG.05     1  0.1216      0.904 0.96 0.00 0.00 0.02 0.02
#&gt; TCGA.2G.AALS.01     2  0.3109      0.758 0.00 0.80 0.00 0.00 0.20
#&gt; TCGA.2G.AAG3.01     2  0.0000      0.858 0.00 1.00 0.00 0.00 0.00
#&gt; TCGA.2G.AALN.01     2  0.0000      0.858 0.00 1.00 0.00 0.00 0.00
#&gt; TCGA.ZM.AA0D.01     1  0.0000      0.923 1.00 0.00 0.00 0.00 0.00
#&gt; TCGA.2G.AAG9.01     3  0.2020      0.886 0.00 0.00 0.90 0.00 0.10
#&gt; TCGA.2G.AAGC.01     2  0.3109      0.758 0.00 0.80 0.00 0.00 0.20
#&gt; TCGA.2X.A9D6.01     1  0.2516      0.894 0.86 0.00 0.00 0.00 0.14
#&gt; TCGA.4K.AAAL.01     3  0.7151      0.555 0.04 0.00 0.48 0.18 0.30
#&gt; TCGA.SN.A84Y.01     2  0.3109      0.758 0.00 0.80 0.00 0.00 0.20
#&gt; TCGA.VF.A8AA.01     1  0.0000      0.923 1.00 0.00 0.00 0.00 0.00
#&gt; TCGA.2G.AAH3.01     4  0.4060      0.723 0.00 0.00 0.00 0.64 0.36
#&gt; TCGA.YU.A90Q.01     3  0.2020      0.886 0.00 0.00 0.90 0.00 0.10
#&gt; TCGA.2G.AAKO.01     1  0.0000      0.923 1.00 0.00 0.00 0.00 0.00
#&gt; TCGA.2G.AAGZ.01     2  0.3109      0.758 0.00 0.80 0.00 0.00 0.20
#&gt; TCGA.VF.A8AB.01     4  0.5394      0.634 0.06 0.00 0.00 0.54 0.40
#&gt; TCGA.2G.AALF.01     2  0.0000      0.858 0.00 1.00 0.00 0.00 0.00
#&gt; TCGA.2G.AAL7.01     2  0.3109      0.758 0.00 0.80 0.00 0.00 0.20
#&gt; TCGA.2G.AALQ.01     2  0.0000      0.858 0.00 1.00 0.00 0.00 0.00
#&gt; TCGA.2G.AAFN.01     2  0.3109      0.758 0.00 0.80 0.00 0.00 0.20
#&gt; TCGA.2G.AAFG.01     4  0.2280      0.887 0.00 0.00 0.00 0.88 0.12
#&gt; TCGA.2G.AAGN.01     2  0.3109      0.758 0.00 0.80 0.00 0.00 0.20
#&gt; TCGA.XE.AAOD.01     1  0.2012      0.881 0.92 0.00 0.00 0.02 0.06
#&gt; TCGA.XE.AAOF.01     1  0.1732      0.914 0.92 0.00 0.00 0.00 0.08
#&gt; TCGA.XY.A8S3.01     2  0.0000      0.858 0.00 1.00 0.00 0.00 0.00
#&gt; TCGA.2G.AAFV.01     2  0.0000      0.858 0.00 1.00 0.00 0.00 0.00
#&gt; TCGA.2G.AAHP.05     1  0.2516      0.894 0.86 0.00 0.00 0.00 0.14
#&gt; TCGA.2G.AAH4.01     2  0.0000      0.858 0.00 1.00 0.00 0.00 0.00
#&gt; TCGA.XE.AAO3.01     4  0.2280      0.884 0.00 0.00 0.00 0.88 0.12
#&gt; TCGA.SB.A76C.01     3  0.1732      0.895 0.00 0.00 0.92 0.00 0.08
#&gt; TCGA.2G.AAHG.01     3  0.5904      0.647 0.00 0.00 0.60 0.20 0.20
#&gt; TCGA.XE.AAO6.01     4  0.0609      0.896 0.00 0.00 0.00 0.98 0.02
#&gt; TCGA.SB.A6J6.01     4  0.0609      0.899 0.00 0.00 0.00 0.98 0.02
#&gt; TCGA.YU.AA61.01     2  0.0000      0.858 0.00 1.00 0.00 0.00 0.00
#&gt; TCGA.2G.AAG7.01     2  0.0000      0.858 0.00 1.00 0.00 0.00 0.00
#&gt; TCGA.XY.A8S2.01     2  0.3109      0.758 0.00 0.80 0.00 0.00 0.20
#&gt; TCGA.2G.AAEX.01     4  0.0609      0.896 0.00 0.00 0.00 0.98 0.02
#&gt; TCGA.2G.AAH0.01     4  0.0609      0.896 0.00 0.00 0.00 0.98 0.02
#&gt; TCGA.2G.AAKD.01     2  0.3109      0.758 0.00 0.80 0.00 0.00 0.20
#&gt; TCGA.VF.A8AD.01     2  0.3109      0.758 0.00 0.80 0.00 0.00 0.20
#&gt; TCGA.2G.AALR.01     2  0.0000      0.858 0.00 1.00 0.00 0.00 0.00
#&gt; TCGA.2G.AAFM.01     2  0.3109      0.758 0.00 0.80 0.00 0.00 0.20
#&gt; TCGA.2G.AALG.01     2  0.0000      0.858 0.00 1.00 0.00 0.00 0.00
#&gt; TCGA.XE.AAOJ.01     2  0.0000      0.858 0.00 1.00 0.00 0.00 0.00
#&gt; TCGA.2G.AAGI.01     2  0.0000      0.858 0.00 1.00 0.00 0.00 0.00
#&gt; TCGA.W4.A7U2.01     4  0.1410      0.896 0.00 0.00 0.00 0.94 0.06
#&gt; TCGA.S6.A8JY.01     3  0.5555      0.717 0.00 0.00 0.64 0.14 0.22
#&gt; TCGA.2G.AAH8.01     3  0.2280      0.887 0.00 0.00 0.88 0.00 0.12
#&gt; TCGA.2G.AAHP.01     4  0.2280      0.884 0.00 0.00 0.00 0.88 0.12
#&gt; TCGA.2G.AAGW.01     2  0.0000      0.858 0.00 1.00 0.00 0.00 0.00
#&gt; TCGA.2X.A9D5.01     1  0.6075      0.707 0.64 0.00 0.04 0.10 0.22
#&gt; TCGA.2G.AAGX.01     2  0.0000      0.858 0.00 1.00 0.00 0.00 0.00
</code></pre>

<script>
$('#tab-node-0-get-classes-4-a').parent().next().next().hide();
$('#tab-node-0-get-classes-4-a').click(function(){
  $('#tab-node-0-get-classes-4-a').parent().next().next().toggle();
  return(false);
});
</script>
</div>

<div id='tab-node-0-get-classes-5'>
<p><a id='tab-node-0-get-classes-5-a' style='color:#0366d6' href='#'>show/hide code output</a></p>
<pre><code class="r">cbind(get_classes(res, k = 6), get_membership(res, k = 6))
</code></pre>

<pre><code>#&gt;                 class entropy silhouette   p1   p2   p3   p4   p5   p6
#&gt; TCGA.XE.A8H4.01     1  0.0000     0.8839 1.00 0.00 0.00 0.00 0.00 0.00
#&gt; TCGA.2G.AAF1.01     1  0.0000     0.8839 1.00 0.00 0.00 0.00 0.00 0.00
#&gt; TCGA.W4.A7U4.01     2  0.3647     0.7255 0.00 0.64 0.00 0.36 0.00 0.00
#&gt; TCGA.2G.AAGO.01     2  0.3647     0.7255 0.00 0.64 0.00 0.36 0.00 0.00
#&gt; TCGA.VF.A8AC.01     1  0.1480     0.8787 0.94 0.00 0.00 0.04 0.02 0.00
#&gt; TCGA.2G.AALX.01     2  0.0000     0.8260 0.00 1.00 0.00 0.00 0.00 0.00
#&gt; TCGA.2G.AAGK.01     2  0.3647     0.7255 0.00 0.64 0.00 0.36 0.00 0.00
#&gt; TCGA.2G.AAGG.01     2  0.0000     0.8260 0.00 1.00 0.00 0.00 0.00 0.00
#&gt; TCGA.2G.AAGP.01     2  0.3706     0.7121 0.00 0.62 0.00 0.38 0.00 0.00
#&gt; TCGA.2G.AAKM.01     2  0.3647     0.7255 0.00 0.64 0.00 0.36 0.00 0.00
#&gt; TCGA.ZM.AA0E.01     1  0.3382     0.8523 0.84 0.00 0.04 0.04 0.08 0.00
#&gt; TCGA.XE.A9SE.01     5  0.3309     0.6556 0.00 0.00 0.00 0.00 0.72 0.28
#&gt; TCGA.2G.AAKO.05     1  0.0000     0.8839 1.00 0.00 0.00 0.00 0.00 0.00
#&gt; TCGA.2G.AAFY.01     2  0.3706     0.7121 0.00 0.62 0.00 0.38 0.00 0.00
#&gt; TCGA.XE.AANI.01     2  0.0000     0.8260 0.00 1.00 0.00 0.00 0.00 0.00
#&gt; TCGA.YU.AA4L.01     2  0.1480     0.7804 0.00 0.94 0.00 0.04 0.02 0.00
#&gt; TCGA.2G.AAGI.05     1  0.2190     0.8713 0.90 0.00 0.00 0.04 0.06 0.00
#&gt; TCGA.XE.AANV.01     3  0.1807     0.7847 0.00 0.00 0.92 0.02 0.06 0.00
#&gt; TCGA.YU.A90S.01     1  0.0000     0.8839 1.00 0.00 0.00 0.00 0.00 0.00
#&gt; TCGA.XY.A89B.01     1  0.3103     0.8603 0.86 0.00 0.04 0.04 0.06 0.00
#&gt; TCGA.ZM.AA05.01     1  0.1865     0.8753 0.92 0.00 0.00 0.04 0.04 0.00
#&gt; TCGA.2G.AAHA.01     3  0.1807     0.7847 0.00 0.00 0.92 0.02 0.06 0.00
#&gt; TCGA.2G.AAH2.01     2  0.0000     0.8260 0.00 1.00 0.00 0.00 0.00 0.00
#&gt; TCGA.2G.AAG6.01     2  0.0000     0.8260 0.00 1.00 0.00 0.00 0.00 0.00
#&gt; TCGA.2G.AAG0.01     2  0.3706     0.7121 0.00 0.62 0.00 0.38 0.00 0.00
#&gt; TCGA.WZ.A7V3.01     3  0.4713     0.7826 0.00 0.00 0.72 0.14 0.02 0.12
#&gt; TCGA.2G.AALO.01     2  0.0000     0.8260 0.00 1.00 0.00 0.00 0.00 0.00
#&gt; TCGA.ZM.AA0F.01     1  0.0000     0.8839 1.00 0.00 0.00 0.00 0.00 0.00
#&gt; TCGA.XE.A8H5.01     3  0.2956     0.8329 0.00 0.00 0.84 0.12 0.04 0.00
#&gt; TCGA.XE.AANJ.01     6  0.0547     0.6964 0.00 0.00 0.00 0.00 0.02 0.98
#&gt; TCGA.YU.A94I.01     2  0.1480     0.7804 0.00 0.94 0.00 0.04 0.02 0.00
#&gt; TCGA.SO.A8JP.01     3  0.5144     0.7537 0.00 0.00 0.56 0.34 0.10 0.00
#&gt; TCGA.2G.AAM4.01     2  0.0000     0.8260 0.00 1.00 0.00 0.00 0.00 0.00
#&gt; TCGA.WZ.A7V5.01     1  0.3382     0.8523 0.84 0.00 0.04 0.04 0.08 0.00
#&gt; TCGA.YU.A90Y.01     2  0.3647     0.7255 0.00 0.64 0.00 0.36 0.00 0.00
#&gt; TCGA.2G.AALZ.01     2  0.0000     0.8260 0.00 1.00 0.00 0.00 0.00 0.00
#&gt; TCGA.WZ.A8D5.01     1  0.3697     0.8421 0.82 0.00 0.06 0.04 0.08 0.00
#&gt; TCGA.2G.AAGA.01     2  0.3647     0.7255 0.00 0.64 0.00 0.36 0.00 0.00
#&gt; TCGA.2G.AALY.01     2  0.0000     0.8260 0.00 1.00 0.00 0.00 0.00 0.00
#&gt; TCGA.2G.AAKG.01     2  0.3647     0.7255 0.00 0.64 0.00 0.36 0.00 0.00
#&gt; TCGA.2G.AAL5.01     2  0.0000     0.8260 0.00 1.00 0.00 0.00 0.00 0.00
#&gt; TCGA.YU.A94D.01     2  0.0000     0.8260 0.00 1.00 0.00 0.00 0.00 0.00
#&gt; TCGA.XE.AAOL.01     3  0.4475     0.8042 0.00 0.00 0.70 0.20 0.10 0.00
#&gt; TCGA.SN.A84X.01     2  0.0000     0.8260 0.00 1.00 0.00 0.00 0.00 0.00
#&gt; TCGA.2G.AAHC.01     1  0.4608     0.5221 0.68 0.00 0.00 0.00 0.10 0.22
#&gt; TCGA.2G.AAHT.01     3  0.1480     0.8230 0.00 0.00 0.94 0.02 0.04 0.00
#&gt; TCGA.2G.AALT.01     2  0.0000     0.8260 0.00 1.00 0.00 0.00 0.00 0.00
#&gt; TCGA.2G.AAM2.01     2  0.0000     0.8260 0.00 1.00 0.00 0.00 0.00 0.00
#&gt; TCGA.2G.AAFH.01     6  0.4534     0.2766 0.00 0.00 0.00 0.04 0.38 0.58
#&gt; TCGA.2G.AAFI.01     2  0.3647     0.7255 0.00 0.64 0.00 0.36 0.00 0.00
#&gt; TCGA.2G.AAHN.01     1  0.0000     0.8839 1.00 0.00 0.00 0.00 0.00 0.00
#&gt; TCGA.2G.AAGT.01     2  0.1480     0.7804 0.00 0.94 0.00 0.04 0.02 0.00
#&gt; TCGA.YU.A90W.01     3  0.3258     0.8325 0.00 0.00 0.84 0.10 0.04 0.02
#&gt; TCGA.2G.AAGJ.01     2  0.3706     0.7121 0.00 0.62 0.00 0.38 0.00 0.00
#&gt; TCGA.2G.AAGV.01     2  0.0000     0.8260 0.00 1.00 0.00 0.00 0.00 0.00
#&gt; TCGA.XE.A8H1.01     2  0.3647     0.7255 0.00 0.64 0.00 0.36 0.00 0.00
#&gt; TCGA.2G.AAFJ.01     2  0.0000     0.8260 0.00 1.00 0.00 0.00 0.00 0.00
#&gt; TCGA.2G.AAG5.01     2  0.0000     0.8260 0.00 1.00 0.00 0.00 0.00 0.00
#&gt; TCGA.X3.A8G4.01     2  0.2631     0.7788 0.00 0.82 0.00 0.18 0.00 0.00
#&gt; TCGA.2G.AAGY.01     2  0.0000     0.8260 0.00 1.00 0.00 0.00 0.00 0.00
#&gt; TCGA.2G.AAG8.01     2  0.3706     0.7121 0.00 0.62 0.00 0.38 0.00 0.00
#&gt; TCGA.S6.A8JW.01     3  0.4631     0.7703 0.00 0.00 0.62 0.32 0.06 0.00
#&gt; TCGA.2G.AAEW.01     1  0.5833     0.3982 0.50 0.00 0.38 0.04 0.08 0.00
#&gt; TCGA.2G.AAFO.01     2  0.3706     0.7121 0.00 0.62 0.00 0.38 0.00 0.00
#&gt; TCGA.YU.A912.01     3  0.0937     0.8184 0.00 0.00 0.96 0.04 0.00 0.00
#&gt; TCGA.2G.AAM3.01     2  0.0000     0.8260 0.00 1.00 0.00 0.00 0.00 0.00
#&gt; TCGA.VF.A8A8.01     2  0.0000     0.8260 0.00 1.00 0.00 0.00 0.00 0.00
#&gt; TCGA.SN.A84W.01     2  0.0000     0.8260 0.00 1.00 0.00 0.00 0.00 0.00
#&gt; TCGA.XE.AAO4.01     1  0.5236     0.6922 0.66 0.00 0.22 0.04 0.08 0.00
#&gt; TCGA.ZM.AA0N.01     6  0.3916     0.4583 0.00 0.00 0.00 0.02 0.30 0.68
#&gt; TCGA.VF.A8AE.01     1  0.0000     0.8839 1.00 0.00 0.00 0.00 0.00 0.00
#&gt; TCGA.2G.AAFZ.01     2  0.0000     0.8260 0.00 1.00 0.00 0.00 0.00 0.00
#&gt; TCGA.2G.AAGM.01     2  0.0000     0.8260 0.00 1.00 0.00 0.00 0.00 0.00
#&gt; TCGA.2G.AAKH.01     2  0.3647     0.7255 0.00 0.64 0.00 0.36 0.00 0.00
#&gt; TCGA.2G.AAF6.01     6  0.0937     0.6914 0.00 0.00 0.00 0.04 0.00 0.96
#&gt; TCGA.4K.AA1I.01     1  0.0000     0.8839 1.00 0.00 0.00 0.00 0.00 0.00
#&gt; TCGA.2G.AAFL.01     2  0.3706     0.7121 0.00 0.62 0.00 0.38 0.00 0.00
#&gt; TCGA.XY.A9T9.01     6  0.0547     0.6964 0.00 0.00 0.00 0.00 0.02 0.98
#&gt; TCGA.WZ.A7V4.01     1  0.0000     0.8839 1.00 0.00 0.00 0.00 0.00 0.00
#&gt; TCGA.S6.A8JX.01     3  0.5083     0.7550 0.00 0.00 0.58 0.32 0.10 0.00
#&gt; TCGA.2G.AAHL.01     3  0.0547     0.8238 0.00 0.00 0.98 0.02 0.00 0.00
#&gt; TCGA.4K.AA1H.01     1  0.0000     0.8839 1.00 0.00 0.00 0.00 0.00 0.00
#&gt; TCGA.ZM.AA06.01     6  0.0937     0.6889 0.00 0.00 0.00 0.04 0.00 0.96
#&gt; TCGA.VF.A8A9.01     6  0.3409     0.4752 0.00 0.00 0.00 0.00 0.30 0.70
#&gt; TCGA.4K.AA1G.01     3  0.2728     0.8283 0.00 0.00 0.86 0.10 0.04 0.00
#&gt; TCGA.2G.AAFE.01     3  0.0937     0.8212 0.00 0.00 0.96 0.00 0.04 0.00
#&gt; TCGA.ZM.AA0H.01     1  0.3382     0.8523 0.84 0.00 0.04 0.04 0.08 0.00
#&gt; TCGA.2G.AAKG.05     2  0.3706     0.7121 0.00 0.62 0.00 0.38 0.00 0.00
#&gt; TCGA.ZM.AA0B.01     6  0.3916     0.4583 0.00 0.00 0.00 0.02 0.30 0.68
#&gt; TCGA.2G.AALP.01     2  0.0000     0.8260 0.00 1.00 0.00 0.00 0.00 0.00
#&gt; TCGA.YU.A90P.01     2  0.3706     0.7121 0.00 0.62 0.00 0.38 0.00 0.00
#&gt; TCGA.2G.AAGS.01     2  0.0000     0.8260 0.00 1.00 0.00 0.00 0.00 0.00
#&gt; TCGA.W4.A7U3.01     2  0.0000     0.8260 0.00 1.00 0.00 0.00 0.00 0.00
#&gt; TCGA.SN.A6IS.01     6  0.1480     0.6641 0.00 0.00 0.00 0.02 0.04 0.94
#&gt; TCGA.2G.AAGF.01     2  0.0000     0.8260 0.00 1.00 0.00 0.00 0.00 0.00
#&gt; TCGA.2G.AAGE.01     2  0.1814     0.8017 0.00 0.90 0.00 0.10 0.00 0.00
#&gt; TCGA.2G.AAGY.05     3  0.3660     0.8239 0.00 0.00 0.78 0.16 0.06 0.00
#&gt; TCGA.2G.AAKL.01     2  0.3647     0.7255 0.00 0.64 0.00 0.36 0.00 0.00
#&gt; TCGA.2G.AAF8.01     5  0.3711     0.6738 0.00 0.00 0.00 0.02 0.72 0.26
#&gt; TCGA.2G.AALW.01     2  0.0000     0.8260 0.00 1.00 0.00 0.00 0.00 0.00
#&gt; TCGA.XE.AAOB.01     2  0.3706     0.7121 0.00 0.62 0.00 0.38 0.00 0.00
#&gt; TCGA.2G.AAF4.01     6  0.0000     0.6954 0.00 0.00 0.00 0.00 0.00 1.00
#&gt; TCGA.XE.AAOC.01     2  0.0000     0.8260 0.00 1.00 0.00 0.00 0.00 0.00
#&gt; TCGA.XE.AANR.01     5  0.4723     0.3591 0.00 0.18 0.00 0.14 0.68 0.00
#&gt; TCGA.2G.AAFG.05     1  0.1267     0.8467 0.94 0.00 0.00 0.00 0.06 0.00
#&gt; TCGA.2G.AALS.01     2  0.3706     0.7121 0.00 0.62 0.00 0.38 0.00 0.00
#&gt; TCGA.2G.AAG3.01     2  0.0000     0.8260 0.00 1.00 0.00 0.00 0.00 0.00
#&gt; TCGA.2G.AALN.01     2  0.0000     0.8260 0.00 1.00 0.00 0.00 0.00 0.00
#&gt; TCGA.ZM.AA0D.01     1  0.0000     0.8839 1.00 0.00 0.00 0.00 0.00 0.00
#&gt; TCGA.2G.AAG9.01     3  0.0547     0.8238 0.00 0.00 0.98 0.02 0.00 0.00
#&gt; TCGA.2G.AAGC.01     2  0.3647     0.7255 0.00 0.64 0.00 0.36 0.00 0.00
#&gt; TCGA.2X.A9D6.01     1  0.3382     0.8523 0.84 0.00 0.04 0.04 0.08 0.00
#&gt; TCGA.4K.AAAL.01     6  0.6948    -0.0929 0.04 0.00 0.40 0.04 0.12 0.40
#&gt; TCGA.SN.A84Y.01     2  0.3647     0.7255 0.00 0.64 0.00 0.36 0.00 0.00
#&gt; TCGA.VF.A8AA.01     1  0.0000     0.8839 1.00 0.00 0.00 0.00 0.00 0.00
#&gt; TCGA.2G.AAH3.01     5  0.3409     0.6529 0.00 0.00 0.00 0.00 0.70 0.30
#&gt; TCGA.YU.A90Q.01     3  0.4873     0.7634 0.00 0.00 0.60 0.32 0.08 0.00
#&gt; TCGA.2G.AAKO.01     1  0.0000     0.8839 1.00 0.00 0.00 0.00 0.00 0.00
#&gt; TCGA.2G.AAGZ.01     2  0.3706     0.7121 0.00 0.62 0.00 0.38 0.00 0.00
#&gt; TCGA.VF.A8AB.01     5  0.4754     0.6350 0.08 0.00 0.00 0.02 0.70 0.20
#&gt; TCGA.2G.AALF.01     2  0.1480     0.7804 0.00 0.94 0.00 0.04 0.02 0.00
#&gt; TCGA.2G.AAL7.01     2  0.3647     0.7255 0.00 0.64 0.00 0.36 0.00 0.00
#&gt; TCGA.2G.AALQ.01     2  0.0000     0.8260 0.00 1.00 0.00 0.00 0.00 0.00
#&gt; TCGA.2G.AAFN.01     2  0.3647     0.7255 0.00 0.64 0.00 0.36 0.00 0.00
#&gt; TCGA.2G.AAFG.01     6  0.3647     0.3633 0.00 0.00 0.00 0.00 0.36 0.64
#&gt; TCGA.2G.AAGN.01     2  0.3706     0.7121 0.00 0.62 0.00 0.38 0.00 0.00
#&gt; TCGA.XE.AAOD.01     1  0.2793     0.7075 0.80 0.00 0.00 0.00 0.20 0.00
#&gt; TCGA.XE.AAOF.01     1  0.2725     0.8666 0.88 0.00 0.02 0.04 0.06 0.00
#&gt; TCGA.XY.A8S3.01     2  0.0000     0.8260 0.00 1.00 0.00 0.00 0.00 0.00
#&gt; TCGA.2G.AAFV.01     2  0.0000     0.8260 0.00 1.00 0.00 0.00 0.00 0.00
#&gt; TCGA.2G.AAHP.05     1  0.3697     0.8412 0.82 0.00 0.06 0.04 0.08 0.00
#&gt; TCGA.2G.AAH4.01     2  0.0000     0.8260 0.00 1.00 0.00 0.00 0.00 0.00
#&gt; TCGA.XE.AAO3.01     6  0.4727     0.4752 0.00 0.00 0.00 0.10 0.24 0.66
#&gt; TCGA.SB.A76C.01     3  0.2190     0.8340 0.00 0.00 0.90 0.06 0.04 0.00
#&gt; TCGA.2G.AAHG.01     6  0.7434    -0.2091 0.00 0.00 0.28 0.28 0.12 0.32
#&gt; TCGA.XE.AAO6.01     6  0.0000     0.6954 0.00 0.00 0.00 0.00 0.00 1.00
#&gt; TCGA.SB.A6J6.01     6  0.0547     0.6964 0.00 0.00 0.00 0.00 0.02 0.98
#&gt; TCGA.YU.AA61.01     2  0.0000     0.8260 0.00 1.00 0.00 0.00 0.00 0.00
#&gt; TCGA.2G.AAG7.01     2  0.0000     0.8260 0.00 1.00 0.00 0.00 0.00 0.00
#&gt; TCGA.XY.A8S2.01     2  0.3647     0.7255 0.00 0.64 0.00 0.36 0.00 0.00
#&gt; TCGA.2G.AAEX.01     6  0.0547     0.6894 0.00 0.00 0.00 0.02 0.00 0.98
#&gt; TCGA.2G.AAH0.01     6  0.0937     0.6889 0.00 0.00 0.00 0.04 0.00 0.96
#&gt; TCGA.2G.AAKD.01     2  0.3647     0.7255 0.00 0.64 0.00 0.36 0.00 0.00
#&gt; TCGA.VF.A8AD.01     2  0.3706     0.7121 0.00 0.62 0.00 0.38 0.00 0.00
#&gt; TCGA.2G.AALR.01     2  0.0000     0.8260 0.00 1.00 0.00 0.00 0.00 0.00
#&gt; TCGA.2G.AAFM.01     2  0.3706     0.7121 0.00 0.62 0.00 0.38 0.00 0.00
#&gt; TCGA.2G.AALG.01     2  0.0000     0.8260 0.00 1.00 0.00 0.00 0.00 0.00
#&gt; TCGA.XE.AAOJ.01     2  0.0000     0.8260 0.00 1.00 0.00 0.00 0.00 0.00
#&gt; TCGA.2G.AAGI.01     2  0.0000     0.8260 0.00 1.00 0.00 0.00 0.00 0.00
#&gt; TCGA.W4.A7U2.01     6  0.3660     0.6021 0.00 0.00 0.00 0.06 0.16 0.78
#&gt; TCGA.S6.A8JY.01     3  0.7204     0.4623 0.00 0.00 0.40 0.30 0.12 0.18
#&gt; TCGA.2G.AAH8.01     3  0.4711     0.7846 0.00 0.00 0.64 0.28 0.08 0.00
#&gt; TCGA.2G.AAHP.01     6  0.4989     0.4593 0.00 0.00 0.00 0.14 0.22 0.64
#&gt; TCGA.2G.AAGW.01     2  0.0000     0.8260 0.00 1.00 0.00 0.00 0.00 0.00
#&gt; TCGA.2X.A9D5.01     1  0.7451     0.3239 0.42 0.00 0.14 0.04 0.08 0.32
#&gt; TCGA.2G.AAGX.01     2  0.0000     0.8260 0.00 1.00 0.00 0.00 0.00 0.00
</code></pre>

<script>
$('#tab-node-0-get-classes-5-a').parent().next().next().hide();
$('#tab-node-0-get-classes-5-a').click(function(){
  $('#tab-node-0-get-classes-5-a').parent().next().next().toggle();
  return(false);
});
</script>
</div>

<div id='tab-node-0-get-classes-6'>
<p><a id='tab-node-0-get-classes-6-a' style='color:#0366d6' href='#'>show/hide code output</a></p>
<pre><code class="r">cbind(get_classes(res, k = 7), get_membership(res, k = 7))
</code></pre>

<pre><code>#&gt;                 class entropy silhouette   p1   p2   p3   p4   p5   p6   p7
#&gt; TCGA.XE.A8H4.01     1  0.0000      0.795 1.00 0.00 0.00 0.00 0.00 0.00 0.00
#&gt; TCGA.2G.AAF1.01     1  0.0504      0.794 0.98 0.00 0.00 0.00 0.02 0.00 0.00
#&gt; TCGA.W4.A7U4.01     4  0.2832      0.988 0.00 0.24 0.00 0.76 0.00 0.00 0.00
#&gt; TCGA.2G.AAGO.01     4  0.2832      0.988 0.00 0.24 0.00 0.76 0.00 0.00 0.00
#&gt; TCGA.VF.A8AC.01     1  0.1433      0.786 0.92 0.00 0.00 0.00 0.00 0.00 0.08
#&gt; TCGA.2G.AALX.01     2  0.0000      0.978 0.00 1.00 0.00 0.00 0.00 0.00 0.00
#&gt; TCGA.2G.AAGK.01     4  0.2832      0.988 0.00 0.24 0.00 0.76 0.00 0.00 0.00
#&gt; TCGA.2G.AAGG.01     2  0.0000      0.978 0.00 1.00 0.00 0.00 0.00 0.00 0.00
#&gt; TCGA.2G.AAGP.01     4  0.2832      0.988 0.00 0.24 0.00 0.76 0.00 0.00 0.00
#&gt; TCGA.2G.AAKM.01     4  0.2832      0.988 0.00 0.24 0.00 0.76 0.00 0.00 0.00
#&gt; TCGA.ZM.AA0E.01     1  0.2945      0.722 0.74 0.00 0.00 0.00 0.00 0.00 0.26
#&gt; TCGA.XE.A9SE.01     5  0.2572      0.721 0.00 0.00 0.00 0.00 0.80 0.20 0.00
#&gt; TCGA.2G.AAKO.05     1  0.2213      0.776 0.90 0.00 0.00 0.02 0.04 0.00 0.04
#&gt; TCGA.2G.AAFY.01     4  0.2832      0.988 0.00 0.24 0.00 0.76 0.00 0.00 0.00
#&gt; TCGA.XE.AANI.01     2  0.0000      0.978 0.00 1.00 0.00 0.00 0.00 0.00 0.00
#&gt; TCGA.YU.AA4L.01     2  0.2016      0.883 0.00 0.90 0.00 0.06 0.00 0.00 0.04
#&gt; TCGA.2G.AAGI.05     1  0.2259      0.766 0.84 0.00 0.00 0.00 0.00 0.00 0.16
#&gt; TCGA.XE.AANV.01     3  0.2906      0.565 0.00 0.00 0.80 0.02 0.00 0.00 0.18
#&gt; TCGA.YU.A90S.01     1  0.2213      0.776 0.90 0.00 0.00 0.02 0.04 0.00 0.04
#&gt; TCGA.XY.A89B.01     1  0.3139      0.692 0.70 0.00 0.00 0.00 0.00 0.00 0.30
#&gt; TCGA.ZM.AA05.01     1  0.2422      0.760 0.82 0.00 0.00 0.00 0.00 0.00 0.18
#&gt; TCGA.2G.AAHA.01     3  0.3047      0.411 0.00 0.00 0.72 0.00 0.00 0.00 0.28
#&gt; TCGA.2G.AAH2.01     2  0.0000      0.978 0.00 1.00 0.00 0.00 0.00 0.00 0.00
#&gt; TCGA.2G.AAG6.01     2  0.0000      0.978 0.00 1.00 0.00 0.00 0.00 0.00 0.00
#&gt; TCGA.2G.AAG0.01     4  0.2832      0.988 0.00 0.24 0.00 0.76 0.00 0.00 0.00
#&gt; TCGA.WZ.A7V3.01     3  0.4243      0.563 0.00 0.00 0.76 0.02 0.02 0.10 0.10
#&gt; TCGA.2G.AALO.01     2  0.0000      0.978 0.00 1.00 0.00 0.00 0.00 0.00 0.00
#&gt; TCGA.ZM.AA0F.01     1  0.1363      0.788 0.94 0.00 0.00 0.02 0.04 0.00 0.00
#&gt; TCGA.XE.A8H5.01     3  0.2569      0.622 0.00 0.00 0.84 0.02 0.00 0.00 0.14
#&gt; TCGA.XE.AANJ.01     6  0.0863      0.710 0.00 0.00 0.00 0.00 0.00 0.96 0.04
#&gt; TCGA.YU.A94I.01     2  0.2016      0.883 0.00 0.90 0.00 0.06 0.00 0.00 0.04
#&gt; TCGA.SO.A8JP.01     3  0.4772      0.531 0.00 0.00 0.60 0.04 0.04 0.00 0.32
#&gt; TCGA.2G.AAM4.01     2  0.0000      0.978 0.00 1.00 0.00 0.00 0.00 0.00 0.00
#&gt; TCGA.WZ.A7V5.01     1  0.3047      0.710 0.72 0.00 0.00 0.00 0.00 0.00 0.28
#&gt; TCGA.YU.A90Y.01     4  0.2832      0.988 0.00 0.24 0.00 0.76 0.00 0.00 0.00
#&gt; TCGA.2G.AALZ.01     2  0.0000      0.978 0.00 1.00 0.00 0.00 0.00 0.00 0.00
#&gt; TCGA.WZ.A8D5.01     1  0.3047      0.710 0.72 0.00 0.00 0.00 0.00 0.00 0.28
#&gt; TCGA.2G.AAGA.01     4  0.3294      0.851 0.00 0.34 0.00 0.66 0.00 0.00 0.00
#&gt; TCGA.2G.AALY.01     2  0.0000      0.978 0.00 1.00 0.00 0.00 0.00 0.00 0.00
#&gt; TCGA.2G.AAKG.01     4  0.2832      0.988 0.00 0.24 0.00 0.76 0.00 0.00 0.00
#&gt; TCGA.2G.AAL5.01     2  0.0000      0.978 0.00 1.00 0.00 0.00 0.00 0.00 0.00
#&gt; TCGA.YU.A94D.01     2  0.0504      0.958 0.00 0.98 0.00 0.02 0.00 0.00 0.00
#&gt; TCGA.XE.AAOL.01     3  0.3661      0.581 0.00 0.00 0.74 0.02 0.02 0.00 0.22
#&gt; TCGA.SN.A84X.01     2  0.0000      0.978 0.00 1.00 0.00 0.00 0.00 0.00 0.00
#&gt; TCGA.2G.AAHC.01     1  0.5617      0.296 0.54 0.00 0.00 0.00 0.10 0.30 0.06
#&gt; TCGA.2G.AAHT.01     3  0.2259      0.563 0.00 0.00 0.84 0.00 0.00 0.00 0.16
#&gt; TCGA.2G.AALT.01     2  0.0000      0.978 0.00 1.00 0.00 0.00 0.00 0.00 0.00
#&gt; TCGA.2G.AAM2.01     2  0.0000      0.978 0.00 1.00 0.00 0.00 0.00 0.00 0.00
#&gt; TCGA.2G.AAFH.01     6  0.5242      0.393 0.00 0.00 0.00 0.04 0.32 0.56 0.08
#&gt; TCGA.2G.AAFI.01     4  0.3358      0.817 0.00 0.36 0.00 0.64 0.00 0.00 0.00
#&gt; TCGA.2G.AAHN.01     1  0.1006      0.791 0.96 0.00 0.00 0.02 0.02 0.00 0.00
#&gt; TCGA.2G.AAGT.01     2  0.2016      0.883 0.00 0.90 0.00 0.06 0.00 0.00 0.04
#&gt; TCGA.YU.A90W.01     3  0.2163      0.640 0.00 0.00 0.88 0.00 0.00 0.02 0.10
#&gt; TCGA.2G.AAGJ.01     4  0.2832      0.988 0.00 0.24 0.00 0.76 0.00 0.00 0.00
#&gt; TCGA.2G.AAGV.01     2  0.0000      0.978 0.00 1.00 0.00 0.00 0.00 0.00 0.00
#&gt; TCGA.XE.A8H1.01     4  0.2832      0.988 0.00 0.24 0.00 0.76 0.00 0.00 0.00
#&gt; TCGA.2G.AAFJ.01     2  0.0000      0.978 0.00 1.00 0.00 0.00 0.00 0.00 0.00
#&gt; TCGA.2G.AAG5.01     2  0.0000      0.978 0.00 1.00 0.00 0.00 0.00 0.00 0.00
#&gt; TCGA.X3.A8G4.01     2  0.3221      0.258 0.00 0.68 0.00 0.32 0.00 0.00 0.00
#&gt; TCGA.2G.AAGY.01     2  0.0000      0.978 0.00 1.00 0.00 0.00 0.00 0.00 0.00
#&gt; TCGA.2G.AAG8.01     4  0.2832      0.988 0.00 0.24 0.00 0.76 0.00 0.00 0.00
#&gt; TCGA.S6.A8JW.01     3  0.4305      0.567 0.00 0.00 0.66 0.04 0.02 0.00 0.28
#&gt; TCGA.2G.AAEW.01     1  0.5490      0.190 0.44 0.00 0.24 0.00 0.00 0.00 0.32
#&gt; TCGA.2G.AAFO.01     4  0.2832      0.988 0.00 0.24 0.00 0.76 0.00 0.00 0.00
#&gt; TCGA.YU.A912.01     3  0.2163      0.613 0.00 0.00 0.88 0.02 0.00 0.00 0.10
#&gt; TCGA.2G.AAM3.01     2  0.0000      0.978 0.00 1.00 0.00 0.00 0.00 0.00 0.00
#&gt; TCGA.VF.A8A8.01     2  0.0000      0.978 0.00 1.00 0.00 0.00 0.00 0.00 0.00
#&gt; TCGA.SN.A84W.01     2  0.0000      0.978 0.00 1.00 0.00 0.00 0.00 0.00 0.00
#&gt; TCGA.XE.AAO4.01     1  0.4787      0.524 0.58 0.00 0.12 0.00 0.00 0.00 0.30
#&gt; TCGA.ZM.AA0N.01     6  0.3052      0.632 0.00 0.00 0.00 0.00 0.20 0.78 0.02
#&gt; TCGA.VF.A8AE.01     1  0.2213      0.776 0.90 0.00 0.00 0.02 0.04 0.00 0.04
#&gt; TCGA.2G.AAFZ.01     2  0.0000      0.978 0.00 1.00 0.00 0.00 0.00 0.00 0.00
#&gt; TCGA.2G.AAGM.01     2  0.0000      0.978 0.00 1.00 0.00 0.00 0.00 0.00 0.00
#&gt; TCGA.2G.AAKH.01     4  0.2832      0.988 0.00 0.24 0.00 0.76 0.00 0.00 0.00
#&gt; TCGA.2G.AAF6.01     6  0.2509      0.700 0.00 0.00 0.00 0.02 0.04 0.88 0.06
#&gt; TCGA.4K.AA1I.01     1  0.1505      0.789 0.94 0.00 0.00 0.02 0.02 0.00 0.02
#&gt; TCGA.2G.AAFL.01     4  0.2832      0.988 0.00 0.24 0.00 0.76 0.00 0.00 0.00
#&gt; TCGA.XY.A9T9.01     6  0.2016      0.700 0.00 0.00 0.00 0.00 0.06 0.90 0.04
#&gt; TCGA.WZ.A7V4.01     1  0.0000      0.795 1.00 0.00 0.00 0.00 0.00 0.00 0.00
#&gt; TCGA.S6.A8JX.01     3  0.4318      0.603 0.00 0.00 0.70 0.04 0.04 0.00 0.22
#&gt; TCGA.2G.AAHL.01     3  0.1928      0.636 0.00 0.00 0.90 0.02 0.00 0.00 0.08
#&gt; TCGA.4K.AA1H.01     1  0.2213      0.776 0.90 0.00 0.00 0.02 0.04 0.00 0.04
#&gt; TCGA.ZM.AA06.01     6  0.3114      0.686 0.00 0.00 0.00 0.04 0.04 0.84 0.08
#&gt; TCGA.VF.A8A9.01     6  0.2745      0.660 0.00 0.00 0.00 0.00 0.16 0.82 0.02
#&gt; TCGA.4K.AA1G.01     3  0.3055      0.635 0.00 0.00 0.82 0.02 0.02 0.00 0.14
#&gt; TCGA.2G.AAFE.01     3  0.2259      0.588 0.00 0.00 0.84 0.00 0.00 0.00 0.16
#&gt; TCGA.ZM.AA0H.01     1  0.3047      0.710 0.72 0.00 0.00 0.00 0.00 0.00 0.28
#&gt; TCGA.2G.AAKG.05     4  0.2832      0.988 0.00 0.24 0.00 0.76 0.00 0.00 0.00
#&gt; TCGA.ZM.AA0B.01     6  0.3667      0.625 0.00 0.00 0.00 0.00 0.20 0.74 0.06
#&gt; TCGA.2G.AALP.01     2  0.0000      0.978 0.00 1.00 0.00 0.00 0.00 0.00 0.00
#&gt; TCGA.YU.A90P.01     4  0.2832      0.988 0.00 0.24 0.00 0.76 0.00 0.00 0.00
#&gt; TCGA.2G.AAGS.01     2  0.0000      0.978 0.00 1.00 0.00 0.00 0.00 0.00 0.00
#&gt; TCGA.W4.A7U3.01     2  0.0000      0.978 0.00 1.00 0.00 0.00 0.00 0.00 0.00
#&gt; TCGA.SN.A6IS.01     6  0.1928      0.694 0.00 0.00 0.00 0.02 0.00 0.90 0.08
#&gt; TCGA.2G.AAGF.01     2  0.0000      0.978 0.00 1.00 0.00 0.00 0.00 0.00 0.00
#&gt; TCGA.2G.AAGE.01     2  0.1166      0.901 0.00 0.94 0.00 0.06 0.00 0.00 0.00
#&gt; TCGA.2G.AAGY.05     3  0.3208      0.640 0.00 0.00 0.82 0.04 0.02 0.00 0.12
#&gt; TCGA.2G.AAKL.01     4  0.2832      0.988 0.00 0.24 0.00 0.76 0.00 0.00 0.00
#&gt; TCGA.2G.AAF8.01     5  0.2572      0.721 0.00 0.00 0.00 0.00 0.80 0.20 0.00
#&gt; TCGA.2G.AALW.01     2  0.0000      0.978 0.00 1.00 0.00 0.00 0.00 0.00 0.00
#&gt; TCGA.XE.AAOB.01     4  0.2832      0.988 0.00 0.24 0.00 0.76 0.00 0.00 0.00
#&gt; TCGA.2G.AAF4.01     6  0.2159      0.710 0.00 0.00 0.00 0.02 0.02 0.90 0.06
#&gt; TCGA.XE.AAOC.01     2  0.0000      0.978 0.00 1.00 0.00 0.00 0.00 0.00 0.00
#&gt; TCGA.XE.AANR.01     5  0.3745      0.385 0.00 0.04 0.00 0.26 0.70 0.00 0.00
#&gt; TCGA.2G.AAFG.05     1  0.3887      0.700 0.80 0.00 0.00 0.02 0.08 0.04 0.06
#&gt; TCGA.2G.AALS.01     4  0.2832      0.988 0.00 0.24 0.00 0.76 0.00 0.00 0.00
#&gt; TCGA.2G.AAG3.01     2  0.0000      0.978 0.00 1.00 0.00 0.00 0.00 0.00 0.00
#&gt; TCGA.2G.AALN.01     2  0.0000      0.978 0.00 1.00 0.00 0.00 0.00 0.00 0.00
#&gt; TCGA.ZM.AA0D.01     1  0.1860      0.782 0.92 0.00 0.00 0.02 0.04 0.00 0.02
#&gt; TCGA.2G.AAG9.01     3  0.3186      0.534 0.00 0.00 0.76 0.02 0.00 0.00 0.22
#&gt; TCGA.2G.AAGC.01     4  0.2832      0.988 0.00 0.24 0.00 0.76 0.00 0.00 0.00
#&gt; TCGA.2X.A9D6.01     1  0.3139      0.692 0.70 0.00 0.00 0.00 0.00 0.00 0.30
#&gt; TCGA.4K.AAAL.01     7  0.6504      0.274 0.04 0.00 0.30 0.02 0.00 0.22 0.42
#&gt; TCGA.SN.A84Y.01     4  0.2832      0.988 0.00 0.24 0.00 0.76 0.00 0.00 0.00
#&gt; TCGA.VF.A8AA.01     1  0.0000      0.795 1.00 0.00 0.00 0.00 0.00 0.00 0.00
#&gt; TCGA.2G.AAH3.01     5  0.2708      0.706 0.00 0.00 0.00 0.00 0.78 0.22 0.00
#&gt; TCGA.YU.A90Q.01     3  0.4623      0.557 0.00 0.00 0.64 0.04 0.04 0.00 0.28
#&gt; TCGA.2G.AAKO.01     1  0.2213      0.776 0.90 0.00 0.00 0.02 0.04 0.00 0.04
#&gt; TCGA.2G.AAGZ.01     4  0.2832      0.988 0.00 0.24 0.00 0.76 0.00 0.00 0.00
#&gt; TCGA.VF.A8AB.01     5  0.4044      0.665 0.02 0.00 0.00 0.02 0.76 0.16 0.04
#&gt; TCGA.2G.AALF.01     2  0.2016      0.883 0.00 0.90 0.00 0.06 0.00 0.00 0.04
#&gt; TCGA.2G.AAL7.01     4  0.2832      0.988 0.00 0.24 0.00 0.76 0.00 0.00 0.00
#&gt; TCGA.2G.AALQ.01     2  0.0000      0.978 0.00 1.00 0.00 0.00 0.00 0.00 0.00
#&gt; TCGA.2G.AAFN.01     4  0.2945      0.963 0.00 0.26 0.00 0.74 0.00 0.00 0.00
#&gt; TCGA.2G.AAFG.01     6  0.3927      0.499 0.00 0.00 0.00 0.00 0.30 0.66 0.04
#&gt; TCGA.2G.AAGN.01     4  0.2832      0.988 0.00 0.24 0.00 0.76 0.00 0.00 0.00
#&gt; TCGA.XE.AAOD.01     1  0.4654      0.626 0.72 0.00 0.00 0.02 0.16 0.04 0.06
#&gt; TCGA.XE.AAOF.01     1  0.2572      0.752 0.80 0.00 0.00 0.00 0.00 0.00 0.20
#&gt; TCGA.XY.A8S3.01     2  0.0000      0.978 0.00 1.00 0.00 0.00 0.00 0.00 0.00
#&gt; TCGA.2G.AAFV.01     2  0.0863      0.937 0.00 0.96 0.00 0.04 0.00 0.00 0.00
#&gt; TCGA.2G.AAHP.05     1  0.3047      0.710 0.72 0.00 0.00 0.00 0.00 0.00 0.28
#&gt; TCGA.2G.AAH4.01     2  0.0000      0.978 0.00 1.00 0.00 0.00 0.00 0.00 0.00
#&gt; TCGA.XE.AAO3.01     6  0.5477      0.354 0.00 0.00 0.00 0.04 0.34 0.52 0.10
#&gt; TCGA.SB.A76C.01     3  0.1928      0.636 0.00 0.00 0.90 0.02 0.00 0.00 0.08
#&gt; TCGA.2G.AAHG.01     7  0.7555      0.219 0.00 0.00 0.32 0.08 0.10 0.18 0.32
#&gt; TCGA.XE.AAO6.01     6  0.2213      0.707 0.00 0.00 0.00 0.02 0.04 0.90 0.04
#&gt; TCGA.SB.A6J6.01     6  0.2163      0.692 0.00 0.00 0.00 0.00 0.10 0.88 0.02
#&gt; TCGA.YU.AA61.01     2  0.0000      0.978 0.00 1.00 0.00 0.00 0.00 0.00 0.00
#&gt; TCGA.2G.AAG7.01     2  0.0000      0.978 0.00 1.00 0.00 0.00 0.00 0.00 0.00
#&gt; TCGA.XY.A8S2.01     4  0.2832      0.988 0.00 0.24 0.00 0.76 0.00 0.00 0.00
#&gt; TCGA.2G.AAEX.01     6  0.1166      0.708 0.00 0.00 0.00 0.00 0.00 0.94 0.06
#&gt; TCGA.2G.AAH0.01     6  0.1433      0.702 0.00 0.00 0.00 0.00 0.00 0.92 0.08
#&gt; TCGA.2G.AAKD.01     4  0.2832      0.988 0.00 0.24 0.00 0.76 0.00 0.00 0.00
#&gt; TCGA.VF.A8AD.01     4  0.2832      0.988 0.00 0.24 0.00 0.76 0.00 0.00 0.00
#&gt; TCGA.2G.AALR.01     2  0.0000      0.978 0.00 1.00 0.00 0.00 0.00 0.00 0.00
#&gt; TCGA.2G.AAFM.01     4  0.2832      0.988 0.00 0.24 0.00 0.76 0.00 0.00 0.00
#&gt; TCGA.2G.AALG.01     2  0.0000      0.978 0.00 1.00 0.00 0.00 0.00 0.00 0.00
#&gt; TCGA.XE.AAOJ.01     2  0.0000      0.978 0.00 1.00 0.00 0.00 0.00 0.00 0.00
#&gt; TCGA.2G.AAGI.01     2  0.0000      0.978 0.00 1.00 0.00 0.00 0.00 0.00 0.00
#&gt; TCGA.W4.A7U2.01     6  0.4298      0.652 0.00 0.00 0.00 0.04 0.12 0.74 0.10
#&gt; TCGA.S6.A8JY.01     3  0.7382     -0.478 0.00 0.00 0.38 0.08 0.10 0.14 0.30
#&gt; TCGA.2G.AAH8.01     3  0.4623      0.570 0.00 0.00 0.64 0.04 0.04 0.00 0.28
#&gt; TCGA.2G.AAHP.01     6  0.5516      0.327 0.00 0.00 0.00 0.04 0.36 0.50 0.10
#&gt; TCGA.2G.AAGW.01     2  0.0000      0.978 0.00 1.00 0.00 0.00 0.00 0.00 0.00
#&gt; TCGA.2X.A9D5.01     6  0.6724     -0.332 0.26 0.00 0.10 0.00 0.00 0.34 0.30
#&gt; TCGA.2G.AAGX.01     2  0.0000      0.978 0.00 1.00 0.00 0.00 0.00 0.00 0.00
</code></pre>

<script>
$('#tab-node-0-get-classes-6-a').parent().next().next().hide();
$('#tab-node-0-get-classes-6-a').click(function(){
  $('#tab-node-0-get-classes-6-a').parent().next().next().toggle();
  return(false);
});
</script>
</div>

<div id='tab-node-0-get-classes-7'>
<p><a id='tab-node-0-get-classes-7-a' style='color:#0366d6' href='#'>show/hide code output</a></p>
<pre><code class="r">cbind(get_classes(res, k = 8), get_membership(res, k = 8))
</code></pre>

<pre><code>#&gt;                 class entropy silhouette   p1   p2   p3   p4   p5   p6   p7   p8
#&gt; TCGA.XE.A8H4.01     1  0.0471     0.8581 0.98 0.00 0.00 0.00 0.00 0.00 0.00 0.02
#&gt; TCGA.2G.AAF1.01     1  0.0000     0.8591 1.00 0.00 0.00 0.00 0.00 0.00 0.00 0.00
#&gt; TCGA.W4.A7U4.01     4  0.1765     0.9855 0.00 0.12 0.00 0.88 0.00 0.00 0.00 0.00
#&gt; TCGA.2G.AAGO.01     4  0.1765     0.9855 0.00 0.12 0.00 0.88 0.00 0.00 0.00 0.00
#&gt; TCGA.VF.A8AC.01     1  0.1341     0.8508 0.92 0.00 0.00 0.00 0.00 0.00 0.00 0.08
#&gt; TCGA.2G.AALX.01     2  0.0000     0.9689 0.00 1.00 0.00 0.00 0.00 0.00 0.00 0.00
#&gt; TCGA.2G.AAGK.01     4  0.2224     0.9867 0.00 0.12 0.00 0.86 0.00 0.00 0.00 0.02
#&gt; TCGA.2G.AAGG.01     2  0.0000     0.9689 0.00 1.00 0.00 0.00 0.00 0.00 0.00 0.00
#&gt; TCGA.2G.AAGP.01     4  0.2224     0.9867 0.00 0.12 0.00 0.86 0.00 0.00 0.00 0.02
#&gt; TCGA.2G.AAKM.01     4  0.1765     0.9855 0.00 0.12 0.00 0.88 0.00 0.00 0.00 0.00
#&gt; TCGA.ZM.AA0E.01     1  0.3434     0.7831 0.76 0.00 0.10 0.00 0.00 0.00 0.00 0.14
#&gt; TCGA.XE.A9SE.01     5  0.1804     0.8565 0.00 0.00 0.00 0.00 0.90 0.02 0.00 0.08
#&gt; TCGA.2G.AAKO.05     1  0.0000     0.8591 1.00 0.00 0.00 0.00 0.00 0.00 0.00 0.00
#&gt; TCGA.2G.AAFY.01     4  0.2224     0.9867 0.00 0.12 0.00 0.86 0.00 0.00 0.00 0.02
#&gt; TCGA.XE.AANI.01     2  0.0000     0.9689 0.00 1.00 0.00 0.00 0.00 0.00 0.00 0.00
#&gt; TCGA.YU.AA4L.01     2  0.3185     0.7950 0.00 0.82 0.04 0.06 0.00 0.00 0.00 0.08
#&gt; TCGA.2G.AAGI.05     1  0.1563     0.8466 0.90 0.00 0.00 0.00 0.00 0.00 0.00 0.10
#&gt; TCGA.XE.AANV.01     3  0.4333     0.5049 0.00 0.00 0.62 0.00 0.00 0.00 0.26 0.12
#&gt; TCGA.YU.A90S.01     1  0.0000     0.8591 1.00 0.00 0.00 0.00 0.00 0.00 0.00 0.00
#&gt; TCGA.XY.A89B.01     1  0.3619     0.7697 0.74 0.00 0.12 0.00 0.00 0.00 0.00 0.14
#&gt; TCGA.ZM.AA05.01     1  0.2224     0.8354 0.86 0.00 0.02 0.00 0.00 0.00 0.00 0.12
#&gt; TCGA.2G.AAHA.01     3  0.4211     0.4945 0.02 0.00 0.68 0.00 0.00 0.00 0.22 0.08
#&gt; TCGA.2G.AAH2.01     2  0.0000     0.9689 0.00 1.00 0.00 0.00 0.00 0.00 0.00 0.00
#&gt; TCGA.2G.AAG6.01     2  0.0000     0.9689 0.00 1.00 0.00 0.00 0.00 0.00 0.00 0.00
#&gt; TCGA.2G.AAG0.01     4  0.2224     0.9867 0.00 0.12 0.00 0.86 0.00 0.00 0.00 0.02
#&gt; TCGA.WZ.A7V3.01     7  0.5448     0.1960 0.00 0.00 0.38 0.00 0.00 0.14 0.44 0.04
#&gt; TCGA.2G.AALO.01     2  0.0000     0.9689 0.00 1.00 0.00 0.00 0.00 0.00 0.00 0.00
#&gt; TCGA.ZM.AA0F.01     1  0.0000     0.8591 1.00 0.00 0.00 0.00 0.00 0.00 0.00 0.00
#&gt; TCGA.XE.A8H5.01     3  0.4954     0.2174 0.00 0.00 0.46 0.02 0.00 0.00 0.42 0.10
#&gt; TCGA.XE.AANJ.01     6  0.0471     0.6193 0.00 0.00 0.02 0.00 0.00 0.98 0.00 0.00
#&gt; TCGA.YU.A94I.01     2  0.3185     0.7950 0.00 0.82 0.04 0.06 0.00 0.00 0.00 0.08
#&gt; TCGA.SO.A8JP.01     7  0.0471     0.5542 0.00 0.00 0.00 0.00 0.00 0.00 0.98 0.02
#&gt; TCGA.2G.AAM4.01     2  0.0000     0.9689 0.00 1.00 0.00 0.00 0.00 0.00 0.00 0.00
#&gt; TCGA.WZ.A7V5.01     1  0.3434     0.7831 0.76 0.00 0.10 0.00 0.00 0.00 0.00 0.14
#&gt; TCGA.YU.A90Y.01     4  0.2224     0.9867 0.00 0.12 0.00 0.86 0.00 0.00 0.00 0.02
#&gt; TCGA.2G.AALZ.01     2  0.0000     0.9689 0.00 1.00 0.00 0.00 0.00 0.00 0.00 0.00
#&gt; TCGA.WZ.A8D5.01     1  0.3619     0.7696 0.74 0.00 0.12 0.00 0.00 0.00 0.00 0.14
#&gt; TCGA.2G.AAGA.01     4  0.1947     0.9682 0.00 0.14 0.00 0.86 0.00 0.00 0.00 0.00
#&gt; TCGA.2G.AALY.01     2  0.0000     0.9689 0.00 1.00 0.00 0.00 0.00 0.00 0.00 0.00
#&gt; TCGA.2G.AAKG.01     4  0.1947     0.9737 0.00 0.14 0.00 0.86 0.00 0.00 0.00 0.00
#&gt; TCGA.2G.AAL5.01     2  0.0000     0.9689 0.00 1.00 0.00 0.00 0.00 0.00 0.00 0.00
#&gt; TCGA.YU.A94D.01     2  0.0000     0.9689 0.00 1.00 0.00 0.00 0.00 0.00 0.00 0.00
#&gt; TCGA.XE.AAOL.01     7  0.4482     0.1361 0.00 0.00 0.26 0.00 0.00 0.00 0.60 0.14
#&gt; TCGA.SN.A84X.01     2  0.0000     0.9689 0.00 1.00 0.00 0.00 0.00 0.00 0.00 0.00
#&gt; TCGA.2G.AAHC.01     1  0.5204    -0.2084 0.42 0.00 0.00 0.02 0.14 0.42 0.00 0.00
#&gt; TCGA.2G.AAHT.01     3  0.2756     0.5251 0.00 0.00 0.74 0.00 0.00 0.00 0.26 0.00
#&gt; TCGA.2G.AALT.01     2  0.0000     0.9689 0.00 1.00 0.00 0.00 0.00 0.00 0.00 0.00
#&gt; TCGA.2G.AAM2.01     2  0.0000     0.9689 0.00 1.00 0.00 0.00 0.00 0.00 0.00 0.00
#&gt; TCGA.2G.AAFH.01     6  0.4998    -0.2379 0.00 0.00 0.00 0.00 0.24 0.50 0.00 0.26
#&gt; TCGA.2G.AAFI.01     4  0.2114     0.9412 0.00 0.16 0.00 0.84 0.00 0.00 0.00 0.00
#&gt; TCGA.2G.AAHN.01     1  0.0000     0.8591 1.00 0.00 0.00 0.00 0.00 0.00 0.00 0.00
#&gt; TCGA.2G.AAGT.01     2  0.3185     0.7950 0.00 0.82 0.04 0.06 0.00 0.00 0.00 0.08
#&gt; TCGA.YU.A90W.01     3  0.5403     0.1278 0.00 0.00 0.50 0.02 0.00 0.04 0.36 0.08
#&gt; TCGA.2G.AAGJ.01     4  0.2224     0.9867 0.00 0.12 0.00 0.86 0.00 0.00 0.00 0.02
#&gt; TCGA.2G.AAGV.01     2  0.0000     0.9689 0.00 1.00 0.00 0.00 0.00 0.00 0.00 0.00
#&gt; TCGA.XE.A8H1.01     4  0.1765     0.9855 0.00 0.12 0.00 0.88 0.00 0.00 0.00 0.00
#&gt; TCGA.2G.AAFJ.01     2  0.0000     0.9689 0.00 1.00 0.00 0.00 0.00 0.00 0.00 0.00
#&gt; TCGA.2G.AAG5.01     2  0.0000     0.9689 0.00 1.00 0.00 0.00 0.00 0.00 0.00 0.00
#&gt; TCGA.X3.A8G4.01     2  0.3237     0.1612 0.00 0.60 0.00 0.40 0.00 0.00 0.00 0.00
#&gt; TCGA.2G.AAGY.01     2  0.0000     0.9689 0.00 1.00 0.00 0.00 0.00 0.00 0.00 0.00
#&gt; TCGA.2G.AAG8.01     4  0.1765     0.9855 0.00 0.12 0.00 0.88 0.00 0.00 0.00 0.00
#&gt; TCGA.S6.A8JW.01     7  0.2404     0.5497 0.00 0.00 0.14 0.00 0.00 0.00 0.84 0.02
#&gt; TCGA.2G.AAEW.01     3  0.5204    -0.2511 0.42 0.00 0.42 0.00 0.00 0.00 0.02 0.14
#&gt; TCGA.2G.AAFO.01     4  0.2224     0.9867 0.00 0.12 0.00 0.86 0.00 0.00 0.00 0.02
#&gt; TCGA.YU.A912.01     3  0.3660     0.5292 0.00 0.00 0.70 0.00 0.00 0.00 0.24 0.06
#&gt; TCGA.2G.AAM3.01     2  0.0000     0.9689 0.00 1.00 0.00 0.00 0.00 0.00 0.00 0.00
#&gt; TCGA.VF.A8A8.01     2  0.0000     0.9689 0.00 1.00 0.00 0.00 0.00 0.00 0.00 0.00
#&gt; TCGA.SN.A84W.01     2  0.0000     0.9689 0.00 1.00 0.00 0.00 0.00 0.00 0.00 0.00
#&gt; TCGA.XE.AAO4.01     1  0.4677     0.4873 0.54 0.00 0.32 0.00 0.00 0.00 0.00 0.14
#&gt; TCGA.ZM.AA0N.01     6  0.3431     0.4694 0.00 0.00 0.00 0.00 0.20 0.74 0.00 0.06
#&gt; TCGA.VF.A8AE.01     1  0.0000     0.8591 1.00 0.00 0.00 0.00 0.00 0.00 0.00 0.00
#&gt; TCGA.2G.AAFZ.01     2  0.0000     0.9689 0.00 1.00 0.00 0.00 0.00 0.00 0.00 0.00
#&gt; TCGA.2G.AAGM.01     2  0.0000     0.9689 0.00 1.00 0.00 0.00 0.00 0.00 0.00 0.00
#&gt; TCGA.2G.AAKH.01     4  0.1765     0.9855 0.00 0.12 0.00 0.88 0.00 0.00 0.00 0.00
#&gt; TCGA.2G.AAF6.01     6  0.3494     0.4375 0.00 0.00 0.04 0.00 0.04 0.78 0.00 0.14
#&gt; TCGA.4K.AA1I.01     1  0.0000     0.8591 1.00 0.00 0.00 0.00 0.00 0.00 0.00 0.00
#&gt; TCGA.2G.AAFL.01     4  0.2224     0.9867 0.00 0.12 0.00 0.86 0.00 0.00 0.00 0.02
#&gt; TCGA.XY.A9T9.01     6  0.2020     0.5995 0.02 0.00 0.00 0.00 0.06 0.90 0.00 0.02
#&gt; TCGA.WZ.A7V4.01     1  0.0000     0.8591 1.00 0.00 0.00 0.00 0.00 0.00 0.00 0.00
#&gt; TCGA.S6.A8JX.01     7  0.2350     0.5341 0.00 0.00 0.10 0.00 0.00 0.00 0.86 0.04
#&gt; TCGA.2G.AAHL.01     3  0.2650     0.5343 0.00 0.00 0.76 0.00 0.00 0.00 0.24 0.00
#&gt; TCGA.4K.AA1H.01     1  0.0000     0.8591 1.00 0.00 0.00 0.00 0.00 0.00 0.00 0.00
#&gt; TCGA.ZM.AA06.01     6  0.2862     0.5176 0.00 0.00 0.10 0.00 0.00 0.82 0.00 0.08
#&gt; TCGA.VF.A8A9.01     6  0.3299     0.4955 0.00 0.00 0.00 0.00 0.18 0.76 0.00 0.06
#&gt; TCGA.4K.AA1G.01     3  0.4224     0.2852 0.00 0.00 0.48 0.00 0.00 0.00 0.46 0.06
#&gt; TCGA.2G.AAFE.01     3  0.3991     0.5016 0.00 0.00 0.62 0.00 0.00 0.00 0.32 0.06
#&gt; TCGA.ZM.AA0H.01     1  0.3619     0.7695 0.74 0.00 0.12 0.00 0.00 0.00 0.00 0.14
#&gt; TCGA.2G.AAKG.05     4  0.2224     0.9867 0.00 0.12 0.00 0.86 0.00 0.00 0.00 0.02
#&gt; TCGA.ZM.AA0B.01     6  0.3263     0.5057 0.00 0.00 0.00 0.00 0.12 0.78 0.00 0.10
#&gt; TCGA.2G.AALP.01     2  0.0000     0.9689 0.00 1.00 0.00 0.00 0.00 0.00 0.00 0.00
#&gt; TCGA.YU.A90P.01     4  0.2224     0.9867 0.00 0.12 0.00 0.86 0.00 0.00 0.00 0.02
#&gt; TCGA.2G.AAGS.01     2  0.0000     0.9689 0.00 1.00 0.00 0.00 0.00 0.00 0.00 0.00
#&gt; TCGA.W4.A7U3.01     2  0.0000     0.9689 0.00 1.00 0.00 0.00 0.00 0.00 0.00 0.00
#&gt; TCGA.SN.A6IS.01     6  0.2994     0.4586 0.00 0.00 0.14 0.00 0.00 0.80 0.00 0.06
#&gt; TCGA.2G.AAGF.01     2  0.0000     0.9689 0.00 1.00 0.00 0.00 0.00 0.00 0.00 0.00
#&gt; TCGA.2G.AAGE.01     2  0.2406     0.7085 0.00 0.80 0.00 0.20 0.00 0.00 0.00 0.00
#&gt; TCGA.2G.AAGY.05     7  0.3594     0.3470 0.00 0.00 0.28 0.00 0.00 0.00 0.68 0.04
#&gt; TCGA.2G.AAKL.01     4  0.1765     0.9855 0.00 0.12 0.00 0.88 0.00 0.00 0.00 0.00
#&gt; TCGA.2G.AAF8.01     5  0.1275     0.9057 0.00 0.00 0.00 0.00 0.94 0.04 0.00 0.02
#&gt; TCGA.2G.AALW.01     2  0.0000     0.9689 0.00 1.00 0.00 0.00 0.00 0.00 0.00 0.00
#&gt; TCGA.XE.AAOB.01     4  0.2224     0.9867 0.00 0.12 0.00 0.86 0.00 0.00 0.00 0.02
#&gt; TCGA.2G.AAF4.01     6  0.1741     0.5955 0.00 0.00 0.04 0.00 0.02 0.92 0.00 0.02
#&gt; TCGA.XE.AAOC.01     2  0.0000     0.9689 0.00 1.00 0.00 0.00 0.00 0.00 0.00 0.00
#&gt; TCGA.XE.AANR.01     5  0.1741     0.8452 0.00 0.02 0.00 0.04 0.92 0.02 0.00 0.00
#&gt; TCGA.2G.AAFG.05     1  0.2348     0.7741 0.88 0.00 0.00 0.02 0.06 0.04 0.00 0.00
#&gt; TCGA.2G.AALS.01     4  0.2224     0.9867 0.00 0.12 0.00 0.86 0.00 0.00 0.00 0.02
#&gt; TCGA.2G.AAG3.01     2  0.0000     0.9689 0.00 1.00 0.00 0.00 0.00 0.00 0.00 0.00
#&gt; TCGA.2G.AALN.01     2  0.0000     0.9689 0.00 1.00 0.00 0.00 0.00 0.00 0.00 0.00
#&gt; TCGA.ZM.AA0D.01     1  0.0000     0.8591 1.00 0.00 0.00 0.00 0.00 0.00 0.00 0.00
#&gt; TCGA.2G.AAG9.01     3  0.3198     0.5395 0.00 0.00 0.72 0.00 0.00 0.00 0.26 0.02
#&gt; TCGA.2G.AAGC.01     4  0.1947     0.9737 0.00 0.14 0.00 0.86 0.00 0.00 0.00 0.00
#&gt; TCGA.2X.A9D6.01     1  0.3909     0.7320 0.70 0.00 0.18 0.00 0.00 0.00 0.00 0.12
#&gt; TCGA.4K.AAAL.01     3  0.5859    -0.0237 0.00 0.00 0.50 0.00 0.02 0.30 0.08 0.10
#&gt; TCGA.SN.A84Y.01     4  0.1765     0.9855 0.00 0.12 0.00 0.88 0.00 0.00 0.00 0.00
#&gt; TCGA.VF.A8AA.01     1  0.0471     0.8585 0.98 0.00 0.00 0.00 0.00 0.00 0.00 0.02
#&gt; TCGA.2G.AAH3.01     5  0.1341     0.8915 0.00 0.00 0.00 0.00 0.92 0.08 0.00 0.00
#&gt; TCGA.YU.A90Q.01     7  0.2025     0.5470 0.00 0.00 0.10 0.00 0.00 0.00 0.88 0.02
#&gt; TCGA.2G.AAKO.01     1  0.0000     0.8591 1.00 0.00 0.00 0.00 0.00 0.00 0.00 0.00
#&gt; TCGA.2G.AAGZ.01     4  0.2224     0.9867 0.00 0.12 0.00 0.86 0.00 0.00 0.00 0.02
#&gt; TCGA.VF.A8AB.01     5  0.1741     0.8824 0.02 0.00 0.00 0.02 0.92 0.04 0.00 0.00
#&gt; TCGA.2G.AALF.01     2  0.3185     0.7950 0.00 0.82 0.04 0.06 0.00 0.00 0.00 0.08
#&gt; TCGA.2G.AAL7.01     4  0.1765     0.9855 0.00 0.12 0.00 0.88 0.00 0.00 0.00 0.00
#&gt; TCGA.2G.AALQ.01     2  0.0000     0.9689 0.00 1.00 0.00 0.00 0.00 0.00 0.00 0.00
#&gt; TCGA.2G.AAFN.01     4  0.1947     0.9682 0.00 0.14 0.00 0.86 0.00 0.00 0.00 0.00
#&gt; TCGA.2G.AAFG.01     6  0.3728     0.3767 0.00 0.00 0.00 0.02 0.28 0.68 0.00 0.02
#&gt; TCGA.2G.AAGN.01     4  0.1765     0.9855 0.00 0.12 0.00 0.88 0.00 0.00 0.00 0.00
#&gt; TCGA.XE.AAOD.01     1  0.4174     0.3781 0.62 0.00 0.00 0.02 0.32 0.04 0.00 0.00
#&gt; TCGA.XE.AAOF.01     1  0.2818     0.8215 0.82 0.00 0.06 0.00 0.00 0.00 0.00 0.12
#&gt; TCGA.XY.A8S3.01     2  0.0000     0.9689 0.00 1.00 0.00 0.00 0.00 0.00 0.00 0.00
#&gt; TCGA.2G.AAFV.01     2  0.0471     0.9485 0.00 0.98 0.00 0.02 0.00 0.00 0.00 0.00
#&gt; TCGA.2G.AAHP.05     1  0.2648     0.8245 0.84 0.00 0.08 0.00 0.00 0.00 0.00 0.08
#&gt; TCGA.2G.AAH4.01     2  0.0000     0.9689 0.00 1.00 0.00 0.00 0.00 0.00 0.00 0.00
#&gt; TCGA.XE.AAO3.01     8  0.4302     0.9572 0.00 0.00 0.00 0.00 0.08 0.36 0.00 0.56
#&gt; TCGA.SB.A76C.01     3  0.4680     0.3134 0.00 0.00 0.48 0.00 0.00 0.00 0.40 0.12
#&gt; TCGA.2G.AAHG.01     7  0.6835     0.2548 0.00 0.00 0.30 0.02 0.00 0.18 0.32 0.18
#&gt; TCGA.XE.AAO6.01     6  0.0471     0.6175 0.00 0.00 0.02 0.00 0.00 0.98 0.00 0.00
#&gt; TCGA.SB.A6J6.01     6  0.2132     0.5855 0.00 0.00 0.00 0.00 0.08 0.88 0.00 0.04
#&gt; TCGA.YU.AA61.01     2  0.0000     0.9689 0.00 1.00 0.00 0.00 0.00 0.00 0.00 0.00
#&gt; TCGA.2G.AAG7.01     2  0.0000     0.9689 0.00 1.00 0.00 0.00 0.00 0.00 0.00 0.00
#&gt; TCGA.XY.A8S2.01     4  0.1765     0.9855 0.00 0.12 0.00 0.88 0.00 0.00 0.00 0.00
#&gt; TCGA.2G.AAEX.01     6  0.1091     0.6053 0.00 0.00 0.06 0.00 0.00 0.94 0.00 0.00
#&gt; TCGA.2G.AAH0.01     6  0.1557     0.5969 0.00 0.00 0.06 0.00 0.00 0.92 0.00 0.02
#&gt; TCGA.2G.AAKD.01     4  0.1765     0.9855 0.00 0.12 0.00 0.88 0.00 0.00 0.00 0.00
#&gt; TCGA.VF.A8AD.01     4  0.2224     0.9867 0.00 0.12 0.00 0.86 0.00 0.00 0.00 0.02
#&gt; TCGA.2G.AALR.01     2  0.0000     0.9689 0.00 1.00 0.00 0.00 0.00 0.00 0.00 0.00
#&gt; TCGA.2G.AAFM.01     4  0.2224     0.9867 0.00 0.12 0.00 0.86 0.00 0.00 0.00 0.02
#&gt; TCGA.2G.AALG.01     2  0.0000     0.9689 0.00 1.00 0.00 0.00 0.00 0.00 0.00 0.00
#&gt; TCGA.XE.AAOJ.01     2  0.0000     0.9689 0.00 1.00 0.00 0.00 0.00 0.00 0.00 0.00
#&gt; TCGA.2G.AAGI.01     2  0.0000     0.9689 0.00 1.00 0.00 0.00 0.00 0.00 0.00 0.00
#&gt; TCGA.W4.A7U2.01     6  0.3431     0.3338 0.00 0.00 0.00 0.00 0.06 0.74 0.00 0.20
#&gt; TCGA.S6.A8JY.01     7  0.6543     0.2700 0.00 0.00 0.34 0.02 0.00 0.16 0.36 0.12
#&gt; TCGA.2G.AAH8.01     7  0.1947     0.5196 0.00 0.00 0.14 0.00 0.00 0.00 0.86 0.00
#&gt; TCGA.2G.AAHP.01     8  0.4673     0.9584 0.00 0.00 0.00 0.02 0.08 0.34 0.00 0.56
#&gt; TCGA.2G.AAGW.01     2  0.0000     0.9689 0.00 1.00 0.00 0.00 0.00 0.00 0.00 0.00
#&gt; TCGA.2X.A9D5.01     6  0.6129    -0.0613 0.18 0.00 0.36 0.00 0.00 0.36 0.00 0.10
#&gt; TCGA.2G.AAGX.01     2  0.0000     0.9689 0.00 1.00 0.00 0.00 0.00 0.00 0.00 0.00
</code></pre>

<script>
$('#tab-node-0-get-classes-7-a').parent().next().next().hide();
$('#tab-node-0-get-classes-7-a').click(function(){
  $('#tab-node-0-get-classes-7-a').parent().next().next().toggle();
  return(false);
});
</script>
</div>
</div>

Heatmaps for the consensus matrix. It visualizes the probability of two
samples to be in a same group.




<script>
$( function() {
	$( '#tabs-node-0-consensus-heatmap' ).tabs();
} );
</script>
<div id='tabs-node-0-consensus-heatmap'>
<ul>
<li><a href='#tab-node-0-consensus-heatmap-1'>k = 2</a></li>
<li><a href='#tab-node-0-consensus-heatmap-2'>k = 3</a></li>
<li><a href='#tab-node-0-consensus-heatmap-3'>k = 4</a></li>
<li><a href='#tab-node-0-consensus-heatmap-4'>k = 5</a></li>
<li><a href='#tab-node-0-consensus-heatmap-5'>k = 6</a></li>
<li><a href='#tab-node-0-consensus-heatmap-6'>k = 7</a></li>
<li><a href='#tab-node-0-consensus-heatmap-7'>k = 8</a></li>
</ul>
<div id='tab-node-0-consensus-heatmap-1'>
<pre><code class="r">consensus_heatmap(res, k = 2)
</code></pre>

<p><img src="figure_cola/tab-node-0-consensus-heatmap-1-1.png" alt="plot of chunk tab-node-0-consensus-heatmap-1"/></p>

</div>
<div id='tab-node-0-consensus-heatmap-2'>
<pre><code class="r">consensus_heatmap(res, k = 3)
</code></pre>

<p><img src="figure_cola/tab-node-0-consensus-heatmap-2-1.png" alt="plot of chunk tab-node-0-consensus-heatmap-2"/></p>

</div>
<div id='tab-node-0-consensus-heatmap-3'>
<pre><code class="r">consensus_heatmap(res, k = 4)
</code></pre>

<p><img src="figure_cola/tab-node-0-consensus-heatmap-3-1.png" alt="plot of chunk tab-node-0-consensus-heatmap-3"/></p>

</div>
<div id='tab-node-0-consensus-heatmap-4'>
<pre><code class="r">consensus_heatmap(res, k = 5)
</code></pre>

<p><img src="figure_cola/tab-node-0-consensus-heatmap-4-1.png" alt="plot of chunk tab-node-0-consensus-heatmap-4"/></p>

</div>
<div id='tab-node-0-consensus-heatmap-5'>
<pre><code class="r">consensus_heatmap(res, k = 6)
</code></pre>

<p><img src="figure_cola/tab-node-0-consensus-heatmap-5-1.png" alt="plot of chunk tab-node-0-consensus-heatmap-5"/></p>

</div>
<div id='tab-node-0-consensus-heatmap-6'>
<pre><code class="r">consensus_heatmap(res, k = 7)
</code></pre>

<p><img src="figure_cola/tab-node-0-consensus-heatmap-6-1.png" alt="plot of chunk tab-node-0-consensus-heatmap-6"/></p>

</div>
<div id='tab-node-0-consensus-heatmap-7'>
<pre><code class="r">consensus_heatmap(res, k = 8)
</code></pre>

<p><img src="figure_cola/tab-node-0-consensus-heatmap-7-1.png" alt="plot of chunk tab-node-0-consensus-heatmap-7"/></p>

</div>
</div>

Heatmaps for the membership of samples in all partitions to see how consistent they are:





<script>
$( function() {
	$( '#tabs-node-0-membership-heatmap' ).tabs();
} );
</script>
<div id='tabs-node-0-membership-heatmap'>
<ul>
<li><a href='#tab-node-0-membership-heatmap-1'>k = 2</a></li>
<li><a href='#tab-node-0-membership-heatmap-2'>k = 3</a></li>
<li><a href='#tab-node-0-membership-heatmap-3'>k = 4</a></li>
<li><a href='#tab-node-0-membership-heatmap-4'>k = 5</a></li>
<li><a href='#tab-node-0-membership-heatmap-5'>k = 6</a></li>
<li><a href='#tab-node-0-membership-heatmap-6'>k = 7</a></li>
<li><a href='#tab-node-0-membership-heatmap-7'>k = 8</a></li>
</ul>
<div id='tab-node-0-membership-heatmap-1'>
<pre><code class="r">membership_heatmap(res, k = 2)
</code></pre>

<p><img src="figure_cola/tab-node-0-membership-heatmap-1-1.png" alt="plot of chunk tab-node-0-membership-heatmap-1"/></p>

</div>
<div id='tab-node-0-membership-heatmap-2'>
<pre><code class="r">membership_heatmap(res, k = 3)
</code></pre>

<p><img src="figure_cola/tab-node-0-membership-heatmap-2-1.png" alt="plot of chunk tab-node-0-membership-heatmap-2"/></p>

</div>
<div id='tab-node-0-membership-heatmap-3'>
<pre><code class="r">membership_heatmap(res, k = 4)
</code></pre>

<p><img src="figure_cola/tab-node-0-membership-heatmap-3-1.png" alt="plot of chunk tab-node-0-membership-heatmap-3"/></p>

</div>
<div id='tab-node-0-membership-heatmap-4'>
<pre><code class="r">membership_heatmap(res, k = 5)
</code></pre>

<p><img src="figure_cola/tab-node-0-membership-heatmap-4-1.png" alt="plot of chunk tab-node-0-membership-heatmap-4"/></p>

</div>
<div id='tab-node-0-membership-heatmap-5'>
<pre><code class="r">membership_heatmap(res, k = 6)
</code></pre>

<p><img src="figure_cola/tab-node-0-membership-heatmap-5-1.png" alt="plot of chunk tab-node-0-membership-heatmap-5"/></p>

</div>
<div id='tab-node-0-membership-heatmap-6'>
<pre><code class="r">membership_heatmap(res, k = 7)
</code></pre>

<p><img src="figure_cola/tab-node-0-membership-heatmap-6-1.png" alt="plot of chunk tab-node-0-membership-heatmap-6"/></p>

</div>
<div id='tab-node-0-membership-heatmap-7'>
<pre><code class="r">membership_heatmap(res, k = 8)
</code></pre>

<p><img src="figure_cola/tab-node-0-membership-heatmap-7-1.png" alt="plot of chunk tab-node-0-membership-heatmap-7"/></p>

</div>
</div>

As soon as the classes for columns are determined, the signatures
that are significantly different between subgroups can be looked for. 
Following are the heatmaps for signatures.






<script>
$( function() {
	$( '#tabs-node-0-get-signatures' ).tabs();
} );
</script>
<div id='tabs-node-0-get-signatures'>
<ul>
<li><a href='#tab-node-0-get-signatures-1'>k = 2</a></li>
<li><a href='#tab-node-0-get-signatures-2'>k = 3</a></li>
<li><a href='#tab-node-0-get-signatures-3'>k = 4</a></li>
<li><a href='#tab-node-0-get-signatures-4'>k = 5</a></li>
<li><a href='#tab-node-0-get-signatures-5'>k = 6</a></li>
<li><a href='#tab-node-0-get-signatures-6'>k = 7</a></li>
<li><a href='#tab-node-0-get-signatures-7'>k = 8</a></li>
</ul>
<div id='tab-node-0-get-signatures-1'>
<pre><code class="r">get_signatures(res, k = 2)
</code></pre>

<p><img src="figure_cola/tab-node-0-get-signatures-1-1.png" alt="plot of chunk tab-node-0-get-signatures-1"/></p>

</div>
<div id='tab-node-0-get-signatures-2'>
<pre><code class="r">get_signatures(res, k = 3)
</code></pre>

<p><img src="figure_cola/tab-node-0-get-signatures-2-1.png" alt="plot of chunk tab-node-0-get-signatures-2"/></p>

</div>
<div id='tab-node-0-get-signatures-3'>
<pre><code class="r">get_signatures(res, k = 4)
</code></pre>

<p><img src="figure_cola/tab-node-0-get-signatures-3-1.png" alt="plot of chunk tab-node-0-get-signatures-3"/></p>

</div>
<div id='tab-node-0-get-signatures-4'>
<pre><code class="r">get_signatures(res, k = 5)
</code></pre>

<p><img src="figure_cola/tab-node-0-get-signatures-4-1.png" alt="plot of chunk tab-node-0-get-signatures-4"/></p>

</div>
<div id='tab-node-0-get-signatures-5'>
<pre><code class="r">get_signatures(res, k = 6)
</code></pre>

<p><img src="figure_cola/tab-node-0-get-signatures-5-1.png" alt="plot of chunk tab-node-0-get-signatures-5"/></p>

</div>
<div id='tab-node-0-get-signatures-6'>
<pre><code class="r">get_signatures(res, k = 7)
</code></pre>

<p><img src="figure_cola/tab-node-0-get-signatures-6-1.png" alt="plot of chunk tab-node-0-get-signatures-6"/></p>

</div>
<div id='tab-node-0-get-signatures-7'>
<pre><code class="r">get_signatures(res, k = 8)
</code></pre>

<p><img src="figure_cola/tab-node-0-get-signatures-7-1.png" alt="plot of chunk tab-node-0-get-signatures-7"/></p>

</div>
</div>



Compare the overlap of signatures from different k:

```r
compare_signatures(res)
```

![plot of chunk node-0-signature_compare](figure_cola/node-0-signature_compare-1.png)

`get_signature()` returns a data frame invisibly. To get the list of signatures, the function
call should be assigned to a variable explicitly. In following code, if `plot` argument is set
to `FALSE`, no heatmap is plotted while only the differential analysis is performed.

```r
# code only for demonstration
tb = get_signature(res, k = ..., plot = FALSE)
```

An example of the output of `tb` is:

```
#>   which_row         fdr    mean_1    mean_2 scaled_mean_1 scaled_mean_2 km
#> 1        38 0.042760348  8.373488  9.131774    -0.5533452     0.5164555  1
#> 2        40 0.018707592  7.106213  8.469186    -0.6173731     0.5762149  1
#> 3        55 0.019134737 10.221463 11.207825    -0.6159697     0.5749050  1
#> 4        59 0.006059896  5.921854  7.869574    -0.6899429     0.6439467  1
#> 5        60 0.018055526  8.928898 10.211722    -0.6204761     0.5791110  1
#> 6        98 0.009384629 15.714769 14.887706     0.6635654    -0.6193277  2
...
```

The columns in `tb` are:

1. `which_row`: row indices corresponding to the input matrix.
2. `fdr`: FDR for the differential test. 
3. `mean_x`: The mean value in group x.
4. `scaled_mean_x`: The mean value in group x after rows are scaled.
5. `km`: Row groups if k-means clustering is applied to rows (which is done by automatically selecting number of clusters).

If there are too many signatures, `top_signatures = ...` can be set to only show the 
signatures with the highest FDRs:

```r
# code only for demonstration
# e.g. to show the top 500 most significant rows
tb = get_signature(res, k = ..., top_signatures = 500)
```

If the signatures are defined as these which are uniquely high in current group, `diff_method` argument
can be set to `"uniquely_high_in_one_group"`:

```r
# code only for demonstration
tb = get_signature(res, k = ..., diff_method = "uniquely_high_in_one_group")
```




UMAP plot which shows how samples are separated.


<script>
$( function() {
	$( '#tabs-node-0-dimension-reduction' ).tabs();
} );
</script>
<div id='tabs-node-0-dimension-reduction'>
<ul>
<li><a href='#tab-node-0-dimension-reduction-1'>k = 2</a></li>
<li><a href='#tab-node-0-dimension-reduction-2'>k = 3</a></li>
<li><a href='#tab-node-0-dimension-reduction-3'>k = 4</a></li>
<li><a href='#tab-node-0-dimension-reduction-4'>k = 5</a></li>
<li><a href='#tab-node-0-dimension-reduction-5'>k = 6</a></li>
<li><a href='#tab-node-0-dimension-reduction-6'>k = 7</a></li>
<li><a href='#tab-node-0-dimension-reduction-7'>k = 8</a></li>
</ul>
<div id='tab-node-0-dimension-reduction-1'>
<pre><code class="r">dimension_reduction(res, k = 2, method = &quot;UMAP&quot;)
</code></pre>

<p><img src="figure_cola/tab-node-0-dimension-reduction-1-1.png" alt="plot of chunk tab-node-0-dimension-reduction-1"/></p>

</div>
<div id='tab-node-0-dimension-reduction-2'>
<pre><code class="r">dimension_reduction(res, k = 3, method = &quot;UMAP&quot;)
</code></pre>

<p><img src="figure_cola/tab-node-0-dimension-reduction-2-1.png" alt="plot of chunk tab-node-0-dimension-reduction-2"/></p>

</div>
<div id='tab-node-0-dimension-reduction-3'>
<pre><code class="r">dimension_reduction(res, k = 4, method = &quot;UMAP&quot;)
</code></pre>

<p><img src="figure_cola/tab-node-0-dimension-reduction-3-1.png" alt="plot of chunk tab-node-0-dimension-reduction-3"/></p>

</div>
<div id='tab-node-0-dimension-reduction-4'>
<pre><code class="r">dimension_reduction(res, k = 5, method = &quot;UMAP&quot;)
</code></pre>

<p><img src="figure_cola/tab-node-0-dimension-reduction-4-1.png" alt="plot of chunk tab-node-0-dimension-reduction-4"/></p>

</div>
<div id='tab-node-0-dimension-reduction-5'>
<pre><code class="r">dimension_reduction(res, k = 6, method = &quot;UMAP&quot;)
</code></pre>

<p><img src="figure_cola/tab-node-0-dimension-reduction-5-1.png" alt="plot of chunk tab-node-0-dimension-reduction-5"/></p>

</div>
<div id='tab-node-0-dimension-reduction-6'>
<pre><code class="r">dimension_reduction(res, k = 7, method = &quot;UMAP&quot;)
</code></pre>

<p><img src="figure_cola/tab-node-0-dimension-reduction-6-1.png" alt="plot of chunk tab-node-0-dimension-reduction-6"/></p>

</div>
<div id='tab-node-0-dimension-reduction-7'>
<pre><code class="r">dimension_reduction(res, k = 8, method = &quot;UMAP&quot;)
</code></pre>

<p><img src="figure_cola/tab-node-0-dimension-reduction-7-1.png" alt="plot of chunk tab-node-0-dimension-reduction-7"/></p>

</div>
</div>



Following heatmap shows how subgroups are split when increasing `k`:

```r
collect_classes(res)
```

![plot of chunk node-0-collect-classes](figure_cola/node-0-collect-classes-1.png)



If matrix rows can be associated to genes, consider to use `functional_enrichment(res,
...)` to perform function enrichment for the signature genes. See [this vignette](https://jokergoo.github.io/cola_vignettes/functional_enrichment.html) for more detailed explanations.


 

---------------------------------------------------




### Node01


Parent node: [Node0](#Node0).
Child nodes: 
                Node011-leaf
        ,
                [Node012](#Node012)
        ,
                Node013-leaf
        ,
                Node021-leaf
        ,
                [Node022](#Node022)
        ,
                [Node023](#Node023)
        ,
                [Node024](#Node024)
        ,
                Node031-leaf
        ,
                Node032-leaf
        ,
                Node033-leaf
        ,
                Node034-leaf
        .







The object with results only for a single top-value method and a single partitioning method 
can be extracted as:

```r
res = res_rh["01"]
```

A summary of `res` and all the functions that can be applied to it:

```r
res
```

```
#> A 'ConsensusPartition' object with k = 2, 3, 4, 5, 6, 7, 8.
#>   On a matrix with 30000 rows and 51 columns.
#>   Top rows (1000) are extracted by 'SD' method.
#>   Subgroups are detected by 'skmeans' method.
#>   Performed in total 350 partitions by row resampling.
#>   Best k for subgroups seems to be 3.
#> 
#> Following methods can be applied to this 'ConsensusPartition' object:
#>  [1] "cola_report"             "collect_classes"         "collect_plots"          
#>  [4] "collect_stats"           "colnames"                "compare_partitions"     
#>  [7] "compare_signatures"      "consensus_heatmap"       "dimension_reduction"    
#> [10] "functional_enrichment"   "get_anno_col"            "get_anno"               
#> [13] "get_classes"             "get_consensus"           "get_matrix"             
#> [16] "get_membership"          "get_param"               "get_signatures"         
#> [19] "get_stats"               "is_best_k"               "is_stable_k"            
#> [22] "membership_heatmap"      "ncol"                    "nrow"                   
#> [25] "plot_ecdf"               "predict_classes"         "rownames"               
#> [28] "select_partition_number" "show"                    "suggest_best_k"         
#> [31] "test_to_known_factors"   "top_rows_heatmap"
```

`collect_plots()` function collects all the plots made from `res` for all `k` (number of subgroups)
into one single page to provide an easy and fast comparison between different `k`.

```r
collect_plots(res)
```

![plot of chunk node-01-collect-plots](figure_cola/node-01-collect-plots-1.png)

The plots are:

- The first row: a plot of the eCDF (empirical cumulative distribution
  function) curves of the consensus matrix for each `k` and the heatmap of
  predicted classes for each `k`.
- The second row: heatmaps of the consensus matrix for each `k`.
- The third row: heatmaps of the membership matrix for each `k`.
- The fouth row: heatmaps of the signatures for each `k`.

All the plots in panels can be made by individual functions and they are
plotted later in this section.

`select_partition_number()` produces several plots showing different
statistics for choosing "optimized" `k`. There are following statistics:

- eCDF curves of the consensus matrix for each `k`;
- 1-PAC. [The PAC score](https://en.wikipedia.org/wiki/Consensus_clustering#Over-interpretation_potential_of_consensus_clustering)
  measures the proportion of the ambiguous subgrouping.
- Mean silhouette score.
- Concordance. The mean probability of fiting the consensus subgroup labels in all
  partitions.
- Area increased. Denote $A_k$ as the area under the eCDF curve for current
  `k`, the area increased is defined as $A_k - A_{k-1}$.
- Rand index. The percent of pairs of samples that are both in a same cluster
  or both are not in a same cluster in the partition of k and k-1.
- Jaccard index. The ratio of pairs of samples are both in a same cluster in
  the partition of k and k-1 and the pairs of samples are both in a same
  cluster in the partition k or k-1.

The detailed explanations of these statistics can be found in [the _cola_
vignette](https://jokergoo.github.io/cola_vignettes/cola.html#toc_13).

Generally speaking, higher 1-PAC score, higher mean silhouette score or higher
concordance corresponds to better partition. Rand index and Jaccard index
measure how similar the current partition is compared to partition with `k-1`.
If they are too similar, we won't accept `k` is better than `k-1`.

```r
select_partition_number(res)
```

![plot of chunk node-01-select-partition-number](figure_cola/node-01-select-partition-number-1.png)

The numeric values for all these statistics can be obtained by `get_stats()`.

```r
get_stats(res)
```

```
#>   k 1-PAC mean_silhouette concordance area_increased  Rand Jaccard
#> 2 2 1.000           1.000       1.000         0.5087 0.492   0.492
#> 3 3 1.000           0.984       0.989         0.2710 0.862   0.719
#> 4 4 0.683           0.822       0.835         0.1107 1.000   1.000
#> 5 5 0.632           0.639       0.765         0.0736 0.888   0.683
#> 6 6 0.622           0.508       0.717         0.0400 0.916   0.682
#> 7 7 0.630           0.372       0.701         0.0272 0.901   0.597
#> 8 8 0.626           0.413       0.680         0.0196 0.925   0.658
```

`suggest_best_k()` suggests the best $k$ based on these statistics. The rules are as follows:

- All $k$ with Jaccard index larger than 0.95 are removed because increasing
  $k$ does not provide enough extra information. If all $k$ are removed, it is
  marked as no subgroup is detected.
- For all $k$ with 1-PAC score larger than 0.9, the maximal $k$ is taken as
  the best $k$, and other $k$ are marked as optional $k$.
- If it does not fit the second rule. The $k$ with the maximal vote of the
  highest 1-PAC score, highest mean silhouette, and highest concordance is
  taken as the best $k$.

```r
suggest_best_k(res)
```

```
#> [1] 3
#> attr(,"optional")
#> [1] 2
```

There is also optional best $k$ = 2 that is worth to check.

Following is the table of the partitions (You need to click the **show/hide
code output** link to see it). The membership matrix (columns with name `p*`)
is inferred by
[`clue::cl_consensus()`](https://www.rdocumentation.org/link/cl_consensus?package=clue)
function with the `SE` method. Basically the value in the membership matrix
represents the probability to belong to a certain group. The finall subgroup
label for an item is determined with the group with highest probability it
belongs to.

In `get_classes()` function, the entropy is calculated from the membership
matrix and the silhouette score is calculated from the consensus matrix.



<script>
$( function() {
	$( '#tabs-node-01-get-classes' ).tabs();
} );
</script>
<div id='tabs-node-01-get-classes'>
<ul>
<li><a href='#tab-node-01-get-classes-1'>k = 2</a></li>
<li><a href='#tab-node-01-get-classes-2'>k = 3</a></li>
<li><a href='#tab-node-01-get-classes-3'>k = 4</a></li>
<li><a href='#tab-node-01-get-classes-4'>k = 5</a></li>
<li><a href='#tab-node-01-get-classes-5'>k = 6</a></li>
<li><a href='#tab-node-01-get-classes-6'>k = 7</a></li>
<li><a href='#tab-node-01-get-classes-7'>k = 8</a></li>
</ul>

<div id='tab-node-01-get-classes-1'>
<p><a id='tab-node-01-get-classes-1-a' style='color:#0366d6' href='#'>show/hide code output</a></p>
<pre><code class="r">cbind(get_classes(res, k = 2), get_membership(res, k = 2))
</code></pre>

<pre><code>#&gt;                 class entropy silhouette p1 p2
#&gt; TCGA.XE.A8H4.01     1       0          1  1  0
#&gt; TCGA.2G.AAF1.01     1       0          1  1  0
#&gt; TCGA.VF.A8AC.01     1       0          1  1  0
#&gt; TCGA.ZM.AA0E.01     1       0          1  1  0
#&gt; TCGA.XE.A9SE.01     2       0          1  0  1
#&gt; TCGA.2G.AAKO.05     1       0          1  1  0
#&gt; TCGA.2G.AAGI.05     1       0          1  1  0
#&gt; TCGA.YU.A90S.01     1       0          1  1  0
#&gt; TCGA.XY.A89B.01     1       0          1  1  0
#&gt; TCGA.ZM.AA05.01     1       0          1  1  0
#&gt; TCGA.ZM.AA0F.01     1       0          1  1  0
#&gt; TCGA.XE.AANJ.01     2       0          1  0  1
#&gt; TCGA.WZ.A7V5.01     1       0          1  1  0
#&gt; TCGA.WZ.A8D5.01     1       0          1  1  0
#&gt; TCGA.2G.AAHC.01     2       0          1  0  1
#&gt; TCGA.2G.AAFH.01     2       0          1  0  1
#&gt; TCGA.2G.AAHN.01     1       0          1  1  0
#&gt; TCGA.XE.AAO4.01     1       0          1  1  0
#&gt; TCGA.ZM.AA0N.01     2       0          1  0  1
#&gt; TCGA.VF.A8AE.01     2       0          1  0  1
#&gt; TCGA.2G.AAF6.01     2       0          1  0  1
#&gt; TCGA.4K.AA1I.01     1       0          1  1  0
#&gt; TCGA.XY.A9T9.01     2       0          1  0  1
#&gt; TCGA.WZ.A7V4.01     1       0          1  1  0
#&gt; TCGA.4K.AA1H.01     1       0          1  1  0
#&gt; TCGA.ZM.AA06.01     2       0          1  0  1
#&gt; TCGA.VF.A8A9.01     2       0          1  0  1
#&gt; TCGA.ZM.AA0H.01     1       0          1  1  0
#&gt; TCGA.ZM.AA0B.01     2       0          1  0  1
#&gt; TCGA.SN.A6IS.01     2       0          1  0  1
#&gt; TCGA.2G.AAF8.01     2       0          1  0  1
#&gt; TCGA.2G.AAF4.01     2       0          1  0  1
#&gt; TCGA.2G.AAFG.05     2       0          1  0  1
#&gt; TCGA.ZM.AA0D.01     1       0          1  1  0
#&gt; TCGA.2X.A9D6.01     1       0          1  1  0
#&gt; TCGA.VF.A8AA.01     1       0          1  1  0
#&gt; TCGA.2G.AAH3.01     2       0          1  0  1
#&gt; TCGA.2G.AAKO.01     1       0          1  1  0
#&gt; TCGA.VF.A8AB.01     2       0          1  0  1
#&gt; TCGA.2G.AAFG.01     2       0          1  0  1
#&gt; TCGA.XE.AAOD.01     2       0          1  0  1
#&gt; TCGA.XE.AAOF.01     1       0          1  1  0
#&gt; TCGA.2G.AAHP.05     1       0          1  1  0
#&gt; TCGA.XE.AAO3.01     2       0          1  0  1
#&gt; TCGA.XE.AAO6.01     2       0          1  0  1
#&gt; TCGA.SB.A6J6.01     2       0          1  0  1
#&gt; TCGA.2G.AAEX.01     2       0          1  0  1
#&gt; TCGA.2G.AAH0.01     2       0          1  0  1
#&gt; TCGA.W4.A7U2.01     2       0          1  0  1
#&gt; TCGA.2G.AAHP.01     2       0          1  0  1
#&gt; TCGA.2X.A9D5.01     2       0          1  0  1
</code></pre>

<script>
$('#tab-node-01-get-classes-1-a').parent().next().next().hide();
$('#tab-node-01-get-classes-1-a').click(function(){
  $('#tab-node-01-get-classes-1-a').parent().next().next().toggle();
  return(false);
});
</script>
</div>

<div id='tab-node-01-get-classes-2'>
<p><a id='tab-node-01-get-classes-2-a' style='color:#0366d6' href='#'>show/hide code output</a></p>
<pre><code class="r">cbind(get_classes(res, k = 3), get_membership(res, k = 3))
</code></pre>

<pre><code>#&gt;                 class entropy silhouette   p1   p2   p3
#&gt; TCGA.XE.A8H4.01     1  0.0000      0.995 1.00 0.00 0.00
#&gt; TCGA.2G.AAF1.01     1  0.0000      0.995 1.00 0.00 0.00
#&gt; TCGA.VF.A8AC.01     1  0.0000      0.995 1.00 0.00 0.00
#&gt; TCGA.ZM.AA0E.01     1  0.0000      0.995 1.00 0.00 0.00
#&gt; TCGA.XE.A9SE.01     3  0.2066      0.960 0.00 0.06 0.94
#&gt; TCGA.2G.AAKO.05     1  0.0892      0.986 0.98 0.00 0.02
#&gt; TCGA.2G.AAGI.05     1  0.0000      0.995 1.00 0.00 0.00
#&gt; TCGA.YU.A90S.01     1  0.0892      0.986 0.98 0.00 0.02
#&gt; TCGA.XY.A89B.01     1  0.0000      0.995 1.00 0.00 0.00
#&gt; TCGA.ZM.AA05.01     1  0.0000      0.995 1.00 0.00 0.00
#&gt; TCGA.ZM.AA0F.01     1  0.0892      0.986 0.98 0.00 0.02
#&gt; TCGA.XE.AANJ.01     2  0.0000      0.988 0.00 1.00 0.00
#&gt; TCGA.WZ.A7V5.01     1  0.0000      0.995 1.00 0.00 0.00
#&gt; TCGA.WZ.A8D5.01     1  0.0000      0.995 1.00 0.00 0.00
#&gt; TCGA.2G.AAHC.01     3  0.0892      0.983 0.00 0.02 0.98
#&gt; TCGA.2G.AAFH.01     3  0.2066      0.960 0.00 0.06 0.94
#&gt; TCGA.2G.AAHN.01     1  0.0000      0.995 1.00 0.00 0.00
#&gt; TCGA.XE.AAO4.01     1  0.0000      0.995 1.00 0.00 0.00
#&gt; TCGA.ZM.AA0N.01     3  0.0892      0.983 0.00 0.02 0.98
#&gt; TCGA.VF.A8AE.01     3  0.0000      0.974 0.00 0.00 1.00
#&gt; TCGA.2G.AAF6.01     2  0.0000      0.988 0.00 1.00 0.00
#&gt; TCGA.4K.AA1I.01     1  0.0000      0.995 1.00 0.00 0.00
#&gt; TCGA.XY.A9T9.01     2  0.4002      0.814 0.00 0.84 0.16
#&gt; TCGA.WZ.A7V4.01     1  0.0000      0.995 1.00 0.00 0.00
#&gt; TCGA.4K.AA1H.01     1  0.0892      0.986 0.98 0.00 0.02
#&gt; TCGA.ZM.AA06.01     2  0.0000      0.988 0.00 1.00 0.00
#&gt; TCGA.VF.A8A9.01     3  0.0892      0.983 0.00 0.02 0.98
#&gt; TCGA.ZM.AA0H.01     1  0.0000      0.995 1.00 0.00 0.00
#&gt; TCGA.ZM.AA0B.01     2  0.0000      0.988 0.00 1.00 0.00
#&gt; TCGA.SN.A6IS.01     2  0.0000      0.988 0.00 1.00 0.00
#&gt; TCGA.2G.AAF8.01     3  0.1529      0.974 0.00 0.04 0.96
#&gt; TCGA.2G.AAF4.01     2  0.0000      0.988 0.00 1.00 0.00
#&gt; TCGA.2G.AAFG.05     3  0.0000      0.974 0.00 0.00 1.00
#&gt; TCGA.ZM.AA0D.01     1  0.0892      0.986 0.98 0.00 0.02
#&gt; TCGA.2X.A9D6.01     1  0.0000      0.995 1.00 0.00 0.00
#&gt; TCGA.VF.A8AA.01     1  0.0000      0.995 1.00 0.00 0.00
#&gt; TCGA.2G.AAH3.01     2  0.0000      0.988 0.00 1.00 0.00
#&gt; TCGA.2G.AAKO.01     1  0.0892      0.986 0.98 0.00 0.02
#&gt; TCGA.VF.A8AB.01     3  0.0892      0.983 0.00 0.02 0.98
#&gt; TCGA.2G.AAFG.01     3  0.0892      0.983 0.00 0.02 0.98
#&gt; TCGA.XE.AAOD.01     3  0.0000      0.974 0.00 0.00 1.00
#&gt; TCGA.XE.AAOF.01     1  0.0000      0.995 1.00 0.00 0.00
#&gt; TCGA.2G.AAHP.05     1  0.0000      0.995 1.00 0.00 0.00
#&gt; TCGA.XE.AAO3.01     2  0.0000      0.988 0.00 1.00 0.00
#&gt; TCGA.XE.AAO6.01     2  0.0000      0.988 0.00 1.00 0.00
#&gt; TCGA.SB.A6J6.01     2  0.0000      0.988 0.00 1.00 0.00
#&gt; TCGA.2G.AAEX.01     2  0.0000      0.988 0.00 1.00 0.00
#&gt; TCGA.2G.AAH0.01     2  0.0000      0.988 0.00 1.00 0.00
#&gt; TCGA.W4.A7U2.01     2  0.0000      0.988 0.00 1.00 0.00
#&gt; TCGA.2G.AAHP.01     2  0.0000      0.988 0.00 1.00 0.00
#&gt; TCGA.2X.A9D5.01     2  0.0892      0.971 0.00 0.98 0.02
</code></pre>

<script>
$('#tab-node-01-get-classes-2-a').parent().next().next().hide();
$('#tab-node-01-get-classes-2-a').click(function(){
  $('#tab-node-01-get-classes-2-a').parent().next().next().toggle();
  return(false);
});
</script>
</div>

<div id='tab-node-01-get-classes-3'>
<p><a id='tab-node-01-get-classes-3-a' style='color:#0366d6' href='#'>show/hide code output</a></p>
<pre><code class="r">cbind(get_classes(res, k = 4), get_membership(res, k = 4))
</code></pre>

<pre><code>#&gt;                 class entropy silhouette   p1   p2   p3   p4
#&gt; TCGA.XE.A8H4.01     1  0.3172      0.826 0.84 0.00 0.00 0.16
#&gt; TCGA.2G.AAF1.01     1  0.4406      0.804 0.70 0.00 0.00 0.30
#&gt; TCGA.VF.A8AC.01     1  0.1211      0.823 0.96 0.00 0.00 0.04
#&gt; TCGA.ZM.AA0E.01     1  0.2647      0.837 0.88 0.00 0.00 0.12
#&gt; TCGA.XE.A9SE.01     3  0.5147      0.796 0.00 0.06 0.74 0.20
#&gt; TCGA.2G.AAKO.05     1  0.4907      0.759 0.58 0.00 0.00 0.42
#&gt; TCGA.2G.AAGI.05     1  0.3172      0.835 0.84 0.00 0.00 0.16
#&gt; TCGA.YU.A90S.01     1  0.4907      0.759 0.58 0.00 0.00 0.42
#&gt; TCGA.XY.A89B.01     1  0.2647      0.806 0.88 0.00 0.00 0.12
#&gt; TCGA.ZM.AA05.01     1  0.0707      0.835 0.98 0.00 0.00 0.02
#&gt; TCGA.ZM.AA0F.01     1  0.4855      0.769 0.60 0.00 0.00 0.40
#&gt; TCGA.XE.AANJ.01     2  0.1211      0.874 0.00 0.96 0.00 0.04
#&gt; TCGA.WZ.A7V5.01     1  0.2647      0.791 0.88 0.00 0.00 0.12
#&gt; TCGA.WZ.A8D5.01     1  0.2345      0.801 0.90 0.00 0.00 0.10
#&gt; TCGA.2G.AAHC.01     3  0.2335      0.877 0.00 0.02 0.92 0.06
#&gt; TCGA.2G.AAFH.01     3  0.5147      0.796 0.00 0.06 0.74 0.20
#&gt; TCGA.2G.AAHN.01     1  0.3975      0.821 0.76 0.00 0.00 0.24
#&gt; TCGA.XE.AAO4.01     1  0.2345      0.801 0.90 0.00 0.00 0.10
#&gt; TCGA.ZM.AA0N.01     3  0.1913      0.895 0.00 0.02 0.94 0.04
#&gt; TCGA.VF.A8AE.01     3  0.3172      0.830 0.00 0.00 0.84 0.16
#&gt; TCGA.2G.AAF6.01     2  0.0000      0.877 0.00 1.00 0.00 0.00
#&gt; TCGA.4K.AA1I.01     1  0.4522      0.802 0.68 0.00 0.00 0.32
#&gt; TCGA.XY.A9T9.01     2  0.5767      0.628 0.00 0.66 0.28 0.06
#&gt; TCGA.WZ.A7V4.01     1  0.3172      0.837 0.84 0.00 0.00 0.16
#&gt; TCGA.4K.AA1H.01     1  0.4907      0.759 0.58 0.00 0.00 0.42
#&gt; TCGA.ZM.AA06.01     2  0.1211      0.878 0.00 0.96 0.00 0.04
#&gt; TCGA.VF.A8A9.01     3  0.0000      0.898 0.00 0.00 1.00 0.00
#&gt; TCGA.ZM.AA0H.01     1  0.2345      0.836 0.90 0.00 0.00 0.10
#&gt; TCGA.ZM.AA0B.01     2  0.3821      0.840 0.00 0.84 0.04 0.12
#&gt; TCGA.SN.A6IS.01     2  0.1211      0.873 0.00 0.96 0.00 0.04
#&gt; TCGA.2G.AAF8.01     3  0.3525      0.870 0.00 0.04 0.86 0.10
#&gt; TCGA.2G.AAF4.01     2  0.1211      0.874 0.00 0.96 0.00 0.04
#&gt; TCGA.2G.AAFG.05     3  0.2011      0.883 0.00 0.00 0.92 0.08
#&gt; TCGA.ZM.AA0D.01     1  0.4790      0.778 0.62 0.00 0.00 0.38
#&gt; TCGA.2X.A9D6.01     1  0.2345      0.839 0.90 0.00 0.00 0.10
#&gt; TCGA.VF.A8AA.01     1  0.3172      0.839 0.84 0.00 0.00 0.16
#&gt; TCGA.2G.AAH3.01     2  0.4292      0.819 0.00 0.82 0.08 0.10
#&gt; TCGA.2G.AAKO.01     1  0.4907      0.759 0.58 0.00 0.00 0.42
#&gt; TCGA.VF.A8AB.01     3  0.2345      0.887 0.00 0.00 0.90 0.10
#&gt; TCGA.2G.AAFG.01     3  0.2706      0.886 0.00 0.02 0.90 0.08
#&gt; TCGA.XE.AAOD.01     3  0.0000      0.898 0.00 0.00 1.00 0.00
#&gt; TCGA.XE.AAOF.01     1  0.2011      0.822 0.92 0.00 0.00 0.08
#&gt; TCGA.2G.AAHP.05     1  0.2921      0.797 0.86 0.00 0.00 0.14
#&gt; TCGA.XE.AAO3.01     2  0.6449      0.661 0.00 0.64 0.14 0.22
#&gt; TCGA.XE.AAO6.01     2  0.0707      0.877 0.00 0.98 0.00 0.02
#&gt; TCGA.SB.A6J6.01     2  0.3606      0.819 0.00 0.84 0.14 0.02
#&gt; TCGA.2G.AAEX.01     2  0.0707      0.876 0.00 0.98 0.00 0.02
#&gt; TCGA.2G.AAH0.01     2  0.0707      0.877 0.00 0.98 0.00 0.02
#&gt; TCGA.W4.A7U2.01     2  0.3198      0.853 0.00 0.88 0.04 0.08
#&gt; TCGA.2G.AAHP.01     2  0.4939      0.777 0.00 0.74 0.04 0.22
#&gt; TCGA.2X.A9D5.01     2  0.5956      0.678 0.00 0.68 0.10 0.22
</code></pre>

<script>
$('#tab-node-01-get-classes-3-a').parent().next().next().hide();
$('#tab-node-01-get-classes-3-a').click(function(){
  $('#tab-node-01-get-classes-3-a').parent().next().next().toggle();
  return(false);
});
</script>
</div>

<div id='tab-node-01-get-classes-4'>
<p><a id='tab-node-01-get-classes-4-a' style='color:#0366d6' href='#'>show/hide code output</a></p>
<pre><code class="r">cbind(get_classes(res, k = 5), get_membership(res, k = 5))
</code></pre>

<pre><code>#&gt;                 class entropy silhouette   p1   p2   p3   p4   p5
#&gt; TCGA.XE.A8H4.01     1  0.4818      0.452 0.52 0.02 0.00 0.00 0.46
#&gt; TCGA.2G.AAF1.01     5  0.3424      0.509 0.24 0.00 0.00 0.00 0.76
#&gt; TCGA.VF.A8AC.01     1  0.5558      0.574 0.56 0.08 0.00 0.00 0.36
#&gt; TCGA.ZM.AA0E.01     1  0.4818      0.440 0.52 0.02 0.00 0.00 0.46
#&gt; TCGA.XE.A9SE.01     3  0.4060      0.729 0.00 0.36 0.64 0.00 0.00
#&gt; TCGA.2G.AAKO.05     5  0.0000      0.711 0.00 0.00 0.00 0.00 1.00
#&gt; TCGA.2G.AAGI.05     1  0.4302      0.342 0.52 0.00 0.00 0.00 0.48
#&gt; TCGA.YU.A90S.01     5  0.0000      0.711 0.00 0.00 0.00 0.00 1.00
#&gt; TCGA.XY.A89B.01     1  0.5156      0.618 0.62 0.06 0.00 0.00 0.32
#&gt; TCGA.ZM.AA05.01     1  0.3983      0.606 0.66 0.00 0.00 0.00 0.34
#&gt; TCGA.ZM.AA0F.01     5  0.1410      0.706 0.06 0.00 0.00 0.00 0.94
#&gt; TCGA.XE.AANJ.01     4  0.2516      0.770 0.00 0.14 0.00 0.86 0.00
#&gt; TCGA.WZ.A7V5.01     1  0.5136      0.664 0.66 0.08 0.00 0.00 0.26
#&gt; TCGA.WZ.A8D5.01     1  0.3922      0.665 0.78 0.04 0.00 0.00 0.18
#&gt; TCGA.2G.AAHC.01     3  0.0000      0.838 0.00 0.00 1.00 0.00 0.00
#&gt; TCGA.2G.AAFH.01     3  0.4060      0.729 0.00 0.36 0.64 0.00 0.00
#&gt; TCGA.2G.AAHN.01     5  0.4456      0.323 0.32 0.02 0.00 0.00 0.66
#&gt; TCGA.XE.AAO4.01     1  0.4170      0.635 0.78 0.08 0.00 0.00 0.14
#&gt; TCGA.ZM.AA0N.01     3  0.2732      0.836 0.00 0.16 0.84 0.00 0.00
#&gt; TCGA.VF.A8AE.01     3  0.2732      0.745 0.00 0.00 0.84 0.00 0.16
#&gt; TCGA.2G.AAF6.01     4  0.1043      0.792 0.00 0.04 0.00 0.96 0.00
#&gt; TCGA.4K.AA1I.01     5  0.3521      0.622 0.14 0.04 0.00 0.00 0.82
#&gt; TCGA.XY.A9T9.01     4  0.4540      0.498 0.00 0.02 0.34 0.64 0.00
#&gt; TCGA.WZ.A7V4.01     5  0.4767     -0.141 0.42 0.02 0.00 0.00 0.56
#&gt; TCGA.4K.AA1H.01     5  0.0000      0.711 0.00 0.00 0.00 0.00 1.00
#&gt; TCGA.ZM.AA06.01     4  0.2516      0.787 0.00 0.14 0.00 0.86 0.00
#&gt; TCGA.VF.A8A9.01     3  0.0609      0.843 0.00 0.02 0.98 0.00 0.00
#&gt; TCGA.ZM.AA0H.01     1  0.4818      0.422 0.52 0.02 0.00 0.00 0.46
#&gt; TCGA.ZM.AA0B.01     4  0.4644      0.707 0.00 0.28 0.04 0.68 0.00
#&gt; TCGA.SN.A6IS.01     4  0.1410      0.787 0.00 0.06 0.00 0.94 0.00
#&gt; TCGA.2G.AAF8.01     3  0.3274      0.817 0.00 0.22 0.78 0.00 0.00
#&gt; TCGA.2G.AAF4.01     4  0.1216      0.787 0.00 0.02 0.02 0.96 0.00
#&gt; TCGA.2G.AAFG.05     3  0.3520      0.790 0.08 0.02 0.86 0.02 0.02
#&gt; TCGA.ZM.AA0D.01     5  0.2020      0.683 0.10 0.00 0.00 0.00 0.90
#&gt; TCGA.2X.A9D6.01     1  0.4540      0.564 0.64 0.02 0.00 0.00 0.34
#&gt; TCGA.VF.A8AA.01     5  0.4767     -0.238 0.42 0.02 0.00 0.00 0.56
#&gt; TCGA.2G.AAH3.01     4  0.5783      0.606 0.00 0.36 0.10 0.54 0.00
#&gt; TCGA.2G.AAKO.01     5  0.0000      0.711 0.00 0.00 0.00 0.00 1.00
#&gt; TCGA.VF.A8AB.01     3  0.2929      0.833 0.00 0.18 0.82 0.00 0.00
#&gt; TCGA.2G.AAFG.01     3  0.3765      0.788 0.08 0.04 0.84 0.04 0.00
#&gt; TCGA.XE.AAOD.01     3  0.0609      0.843 0.00 0.02 0.98 0.00 0.00
#&gt; TCGA.XE.AAOF.01     1  0.3690      0.659 0.78 0.02 0.00 0.00 0.20
#&gt; TCGA.2G.AAHP.05     1  0.4982      0.672 0.70 0.10 0.00 0.00 0.20
#&gt; TCGA.XE.AAO3.01     4  0.5694      0.495 0.00 0.46 0.08 0.46 0.00
#&gt; TCGA.XE.AAO6.01     4  0.2929      0.781 0.00 0.18 0.00 0.82 0.00
#&gt; TCGA.SB.A6J6.01     4  0.4216      0.743 0.00 0.12 0.10 0.78 0.00
#&gt; TCGA.2G.AAEX.01     4  0.1043      0.789 0.00 0.04 0.00 0.96 0.00
#&gt; TCGA.2G.AAH0.01     4  0.2732      0.780 0.00 0.16 0.00 0.84 0.00
#&gt; TCGA.W4.A7U2.01     4  0.3852      0.736 0.00 0.22 0.02 0.76 0.00
#&gt; TCGA.2G.AAHP.01     4  0.5351      0.608 0.00 0.38 0.06 0.56 0.00
#&gt; TCGA.2X.A9D5.01     4  0.6280      0.525 0.04 0.40 0.06 0.50 0.00
</code></pre>

<script>
$('#tab-node-01-get-classes-4-a').parent().next().next().hide();
$('#tab-node-01-get-classes-4-a').click(function(){
  $('#tab-node-01-get-classes-4-a').parent().next().next().toggle();
  return(false);
});
</script>
</div>

<div id='tab-node-01-get-classes-5'>
<p><a id='tab-node-01-get-classes-5-a' style='color:#0366d6' href='#'>show/hide code output</a></p>
<pre><code class="r">cbind(get_classes(res, k = 6), get_membership(res, k = 6))
</code></pre>

<pre><code>#&gt;                 class entropy silhouette   p1   p2   p3   p4   p5   p6
#&gt; TCGA.XE.A8H4.01     1   0.465    0.23470 0.50 0.04 0.00 0.00 0.46 0.00
#&gt; TCGA.2G.AAF1.01     5   0.263    0.64256 0.18 0.00 0.00 0.00 0.82 0.00
#&gt; TCGA.VF.A8AC.01     1   0.532    0.47985 0.54 0.12 0.00 0.00 0.34 0.00
#&gt; TCGA.ZM.AA0E.01     1   0.480    0.57265 0.62 0.08 0.00 0.00 0.30 0.00
#&gt; TCGA.XE.A9SE.01     6   0.331    0.60518 0.00 0.00 0.28 0.00 0.00 0.72
#&gt; TCGA.2G.AAKO.05     5   0.000    0.71321 0.00 0.00 0.00 0.00 1.00 0.00
#&gt; TCGA.2G.AAGI.05     1   0.510    0.40075 0.50 0.08 0.00 0.00 0.42 0.00
#&gt; TCGA.YU.A90S.01     5   0.000    0.71321 0.00 0.00 0.00 0.00 1.00 0.00
#&gt; TCGA.XY.A89B.01     1   0.535    0.51581 0.58 0.16 0.00 0.00 0.26 0.00
#&gt; TCGA.ZM.AA05.01     1   0.408    0.54210 0.64 0.02 0.00 0.00 0.34 0.00
#&gt; TCGA.ZM.AA0F.01     5   0.235    0.69232 0.10 0.02 0.00 0.00 0.88 0.00
#&gt; TCGA.XE.AANJ.01     4   0.385    0.68441 0.00 0.10 0.02 0.80 0.00 0.08
#&gt; TCGA.WZ.A7V5.01     1   0.352    0.63234 0.78 0.04 0.00 0.00 0.18 0.00
#&gt; TCGA.WZ.A8D5.01     1   0.251    0.60937 0.88 0.06 0.00 0.00 0.06 0.00
#&gt; TCGA.2G.AAHC.01     3   0.209    0.65129 0.00 0.00 0.90 0.02 0.00 0.08
#&gt; TCGA.2G.AAFH.01     6   0.331    0.60518 0.00 0.00 0.28 0.00 0.00 0.72
#&gt; TCGA.2G.AAHN.01     5   0.552    0.00231 0.36 0.14 0.00 0.00 0.50 0.00
#&gt; TCGA.XE.AAO4.01     1   0.446    0.52310 0.66 0.28 0.00 0.00 0.06 0.00
#&gt; TCGA.ZM.AA0N.01     3   0.350    0.25249 0.00 0.00 0.68 0.00 0.00 0.32
#&gt; TCGA.VF.A8AE.01     3   0.258    0.62540 0.00 0.02 0.86 0.00 0.12 0.00
#&gt; TCGA.2G.AAF6.01     4   0.219    0.70124 0.00 0.00 0.04 0.90 0.00 0.06
#&gt; TCGA.4K.AA1I.01     5   0.410    0.50598 0.24 0.02 0.02 0.00 0.72 0.00
#&gt; TCGA.XY.A9T9.01     3   0.720   -0.17626 0.02 0.08 0.38 0.38 0.00 0.14
#&gt; TCGA.WZ.A7V4.01     5   0.559   -0.29772 0.42 0.14 0.00 0.00 0.44 0.00
#&gt; TCGA.4K.AA1H.01     5   0.000    0.71321 0.00 0.00 0.00 0.00 1.00 0.00
#&gt; TCGA.ZM.AA06.01     4   0.357    0.69339 0.00 0.10 0.00 0.80 0.00 0.10
#&gt; TCGA.VF.A8A9.01     3   0.205    0.62171 0.00 0.00 0.88 0.00 0.00 0.12
#&gt; TCGA.ZM.AA0H.01     1   0.427    0.57654 0.66 0.04 0.00 0.00 0.30 0.00
#&gt; TCGA.ZM.AA0B.01     4   0.433    0.17581 0.00 0.00 0.02 0.52 0.00 0.46
#&gt; TCGA.SN.A6IS.01     4   0.473    0.68301 0.02 0.08 0.04 0.76 0.00 0.10
#&gt; TCGA.2G.AAF8.01     6   0.385    0.38191 0.00 0.00 0.46 0.00 0.00 0.54
#&gt; TCGA.2G.AAF4.01     4   0.544    0.66149 0.02 0.06 0.08 0.70 0.00 0.14
#&gt; TCGA.2G.AAFG.05     3   0.326    0.63206 0.02 0.06 0.86 0.00 0.02 0.04
#&gt; TCGA.ZM.AA0D.01     5   0.279    0.61185 0.20 0.00 0.00 0.00 0.80 0.00
#&gt; TCGA.2X.A9D6.01     1   0.468    0.57168 0.68 0.12 0.00 0.00 0.20 0.00
#&gt; TCGA.VF.A8AA.01     1   0.543    0.37747 0.48 0.12 0.00 0.00 0.40 0.00
#&gt; TCGA.2G.AAH3.01     4   0.621    0.25066 0.00 0.06 0.10 0.50 0.00 0.34
#&gt; TCGA.2G.AAKO.01     5   0.000    0.71321 0.00 0.00 0.00 0.00 1.00 0.00
#&gt; TCGA.VF.A8AB.01     6   0.385    0.37580 0.00 0.00 0.46 0.00 0.00 0.54
#&gt; TCGA.2G.AAFG.01     3   0.395    0.60957 0.02 0.06 0.82 0.06 0.00 0.04
#&gt; TCGA.XE.AAOD.01     3   0.181    0.66104 0.00 0.00 0.92 0.00 0.02 0.06
#&gt; TCGA.XE.AAOF.01     1   0.433    0.62150 0.72 0.10 0.00 0.00 0.18 0.00
#&gt; TCGA.2G.AAHP.05     1   0.481    0.59162 0.66 0.22 0.00 0.00 0.12 0.00
#&gt; TCGA.XE.AAO3.01     6   0.395    0.41398 0.00 0.00 0.04 0.24 0.00 0.72
#&gt; TCGA.XE.AAO6.01     4   0.304    0.68583 0.00 0.10 0.00 0.84 0.00 0.06
#&gt; TCGA.SB.A6J6.01     4   0.701    0.44548 0.02 0.10 0.22 0.52 0.00 0.14
#&gt; TCGA.2G.AAEX.01     4   0.326    0.70207 0.02 0.04 0.02 0.86 0.00 0.06
#&gt; TCGA.2G.AAH0.01     4   0.332    0.68057 0.00 0.10 0.00 0.82 0.00 0.08
#&gt; TCGA.W4.A7U2.01     4   0.407    0.53679 0.00 0.00 0.04 0.70 0.00 0.26
#&gt; TCGA.2G.AAHP.01     6   0.408    0.11689 0.00 0.02 0.00 0.34 0.00 0.64
#&gt; TCGA.2X.A9D5.01     4   0.663    0.38329 0.00 0.38 0.08 0.42 0.00 0.12
</code></pre>

<script>
$('#tab-node-01-get-classes-5-a').parent().next().next().hide();
$('#tab-node-01-get-classes-5-a').click(function(){
  $('#tab-node-01-get-classes-5-a').parent().next().next().toggle();
  return(false);
});
</script>
</div>

<div id='tab-node-01-get-classes-6'>
<p><a id='tab-node-01-get-classes-6-a' style='color:#0366d6' href='#'>show/hide code output</a></p>
<pre><code class="r">cbind(get_classes(res, k = 7), get_membership(res, k = 7))
</code></pre>

<pre><code>#&gt;                 class entropy silhouette   p1   p2   p3   p4   p5   p6   p7
#&gt; TCGA.XE.A8H4.01     5  0.5293     0.2719 0.32 0.12 0.00 0.00 0.54 0.00 0.02
#&gt; TCGA.2G.AAF1.01     5  0.4499     0.5116 0.16 0.12 0.00 0.00 0.70 0.00 0.02
#&gt; TCGA.VF.A8AC.01     1  0.5180     0.1357 0.58 0.08 0.00 0.00 0.30 0.00 0.04
#&gt; TCGA.ZM.AA0E.01     1  0.4813     0.3617 0.64 0.10 0.00 0.00 0.24 0.00 0.02
#&gt; TCGA.XE.A9SE.01     6  0.3525     0.3154 0.00 0.00 0.44 0.00 0.00 0.56 0.00
#&gt; TCGA.2G.AAKO.05     5  0.0504     0.6308 0.00 0.02 0.00 0.00 0.98 0.00 0.00
#&gt; TCGA.2G.AAGI.05     1  0.5944     0.2949 0.46 0.14 0.00 0.00 0.36 0.02 0.02
#&gt; TCGA.YU.A90S.01     5  0.0000     0.6310 0.00 0.00 0.00 0.00 1.00 0.00 0.00
#&gt; TCGA.XY.A89B.01     1  0.5579     0.0219 0.38 0.26 0.00 0.00 0.36 0.00 0.00
#&gt; TCGA.ZM.AA05.01     5  0.5077     0.0770 0.38 0.08 0.00 0.00 0.52 0.02 0.00
#&gt; TCGA.ZM.AA0F.01     5  0.2376     0.6045 0.12 0.02 0.00 0.00 0.86 0.00 0.00
#&gt; TCGA.XE.AANJ.01     4  0.4308     0.5206 0.00 0.02 0.00 0.72 0.00 0.10 0.16
#&gt; TCGA.WZ.A7V5.01     1  0.2769     0.1650 0.86 0.04 0.00 0.00 0.08 0.00 0.02
#&gt; TCGA.WZ.A8D5.01     1  0.3566    -0.1488 0.78 0.16 0.00 0.00 0.04 0.00 0.02
#&gt; TCGA.2G.AAHC.01     3  0.0504     0.6883 0.00 0.00 0.98 0.00 0.00 0.00 0.02
#&gt; TCGA.2G.AAFH.01     6  0.3968     0.3233 0.00 0.00 0.44 0.02 0.00 0.54 0.00
#&gt; TCGA.2G.AAHN.01     5  0.5451     0.2246 0.28 0.16 0.00 0.00 0.54 0.02 0.00
#&gt; TCGA.XE.AAO4.01     2  0.4701     0.0000 0.44 0.50 0.00 0.00 0.04 0.00 0.02
#&gt; TCGA.ZM.AA0N.01     3  0.3052     0.5584 0.00 0.00 0.78 0.02 0.00 0.20 0.00
#&gt; TCGA.VF.A8AE.01     3  0.2512     0.6287 0.00 0.00 0.86 0.00 0.10 0.00 0.04
#&gt; TCGA.2G.AAF6.01     4  0.5167     0.4723 0.00 0.02 0.02 0.64 0.00 0.10 0.22
#&gt; TCGA.4K.AA1I.01     5  0.4479     0.4456 0.26 0.06 0.00 0.00 0.66 0.00 0.02
#&gt; TCGA.XY.A9T9.01     4  0.5837     0.1306 0.00 0.02 0.38 0.48 0.00 0.06 0.06
#&gt; TCGA.WZ.A7V4.01     5  0.5542    -0.0259 0.38 0.14 0.00 0.00 0.46 0.02 0.00
#&gt; TCGA.4K.AA1H.01     5  0.0504     0.6308 0.00 0.02 0.00 0.00 0.98 0.00 0.00
#&gt; TCGA.ZM.AA06.01     4  0.3208     0.5512 0.00 0.04 0.00 0.82 0.00 0.12 0.02
#&gt; TCGA.VF.A8A9.01     3  0.1363     0.6771 0.00 0.00 0.94 0.00 0.00 0.04 0.02
#&gt; TCGA.ZM.AA0H.01     1  0.4338     0.4039 0.64 0.08 0.00 0.00 0.28 0.00 0.00
#&gt; TCGA.ZM.AA0B.01     4  0.4701     0.2893 0.00 0.02 0.00 0.50 0.00 0.44 0.04
#&gt; TCGA.SN.A6IS.01     4  0.2509     0.5221 0.00 0.02 0.00 0.88 0.00 0.06 0.04
#&gt; TCGA.2G.AAF8.01     3  0.3780     0.4320 0.00 0.02 0.72 0.02 0.00 0.24 0.00
#&gt; TCGA.2G.AAF4.01     4  0.3635     0.4611 0.00 0.02 0.06 0.82 0.00 0.06 0.04
#&gt; TCGA.2G.AAFG.05     3  0.5946     0.5060 0.00 0.10 0.64 0.02 0.02 0.10 0.12
#&gt; TCGA.ZM.AA0D.01     5  0.2081     0.5953 0.14 0.00 0.00 0.00 0.86 0.00 0.00
#&gt; TCGA.2X.A9D6.01     1  0.5324     0.2497 0.58 0.22 0.00 0.00 0.18 0.02 0.00
#&gt; TCGA.VF.A8AA.01     5  0.5164     0.2361 0.20 0.26 0.00 0.00 0.54 0.00 0.00
#&gt; TCGA.2G.AAH3.01     4  0.6812     0.2448 0.00 0.12 0.14 0.44 0.00 0.28 0.02
#&gt; TCGA.2G.AAKO.01     5  0.0504     0.6308 0.00 0.02 0.00 0.00 0.98 0.00 0.00
#&gt; TCGA.VF.A8AB.01     3  0.3139     0.3613 0.00 0.00 0.70 0.00 0.00 0.30 0.00
#&gt; TCGA.2G.AAFG.01     3  0.6288     0.4508 0.00 0.10 0.60 0.08 0.00 0.10 0.12
#&gt; TCGA.XE.AAOD.01     3  0.0000     0.6897 0.00 0.00 1.00 0.00 0.00 0.00 0.00
#&gt; TCGA.XE.AAOF.01     1  0.6308     0.0267 0.42 0.30 0.00 0.00 0.22 0.00 0.06
#&gt; TCGA.2G.AAHP.05     1  0.3257     0.0299 0.84 0.04 0.00 0.00 0.08 0.02 0.02
#&gt; TCGA.XE.AAO3.01     6  0.3908     0.4638 0.00 0.00 0.08 0.20 0.00 0.72 0.00
#&gt; TCGA.XE.AAO6.01     4  0.5521     0.5063 0.00 0.12 0.00 0.62 0.00 0.16 0.10
#&gt; TCGA.SB.A6J6.01     4  0.3780     0.3796 0.00 0.00 0.24 0.72 0.00 0.02 0.02
#&gt; TCGA.2G.AAEX.01     4  0.1505     0.5468 0.00 0.02 0.00 0.94 0.00 0.02 0.02
#&gt; TCGA.2G.AAH0.01     4  0.4774     0.5255 0.00 0.08 0.00 0.70 0.00 0.14 0.08
#&gt; TCGA.W4.A7U2.01     4  0.5180     0.4285 0.00 0.02 0.00 0.54 0.00 0.34 0.10
#&gt; TCGA.2G.AAHP.01     6  0.3307     0.2946 0.00 0.00 0.00 0.24 0.00 0.74 0.02
#&gt; TCGA.2X.A9D5.01     7  0.3637     0.0000 0.00 0.00 0.04 0.24 0.00 0.00 0.72
</code></pre>

<script>
$('#tab-node-01-get-classes-6-a').parent().next().next().hide();
$('#tab-node-01-get-classes-6-a').click(function(){
  $('#tab-node-01-get-classes-6-a').parent().next().next().toggle();
  return(false);
});
</script>
</div>

<div id='tab-node-01-get-classes-7'>
<p><a id='tab-node-01-get-classes-7-a' style='color:#0366d6' href='#'>show/hide code output</a></p>
<pre><code class="r">cbind(get_classes(res, k = 8), get_membership(res, k = 8))
</code></pre>

<pre><code>#&gt;                 class entropy silhouette   p1   p2   p3   p4   p5   p6   p7   p8
#&gt; TCGA.XE.A8H4.01     5  0.5677    0.05648 0.12 0.34 0.00 0.00 0.48 0.02 0.00 0.04
#&gt; TCGA.2G.AAF1.01     5  0.3314    0.63029 0.10 0.08 0.00 0.00 0.80 0.02 0.00 0.00
#&gt; TCGA.VF.A8AC.01     2  0.6006    0.42345 0.10 0.54 0.00 0.00 0.26 0.02 0.04 0.04
#&gt; TCGA.ZM.AA0E.01     2  0.5159    0.39857 0.16 0.52 0.00 0.00 0.30 0.02 0.00 0.00
#&gt; TCGA.XE.A9SE.01     6  0.3015    0.38436 0.00 0.00 0.32 0.00 0.00 0.68 0.00 0.00
#&gt; TCGA.2G.AAKO.05     5  0.0471    0.68540 0.02 0.00 0.00 0.00 0.98 0.00 0.00 0.00
#&gt; TCGA.2G.AAGI.05     5  0.4480    0.25686 0.12 0.30 0.00 0.00 0.58 0.00 0.00 0.00
#&gt; TCGA.YU.A90S.01     5  0.0471    0.68540 0.02 0.00 0.00 0.00 0.98 0.00 0.00 0.00
#&gt; TCGA.XY.A89B.01     2  0.6269    0.32634 0.12 0.48 0.00 0.00 0.30 0.04 0.02 0.04
#&gt; TCGA.ZM.AA05.01     2  0.4717    0.30703 0.08 0.54 0.00 0.00 0.36 0.00 0.02 0.00
#&gt; TCGA.ZM.AA0F.01     5  0.1408    0.67867 0.02 0.02 0.00 0.00 0.94 0.02 0.00 0.00
#&gt; TCGA.XE.AANJ.01     4  0.5746    0.19699 0.02 0.02 0.00 0.60 0.00 0.06 0.18 0.12
#&gt; TCGA.WZ.A7V5.01     2  0.4293    0.54323 0.20 0.68 0.00 0.00 0.10 0.00 0.02 0.00
#&gt; TCGA.WZ.A8D5.01     2  0.3763    0.55038 0.10 0.78 0.00 0.00 0.08 0.00 0.02 0.02
#&gt; TCGA.2G.AAHC.01     3  0.1874    0.62821 0.00 0.00 0.92 0.02 0.00 0.02 0.02 0.02
#&gt; TCGA.2G.AAFH.01     6  0.2852    0.44766 0.00 0.00 0.28 0.00 0.00 0.72 0.00 0.00
#&gt; TCGA.2G.AAHN.01     5  0.4560    0.39007 0.22 0.18 0.00 0.00 0.60 0.00 0.00 0.00
#&gt; TCGA.XE.AAO4.01     2  0.6039    0.41115 0.32 0.50 0.00 0.00 0.04 0.06 0.02 0.06
#&gt; TCGA.ZM.AA0N.01     3  0.2852    0.44713 0.00 0.00 0.72 0.00 0.00 0.28 0.00 0.00
#&gt; TCGA.VF.A8AE.01     3  0.4781    0.49485 0.08 0.02 0.72 0.06 0.10 0.00 0.00 0.02
#&gt; TCGA.2G.AAF6.01     4  0.4627    0.27184 0.00 0.00 0.02 0.70 0.00 0.04 0.10 0.14
#&gt; TCGA.4K.AA1I.01     5  0.5201    0.28716 0.08 0.28 0.00 0.00 0.58 0.02 0.00 0.04
#&gt; TCGA.XY.A9T9.01     4  0.6128    0.15085 0.04 0.00 0.28 0.52 0.00 0.06 0.08 0.02
#&gt; TCGA.WZ.A7V4.01     5  0.4165    0.45689 0.10 0.26 0.00 0.00 0.64 0.00 0.00 0.00
#&gt; TCGA.4K.AA1H.01     5  0.0471    0.68540 0.02 0.00 0.00 0.00 0.98 0.00 0.00 0.00
#&gt; TCGA.ZM.AA06.01     4  0.5081    0.05815 0.06 0.00 0.00 0.64 0.00 0.08 0.02 0.20
#&gt; TCGA.VF.A8A9.01     3  0.2204    0.63571 0.02 0.00 0.90 0.02 0.00 0.04 0.00 0.02
#&gt; TCGA.ZM.AA0H.01     2  0.5116    0.37831 0.26 0.46 0.00 0.00 0.28 0.00 0.00 0.00
#&gt; TCGA.ZM.AA0B.01     6  0.3737   -0.00734 0.00 0.00 0.02 0.48 0.00 0.50 0.00 0.00
#&gt; TCGA.SN.A6IS.01     4  0.3080    0.42750 0.02 0.00 0.00 0.84 0.00 0.02 0.06 0.06
#&gt; TCGA.2G.AAF8.01     3  0.3272    0.19400 0.00 0.00 0.58 0.00 0.00 0.42 0.00 0.00
#&gt; TCGA.2G.AAF4.01     4  0.4401    0.40233 0.02 0.00 0.06 0.76 0.00 0.04 0.08 0.04
#&gt; TCGA.2G.AAFG.05     3  0.6065    0.45976 0.14 0.00 0.60 0.06 0.00 0.02 0.08 0.10
#&gt; TCGA.ZM.AA0D.01     5  0.3454    0.60707 0.02 0.12 0.00 0.00 0.80 0.04 0.02 0.00
#&gt; TCGA.2X.A9D6.01     2  0.5355    0.43786 0.30 0.48 0.00 0.00 0.20 0.00 0.00 0.02
#&gt; TCGA.VF.A8AA.01     5  0.3970    0.55016 0.08 0.18 0.00 0.00 0.72 0.00 0.00 0.02
#&gt; TCGA.2G.AAH3.01     8  0.5954    0.23302 0.04 0.00 0.04 0.16 0.00 0.16 0.02 0.58
#&gt; TCGA.2G.AAKO.01     5  0.0471    0.68540 0.02 0.00 0.00 0.00 0.98 0.00 0.00 0.00
#&gt; TCGA.VF.A8AB.01     3  0.3193    0.27361 0.00 0.00 0.62 0.00 0.00 0.38 0.00 0.00
#&gt; TCGA.2G.AAFG.01     3  0.6856    0.34071 0.14 0.00 0.50 0.16 0.00 0.02 0.08 0.10
#&gt; TCGA.XE.AAOD.01     3  0.0941    0.63591 0.02 0.00 0.96 0.00 0.00 0.02 0.00 0.00
#&gt; TCGA.XE.AAOF.01     2  0.5975    0.42237 0.20 0.46 0.00 0.00 0.28 0.04 0.02 0.00
#&gt; TCGA.2G.AAHP.05     2  0.5718    0.50705 0.10 0.60 0.00 0.00 0.16 0.04 0.00 0.10
#&gt; TCGA.XE.AAO3.01     6  0.2648    0.59658 0.00 0.00 0.08 0.08 0.00 0.84 0.00 0.00
#&gt; TCGA.XE.AAO6.01     8  0.5061    0.41768 0.00 0.00 0.00 0.42 0.00 0.04 0.08 0.46
#&gt; TCGA.SB.A6J6.01     4  0.4262    0.40706 0.00 0.00 0.12 0.74 0.00 0.08 0.04 0.02
#&gt; TCGA.2G.AAEX.01     4  0.3080    0.45064 0.02 0.00 0.00 0.84 0.00 0.02 0.06 0.06
#&gt; TCGA.2G.AAH0.01     8  0.5264    0.43917 0.00 0.00 0.00 0.40 0.00 0.06 0.08 0.46
#&gt; TCGA.W4.A7U2.01     4  0.5298    0.22486 0.00 0.00 0.02 0.56 0.00 0.30 0.06 0.06
#&gt; TCGA.2G.AAHP.01     6  0.3615    0.49405 0.00 0.00 0.00 0.20 0.00 0.74 0.02 0.04
#&gt; TCGA.2X.A9D5.01     7  0.3154    0.00000 0.00 0.00 0.06 0.16 0.00 0.00 0.78 0.00
</code></pre>

<script>
$('#tab-node-01-get-classes-7-a').parent().next().next().hide();
$('#tab-node-01-get-classes-7-a').click(function(){
  $('#tab-node-01-get-classes-7-a').parent().next().next().toggle();
  return(false);
});
</script>
</div>
</div>

Heatmaps for the consensus matrix. It visualizes the probability of two
samples to be in a same group.




<script>
$( function() {
	$( '#tabs-node-01-consensus-heatmap' ).tabs();
} );
</script>
<div id='tabs-node-01-consensus-heatmap'>
<ul>
<li><a href='#tab-node-01-consensus-heatmap-1'>k = 2</a></li>
<li><a href='#tab-node-01-consensus-heatmap-2'>k = 3</a></li>
<li><a href='#tab-node-01-consensus-heatmap-3'>k = 4</a></li>
<li><a href='#tab-node-01-consensus-heatmap-4'>k = 5</a></li>
<li><a href='#tab-node-01-consensus-heatmap-5'>k = 6</a></li>
<li><a href='#tab-node-01-consensus-heatmap-6'>k = 7</a></li>
<li><a href='#tab-node-01-consensus-heatmap-7'>k = 8</a></li>
</ul>
<div id='tab-node-01-consensus-heatmap-1'>
<pre><code class="r">consensus_heatmap(res, k = 2)
</code></pre>

<p><img src="figure_cola/tab-node-01-consensus-heatmap-1-1.png" alt="plot of chunk tab-node-01-consensus-heatmap-1"/></p>

</div>
<div id='tab-node-01-consensus-heatmap-2'>
<pre><code class="r">consensus_heatmap(res, k = 3)
</code></pre>

<p><img src="figure_cola/tab-node-01-consensus-heatmap-2-1.png" alt="plot of chunk tab-node-01-consensus-heatmap-2"/></p>

</div>
<div id='tab-node-01-consensus-heatmap-3'>
<pre><code class="r">consensus_heatmap(res, k = 4)
</code></pre>

<p><img src="figure_cola/tab-node-01-consensus-heatmap-3-1.png" alt="plot of chunk tab-node-01-consensus-heatmap-3"/></p>

</div>
<div id='tab-node-01-consensus-heatmap-4'>
<pre><code class="r">consensus_heatmap(res, k = 5)
</code></pre>

<p><img src="figure_cola/tab-node-01-consensus-heatmap-4-1.png" alt="plot of chunk tab-node-01-consensus-heatmap-4"/></p>

</div>
<div id='tab-node-01-consensus-heatmap-5'>
<pre><code class="r">consensus_heatmap(res, k = 6)
</code></pre>

<p><img src="figure_cola/tab-node-01-consensus-heatmap-5-1.png" alt="plot of chunk tab-node-01-consensus-heatmap-5"/></p>

</div>
<div id='tab-node-01-consensus-heatmap-6'>
<pre><code class="r">consensus_heatmap(res, k = 7)
</code></pre>

<p><img src="figure_cola/tab-node-01-consensus-heatmap-6-1.png" alt="plot of chunk tab-node-01-consensus-heatmap-6"/></p>

</div>
<div id='tab-node-01-consensus-heatmap-7'>
<pre><code class="r">consensus_heatmap(res, k = 8)
</code></pre>

<p><img src="figure_cola/tab-node-01-consensus-heatmap-7-1.png" alt="plot of chunk tab-node-01-consensus-heatmap-7"/></p>

</div>
</div>

Heatmaps for the membership of samples in all partitions to see how consistent they are:





<script>
$( function() {
	$( '#tabs-node-01-membership-heatmap' ).tabs();
} );
</script>
<div id='tabs-node-01-membership-heatmap'>
<ul>
<li><a href='#tab-node-01-membership-heatmap-1'>k = 2</a></li>
<li><a href='#tab-node-01-membership-heatmap-2'>k = 3</a></li>
<li><a href='#tab-node-01-membership-heatmap-3'>k = 4</a></li>
<li><a href='#tab-node-01-membership-heatmap-4'>k = 5</a></li>
<li><a href='#tab-node-01-membership-heatmap-5'>k = 6</a></li>
<li><a href='#tab-node-01-membership-heatmap-6'>k = 7</a></li>
<li><a href='#tab-node-01-membership-heatmap-7'>k = 8</a></li>
</ul>
<div id='tab-node-01-membership-heatmap-1'>
<pre><code class="r">membership_heatmap(res, k = 2)
</code></pre>

<p><img src="figure_cola/tab-node-01-membership-heatmap-1-1.png" alt="plot of chunk tab-node-01-membership-heatmap-1"/></p>

</div>
<div id='tab-node-01-membership-heatmap-2'>
<pre><code class="r">membership_heatmap(res, k = 3)
</code></pre>

<p><img src="figure_cola/tab-node-01-membership-heatmap-2-1.png" alt="plot of chunk tab-node-01-membership-heatmap-2"/></p>

</div>
<div id='tab-node-01-membership-heatmap-3'>
<pre><code class="r">membership_heatmap(res, k = 4)
</code></pre>

<p><img src="figure_cola/tab-node-01-membership-heatmap-3-1.png" alt="plot of chunk tab-node-01-membership-heatmap-3"/></p>

</div>
<div id='tab-node-01-membership-heatmap-4'>
<pre><code class="r">membership_heatmap(res, k = 5)
</code></pre>

<p><img src="figure_cola/tab-node-01-membership-heatmap-4-1.png" alt="plot of chunk tab-node-01-membership-heatmap-4"/></p>

</div>
<div id='tab-node-01-membership-heatmap-5'>
<pre><code class="r">membership_heatmap(res, k = 6)
</code></pre>

<p><img src="figure_cola/tab-node-01-membership-heatmap-5-1.png" alt="plot of chunk tab-node-01-membership-heatmap-5"/></p>

</div>
<div id='tab-node-01-membership-heatmap-6'>
<pre><code class="r">membership_heatmap(res, k = 7)
</code></pre>

<p><img src="figure_cola/tab-node-01-membership-heatmap-6-1.png" alt="plot of chunk tab-node-01-membership-heatmap-6"/></p>

</div>
<div id='tab-node-01-membership-heatmap-7'>
<pre><code class="r">membership_heatmap(res, k = 8)
</code></pre>

<p><img src="figure_cola/tab-node-01-membership-heatmap-7-1.png" alt="plot of chunk tab-node-01-membership-heatmap-7"/></p>

</div>
</div>

As soon as the classes for columns are determined, the signatures
that are significantly different between subgroups can be looked for. 
Following are the heatmaps for signatures.






<script>
$( function() {
	$( '#tabs-node-01-get-signatures' ).tabs();
} );
</script>
<div id='tabs-node-01-get-signatures'>
<ul>
<li><a href='#tab-node-01-get-signatures-1'>k = 2</a></li>
<li><a href='#tab-node-01-get-signatures-2'>k = 3</a></li>
<li><a href='#tab-node-01-get-signatures-3'>k = 4</a></li>
<li><a href='#tab-node-01-get-signatures-4'>k = 5</a></li>
<li><a href='#tab-node-01-get-signatures-5'>k = 6</a></li>
<li><a href='#tab-node-01-get-signatures-6'>k = 7</a></li>
<li><a href='#tab-node-01-get-signatures-7'>k = 8</a></li>
</ul>
<div id='tab-node-01-get-signatures-1'>
<pre><code class="r">get_signatures(res, k = 2)
</code></pre>

<p><img src="figure_cola/tab-node-01-get-signatures-1-1.png" alt="plot of chunk tab-node-01-get-signatures-1"/></p>

</div>
<div id='tab-node-01-get-signatures-2'>
<pre><code class="r">get_signatures(res, k = 3)
</code></pre>

<p><img src="figure_cola/tab-node-01-get-signatures-2-1.png" alt="plot of chunk tab-node-01-get-signatures-2"/></p>

</div>
<div id='tab-node-01-get-signatures-3'>
<pre><code class="r">get_signatures(res, k = 4)
</code></pre>

<p><img src="figure_cola/tab-node-01-get-signatures-3-1.png" alt="plot of chunk tab-node-01-get-signatures-3"/></p>

</div>
<div id='tab-node-01-get-signatures-4'>
<pre><code class="r">get_signatures(res, k = 5)
</code></pre>

<p><img src="figure_cola/tab-node-01-get-signatures-4-1.png" alt="plot of chunk tab-node-01-get-signatures-4"/></p>

</div>
<div id='tab-node-01-get-signatures-5'>
<pre><code class="r">get_signatures(res, k = 6)
</code></pre>

<p><img src="figure_cola/tab-node-01-get-signatures-5-1.png" alt="plot of chunk tab-node-01-get-signatures-5"/></p>

</div>
<div id='tab-node-01-get-signatures-6'>
<pre><code class="r">get_signatures(res, k = 7)
</code></pre>

<p><img src="figure_cola/tab-node-01-get-signatures-6-1.png" alt="plot of chunk tab-node-01-get-signatures-6"/></p>

</div>
<div id='tab-node-01-get-signatures-7'>
<pre><code class="r">get_signatures(res, k = 8)
</code></pre>

<p><img src="figure_cola/tab-node-01-get-signatures-7-1.png" alt="plot of chunk tab-node-01-get-signatures-7"/></p>

</div>
</div>



Compare the overlap of signatures from different k:

```r
compare_signatures(res)
```

![plot of chunk node-01-signature_compare](figure_cola/node-01-signature_compare-1.png)

`get_signature()` returns a data frame invisibly. To get the list of signatures, the function
call should be assigned to a variable explicitly. In following code, if `plot` argument is set
to `FALSE`, no heatmap is plotted while only the differential analysis is performed.

```r
# code only for demonstration
tb = get_signature(res, k = ..., plot = FALSE)
```

An example of the output of `tb` is:

```
#>   which_row         fdr    mean_1    mean_2 scaled_mean_1 scaled_mean_2 km
#> 1        38 0.042760348  8.373488  9.131774    -0.5533452     0.5164555  1
#> 2        40 0.018707592  7.106213  8.469186    -0.6173731     0.5762149  1
#> 3        55 0.019134737 10.221463 11.207825    -0.6159697     0.5749050  1
#> 4        59 0.006059896  5.921854  7.869574    -0.6899429     0.6439467  1
#> 5        60 0.018055526  8.928898 10.211722    -0.6204761     0.5791110  1
#> 6        98 0.009384629 15.714769 14.887706     0.6635654    -0.6193277  2
...
```

The columns in `tb` are:

1. `which_row`: row indices corresponding to the input matrix.
2. `fdr`: FDR for the differential test. 
3. `mean_x`: The mean value in group x.
4. `scaled_mean_x`: The mean value in group x after rows are scaled.
5. `km`: Row groups if k-means clustering is applied to rows (which is done by automatically selecting number of clusters).

If there are too many signatures, `top_signatures = ...` can be set to only show the 
signatures with the highest FDRs:

```r
# code only for demonstration
# e.g. to show the top 500 most significant rows
tb = get_signature(res, k = ..., top_signatures = 500)
```

If the signatures are defined as these which are uniquely high in current group, `diff_method` argument
can be set to `"uniquely_high_in_one_group"`:

```r
# code only for demonstration
tb = get_signature(res, k = ..., diff_method = "uniquely_high_in_one_group")
```




UMAP plot which shows how samples are separated.


<script>
$( function() {
	$( '#tabs-node-01-dimension-reduction' ).tabs();
} );
</script>
<div id='tabs-node-01-dimension-reduction'>
<ul>
<li><a href='#tab-node-01-dimension-reduction-1'>k = 2</a></li>
<li><a href='#tab-node-01-dimension-reduction-2'>k = 3</a></li>
<li><a href='#tab-node-01-dimension-reduction-3'>k = 4</a></li>
<li><a href='#tab-node-01-dimension-reduction-4'>k = 5</a></li>
<li><a href='#tab-node-01-dimension-reduction-5'>k = 6</a></li>
<li><a href='#tab-node-01-dimension-reduction-6'>k = 7</a></li>
<li><a href='#tab-node-01-dimension-reduction-7'>k = 8</a></li>
</ul>
<div id='tab-node-01-dimension-reduction-1'>
<pre><code class="r">dimension_reduction(res, k = 2, method = &quot;UMAP&quot;)
</code></pre>

<p><img src="figure_cola/tab-node-01-dimension-reduction-1-1.png" alt="plot of chunk tab-node-01-dimension-reduction-1"/></p>

</div>
<div id='tab-node-01-dimension-reduction-2'>
<pre><code class="r">dimension_reduction(res, k = 3, method = &quot;UMAP&quot;)
</code></pre>

<p><img src="figure_cola/tab-node-01-dimension-reduction-2-1.png" alt="plot of chunk tab-node-01-dimension-reduction-2"/></p>

</div>
<div id='tab-node-01-dimension-reduction-3'>
<pre><code class="r">dimension_reduction(res, k = 4, method = &quot;UMAP&quot;)
</code></pre>

<p><img src="figure_cola/tab-node-01-dimension-reduction-3-1.png" alt="plot of chunk tab-node-01-dimension-reduction-3"/></p>

</div>
<div id='tab-node-01-dimension-reduction-4'>
<pre><code class="r">dimension_reduction(res, k = 5, method = &quot;UMAP&quot;)
</code></pre>

<p><img src="figure_cola/tab-node-01-dimension-reduction-4-1.png" alt="plot of chunk tab-node-01-dimension-reduction-4"/></p>

</div>
<div id='tab-node-01-dimension-reduction-5'>
<pre><code class="r">dimension_reduction(res, k = 6, method = &quot;UMAP&quot;)
</code></pre>

<p><img src="figure_cola/tab-node-01-dimension-reduction-5-1.png" alt="plot of chunk tab-node-01-dimension-reduction-5"/></p>

</div>
<div id='tab-node-01-dimension-reduction-6'>
<pre><code class="r">dimension_reduction(res, k = 7, method = &quot;UMAP&quot;)
</code></pre>

<p><img src="figure_cola/tab-node-01-dimension-reduction-6-1.png" alt="plot of chunk tab-node-01-dimension-reduction-6"/></p>

</div>
<div id='tab-node-01-dimension-reduction-7'>
<pre><code class="r">dimension_reduction(res, k = 8, method = &quot;UMAP&quot;)
</code></pre>

<p><img src="figure_cola/tab-node-01-dimension-reduction-7-1.png" alt="plot of chunk tab-node-01-dimension-reduction-7"/></p>

</div>
</div>



Following heatmap shows how subgroups are split when increasing `k`:

```r
collect_classes(res)
```

![plot of chunk node-01-collect-classes](figure_cola/node-01-collect-classes-1.png)



If matrix rows can be associated to genes, consider to use `functional_enrichment(res,
...)` to perform function enrichment for the signature genes. See [this vignette](https://jokergoo.github.io/cola_vignettes/functional_enrichment.html) for more detailed explanations.


 

---------------------------------------------------




### Node012


Parent node: [Node01](#Node01).
Child nodes: 
                Node0121-leaf
        ,
                Node0122-leaf
        ,
                Node0123-leaf
        ,
                Node0221-leaf
        ,
                Node0222-leaf
        ,
                Node0223-leaf
        ,
                Node0224-leaf
        ,
                Node0231-leaf
        ,
                Node0232-leaf
        ,
                Node0233-leaf
        ,
                Node0234-leaf
        ,
                Node0241-leaf
        ,
                Node0242-leaf
        ,
                Node0243-leaf
        .







The object with results only for a single top-value method and a single partitioning method 
can be extracted as:

```r
res = res_rh["012"]
```

A summary of `res` and all the functions that can be applied to it:

```r
res
```

```
#> A 'ConsensusPartition' object with k = 2, 3, 4, 5, 6, 7, 8.
#>   On a matrix with 30000 rows and 16 columns.
#>   Top rows (1000) are extracted by 'ATC' method.
#>   Subgroups are detected by 'kmeans' method.
#>   Performed in total 350 partitions by row resampling.
#>   Best k for subgroups seems to be 3.
#> 
#> Following methods can be applied to this 'ConsensusPartition' object:
#>  [1] "cola_report"             "collect_classes"         "collect_plots"          
#>  [4] "collect_stats"           "colnames"                "compare_partitions"     
#>  [7] "compare_signatures"      "consensus_heatmap"       "dimension_reduction"    
#> [10] "functional_enrichment"   "get_anno_col"            "get_anno"               
#> [13] "get_classes"             "get_consensus"           "get_matrix"             
#> [16] "get_membership"          "get_param"               "get_signatures"         
#> [19] "get_stats"               "is_best_k"               "is_stable_k"            
#> [22] "membership_heatmap"      "ncol"                    "nrow"                   
#> [25] "plot_ecdf"               "predict_classes"         "rownames"               
#> [28] "select_partition_number" "show"                    "suggest_best_k"         
#> [31] "test_to_known_factors"   "top_rows_heatmap"
```

`collect_plots()` function collects all the plots made from `res` for all `k` (number of subgroups)
into one single page to provide an easy and fast comparison between different `k`.

```r
collect_plots(res)
```

![plot of chunk node-012-collect-plots](figure_cola/node-012-collect-plots-1.png)

The plots are:

- The first row: a plot of the eCDF (empirical cumulative distribution
  function) curves of the consensus matrix for each `k` and the heatmap of
  predicted classes for each `k`.
- The second row: heatmaps of the consensus matrix for each `k`.
- The third row: heatmaps of the membership matrix for each `k`.
- The fouth row: heatmaps of the signatures for each `k`.

All the plots in panels can be made by individual functions and they are
plotted later in this section.

`select_partition_number()` produces several plots showing different
statistics for choosing "optimized" `k`. There are following statistics:

- eCDF curves of the consensus matrix for each `k`;
- 1-PAC. [The PAC score](https://en.wikipedia.org/wiki/Consensus_clustering#Over-interpretation_potential_of_consensus_clustering)
  measures the proportion of the ambiguous subgrouping.
- Mean silhouette score.
- Concordance. The mean probability of fiting the consensus subgroup labels in all
  partitions.
- Area increased. Denote $A_k$ as the area under the eCDF curve for current
  `k`, the area increased is defined as $A_k - A_{k-1}$.
- Rand index. The percent of pairs of samples that are both in a same cluster
  or both are not in a same cluster in the partition of k and k-1.
- Jaccard index. The ratio of pairs of samples are both in a same cluster in
  the partition of k and k-1 and the pairs of samples are both in a same
  cluster in the partition k or k-1.

The detailed explanations of these statistics can be found in [the _cola_
vignette](https://jokergoo.github.io/cola_vignettes/cola.html#toc_13).

Generally speaking, higher 1-PAC score, higher mean silhouette score or higher
concordance corresponds to better partition. Rand index and Jaccard index
measure how similar the current partition is compared to partition with `k-1`.
If they are too similar, we won't accept `k` is better than `k-1`.

```r
select_partition_number(res)
```

![plot of chunk node-012-select-partition-number](figure_cola/node-012-select-partition-number-1.png)

The numeric values for all these statistics can be obtained by `get_stats()`.

```r
get_stats(res)
```

```
#>   k 1-PAC mean_silhouette concordance area_increased  Rand Jaccard
#> 2 2 0.542           0.939       0.925         0.4557 0.475   0.475
#> 3 3 1.000           0.969       0.974         0.4132 0.717   0.493
#> 4 4 0.775           0.940       0.935         0.1565 0.817   0.532
#> 5 5 0.858           0.775       0.924         0.0822 0.958   0.828
#> 6 6 0.883           0.840       0.938         0.0547 0.925   0.640
#> 7 7 0.900           0.788       0.900         0.0340 1.000   1.000
#> 8 8 0.875           0.684       0.744         0.0252 1.000   1.000
```

`suggest_best_k()` suggests the best $k$ based on these statistics. The rules are as follows:

- All $k$ with Jaccard index larger than 0.95 are removed because increasing
  $k$ does not provide enough extra information. If all $k$ are removed, it is
  marked as no subgroup is detected.
- For all $k$ with 1-PAC score larger than 0.9, the maximal $k$ is taken as
  the best $k$, and other $k$ are marked as optional $k$.
- If it does not fit the second rule. The $k$ with the maximal vote of the
  highest 1-PAC score, highest mean silhouette, and highest concordance is
  taken as the best $k$.

```r
suggest_best_k(res)
```

```
#> [1] 3
```


Following is the table of the partitions (You need to click the **show/hide
code output** link to see it). The membership matrix (columns with name `p*`)
is inferred by
[`clue::cl_consensus()`](https://www.rdocumentation.org/link/cl_consensus?package=clue)
function with the `SE` method. Basically the value in the membership matrix
represents the probability to belong to a certain group. The finall subgroup
label for an item is determined with the group with highest probability it
belongs to.

In `get_classes()` function, the entropy is calculated from the membership
matrix and the silhouette score is calculated from the consensus matrix.



<script>
$( function() {
	$( '#tabs-node-012-get-classes' ).tabs();
} );
</script>
<div id='tabs-node-012-get-classes'>
<ul>
<li><a href='#tab-node-012-get-classes-1'>k = 2</a></li>
<li><a href='#tab-node-012-get-classes-2'>k = 3</a></li>
<li><a href='#tab-node-012-get-classes-3'>k = 4</a></li>
<li><a href='#tab-node-012-get-classes-4'>k = 5</a></li>
<li><a href='#tab-node-012-get-classes-5'>k = 6</a></li>
<li><a href='#tab-node-012-get-classes-6'>k = 7</a></li>
<li><a href='#tab-node-012-get-classes-7'>k = 8</a></li>
</ul>

<div id='tab-node-012-get-classes-1'>
<p><a id='tab-node-012-get-classes-1-a' style='color:#0366d6' href='#'>show/hide code output</a></p>
<pre><code class="r">cbind(get_classes(res, k = 2), get_membership(res, k = 2))
</code></pre>

<pre><code>#&gt;                 class entropy silhouette   p1   p2
#&gt; TCGA.XE.AANJ.01     2   0.795      0.895 0.24 0.76
#&gt; TCGA.2G.AAF6.01     1   0.000      1.000 1.00 0.00
#&gt; TCGA.XY.A9T9.01     1   0.000      1.000 1.00 0.00
#&gt; TCGA.ZM.AA06.01     2   0.795      0.895 0.24 0.76
#&gt; TCGA.ZM.AA0B.01     1   0.000      1.000 1.00 0.00
#&gt; TCGA.SN.A6IS.01     2   0.795      0.895 0.24 0.76
#&gt; TCGA.2G.AAF4.01     1   0.000      1.000 1.00 0.00
#&gt; TCGA.2G.AAH3.01     2   0.795      0.895 0.24 0.76
#&gt; TCGA.XE.AAO3.01     2   0.000      0.772 0.00 1.00
#&gt; TCGA.XE.AAO6.01     1   0.000      1.000 1.00 0.00
#&gt; TCGA.SB.A6J6.01     1   0.000      1.000 1.00 0.00
#&gt; TCGA.2G.AAEX.01     1   0.000      1.000 1.00 0.00
#&gt; TCGA.2G.AAH0.01     1   0.000      1.000 1.00 0.00
#&gt; TCGA.W4.A7U2.01     2   0.795      0.895 0.24 0.76
#&gt; TCGA.2G.AAHP.01     2   0.000      0.772 0.00 1.00
#&gt; TCGA.2X.A9D5.01     1   0.000      1.000 1.00 0.00
</code></pre>

<script>
$('#tab-node-012-get-classes-1-a').parent().next().next().hide();
$('#tab-node-012-get-classes-1-a').click(function(){
  $('#tab-node-012-get-classes-1-a').parent().next().next().toggle();
  return(false);
});
</script>
</div>

<div id='tab-node-012-get-classes-2'>
<p><a id='tab-node-012-get-classes-2-a' style='color:#0366d6' href='#'>show/hide code output</a></p>
<pre><code class="r">cbind(get_classes(res, k = 3), get_membership(res, k = 3))
</code></pre>

<pre><code>#&gt;                 class entropy silhouette   p1   p2   p3
#&gt; TCGA.XE.AANJ.01     2   0.000      0.974 0.00 1.00 0.00
#&gt; TCGA.2G.AAF6.01     2   0.207      0.936 0.06 0.94 0.00
#&gt; TCGA.XY.A9T9.01     1   0.207      0.959 0.94 0.00 0.06
#&gt; TCGA.ZM.AA06.01     2   0.000      0.974 0.00 1.00 0.00
#&gt; TCGA.ZM.AA0B.01     1   0.000      0.969 1.00 0.00 0.00
#&gt; TCGA.SN.A6IS.01     2   0.000      0.974 0.00 1.00 0.00
#&gt; TCGA.2G.AAF4.01     1   0.207      0.959 0.94 0.00 0.06
#&gt; TCGA.2G.AAH3.01     2   0.000      0.974 0.00 1.00 0.00
#&gt; TCGA.XE.AAO3.01     3   0.207      1.000 0.00 0.06 0.94
#&gt; TCGA.XE.AAO6.01     2   0.207      0.936 0.06 0.94 0.00
#&gt; TCGA.SB.A6J6.01     1   0.207      0.959 0.94 0.00 0.06
#&gt; TCGA.2G.AAEX.01     1   0.000      0.969 1.00 0.00 0.00
#&gt; TCGA.2G.AAH0.01     1   0.000      0.969 1.00 0.00 0.00
#&gt; TCGA.W4.A7U2.01     2   0.000      0.974 0.00 1.00 0.00
#&gt; TCGA.2G.AAHP.01     3   0.207      1.000 0.00 0.06 0.94
#&gt; TCGA.2X.A9D5.01     1   0.000      0.969 1.00 0.00 0.00
</code></pre>

<script>
$('#tab-node-012-get-classes-2-a').parent().next().next().hide();
$('#tab-node-012-get-classes-2-a').click(function(){
  $('#tab-node-012-get-classes-2-a').parent().next().next().toggle();
  return(false);
});
</script>
</div>

<div id='tab-node-012-get-classes-3'>
<p><a id='tab-node-012-get-classes-3-a' style='color:#0366d6' href='#'>show/hide code output</a></p>
<pre><code class="r">cbind(get_classes(res, k = 4), get_membership(res, k = 4))
</code></pre>

<pre><code>#&gt;                 class entropy silhouette   p1   p2   p3  p4
#&gt; TCGA.XE.AANJ.01     2   0.000      0.969 0.00 1.00 0.00 0.0
#&gt; TCGA.2G.AAF6.01     2   0.121      0.949 0.04 0.96 0.00 0.0
#&gt; TCGA.XY.A9T9.01     4   0.000      1.000 0.00 0.00 0.00 1.0
#&gt; TCGA.ZM.AA06.01     2   0.000      0.969 0.00 1.00 0.00 0.0
#&gt; TCGA.ZM.AA0B.01     1   0.361      0.924 0.80 0.00 0.00 0.2
#&gt; TCGA.SN.A6IS.01     2   0.000      0.969 0.00 1.00 0.00 0.0
#&gt; TCGA.2G.AAF4.01     4   0.000      1.000 0.00 0.00 0.00 1.0
#&gt; TCGA.2G.AAH3.01     2   0.292      0.879 0.14 0.86 0.00 0.0
#&gt; TCGA.XE.AAO3.01     3   0.000      0.962 0.00 0.00 1.00 0.0
#&gt; TCGA.XE.AAO6.01     1   0.317      0.709 0.84 0.16 0.00 0.0
#&gt; TCGA.SB.A6J6.01     4   0.000      1.000 0.00 0.00 0.00 1.0
#&gt; TCGA.2G.AAEX.01     1   0.361      0.924 0.80 0.00 0.00 0.2
#&gt; TCGA.2G.AAH0.01     1   0.361      0.924 0.80 0.00 0.00 0.2
#&gt; TCGA.W4.A7U2.01     2   0.000      0.969 0.00 1.00 0.00 0.0
#&gt; TCGA.2G.AAHP.01     3   0.164      0.962 0.06 0.00 0.94 0.0
#&gt; TCGA.2X.A9D5.01     1   0.361      0.924 0.80 0.00 0.00 0.2
</code></pre>

<script>
$('#tab-node-012-get-classes-3-a').parent().next().next().hide();
$('#tab-node-012-get-classes-3-a').click(function(){
  $('#tab-node-012-get-classes-3-a').parent().next().next().toggle();
  return(false);
});
</script>
</div>

<div id='tab-node-012-get-classes-4'>
<p><a id='tab-node-012-get-classes-4-a' style='color:#0366d6' href='#'>show/hide code output</a></p>
<pre><code class="r">cbind(get_classes(res, k = 5), get_membership(res, k = 5))
</code></pre>

<pre><code>#&gt;                 class entropy silhouette   p1   p2   p3   p4   p5
#&gt; TCGA.XE.AANJ.01     2   0.000      0.880 0.00 1.00 0.00 0.00 0.00
#&gt; TCGA.2G.AAF6.01     2   0.398      0.235 0.00 0.66 0.00 0.00 0.34
#&gt; TCGA.XY.A9T9.01     4   0.104      0.933 0.04 0.00 0.00 0.96 0.00
#&gt; TCGA.ZM.AA06.01     2   0.000      0.880 0.00 1.00 0.00 0.00 0.00
#&gt; TCGA.ZM.AA0B.01     1   0.000      0.899 1.00 0.00 0.00 0.00 0.00
#&gt; TCGA.SN.A6IS.01     2   0.000      0.880 0.00 1.00 0.00 0.00 0.00
#&gt; TCGA.2G.AAF4.01     4   0.104      0.933 0.04 0.00 0.00 0.96 0.00
#&gt; TCGA.2G.AAH3.01     5   0.293      0.000 0.00 0.18 0.00 0.00 0.82
#&gt; TCGA.XE.AAO3.01     3   0.165      0.954 0.00 0.00 0.94 0.04 0.02
#&gt; TCGA.XE.AAO6.01     1   0.454      0.416 0.64 0.02 0.00 0.00 0.34
#&gt; TCGA.SB.A6J6.01     4   0.373      0.860 0.04 0.00 0.00 0.80 0.16
#&gt; TCGA.2G.AAEX.01     1   0.000      0.899 1.00 0.00 0.00 0.00 0.00
#&gt; TCGA.2G.AAH0.01     1   0.000      0.899 1.00 0.00 0.00 0.00 0.00
#&gt; TCGA.W4.A7U2.01     2   0.000      0.880 0.00 1.00 0.00 0.00 0.00
#&gt; TCGA.2G.AAHP.01     3   0.000      0.954 0.00 0.00 1.00 0.00 0.00
#&gt; TCGA.2X.A9D5.01     1   0.000      0.899 1.00 0.00 0.00 0.00 0.00
</code></pre>

<script>
$('#tab-node-012-get-classes-4-a').parent().next().next().hide();
$('#tab-node-012-get-classes-4-a').click(function(){
  $('#tab-node-012-get-classes-4-a').parent().next().next().toggle();
  return(false);
});
</script>
</div>

<div id='tab-node-012-get-classes-5'>
<p><a id='tab-node-012-get-classes-5-a' style='color:#0366d6' href='#'>show/hide code output</a></p>
<pre><code class="r">cbind(get_classes(res, k = 6), get_membership(res, k = 6))
</code></pre>

<pre><code>#&gt;                 class entropy silhouette   p1   p2   p3   p4   p5   p6
#&gt; TCGA.XE.AANJ.01     2  0.0000      1.000 0.00 1.00 0.00 0.00 0.00 0.00
#&gt; TCGA.2G.AAF6.01     6  0.5259      0.591 0.00 0.16 0.00 0.00 0.24 0.60
#&gt; TCGA.XY.A9T9.01     4  0.0000      0.883 0.00 0.00 0.00 1.00 0.00 0.00
#&gt; TCGA.ZM.AA06.01     2  0.0000      1.000 0.00 1.00 0.00 0.00 0.00 0.00
#&gt; TCGA.ZM.AA0B.01     1  0.0000      1.000 1.00 0.00 0.00 0.00 0.00 0.00
#&gt; TCGA.SN.A6IS.01     2  0.0000      1.000 0.00 1.00 0.00 0.00 0.00 0.00
#&gt; TCGA.2G.AAF4.01     4  0.0000      0.883 0.00 0.00 0.00 1.00 0.00 0.00
#&gt; TCGA.2G.AAH3.01     5  0.0547      0.000 0.00 0.02 0.00 0.00 0.98 0.00
#&gt; TCGA.XE.AAO3.01     3  0.2790      0.866 0.00 0.00 0.84 0.00 0.02 0.14
#&gt; TCGA.XE.AAO6.01     6  0.5259      0.599 0.16 0.00 0.00 0.00 0.24 0.60
#&gt; TCGA.SB.A6J6.01     4  0.3198      0.749 0.00 0.00 0.00 0.74 0.00 0.26
#&gt; TCGA.2G.AAEX.01     1  0.0000      1.000 1.00 0.00 0.00 0.00 0.00 0.00
#&gt; TCGA.2G.AAH0.01     1  0.0000      1.000 1.00 0.00 0.00 0.00 0.00 0.00
#&gt; TCGA.W4.A7U2.01     2  0.0000      1.000 0.00 1.00 0.00 0.00 0.00 0.00
#&gt; TCGA.2G.AAHP.01     3  0.0000      0.866 0.00 0.00 1.00 0.00 0.00 0.00
#&gt; TCGA.2X.A9D5.01     1  0.0000      1.000 1.00 0.00 0.00 0.00 0.00 0.00
</code></pre>

<script>
$('#tab-node-012-get-classes-5-a').parent().next().next().hide();
$('#tab-node-012-get-classes-5-a').click(function(){
  $('#tab-node-012-get-classes-5-a').parent().next().next().toggle();
  return(false);
});
</script>
</div>

<div id='tab-node-012-get-classes-6'>
<p><a id='tab-node-012-get-classes-6-a' style='color:#0366d6' href='#'>show/hide code output</a></p>
<pre><code class="r">cbind(get_classes(res, k = 7), get_membership(res, k = 7))
</code></pre>

<pre><code>#&gt;                 class entropy silhouette   p1   p2   p3   p4   p5   p6   p7
#&gt; TCGA.XE.AANJ.01     7  0.0000      0.931 0.00 0.00 0.00 0.00 0.00 0.00 1.00
#&gt; TCGA.2G.AAF6.01     6  0.2512      0.859 0.00 0.10 0.00 0.00 0.00 0.86 0.04
#&gt; TCGA.XY.A9T9.01     4  0.0504      0.827 0.00 0.02 0.00 0.98 0.00 0.00 0.00
#&gt; TCGA.ZM.AA06.01     7  0.1886      0.931 0.00 0.12 0.00 0.00 0.00 0.00 0.88
#&gt; TCGA.ZM.AA0B.01     1  0.3221      0.780 0.68 0.32 0.00 0.00 0.00 0.00 0.00
#&gt; TCGA.SN.A6IS.01     7  0.1671      0.931 0.00 0.10 0.00 0.00 0.00 0.00 0.90
#&gt; TCGA.2G.AAF4.01     4  0.0000      0.831 0.00 0.00 0.00 1.00 0.00 0.00 0.00
#&gt; TCGA.2G.AAH3.01     5  0.0504      0.000 0.00 0.00 0.00 0.00 0.98 0.02 0.00
#&gt; TCGA.XE.AAO3.01     3  0.0000      0.880 0.00 0.00 1.00 0.00 0.00 0.00 0.00
#&gt; TCGA.XE.AAO6.01     6  0.0863      0.859 0.04 0.00 0.00 0.00 0.00 0.96 0.00
#&gt; TCGA.SB.A6J6.01     4  0.3294      0.647 0.00 0.34 0.00 0.66 0.00 0.00 0.00
#&gt; TCGA.2G.AAEX.01     1  0.3221      0.780 0.68 0.32 0.00 0.00 0.00 0.00 0.00
#&gt; TCGA.2G.AAH0.01     1  0.0504      0.768 0.98 0.02 0.00 0.00 0.00 0.00 0.00
#&gt; TCGA.W4.A7U2.01     7  0.0504      0.931 0.00 0.02 0.00 0.00 0.00 0.00 0.98
#&gt; TCGA.2G.AAHP.01     3  0.2769      0.880 0.00 0.08 0.86 0.00 0.02 0.04 0.00
#&gt; TCGA.2X.A9D5.01     1  0.0000      0.777 1.00 0.00 0.00 0.00 0.00 0.00 0.00
</code></pre>

<script>
$('#tab-node-012-get-classes-6-a').parent().next().next().hide();
$('#tab-node-012-get-classes-6-a').click(function(){
  $('#tab-node-012-get-classes-6-a').parent().next().next().toggle();
  return(false);
});
</script>
</div>

<div id='tab-node-012-get-classes-7'>
<p><a id='tab-node-012-get-classes-7-a' style='color:#0366d6' href='#'>show/hide code output</a></p>
<pre><code class="r">cbind(get_classes(res, k = 8), get_membership(res, k = 8))
</code></pre>

<pre><code>#&gt;                 class entropy silhouette   p1   p2  p3   p4   p5   p6   p7   p8
#&gt; TCGA.XE.AANJ.01     2  0.3757      0.759 0.00 0.68 0.0 0.00 0.00 0.06 0.26 0.00
#&gt; TCGA.2G.AAF6.01     8  0.0000      0.841 0.00 0.00 0.0 0.00 0.00 0.00 0.00 1.00
#&gt; TCGA.XY.A9T9.01     4  0.2265      0.746 0.00 0.00 0.0 0.88 0.02 0.08 0.02 0.00
#&gt; TCGA.ZM.AA06.01     2  0.0808      0.775 0.00 0.96 0.0 0.00 0.00 0.00 0.04 0.00
#&gt; TCGA.ZM.AA0B.01     1  0.0471      0.642 0.98 0.00 0.0 0.00 0.00 0.00 0.02 0.00
#&gt; TCGA.SN.A6IS.01     2  0.0000      0.775 0.00 1.00 0.0 0.00 0.00 0.00 0.00 0.00
#&gt; TCGA.2G.AAF4.01     4  0.0000      0.757 0.00 0.00 0.0 1.00 0.00 0.00 0.00 0.00
#&gt; TCGA.2G.AAH3.01     5  0.0471      0.000 0.00 0.00 0.0 0.00 0.98 0.00 0.00 0.02
#&gt; TCGA.XE.AAO3.01     3  0.0000      0.826 0.00 0.00 1.0 0.00 0.00 0.00 0.00 0.00
#&gt; TCGA.XE.AAO6.01     8  0.2569      0.841 0.00 0.00 0.0 0.00 0.00 0.16 0.02 0.82
#&gt; TCGA.SB.A6J6.01     4  0.4255      0.568 0.00 0.00 0.0 0.58 0.00 0.08 0.34 0.00
#&gt; TCGA.2G.AAEX.01     1  0.0000      0.646 1.00 0.00 0.0 0.00 0.00 0.00 0.00 0.00
#&gt; TCGA.2G.AAH0.01     1  0.4693      0.584 0.46 0.00 0.0 0.00 0.00 0.42 0.12 0.00
#&gt; TCGA.W4.A7U2.01     2  0.3142      0.759 0.00 0.64 0.0 0.00 0.00 0.00 0.36 0.00
#&gt; TCGA.2G.AAHP.01     3  0.3054      0.826 0.00 0.00 0.8 0.00 0.00 0.08 0.12 0.00
#&gt; TCGA.2X.A9D5.01     1  0.3333      0.602 0.50 0.00 0.0 0.00 0.00 0.50 0.00 0.00
</code></pre>

<script>
$('#tab-node-012-get-classes-7-a').parent().next().next().hide();
$('#tab-node-012-get-classes-7-a').click(function(){
  $('#tab-node-012-get-classes-7-a').parent().next().next().toggle();
  return(false);
});
</script>
</div>
</div>

Heatmaps for the consensus matrix. It visualizes the probability of two
samples to be in a same group.




<script>
$( function() {
	$( '#tabs-node-012-consensus-heatmap' ).tabs();
} );
</script>
<div id='tabs-node-012-consensus-heatmap'>
<ul>
<li><a href='#tab-node-012-consensus-heatmap-1'>k = 2</a></li>
<li><a href='#tab-node-012-consensus-heatmap-2'>k = 3</a></li>
<li><a href='#tab-node-012-consensus-heatmap-3'>k = 4</a></li>
<li><a href='#tab-node-012-consensus-heatmap-4'>k = 5</a></li>
<li><a href='#tab-node-012-consensus-heatmap-5'>k = 6</a></li>
<li><a href='#tab-node-012-consensus-heatmap-6'>k = 7</a></li>
<li><a href='#tab-node-012-consensus-heatmap-7'>k = 8</a></li>
</ul>
<div id='tab-node-012-consensus-heatmap-1'>
<pre><code class="r">consensus_heatmap(res, k = 2)
</code></pre>

<p><img src="figure_cola/tab-node-012-consensus-heatmap-1-1.png" alt="plot of chunk tab-node-012-consensus-heatmap-1"/></p>

</div>
<div id='tab-node-012-consensus-heatmap-2'>
<pre><code class="r">consensus_heatmap(res, k = 3)
</code></pre>

<p><img src="figure_cola/tab-node-012-consensus-heatmap-2-1.png" alt="plot of chunk tab-node-012-consensus-heatmap-2"/></p>

</div>
<div id='tab-node-012-consensus-heatmap-3'>
<pre><code class="r">consensus_heatmap(res, k = 4)
</code></pre>

<p><img src="figure_cola/tab-node-012-consensus-heatmap-3-1.png" alt="plot of chunk tab-node-012-consensus-heatmap-3"/></p>

</div>
<div id='tab-node-012-consensus-heatmap-4'>
<pre><code class="r">consensus_heatmap(res, k = 5)
</code></pre>

<p><img src="figure_cola/tab-node-012-consensus-heatmap-4-1.png" alt="plot of chunk tab-node-012-consensus-heatmap-4"/></p>

</div>
<div id='tab-node-012-consensus-heatmap-5'>
<pre><code class="r">consensus_heatmap(res, k = 6)
</code></pre>

<p><img src="figure_cola/tab-node-012-consensus-heatmap-5-1.png" alt="plot of chunk tab-node-012-consensus-heatmap-5"/></p>

</div>
<div id='tab-node-012-consensus-heatmap-6'>
<pre><code class="r">consensus_heatmap(res, k = 7)
</code></pre>

<p><img src="figure_cola/tab-node-012-consensus-heatmap-6-1.png" alt="plot of chunk tab-node-012-consensus-heatmap-6"/></p>

</div>
<div id='tab-node-012-consensus-heatmap-7'>
<pre><code class="r">consensus_heatmap(res, k = 8)
</code></pre>

<p><img src="figure_cola/tab-node-012-consensus-heatmap-7-1.png" alt="plot of chunk tab-node-012-consensus-heatmap-7"/></p>

</div>
</div>

Heatmaps for the membership of samples in all partitions to see how consistent they are:





<script>
$( function() {
	$( '#tabs-node-012-membership-heatmap' ).tabs();
} );
</script>
<div id='tabs-node-012-membership-heatmap'>
<ul>
<li><a href='#tab-node-012-membership-heatmap-1'>k = 2</a></li>
<li><a href='#tab-node-012-membership-heatmap-2'>k = 3</a></li>
<li><a href='#tab-node-012-membership-heatmap-3'>k = 4</a></li>
<li><a href='#tab-node-012-membership-heatmap-4'>k = 5</a></li>
<li><a href='#tab-node-012-membership-heatmap-5'>k = 6</a></li>
<li><a href='#tab-node-012-membership-heatmap-6'>k = 7</a></li>
<li><a href='#tab-node-012-membership-heatmap-7'>k = 8</a></li>
</ul>
<div id='tab-node-012-membership-heatmap-1'>
<pre><code class="r">membership_heatmap(res, k = 2)
</code></pre>

<p><img src="figure_cola/tab-node-012-membership-heatmap-1-1.png" alt="plot of chunk tab-node-012-membership-heatmap-1"/></p>

</div>
<div id='tab-node-012-membership-heatmap-2'>
<pre><code class="r">membership_heatmap(res, k = 3)
</code></pre>

<p><img src="figure_cola/tab-node-012-membership-heatmap-2-1.png" alt="plot of chunk tab-node-012-membership-heatmap-2"/></p>

</div>
<div id='tab-node-012-membership-heatmap-3'>
<pre><code class="r">membership_heatmap(res, k = 4)
</code></pre>

<p><img src="figure_cola/tab-node-012-membership-heatmap-3-1.png" alt="plot of chunk tab-node-012-membership-heatmap-3"/></p>

</div>
<div id='tab-node-012-membership-heatmap-4'>
<pre><code class="r">membership_heatmap(res, k = 5)
</code></pre>

<p><img src="figure_cola/tab-node-012-membership-heatmap-4-1.png" alt="plot of chunk tab-node-012-membership-heatmap-4"/></p>

</div>
<div id='tab-node-012-membership-heatmap-5'>
<pre><code class="r">membership_heatmap(res, k = 6)
</code></pre>

<p><img src="figure_cola/tab-node-012-membership-heatmap-5-1.png" alt="plot of chunk tab-node-012-membership-heatmap-5"/></p>

</div>
<div id='tab-node-012-membership-heatmap-6'>
<pre><code class="r">membership_heatmap(res, k = 7)
</code></pre>

<p><img src="figure_cola/tab-node-012-membership-heatmap-6-1.png" alt="plot of chunk tab-node-012-membership-heatmap-6"/></p>

</div>
<div id='tab-node-012-membership-heatmap-7'>
<pre><code class="r">membership_heatmap(res, k = 8)
</code></pre>

<p><img src="figure_cola/tab-node-012-membership-heatmap-7-1.png" alt="plot of chunk tab-node-012-membership-heatmap-7"/></p>

</div>
</div>

As soon as the classes for columns are determined, the signatures
that are significantly different between subgroups can be looked for. 
Following are the heatmaps for signatures.






<script>
$( function() {
	$( '#tabs-node-012-get-signatures' ).tabs();
} );
</script>
<div id='tabs-node-012-get-signatures'>
<ul>
<li><a href='#tab-node-012-get-signatures-1'>k = 2</a></li>
<li><a href='#tab-node-012-get-signatures-2'>k = 3</a></li>
<li><a href='#tab-node-012-get-signatures-3'>k = 4</a></li>
<li><a href='#tab-node-012-get-signatures-4'>k = 5</a></li>
<li><a href='#tab-node-012-get-signatures-5'>k = 6</a></li>
<li><a href='#tab-node-012-get-signatures-6'>k = 7</a></li>
<li><a href='#tab-node-012-get-signatures-7'>k = 8</a></li>
</ul>
<div id='tab-node-012-get-signatures-1'>
<pre><code class="r">get_signatures(res, k = 2)
</code></pre>

<p><img src="figure_cola/tab-node-012-get-signatures-1-1.png" alt="plot of chunk tab-node-012-get-signatures-1"/></p>

</div>
<div id='tab-node-012-get-signatures-2'>
<pre><code class="r">get_signatures(res, k = 3)
</code></pre>

<p><img src="figure_cola/tab-node-012-get-signatures-2-1.png" alt="plot of chunk tab-node-012-get-signatures-2"/></p>

</div>
<div id='tab-node-012-get-signatures-3'>
<pre><code class="r">get_signatures(res, k = 4)
</code></pre>

<p><img src="figure_cola/tab-node-012-get-signatures-3-1.png" alt="plot of chunk tab-node-012-get-signatures-3"/></p>

</div>
<div id='tab-node-012-get-signatures-4'>
<pre><code class="r">get_signatures(res, k = 5)
</code></pre>

<p><img src="figure_cola/tab-node-012-get-signatures-4-1.png" alt="plot of chunk tab-node-012-get-signatures-4"/></p>

</div>
<div id='tab-node-012-get-signatures-5'>
<pre><code class="r">get_signatures(res, k = 6)
</code></pre>

<p><img src="figure_cola/tab-node-012-get-signatures-5-1.png" alt="plot of chunk tab-node-012-get-signatures-5"/></p>

</div>
<div id='tab-node-012-get-signatures-6'>
<pre><code class="r">get_signatures(res, k = 7)
</code></pre>

<p><img src="figure_cola/tab-node-012-get-signatures-6-1.png" alt="plot of chunk tab-node-012-get-signatures-6"/></p>

</div>
<div id='tab-node-012-get-signatures-7'>
<pre><code class="r">get_signatures(res, k = 8)
</code></pre>

<p><img src="figure_cola/tab-node-012-get-signatures-7-1.png" alt="plot of chunk tab-node-012-get-signatures-7"/></p>

</div>
</div>



Compare the overlap of signatures from different k:

```r
compare_signatures(res)
```

![plot of chunk node-012-signature_compare](figure_cola/node-012-signature_compare-1.png)

`get_signature()` returns a data frame invisibly. To get the list of signatures, the function
call should be assigned to a variable explicitly. In following code, if `plot` argument is set
to `FALSE`, no heatmap is plotted while only the differential analysis is performed.

```r
# code only for demonstration
tb = get_signature(res, k = ..., plot = FALSE)
```

An example of the output of `tb` is:

```
#>   which_row         fdr    mean_1    mean_2 scaled_mean_1 scaled_mean_2 km
#> 1        38 0.042760348  8.373488  9.131774    -0.5533452     0.5164555  1
#> 2        40 0.018707592  7.106213  8.469186    -0.6173731     0.5762149  1
#> 3        55 0.019134737 10.221463 11.207825    -0.6159697     0.5749050  1
#> 4        59 0.006059896  5.921854  7.869574    -0.6899429     0.6439467  1
#> 5        60 0.018055526  8.928898 10.211722    -0.6204761     0.5791110  1
#> 6        98 0.009384629 15.714769 14.887706     0.6635654    -0.6193277  2
...
```

The columns in `tb` are:

1. `which_row`: row indices corresponding to the input matrix.
2. `fdr`: FDR for the differential test. 
3. `mean_x`: The mean value in group x.
4. `scaled_mean_x`: The mean value in group x after rows are scaled.
5. `km`: Row groups if k-means clustering is applied to rows (which is done by automatically selecting number of clusters).

If there are too many signatures, `top_signatures = ...` can be set to only show the 
signatures with the highest FDRs:

```r
# code only for demonstration
# e.g. to show the top 500 most significant rows
tb = get_signature(res, k = ..., top_signatures = 500)
```

If the signatures are defined as these which are uniquely high in current group, `diff_method` argument
can be set to `"uniquely_high_in_one_group"`:

```r
# code only for demonstration
tb = get_signature(res, k = ..., diff_method = "uniquely_high_in_one_group")
```




UMAP plot which shows how samples are separated.


<script>
$( function() {
	$( '#tabs-node-012-dimension-reduction' ).tabs();
} );
</script>
<div id='tabs-node-012-dimension-reduction'>
<ul>
<li><a href='#tab-node-012-dimension-reduction-1'>k = 2</a></li>
<li><a href='#tab-node-012-dimension-reduction-2'>k = 3</a></li>
<li><a href='#tab-node-012-dimension-reduction-3'>k = 4</a></li>
<li><a href='#tab-node-012-dimension-reduction-4'>k = 5</a></li>
<li><a href='#tab-node-012-dimension-reduction-5'>k = 6</a></li>
<li><a href='#tab-node-012-dimension-reduction-6'>k = 7</a></li>
<li><a href='#tab-node-012-dimension-reduction-7'>k = 8</a></li>
</ul>
<div id='tab-node-012-dimension-reduction-1'>
<pre><code class="r">dimension_reduction(res, k = 2, method = &quot;UMAP&quot;)
</code></pre>

<p><img src="figure_cola/tab-node-012-dimension-reduction-1-1.png" alt="plot of chunk tab-node-012-dimension-reduction-1"/></p>

</div>
<div id='tab-node-012-dimension-reduction-2'>
<pre><code class="r">dimension_reduction(res, k = 3, method = &quot;UMAP&quot;)
</code></pre>

<p><img src="figure_cola/tab-node-012-dimension-reduction-2-1.png" alt="plot of chunk tab-node-012-dimension-reduction-2"/></p>

</div>
<div id='tab-node-012-dimension-reduction-3'>
<pre><code class="r">dimension_reduction(res, k = 4, method = &quot;UMAP&quot;)
</code></pre>

<p><img src="figure_cola/tab-node-012-dimension-reduction-3-1.png" alt="plot of chunk tab-node-012-dimension-reduction-3"/></p>

</div>
<div id='tab-node-012-dimension-reduction-4'>
<pre><code class="r">dimension_reduction(res, k = 5, method = &quot;UMAP&quot;)
</code></pre>

<p><img src="figure_cola/tab-node-012-dimension-reduction-4-1.png" alt="plot of chunk tab-node-012-dimension-reduction-4"/></p>

</div>
<div id='tab-node-012-dimension-reduction-5'>
<pre><code class="r">dimension_reduction(res, k = 6, method = &quot;UMAP&quot;)
</code></pre>

<p><img src="figure_cola/tab-node-012-dimension-reduction-5-1.png" alt="plot of chunk tab-node-012-dimension-reduction-5"/></p>

</div>
<div id='tab-node-012-dimension-reduction-6'>
<pre><code class="r">dimension_reduction(res, k = 7, method = &quot;UMAP&quot;)
</code></pre>

<p><img src="figure_cola/tab-node-012-dimension-reduction-6-1.png" alt="plot of chunk tab-node-012-dimension-reduction-6"/></p>

</div>
<div id='tab-node-012-dimension-reduction-7'>
<pre><code class="r">dimension_reduction(res, k = 8, method = &quot;UMAP&quot;)
</code></pre>

<p><img src="figure_cola/tab-node-012-dimension-reduction-7-1.png" alt="plot of chunk tab-node-012-dimension-reduction-7"/></p>

</div>
</div>



Following heatmap shows how subgroups are split when increasing `k`:

```r
collect_classes(res)
```

![plot of chunk node-012-collect-classes](figure_cola/node-012-collect-classes-1.png)



If matrix rows can be associated to genes, consider to use `functional_enrichment(res,
...)` to perform function enrichment for the signature genes. See [this vignette](https://jokergoo.github.io/cola_vignettes/functional_enrichment.html) for more detailed explanations.


 

---------------------------------------------------




### Node02


Parent node: [Node0](#Node0).
Child nodes: 
                Node011-leaf
        ,
                [Node012](#Node012)
        ,
                Node013-leaf
        ,
                Node021-leaf
        ,
                [Node022](#Node022)
        ,
                [Node023](#Node023)
        ,
                [Node024](#Node024)
        ,
                Node031-leaf
        ,
                Node032-leaf
        ,
                Node033-leaf
        ,
                Node034-leaf
        .







The object with results only for a single top-value method and a single partitioning method 
can be extracted as:

```r
res = res_rh["02"]
```

A summary of `res` and all the functions that can be applied to it:

```r
res
```

```
#> A 'ConsensusPartition' object with k = 2, 3, 4, 5, 6, 7, 8.
#>   On a matrix with 30000 rows and 82 columns.
#>   Top rows (1000) are extracted by 'ATC' method.
#>   Subgroups are detected by 'skmeans' method.
#>   Performed in total 350 partitions by row resampling.
#>   Best k for subgroups seems to be 6.
#> 
#> Following methods can be applied to this 'ConsensusPartition' object:
#>  [1] "cola_report"             "collect_classes"         "collect_plots"          
#>  [4] "collect_stats"           "colnames"                "compare_partitions"     
#>  [7] "compare_signatures"      "consensus_heatmap"       "dimension_reduction"    
#> [10] "functional_enrichment"   "get_anno_col"            "get_anno"               
#> [13] "get_classes"             "get_consensus"           "get_matrix"             
#> [16] "get_membership"          "get_param"               "get_signatures"         
#> [19] "get_stats"               "is_best_k"               "is_stable_k"            
#> [22] "membership_heatmap"      "ncol"                    "nrow"                   
#> [25] "plot_ecdf"               "predict_classes"         "rownames"               
#> [28] "select_partition_number" "show"                    "suggest_best_k"         
#> [31] "test_to_known_factors"   "top_rows_heatmap"
```

`collect_plots()` function collects all the plots made from `res` for all `k` (number of subgroups)
into one single page to provide an easy and fast comparison between different `k`.

```r
collect_plots(res)
```

![plot of chunk node-02-collect-plots](figure_cola/node-02-collect-plots-1.png)

The plots are:

- The first row: a plot of the eCDF (empirical cumulative distribution
  function) curves of the consensus matrix for each `k` and the heatmap of
  predicted classes for each `k`.
- The second row: heatmaps of the consensus matrix for each `k`.
- The third row: heatmaps of the membership matrix for each `k`.
- The fouth row: heatmaps of the signatures for each `k`.

All the plots in panels can be made by individual functions and they are
plotted later in this section.

`select_partition_number()` produces several plots showing different
statistics for choosing "optimized" `k`. There are following statistics:

- eCDF curves of the consensus matrix for each `k`;
- 1-PAC. [The PAC score](https://en.wikipedia.org/wiki/Consensus_clustering#Over-interpretation_potential_of_consensus_clustering)
  measures the proportion of the ambiguous subgrouping.
- Mean silhouette score.
- Concordance. The mean probability of fiting the consensus subgroup labels in all
  partitions.
- Area increased. Denote $A_k$ as the area under the eCDF curve for current
  `k`, the area increased is defined as $A_k - A_{k-1}$.
- Rand index. The percent of pairs of samples that are both in a same cluster
  or both are not in a same cluster in the partition of k and k-1.
- Jaccard index. The ratio of pairs of samples are both in a same cluster in
  the partition of k and k-1 and the pairs of samples are both in a same
  cluster in the partition k or k-1.

The detailed explanations of these statistics can be found in [the _cola_
vignette](https://jokergoo.github.io/cola_vignettes/cola.html#toc_13).

Generally speaking, higher 1-PAC score, higher mean silhouette score or higher
concordance corresponds to better partition. Rand index and Jaccard index
measure how similar the current partition is compared to partition with `k-1`.
If they are too similar, we won't accept `k` is better than `k-1`.

```r
select_partition_number(res)
```

![plot of chunk node-02-select-partition-number](figure_cola/node-02-select-partition-number-1.png)

The numeric values for all these statistics can be obtained by `get_stats()`.

```r
get_stats(res)
```

```
#>   k 1-PAC mean_silhouette concordance area_increased  Rand Jaccard
#> 2 2 1.000           1.000       1.000         0.4991 0.501   0.501
#> 3 3 1.000           1.000       1.000         0.2802 0.830   0.671
#> 4 4 0.997           0.965       0.983         0.1136 0.896   0.723
#> 5 5 0.943           0.815       0.678         0.0877 0.923   0.739
#> 6 6 0.920           0.821       0.932         0.0118 0.965   0.855
#> 7 7 0.857           0.776       0.905         0.0430 0.962   0.828
#> 8 8 0.870           0.852       0.914         0.0392 0.908   0.562
```

`suggest_best_k()` suggests the best $k$ based on these statistics. The rules are as follows:

- All $k$ with Jaccard index larger than 0.95 are removed because increasing
  $k$ does not provide enough extra information. If all $k$ are removed, it is
  marked as no subgroup is detected.
- For all $k$ with 1-PAC score larger than 0.9, the maximal $k$ is taken as
  the best $k$, and other $k$ are marked as optional $k$.
- If it does not fit the second rule. The $k$ with the maximal vote of the
  highest 1-PAC score, highest mean silhouette, and highest concordance is
  taken as the best $k$.

```r
suggest_best_k(res)
```

```
#> [1] 6
#> attr(,"optional")
#> [1] 2 3 4 5
```

There is also optional best $k$ = 2 3 4 5 that is worth to check.

Following is the table of the partitions (You need to click the **show/hide
code output** link to see it). The membership matrix (columns with name `p*`)
is inferred by
[`clue::cl_consensus()`](https://www.rdocumentation.org/link/cl_consensus?package=clue)
function with the `SE` method. Basically the value in the membership matrix
represents the probability to belong to a certain group. The finall subgroup
label for an item is determined with the group with highest probability it
belongs to.

In `get_classes()` function, the entropy is calculated from the membership
matrix and the silhouette score is calculated from the consensus matrix.



<script>
$( function() {
	$( '#tabs-node-02-get-classes' ).tabs();
} );
</script>
<div id='tabs-node-02-get-classes'>
<ul>
<li><a href='#tab-node-02-get-classes-1'>k = 2</a></li>
<li><a href='#tab-node-02-get-classes-2'>k = 3</a></li>
<li><a href='#tab-node-02-get-classes-3'>k = 4</a></li>
<li><a href='#tab-node-02-get-classes-4'>k = 5</a></li>
<li><a href='#tab-node-02-get-classes-5'>k = 6</a></li>
<li><a href='#tab-node-02-get-classes-6'>k = 7</a></li>
<li><a href='#tab-node-02-get-classes-7'>k = 8</a></li>
</ul>

<div id='tab-node-02-get-classes-1'>
<p><a id='tab-node-02-get-classes-1-a' style='color:#0366d6' href='#'>show/hide code output</a></p>
<pre><code class="r">cbind(get_classes(res, k = 2), get_membership(res, k = 2))
</code></pre>

<pre><code>#&gt;                 class entropy silhouette p1 p2
#&gt; TCGA.W4.A7U4.01     1       0          1  1  0
#&gt; TCGA.2G.AAGO.01     1       0          1  1  0
#&gt; TCGA.2G.AALX.01     2       0          1  0  1
#&gt; TCGA.2G.AAGK.01     1       0          1  1  0
#&gt; TCGA.2G.AAGG.01     2       0          1  0  1
#&gt; TCGA.2G.AAGP.01     2       0          1  0  1
#&gt; TCGA.2G.AAKM.01     1       0          1  1  0
#&gt; TCGA.2G.AAFY.01     1       0          1  1  0
#&gt; TCGA.XE.AANI.01     2       0          1  0  1
#&gt; TCGA.YU.AA4L.01     2       0          1  0  1
#&gt; TCGA.2G.AAH2.01     2       0          1  0  1
#&gt; TCGA.2G.AAG6.01     2       0          1  0  1
#&gt; TCGA.2G.AAG0.01     1       0          1  1  0
#&gt; TCGA.2G.AALO.01     2       0          1  0  1
#&gt; TCGA.YU.A94I.01     2       0          1  0  1
#&gt; TCGA.2G.AAM4.01     1       0          1  1  0
#&gt; TCGA.YU.A90Y.01     2       0          1  0  1
#&gt; TCGA.2G.AALZ.01     2       0          1  0  1
#&gt; TCGA.2G.AAGA.01     1       0          1  1  0
#&gt; TCGA.2G.AALY.01     2       0          1  0  1
#&gt; TCGA.2G.AAKG.01     1       0          1  1  0
#&gt; TCGA.2G.AAL5.01     2       0          1  0  1
#&gt; TCGA.YU.A94D.01     2       0          1  0  1
#&gt; TCGA.SN.A84X.01     2       0          1  0  1
#&gt; TCGA.2G.AALT.01     2       0          1  0  1
#&gt; TCGA.2G.AAM2.01     1       0          1  1  0
#&gt; TCGA.2G.AAFI.01     1       0          1  1  0
#&gt; TCGA.2G.AAGT.01     2       0          1  0  1
#&gt; TCGA.2G.AAGJ.01     1       0          1  1  0
#&gt; TCGA.2G.AAGV.01     2       0          1  0  1
#&gt; TCGA.XE.A8H1.01     1       0          1  1  0
#&gt; TCGA.2G.AAFJ.01     2       0          1  0  1
#&gt; TCGA.2G.AAG5.01     2       0          1  0  1
#&gt; TCGA.X3.A8G4.01     2       0          1  0  1
#&gt; TCGA.2G.AAGY.01     2       0          1  0  1
#&gt; TCGA.2G.AAG8.01     1       0          1  1  0
#&gt; TCGA.2G.AAFO.01     1       0          1  1  0
#&gt; TCGA.2G.AAM3.01     2       0          1  0  1
#&gt; TCGA.VF.A8A8.01     1       0          1  1  0
#&gt; TCGA.SN.A84W.01     2       0          1  0  1
#&gt; TCGA.2G.AAFZ.01     2       0          1  0  1
#&gt; TCGA.2G.AAGM.01     2       0          1  0  1
#&gt; TCGA.2G.AAKH.01     1       0          1  1  0
#&gt; TCGA.2G.AAFL.01     1       0          1  1  0
#&gt; TCGA.2G.AAKG.05     1       0          1  1  0
#&gt; TCGA.2G.AALP.01     1       0          1  1  0
#&gt; TCGA.YU.A90P.01     1       0          1  1  0
#&gt; TCGA.2G.AAGS.01     2       0          1  0  1
#&gt; TCGA.W4.A7U3.01     2       0          1  0  1
#&gt; TCGA.2G.AAGF.01     1       0          1  1  0
#&gt; TCGA.2G.AAGE.01     1       0          1  1  0
#&gt; TCGA.2G.AAKL.01     1       0          1  1  0
#&gt; TCGA.2G.AALW.01     2       0          1  0  1
#&gt; TCGA.XE.AAOB.01     2       0          1  0  1
#&gt; TCGA.XE.AAOC.01     2       0          1  0  1
#&gt; TCGA.XE.AANR.01     2       0          1  0  1
#&gt; TCGA.2G.AALS.01     2       0          1  0  1
#&gt; TCGA.2G.AAG3.01     2       0          1  0  1
#&gt; TCGA.2G.AALN.01     2       0          1  0  1
#&gt; TCGA.2G.AAGC.01     1       0          1  1  0
#&gt; TCGA.SN.A84Y.01     1       0          1  1  0
#&gt; TCGA.2G.AAGZ.01     2       0          1  0  1
#&gt; TCGA.2G.AALF.01     2       0          1  0  1
#&gt; TCGA.2G.AAL7.01     1       0          1  1  0
#&gt; TCGA.2G.AALQ.01     2       0          1  0  1
#&gt; TCGA.2G.AAFN.01     1       0          1  1  0
#&gt; TCGA.2G.AAGN.01     1       0          1  1  0
#&gt; TCGA.XY.A8S3.01     1       0          1  1  0
#&gt; TCGA.2G.AAFV.01     2       0          1  0  1
#&gt; TCGA.2G.AAH4.01     2       0          1  0  1
#&gt; TCGA.YU.AA61.01     2       0          1  0  1
#&gt; TCGA.2G.AAG7.01     1       0          1  1  0
#&gt; TCGA.XY.A8S2.01     1       0          1  1  0
#&gt; TCGA.2G.AAKD.01     1       0          1  1  0
#&gt; TCGA.VF.A8AD.01     1       0          1  1  0
#&gt; TCGA.2G.AALR.01     2       0          1  0  1
#&gt; TCGA.2G.AAFM.01     1       0          1  1  0
#&gt; TCGA.2G.AALG.01     2       0          1  0  1
#&gt; TCGA.XE.AAOJ.01     2       0          1  0  1
#&gt; TCGA.2G.AAGI.01     2       0          1  0  1
#&gt; TCGA.2G.AAGW.01     1       0          1  1  0
#&gt; TCGA.2G.AAGX.01     2       0          1  0  1
</code></pre>

<script>
$('#tab-node-02-get-classes-1-a').parent().next().next().hide();
$('#tab-node-02-get-classes-1-a').click(function(){
  $('#tab-node-02-get-classes-1-a').parent().next().next().toggle();
  return(false);
});
</script>
</div>

<div id='tab-node-02-get-classes-2'>
<p><a id='tab-node-02-get-classes-2-a' style='color:#0366d6' href='#'>show/hide code output</a></p>
<pre><code class="r">cbind(get_classes(res, k = 3), get_membership(res, k = 3))
</code></pre>

<pre><code>#&gt;                 class entropy silhouette p1 p2 p3
#&gt; TCGA.W4.A7U4.01     1       0          1  1  0  0
#&gt; TCGA.2G.AAGO.01     1       0          1  1  0  0
#&gt; TCGA.2G.AALX.01     2       0          1  0  1  0
#&gt; TCGA.2G.AAGK.01     1       0          1  1  0  0
#&gt; TCGA.2G.AAGG.01     2       0          1  0  1  0
#&gt; TCGA.2G.AAGP.01     3       0          1  0  0  1
#&gt; TCGA.2G.AAKM.01     1       0          1  1  0  0
#&gt; TCGA.2G.AAFY.01     1       0          1  1  0  0
#&gt; TCGA.XE.AANI.01     2       0          1  0  1  0
#&gt; TCGA.YU.AA4L.01     2       0          1  0  1  0
#&gt; TCGA.2G.AAH2.01     2       0          1  0  1  0
#&gt; TCGA.2G.AAG6.01     2       0          1  0  1  0
#&gt; TCGA.2G.AAG0.01     1       0          1  1  0  0
#&gt; TCGA.2G.AALO.01     2       0          1  0  1  0
#&gt; TCGA.YU.A94I.01     2       0          1  0  1  0
#&gt; TCGA.2G.AAM4.01     1       0          1  1  0  0
#&gt; TCGA.YU.A90Y.01     3       0          1  0  0  1
#&gt; TCGA.2G.AALZ.01     2       0          1  0  1  0
#&gt; TCGA.2G.AAGA.01     1       0          1  1  0  0
#&gt; TCGA.2G.AALY.01     3       0          1  0  0  1
#&gt; TCGA.2G.AAKG.01     3       0          1  0  0  1
#&gt; TCGA.2G.AAL5.01     2       0          1  0  1  0
#&gt; TCGA.YU.A94D.01     2       0          1  0  1  0
#&gt; TCGA.SN.A84X.01     2       0          1  0  1  0
#&gt; TCGA.2G.AALT.01     2       0          1  0  1  0
#&gt; TCGA.2G.AAM2.01     1       0          1  1  0  0
#&gt; TCGA.2G.AAFI.01     1       0          1  1  0  0
#&gt; TCGA.2G.AAGT.01     2       0          1  0  1  0
#&gt; TCGA.2G.AAGJ.01     1       0          1  1  0  0
#&gt; TCGA.2G.AAGV.01     2       0          1  0  1  0
#&gt; TCGA.XE.A8H1.01     1       0          1  1  0  0
#&gt; TCGA.2G.AAFJ.01     2       0          1  0  1  0
#&gt; TCGA.2G.AAG5.01     2       0          1  0  1  0
#&gt; TCGA.X3.A8G4.01     3       0          1  0  0  1
#&gt; TCGA.2G.AAGY.01     2       0          1  0  1  0
#&gt; TCGA.2G.AAG8.01     1       0          1  1  0  0
#&gt; TCGA.2G.AAFO.01     3       0          1  0  0  1
#&gt; TCGA.2G.AAM3.01     2       0          1  0  1  0
#&gt; TCGA.VF.A8A8.01     1       0          1  1  0  0
#&gt; TCGA.SN.A84W.01     2       0          1  0  1  0
#&gt; TCGA.2G.AAFZ.01     2       0          1  0  1  0
#&gt; TCGA.2G.AAGM.01     2       0          1  0  1  0
#&gt; TCGA.2G.AAKH.01     1       0          1  1  0  0
#&gt; TCGA.2G.AAFL.01     3       0          1  0  0  1
#&gt; TCGA.2G.AAKG.05     3       0          1  0  0  1
#&gt; TCGA.2G.AALP.01     1       0          1  1  0  0
#&gt; TCGA.YU.A90P.01     1       0          1  1  0  0
#&gt; TCGA.2G.AAGS.01     3       0          1  0  0  1
#&gt; TCGA.W4.A7U3.01     2       0          1  0  1  0
#&gt; TCGA.2G.AAGF.01     1       0          1  1  0  0
#&gt; TCGA.2G.AAGE.01     1       0          1  1  0  0
#&gt; TCGA.2G.AAKL.01     1       0          1  1  0  0
#&gt; TCGA.2G.AALW.01     2       0          1  0  1  0
#&gt; TCGA.XE.AAOB.01     3       0          1  0  0  1
#&gt; TCGA.XE.AAOC.01     2       0          1  0  1  0
#&gt; TCGA.XE.AANR.01     3       0          1  0  0  1
#&gt; TCGA.2G.AALS.01     3       0          1  0  0  1
#&gt; TCGA.2G.AAG3.01     2       0          1  0  1  0
#&gt; TCGA.2G.AALN.01     3       0          1  0  0  1
#&gt; TCGA.2G.AAGC.01     3       0          1  0  0  1
#&gt; TCGA.SN.A84Y.01     1       0          1  1  0  0
#&gt; TCGA.2G.AAGZ.01     3       0          1  0  0  1
#&gt; TCGA.2G.AALF.01     2       0          1  0  1  0
#&gt; TCGA.2G.AAL7.01     1       0          1  1  0  0
#&gt; TCGA.2G.AALQ.01     2       0          1  0  1  0
#&gt; TCGA.2G.AAFN.01     1       0          1  1  0  0
#&gt; TCGA.2G.AAGN.01     1       0          1  1  0  0
#&gt; TCGA.XY.A8S3.01     1       0          1  1  0  0
#&gt; TCGA.2G.AAFV.01     2       0          1  0  1  0
#&gt; TCGA.2G.AAH4.01     2       0          1  0  1  0
#&gt; TCGA.YU.AA61.01     2       0          1  0  1  0
#&gt; TCGA.2G.AAG7.01     1       0          1  1  0  0
#&gt; TCGA.XY.A8S2.01     1       0          1  1  0  0
#&gt; TCGA.2G.AAKD.01     1       0          1  1  0  0
#&gt; TCGA.VF.A8AD.01     1       0          1  1  0  0
#&gt; TCGA.2G.AALR.01     2       0          1  0  1  0
#&gt; TCGA.2G.AAFM.01     1       0          1  1  0  0
#&gt; TCGA.2G.AALG.01     2       0          1  0  1  0
#&gt; TCGA.XE.AAOJ.01     2       0          1  0  1  0
#&gt; TCGA.2G.AAGI.01     2       0          1  0  1  0
#&gt; TCGA.2G.AAGW.01     1       0          1  1  0  0
#&gt; TCGA.2G.AAGX.01     2       0          1  0  1  0
</code></pre>

<script>
$('#tab-node-02-get-classes-2-a').parent().next().next().hide();
$('#tab-node-02-get-classes-2-a').click(function(){
  $('#tab-node-02-get-classes-2-a').parent().next().next().toggle();
  return(false);
});
</script>
</div>

<div id='tab-node-02-get-classes-3'>
<p><a id='tab-node-02-get-classes-3-a' style='color:#0366d6' href='#'>show/hide code output</a></p>
<pre><code class="r">cbind(get_classes(res, k = 4), get_membership(res, k = 4))
</code></pre>

<pre><code>#&gt;                 class entropy silhouette   p1   p2   p3   p4
#&gt; TCGA.W4.A7U4.01     4  0.0000      0.983 0.00 0.00 0.00 1.00
#&gt; TCGA.2G.AAGO.01     4  0.0000      0.983 0.00 0.00 0.00 1.00
#&gt; TCGA.2G.AALX.01     2  0.0000      0.998 0.00 1.00 0.00 0.00
#&gt; TCGA.2G.AAGK.01     1  0.0000      0.965 1.00 0.00 0.00 0.00
#&gt; TCGA.2G.AAGG.01     2  0.0000      0.998 0.00 1.00 0.00 0.00
#&gt; TCGA.2G.AAGP.01     3  0.0000      0.946 0.00 0.00 1.00 0.00
#&gt; TCGA.2G.AAKM.01     4  0.0000      0.983 0.00 0.00 0.00 1.00
#&gt; TCGA.2G.AAFY.01     1  0.0000      0.965 1.00 0.00 0.00 0.00
#&gt; TCGA.XE.AANI.01     2  0.0000      0.998 0.00 1.00 0.00 0.00
#&gt; TCGA.YU.AA4L.01     2  0.0000      0.998 0.00 1.00 0.00 0.00
#&gt; TCGA.2G.AAH2.01     2  0.0707      0.981 0.00 0.98 0.02 0.00
#&gt; TCGA.2G.AAG6.01     2  0.0000      0.998 0.00 1.00 0.00 0.00
#&gt; TCGA.2G.AAG0.01     1  0.1637      0.951 0.94 0.00 0.00 0.06
#&gt; TCGA.2G.AALO.01     2  0.0000      0.998 0.00 1.00 0.00 0.00
#&gt; TCGA.YU.A94I.01     2  0.0000      0.998 0.00 1.00 0.00 0.00
#&gt; TCGA.2G.AAM4.01     1  0.2011      0.943 0.92 0.00 0.00 0.08
#&gt; TCGA.YU.A90Y.01     3  0.0000      0.946 0.00 0.00 1.00 0.00
#&gt; TCGA.2G.AALZ.01     2  0.0000      0.998 0.00 1.00 0.00 0.00
#&gt; TCGA.2G.AAGA.01     4  0.0000      0.983 0.00 0.00 0.00 1.00
#&gt; TCGA.2G.AALY.01     3  0.0000      0.946 0.00 0.00 1.00 0.00
#&gt; TCGA.2G.AAKG.01     3  0.2647      0.847 0.12 0.00 0.88 0.00
#&gt; TCGA.2G.AAL5.01     2  0.0000      0.998 0.00 1.00 0.00 0.00
#&gt; TCGA.YU.A94D.01     2  0.0000      0.998 0.00 1.00 0.00 0.00
#&gt; TCGA.SN.A84X.01     3  0.4855      0.328 0.00 0.40 0.60 0.00
#&gt; TCGA.2G.AALT.01     2  0.0000      0.998 0.00 1.00 0.00 0.00
#&gt; TCGA.2G.AAM2.01     4  0.1211      0.948 0.04 0.00 0.00 0.96
#&gt; TCGA.2G.AAFI.01     1  0.0000      0.965 1.00 0.00 0.00 0.00
#&gt; TCGA.2G.AAGT.01     2  0.0000      0.998 0.00 1.00 0.00 0.00
#&gt; TCGA.2G.AAGJ.01     1  0.1637      0.951 0.94 0.00 0.00 0.06
#&gt; TCGA.2G.AAGV.01     2  0.0000      0.998 0.00 1.00 0.00 0.00
#&gt; TCGA.XE.A8H1.01     1  0.2011      0.943 0.92 0.00 0.00 0.08
#&gt; TCGA.2G.AAFJ.01     2  0.0000      0.998 0.00 1.00 0.00 0.00
#&gt; TCGA.2G.AAG5.01     2  0.0000      0.998 0.00 1.00 0.00 0.00
#&gt; TCGA.X3.A8G4.01     3  0.0000      0.946 0.00 0.00 1.00 0.00
#&gt; TCGA.2G.AAGY.01     2  0.0000      0.998 0.00 1.00 0.00 0.00
#&gt; TCGA.2G.AAG8.01     1  0.0000      0.965 1.00 0.00 0.00 0.00
#&gt; TCGA.2G.AAFO.01     1  0.0000      0.965 1.00 0.00 0.00 0.00
#&gt; TCGA.2G.AAM3.01     2  0.0000      0.998 0.00 1.00 0.00 0.00
#&gt; TCGA.VF.A8A8.01     4  0.0000      0.983 0.00 0.00 0.00 1.00
#&gt; TCGA.SN.A84W.01     2  0.0000      0.998 0.00 1.00 0.00 0.00
#&gt; TCGA.2G.AAFZ.01     2  0.0000      0.998 0.00 1.00 0.00 0.00
#&gt; TCGA.2G.AAGM.01     2  0.0000      0.998 0.00 1.00 0.00 0.00
#&gt; TCGA.2G.AAKH.01     1  0.0000      0.965 1.00 0.00 0.00 0.00
#&gt; TCGA.2G.AAFL.01     1  0.0000      0.965 1.00 0.00 0.00 0.00
#&gt; TCGA.2G.AAKG.05     3  0.0707      0.934 0.02 0.00 0.98 0.00
#&gt; TCGA.2G.AALP.01     1  0.0000      0.965 1.00 0.00 0.00 0.00
#&gt; TCGA.YU.A90P.01     1  0.2011      0.943 0.92 0.00 0.00 0.08
#&gt; TCGA.2G.AAGS.01     3  0.0000      0.946 0.00 0.00 1.00 0.00
#&gt; TCGA.W4.A7U3.01     2  0.0000      0.998 0.00 1.00 0.00 0.00
#&gt; TCGA.2G.AAGF.01     1  0.2011      0.943 0.92 0.00 0.00 0.08
#&gt; TCGA.2G.AAGE.01     1  0.2011      0.943 0.92 0.00 0.00 0.08
#&gt; TCGA.2G.AAKL.01     4  0.0000      0.983 0.00 0.00 0.00 1.00
#&gt; TCGA.2G.AALW.01     2  0.0000      0.998 0.00 1.00 0.00 0.00
#&gt; TCGA.XE.AAOB.01     3  0.0000      0.946 0.00 0.00 1.00 0.00
#&gt; TCGA.XE.AAOC.01     2  0.0000      0.998 0.00 1.00 0.00 0.00
#&gt; TCGA.XE.AANR.01     3  0.0000      0.946 0.00 0.00 1.00 0.00
#&gt; TCGA.2G.AALS.01     3  0.0000      0.946 0.00 0.00 1.00 0.00
#&gt; TCGA.2G.AAG3.01     2  0.0000      0.998 0.00 1.00 0.00 0.00
#&gt; TCGA.2G.AALN.01     3  0.0000      0.946 0.00 0.00 1.00 0.00
#&gt; TCGA.2G.AAGC.01     3  0.0707      0.934 0.02 0.00 0.98 0.00
#&gt; TCGA.SN.A84Y.01     4  0.0000      0.983 0.00 0.00 0.00 1.00
#&gt; TCGA.2G.AAGZ.01     3  0.0000      0.946 0.00 0.00 1.00 0.00
#&gt; TCGA.2G.AALF.01     2  0.0000      0.998 0.00 1.00 0.00 0.00
#&gt; TCGA.2G.AAL7.01     4  0.0000      0.983 0.00 0.00 0.00 1.00
#&gt; TCGA.2G.AALQ.01     2  0.0000      0.998 0.00 1.00 0.00 0.00
#&gt; TCGA.2G.AAFN.01     4  0.0000      0.983 0.00 0.00 0.00 1.00
#&gt; TCGA.2G.AAGN.01     1  0.2011      0.943 0.92 0.00 0.00 0.08
#&gt; TCGA.XY.A8S3.01     1  0.0000      0.965 1.00 0.00 0.00 0.00
#&gt; TCGA.2G.AAFV.01     2  0.0000      0.998 0.00 1.00 0.00 0.00
#&gt; TCGA.2G.AAH4.01     2  0.0000      0.998 0.00 1.00 0.00 0.00
#&gt; TCGA.YU.AA61.01     2  0.0707      0.981 0.00 0.98 0.02 0.00
#&gt; TCGA.2G.AAG7.01     4  0.3172      0.803 0.16 0.00 0.00 0.84
#&gt; TCGA.XY.A8S2.01     4  0.0000      0.983 0.00 0.00 0.00 1.00
#&gt; TCGA.2G.AAKD.01     4  0.0000      0.983 0.00 0.00 0.00 1.00
#&gt; TCGA.VF.A8AD.01     1  0.0000      0.965 1.00 0.00 0.00 0.00
#&gt; TCGA.2G.AALR.01     2  0.0000      0.998 0.00 1.00 0.00 0.00
#&gt; TCGA.2G.AAFM.01     1  0.0000      0.965 1.00 0.00 0.00 0.00
#&gt; TCGA.2G.AALG.01     2  0.0000      0.998 0.00 1.00 0.00 0.00
#&gt; TCGA.XE.AAOJ.01     2  0.0000      0.998 0.00 1.00 0.00 0.00
#&gt; TCGA.2G.AAGI.01     2  0.0707      0.981 0.00 0.98 0.02 0.00
#&gt; TCGA.2G.AAGW.01     4  0.0000      0.983 0.00 0.00 0.00 1.00
#&gt; TCGA.2G.AAGX.01     2  0.0000      0.998 0.00 1.00 0.00 0.00
</code></pre>

<script>
$('#tab-node-02-get-classes-3-a').parent().next().next().hide();
$('#tab-node-02-get-classes-3-a').click(function(){
  $('#tab-node-02-get-classes-3-a').parent().next().next().toggle();
  return(false);
});
</script>
</div>

<div id='tab-node-02-get-classes-4'>
<p><a id='tab-node-02-get-classes-4-a' style='color:#0366d6' href='#'>show/hide code output</a></p>
<pre><code class="r">cbind(get_classes(res, k = 5), get_membership(res, k = 5))
</code></pre>

<pre><code>#&gt;                 class entropy silhouette   p1   p2   p3   p4   p5
#&gt; TCGA.W4.A7U4.01     4   0.000     0.9818 0.00 0.00 0.00 1.00 0.00
#&gt; TCGA.2G.AAGO.01     4   0.000     0.9818 0.00 0.00 0.00 1.00 0.00
#&gt; TCGA.2G.AALX.01     2   0.000     0.9401 0.00 1.00 0.00 0.00 0.00
#&gt; TCGA.2G.AAGK.01     1   0.000     0.9261 1.00 0.00 0.00 0.00 0.00
#&gt; TCGA.2G.AAGG.01     5   0.429     0.1418 0.00 0.46 0.00 0.00 0.54
#&gt; TCGA.2G.AAGP.01     5   0.000     0.7699 0.00 0.00 0.00 0.00 1.00
#&gt; TCGA.2G.AAKM.01     4   0.000     0.9818 0.00 0.00 0.00 1.00 0.00
#&gt; TCGA.2G.AAFY.01     1   0.000     0.9261 1.00 0.00 0.00 0.00 0.00
#&gt; TCGA.XE.AANI.01     2   0.000     0.9401 0.00 1.00 0.00 0.00 0.00
#&gt; TCGA.YU.AA4L.01     2   0.000     0.9401 0.00 1.00 0.00 0.00 0.00
#&gt; TCGA.2G.AAH2.01     5   0.000     0.7699 0.00 0.00 0.00 0.00 1.00
#&gt; TCGA.2G.AAG6.01     2   0.000     0.9401 0.00 1.00 0.00 0.00 0.00
#&gt; TCGA.2G.AAG0.01     1   0.000     0.9261 1.00 0.00 0.00 0.00 0.00
#&gt; TCGA.2G.AALO.01     2   0.000     0.9401 0.00 1.00 0.00 0.00 0.00
#&gt; TCGA.YU.A94I.01     2   0.000     0.9401 0.00 1.00 0.00 0.00 0.00
#&gt; TCGA.2G.AAM4.01     1   0.000     0.9261 1.00 0.00 0.00 0.00 0.00
#&gt; TCGA.YU.A90Y.01     3   0.000     0.8166 0.00 0.00 1.00 0.00 0.00
#&gt; TCGA.2G.AALZ.01     2   0.000     0.9401 0.00 1.00 0.00 0.00 0.00
#&gt; TCGA.2G.AAGA.01     4   0.000     0.9818 0.00 0.00 0.00 1.00 0.00
#&gt; TCGA.2G.AALY.01     3   0.000     0.8166 0.00 0.00 1.00 0.00 0.00
#&gt; TCGA.2G.AAKG.01     3   0.000     0.8166 0.00 0.00 1.00 0.00 0.00
#&gt; TCGA.2G.AAL5.01     2   0.000     0.9401 0.00 1.00 0.00 0.00 0.00
#&gt; TCGA.YU.A94D.01     2   0.000     0.9401 0.00 1.00 0.00 0.00 0.00
#&gt; TCGA.SN.A84X.01     5   0.000     0.7699 0.00 0.00 0.00 0.00 1.00
#&gt; TCGA.2G.AALT.01     5   0.141     0.7281 0.00 0.06 0.00 0.00 0.94
#&gt; TCGA.2G.AAM2.01     4   0.293     0.7641 0.18 0.00 0.00 0.82 0.00
#&gt; TCGA.2G.AAFI.01     1   0.000     0.9261 1.00 0.00 0.00 0.00 0.00
#&gt; TCGA.2G.AAGT.01     2   0.000     0.9401 0.00 1.00 0.00 0.00 0.00
#&gt; TCGA.2G.AAGJ.01     1   0.000     0.9261 1.00 0.00 0.00 0.00 0.00
#&gt; TCGA.2G.AAGV.01     2   0.000     0.9401 0.00 1.00 0.00 0.00 0.00
#&gt; TCGA.XE.A8H1.01     1   0.000     0.9261 1.00 0.00 0.00 0.00 0.00
#&gt; TCGA.2G.AAFJ.01     2   0.000     0.9401 0.00 1.00 0.00 0.00 0.00
#&gt; TCGA.2G.AAG5.01     2   0.000     0.9401 0.00 1.00 0.00 0.00 0.00
#&gt; TCGA.X3.A8G4.01     3   0.413     0.5885 0.00 0.00 0.62 0.00 0.38
#&gt; TCGA.2G.AAGY.01     2   0.000     0.9401 0.00 1.00 0.00 0.00 0.00
#&gt; TCGA.2G.AAG8.01     1   0.000     0.9261 1.00 0.00 0.00 0.00 0.00
#&gt; TCGA.2G.AAFO.01     1   0.429     0.2724 0.54 0.00 0.46 0.00 0.00
#&gt; TCGA.2G.AAM3.01     2   0.000     0.9401 0.00 1.00 0.00 0.00 0.00
#&gt; TCGA.VF.A8A8.01     4   0.000     0.9818 0.00 0.00 0.00 1.00 0.00
#&gt; TCGA.SN.A84W.01     2   0.000     0.9401 0.00 1.00 0.00 0.00 0.00
#&gt; TCGA.2G.AAFZ.01     2   0.429     0.0112 0.00 0.54 0.00 0.00 0.46
#&gt; TCGA.2G.AAGM.01     2   0.000     0.9401 0.00 1.00 0.00 0.00 0.00
#&gt; TCGA.2G.AAKH.01     1   0.000     0.9261 1.00 0.00 0.00 0.00 0.00
#&gt; TCGA.2G.AAFL.01     1   0.426     0.3197 0.56 0.00 0.44 0.00 0.00
#&gt; TCGA.2G.AAKG.05     3   0.000     0.8166 0.00 0.00 1.00 0.00 0.00
#&gt; TCGA.2G.AALP.01     1   0.000     0.9261 1.00 0.00 0.00 0.00 0.00
#&gt; TCGA.YU.A90P.01     1   0.000     0.9261 1.00 0.00 0.00 0.00 0.00
#&gt; TCGA.2G.AAGS.01     3   0.000     0.8166 0.00 0.00 1.00 0.00 0.00
#&gt; TCGA.W4.A7U3.01     2   0.429     0.0116 0.00 0.54 0.00 0.00 0.46
#&gt; TCGA.2G.AAGF.01     1   0.000     0.9261 1.00 0.00 0.00 0.00 0.00
#&gt; TCGA.2G.AAGE.01     1   0.000     0.9261 1.00 0.00 0.00 0.00 0.00
#&gt; TCGA.2G.AAKL.01     4   0.000     0.9818 0.00 0.00 0.00 1.00 0.00
#&gt; TCGA.2G.AALW.01     2   0.000     0.9401 0.00 1.00 0.00 0.00 0.00
#&gt; TCGA.XE.AAOB.01     5   0.000     0.7699 0.00 0.00 0.00 0.00 1.00
#&gt; TCGA.XE.AAOC.01     2   0.000     0.9401 0.00 1.00 0.00 0.00 0.00
#&gt; TCGA.XE.AANR.01     3   0.426     0.5274 0.00 0.00 0.56 0.00 0.44
#&gt; TCGA.2G.AALS.01     3   0.429     0.4981 0.00 0.00 0.54 0.00 0.46
#&gt; TCGA.2G.AAG3.01     2   0.431    -0.1374 0.00 0.50 0.00 0.00 0.50
#&gt; TCGA.2G.AALN.01     3   0.426     0.5268 0.00 0.00 0.56 0.00 0.44
#&gt; TCGA.2G.AAGC.01     3   0.000     0.8166 0.00 0.00 1.00 0.00 0.00
#&gt; TCGA.SN.A84Y.01     4   0.000     0.9818 0.00 0.00 0.00 1.00 0.00
#&gt; TCGA.2G.AAGZ.01     3   0.000     0.8166 0.00 0.00 1.00 0.00 0.00
#&gt; TCGA.2G.AALF.01     2   0.000     0.9401 0.00 1.00 0.00 0.00 0.00
#&gt; TCGA.2G.AAL7.01     4   0.000     0.9818 0.00 0.00 0.00 1.00 0.00
#&gt; TCGA.2G.AALQ.01     2   0.000     0.9401 0.00 1.00 0.00 0.00 0.00
#&gt; TCGA.2G.AAFN.01     4   0.000     0.9818 0.00 0.00 0.00 1.00 0.00
#&gt; TCGA.2G.AAGN.01     1   0.000     0.9261 1.00 0.00 0.00 0.00 0.00
#&gt; TCGA.XY.A8S3.01     1   0.000     0.9261 1.00 0.00 0.00 0.00 0.00
#&gt; TCGA.2G.AAFV.01     2   0.000     0.9401 0.00 1.00 0.00 0.00 0.00
#&gt; TCGA.2G.AAH4.01     2   0.000     0.9401 0.00 1.00 0.00 0.00 0.00
#&gt; TCGA.YU.AA61.01     5   0.000     0.7699 0.00 0.00 0.00 0.00 1.00
#&gt; TCGA.2G.AAG7.01     1   0.423     0.2237 0.58 0.00 0.00 0.42 0.00
#&gt; TCGA.XY.A8S2.01     4   0.000     0.9818 0.00 0.00 0.00 1.00 0.00
#&gt; TCGA.2G.AAKD.01     4   0.000     0.9818 0.00 0.00 0.00 1.00 0.00
#&gt; TCGA.VF.A8AD.01     1   0.000     0.9261 1.00 0.00 0.00 0.00 0.00
#&gt; TCGA.2G.AALR.01     2   0.000     0.9401 0.00 1.00 0.00 0.00 0.00
#&gt; TCGA.2G.AAFM.01     1   0.000     0.9261 1.00 0.00 0.00 0.00 0.00
#&gt; TCGA.2G.AALG.01     5   0.430     0.0773 0.00 0.48 0.00 0.00 0.52
#&gt; TCGA.XE.AAOJ.01     2   0.000     0.9401 0.00 1.00 0.00 0.00 0.00
#&gt; TCGA.2G.AAGI.01     5   0.000     0.7699 0.00 0.00 0.00 0.00 1.00
#&gt; TCGA.2G.AAGW.01     4   0.000     0.9818 0.00 0.00 0.00 1.00 0.00
#&gt; TCGA.2G.AAGX.01     2   0.000     0.9401 0.00 1.00 0.00 0.00 0.00
</code></pre>

<script>
$('#tab-node-02-get-classes-4-a').parent().next().next().hide();
$('#tab-node-02-get-classes-4-a').click(function(){
  $('#tab-node-02-get-classes-4-a').parent().next().next().toggle();
  return(false);
});
</script>
</div>

<div id='tab-node-02-get-classes-5'>
<p><a id='tab-node-02-get-classes-5-a' style='color:#0366d6' href='#'>show/hide code output</a></p>
<pre><code class="r">cbind(get_classes(res, k = 6), get_membership(res, k = 6))
</code></pre>

<pre><code>#&gt;                 class entropy silhouette   p1   p2   p3   p4   p5   p6
#&gt; TCGA.W4.A7U4.01     4  0.0000     0.9808 0.00 0.00 0.00 1.00 0.00 0.00
#&gt; TCGA.2G.AAGO.01     4  0.0000     0.9808 0.00 0.00 0.00 1.00 0.00 0.00
#&gt; TCGA.2G.AALX.01     2  0.0000     0.9952 0.00 1.00 0.00 0.00 0.00 0.00
#&gt; TCGA.2G.AAGK.01     1  0.0937     0.8853 0.96 0.00 0.00 0.00 0.00 0.04
#&gt; TCGA.2G.AAGG.01     5  0.3647     0.5585 0.00 0.36 0.00 0.00 0.64 0.00
#&gt; TCGA.2G.AAGP.01     5  0.0547     0.6355 0.00 0.00 0.00 0.00 0.98 0.02
#&gt; TCGA.2G.AAKM.01     4  0.0000     0.9808 0.00 0.00 0.00 1.00 0.00 0.00
#&gt; TCGA.2G.AAFY.01     1  0.0937     0.8853 0.96 0.00 0.00 0.00 0.00 0.04
#&gt; TCGA.XE.AANI.01     2  0.0000     0.9952 0.00 1.00 0.00 0.00 0.00 0.00
#&gt; TCGA.YU.AA4L.01     2  0.0000     0.9952 0.00 1.00 0.00 0.00 0.00 0.00
#&gt; TCGA.2G.AAH2.01     5  0.0000     0.6465 0.00 0.00 0.00 0.00 1.00 0.00
#&gt; TCGA.2G.AAG6.01     2  0.0000     0.9952 0.00 1.00 0.00 0.00 0.00 0.00
#&gt; TCGA.2G.AAG0.01     1  0.0000     0.9066 1.00 0.00 0.00 0.00 0.00 0.00
#&gt; TCGA.2G.AALO.01     2  0.0547     0.9795 0.00 0.98 0.00 0.00 0.02 0.00
#&gt; TCGA.YU.A94I.01     2  0.0000     0.9952 0.00 1.00 0.00 0.00 0.00 0.00
#&gt; TCGA.2G.AAM4.01     1  0.0000     0.9066 1.00 0.00 0.00 0.00 0.00 0.00
#&gt; TCGA.YU.A90Y.01     3  0.0000     0.7428 0.00 0.00 1.00 0.00 0.00 0.00
#&gt; TCGA.2G.AALZ.01     2  0.0547     0.9795 0.00 0.98 0.00 0.00 0.02 0.00
#&gt; TCGA.2G.AAGA.01     4  0.0000     0.9808 0.00 0.00 0.00 1.00 0.00 0.00
#&gt; TCGA.2G.AALY.01     3  0.0000     0.7428 0.00 0.00 1.00 0.00 0.00 0.00
#&gt; TCGA.2G.AAKG.01     3  0.0937     0.7131 0.00 0.00 0.96 0.00 0.00 0.04
#&gt; TCGA.2G.AAL5.01     2  0.0000     0.9952 0.00 1.00 0.00 0.00 0.00 0.00
#&gt; TCGA.YU.A94D.01     2  0.0000     0.9952 0.00 1.00 0.00 0.00 0.00 0.00
#&gt; TCGA.SN.A84X.01     5  0.0547     0.6355 0.00 0.00 0.00 0.00 0.98 0.02
#&gt; TCGA.2G.AALT.01     5  0.0000     0.6465 0.00 0.00 0.00 0.00 1.00 0.00
#&gt; TCGA.2G.AAM2.01     4  0.2454     0.7433 0.16 0.00 0.00 0.84 0.00 0.00
#&gt; TCGA.2G.AAFI.01     1  0.0000     0.9066 1.00 0.00 0.00 0.00 0.00 0.00
#&gt; TCGA.2G.AAGT.01     2  0.0000     0.9952 0.00 1.00 0.00 0.00 0.00 0.00
#&gt; TCGA.2G.AAGJ.01     1  0.0000     0.9066 1.00 0.00 0.00 0.00 0.00 0.00
#&gt; TCGA.2G.AAGV.01     2  0.0547     0.9795 0.00 0.98 0.00 0.00 0.02 0.00
#&gt; TCGA.XE.A8H1.01     1  0.0000     0.9066 1.00 0.00 0.00 0.00 0.00 0.00
#&gt; TCGA.2G.AAFJ.01     2  0.0000     0.9952 0.00 1.00 0.00 0.00 0.00 0.00
#&gt; TCGA.2G.AAG5.01     2  0.0547     0.9795 0.00 0.98 0.00 0.00 0.02 0.00
#&gt; TCGA.X3.A8G4.01     3  0.4078     0.5030 0.00 0.00 0.64 0.00 0.34 0.02
#&gt; TCGA.2G.AAGY.01     2  0.0000     0.9952 0.00 1.00 0.00 0.00 0.00 0.00
#&gt; TCGA.2G.AAG8.01     1  0.0000     0.9066 1.00 0.00 0.00 0.00 0.00 0.00
#&gt; TCGA.2G.AAFO.01     1  0.4651     0.0971 0.48 0.00 0.48 0.00 0.00 0.04
#&gt; TCGA.2G.AAM3.01     2  0.0000     0.9952 0.00 1.00 0.00 0.00 0.00 0.00
#&gt; TCGA.VF.A8A8.01     4  0.0000     0.9808 0.00 0.00 0.00 1.00 0.00 0.00
#&gt; TCGA.SN.A84W.01     2  0.0000     0.9952 0.00 1.00 0.00 0.00 0.00 0.00
#&gt; TCGA.2G.AAFZ.01     5  0.3756     0.5291 0.00 0.40 0.00 0.00 0.60 0.00
#&gt; TCGA.2G.AAGM.01     2  0.0000     0.9952 0.00 1.00 0.00 0.00 0.00 0.00
#&gt; TCGA.2G.AAKH.01     1  0.0000     0.9066 1.00 0.00 0.00 0.00 0.00 0.00
#&gt; TCGA.2G.AAFL.01     1  0.4576     0.3125 0.56 0.00 0.40 0.00 0.00 0.04
#&gt; TCGA.2G.AAKG.05     3  0.3851    -0.0728 0.00 0.00 0.54 0.00 0.00 0.46
#&gt; TCGA.2G.AALP.01     1  0.0000     0.9066 1.00 0.00 0.00 0.00 0.00 0.00
#&gt; TCGA.YU.A90P.01     1  0.0000     0.9066 1.00 0.00 0.00 0.00 0.00 0.00
#&gt; TCGA.2G.AAGS.01     3  0.0000     0.7428 0.00 0.00 1.00 0.00 0.00 0.00
#&gt; TCGA.W4.A7U3.01     5  0.3797     0.4970 0.00 0.42 0.00 0.00 0.58 0.00
#&gt; TCGA.2G.AAGF.01     1  0.0000     0.9066 1.00 0.00 0.00 0.00 0.00 0.00
#&gt; TCGA.2G.AAGE.01     1  0.0000     0.9066 1.00 0.00 0.00 0.00 0.00 0.00
#&gt; TCGA.2G.AAKL.01     4  0.0000     0.9808 0.00 0.00 0.00 1.00 0.00 0.00
#&gt; TCGA.2G.AALW.01     2  0.0000     0.9952 0.00 1.00 0.00 0.00 0.00 0.00
#&gt; TCGA.XE.AAOB.01     5  0.0547     0.6355 0.00 0.00 0.00 0.00 0.98 0.02
#&gt; TCGA.XE.AAOC.01     2  0.0000     0.9952 0.00 1.00 0.00 0.00 0.00 0.00
#&gt; TCGA.XE.AANR.01     6  0.0937     0.0000 0.00 0.00 0.04 0.00 0.00 0.96
#&gt; TCGA.2G.AALS.01     3  0.4144     0.4845 0.00 0.00 0.62 0.00 0.36 0.02
#&gt; TCGA.2G.AAG3.01     5  0.3647     0.5585 0.00 0.36 0.00 0.00 0.64 0.00
#&gt; TCGA.2G.AALN.01     3  0.4144     0.4845 0.00 0.00 0.62 0.00 0.36 0.02
#&gt; TCGA.2G.AAGC.01     3  0.0000     0.7428 0.00 0.00 1.00 0.00 0.00 0.00
#&gt; TCGA.SN.A84Y.01     4  0.0000     0.9808 0.00 0.00 0.00 1.00 0.00 0.00
#&gt; TCGA.2G.AAGZ.01     3  0.0000     0.7428 0.00 0.00 1.00 0.00 0.00 0.00
#&gt; TCGA.2G.AALF.01     2  0.0000     0.9952 0.00 1.00 0.00 0.00 0.00 0.00
#&gt; TCGA.2G.AAL7.01     4  0.0000     0.9808 0.00 0.00 0.00 1.00 0.00 0.00
#&gt; TCGA.2G.AALQ.01     2  0.0000     0.9952 0.00 1.00 0.00 0.00 0.00 0.00
#&gt; TCGA.2G.AAFN.01     4  0.0000     0.9808 0.00 0.00 0.00 1.00 0.00 0.00
#&gt; TCGA.2G.AAGN.01     1  0.0000     0.9066 1.00 0.00 0.00 0.00 0.00 0.00
#&gt; TCGA.XY.A8S3.01     1  0.0000     0.9066 1.00 0.00 0.00 0.00 0.00 0.00
#&gt; TCGA.2G.AAFV.01     2  0.0000     0.9952 0.00 1.00 0.00 0.00 0.00 0.00
#&gt; TCGA.2G.AAH4.01     2  0.0000     0.9952 0.00 1.00 0.00 0.00 0.00 0.00
#&gt; TCGA.YU.AA61.01     5  0.0000     0.6465 0.00 0.00 0.00 0.00 1.00 0.00
#&gt; TCGA.2G.AAG7.01     1  0.3756     0.2828 0.60 0.00 0.00 0.40 0.00 0.00
#&gt; TCGA.XY.A8S2.01     4  0.0000     0.9808 0.00 0.00 0.00 1.00 0.00 0.00
#&gt; TCGA.2G.AAKD.01     4  0.0000     0.9808 0.00 0.00 0.00 1.00 0.00 0.00
#&gt; TCGA.VF.A8AD.01     1  0.0937     0.8853 0.96 0.00 0.00 0.00 0.00 0.04
#&gt; TCGA.2G.AALR.01     2  0.0000     0.9952 0.00 1.00 0.00 0.00 0.00 0.00
#&gt; TCGA.2G.AAFM.01     1  0.0547     0.8968 0.98 0.00 0.00 0.00 0.00 0.02
#&gt; TCGA.2G.AALG.01     5  0.3706     0.5468 0.00 0.38 0.00 0.00 0.62 0.00
#&gt; TCGA.XE.AAOJ.01     2  0.0000     0.9952 0.00 1.00 0.00 0.00 0.00 0.00
#&gt; TCGA.2G.AAGI.01     5  0.0000     0.6465 0.00 0.00 0.00 0.00 1.00 0.00
#&gt; TCGA.2G.AAGW.01     4  0.0000     0.9808 0.00 0.00 0.00 1.00 0.00 0.00
#&gt; TCGA.2G.AAGX.01     2  0.0547     0.9795 0.00 0.98 0.00 0.00 0.02 0.00
</code></pre>

<script>
$('#tab-node-02-get-classes-5-a').parent().next().next().hide();
$('#tab-node-02-get-classes-5-a').click(function(){
  $('#tab-node-02-get-classes-5-a').parent().next().next().toggle();
  return(false);
});
</script>
</div>

<div id='tab-node-02-get-classes-6'>
<p><a id='tab-node-02-get-classes-6-a' style='color:#0366d6' href='#'>show/hide code output</a></p>
<pre><code class="r">cbind(get_classes(res, k = 7), get_membership(res, k = 7))
</code></pre>

<pre><code>#&gt;                 class entropy silhouette   p1   p2   p3   p4   p5   p6   p7
#&gt; TCGA.W4.A7U4.01     4  0.0000    1.00000 0.00 0.00 0.00 1.00 0.00 0.00 0.00
#&gt; TCGA.2G.AAGO.01     4  0.0000    1.00000 0.00 0.00 0.00 1.00 0.00 0.00 0.00
#&gt; TCGA.2G.AALX.01     2  0.0000    0.90067 0.00 1.00 0.00 0.00 0.00 0.00 0.00
#&gt; TCGA.2G.AAGK.01     7  0.3139    0.55656 0.30 0.00 0.00 0.00 0.00 0.00 0.70
#&gt; TCGA.2G.AAGG.01     5  0.1166    0.80095 0.00 0.06 0.00 0.00 0.94 0.00 0.00
#&gt; TCGA.2G.AAGP.01     5  0.3755    0.49980 0.00 0.00 0.34 0.00 0.64 0.00 0.02
#&gt; TCGA.2G.AAKM.01     4  0.0000    1.00000 0.00 0.00 0.00 1.00 0.00 0.00 0.00
#&gt; TCGA.2G.AAFY.01     7  0.3413    0.44397 0.38 0.00 0.00 0.00 0.00 0.00 0.62
#&gt; TCGA.XE.AANI.01     2  0.0000    0.90067 0.00 1.00 0.00 0.00 0.00 0.00 0.00
#&gt; TCGA.YU.AA4L.01     2  0.0000    0.90067 0.00 1.00 0.00 0.00 0.00 0.00 0.00
#&gt; TCGA.2G.AAH2.01     5  0.1664    0.80465 0.00 0.00 0.06 0.00 0.92 0.00 0.02
#&gt; TCGA.2G.AAG6.01     2  0.2259    0.81603 0.00 0.84 0.00 0.00 0.16 0.00 0.00
#&gt; TCGA.2G.AAG0.01     1  0.0000    0.89920 1.00 0.00 0.00 0.00 0.00 0.00 0.00
#&gt; TCGA.2G.AALO.01     2  0.3294    0.60582 0.00 0.66 0.00 0.00 0.34 0.00 0.00
#&gt; TCGA.YU.A94I.01     2  0.0000    0.90067 0.00 1.00 0.00 0.00 0.00 0.00 0.00
#&gt; TCGA.2G.AAM4.01     1  0.0000    0.89920 1.00 0.00 0.00 0.00 0.00 0.00 0.00
#&gt; TCGA.YU.A90Y.01     3  0.2259    0.80524 0.00 0.00 0.84 0.00 0.00 0.00 0.16
#&gt; TCGA.2G.AALZ.01     2  0.2572    0.78238 0.00 0.80 0.00 0.00 0.20 0.00 0.00
#&gt; TCGA.2G.AAGA.01     4  0.0000    1.00000 0.00 0.00 0.00 1.00 0.00 0.00 0.00
#&gt; TCGA.2G.AALY.01     3  0.1433    0.83672 0.00 0.00 0.92 0.00 0.00 0.00 0.08
#&gt; TCGA.2G.AAKG.01     7  0.3496   -0.32474 0.00 0.00 0.42 0.00 0.00 0.00 0.58
#&gt; TCGA.2G.AAL5.01     2  0.0000    0.90067 0.00 1.00 0.00 0.00 0.00 0.00 0.00
#&gt; TCGA.YU.A94D.01     2  0.0000    0.90067 0.00 1.00 0.00 0.00 0.00 0.00 0.00
#&gt; TCGA.SN.A84X.01     5  0.1928    0.79136 0.00 0.00 0.08 0.00 0.90 0.00 0.02
#&gt; TCGA.2G.AALT.01     5  0.0000    0.80329 0.00 0.00 0.00 0.00 1.00 0.00 0.00
#&gt; TCGA.2G.AAM2.01     1  0.2572    0.62043 0.80 0.00 0.00 0.20 0.00 0.00 0.00
#&gt; TCGA.2G.AAFI.01     1  0.0000    0.89920 1.00 0.00 0.00 0.00 0.00 0.00 0.00
#&gt; TCGA.2G.AAGT.01     2  0.0000    0.90067 0.00 1.00 0.00 0.00 0.00 0.00 0.00
#&gt; TCGA.2G.AAGJ.01     1  0.0000    0.89920 1.00 0.00 0.00 0.00 0.00 0.00 0.00
#&gt; TCGA.2G.AAGV.01     2  0.3413    0.53586 0.00 0.62 0.00 0.00 0.38 0.00 0.00
#&gt; TCGA.XE.A8H1.01     1  0.0000    0.89920 1.00 0.00 0.00 0.00 0.00 0.00 0.00
#&gt; TCGA.2G.AAFJ.01     2  0.0000    0.90067 0.00 1.00 0.00 0.00 0.00 0.00 0.00
#&gt; TCGA.2G.AAG5.01     2  0.3413    0.53586 0.00 0.62 0.00 0.00 0.38 0.00 0.00
#&gt; TCGA.X3.A8G4.01     3  0.0000    0.81326 0.00 0.00 1.00 0.00 0.00 0.00 0.00
#&gt; TCGA.2G.AAGY.01     2  0.0000    0.90067 0.00 1.00 0.00 0.00 0.00 0.00 0.00
#&gt; TCGA.2G.AAG8.01     1  0.0000    0.89920 1.00 0.00 0.00 0.00 0.00 0.00 0.00
#&gt; TCGA.2G.AAFO.01     7  0.0504    0.37742 0.02 0.00 0.00 0.00 0.00 0.00 0.98
#&gt; TCGA.2G.AAM3.01     2  0.2081    0.82903 0.00 0.86 0.00 0.00 0.14 0.00 0.00
#&gt; TCGA.VF.A8A8.01     4  0.0000    1.00000 0.00 0.00 0.00 1.00 0.00 0.00 0.00
#&gt; TCGA.SN.A84W.01     2  0.0000    0.90067 0.00 1.00 0.00 0.00 0.00 0.00 0.00
#&gt; TCGA.2G.AAFZ.01     5  0.1886    0.74752 0.00 0.12 0.00 0.00 0.88 0.00 0.00
#&gt; TCGA.2G.AAGM.01     2  0.0000    0.90067 0.00 1.00 0.00 0.00 0.00 0.00 0.00
#&gt; TCGA.2G.AAKH.01     1  0.3525   -0.00679 0.56 0.00 0.00 0.00 0.00 0.00 0.44
#&gt; TCGA.2G.AAFL.01     7  0.0504    0.37742 0.02 0.00 0.00 0.00 0.00 0.00 0.98
#&gt; TCGA.2G.AAKG.05     6  0.5020    0.30515 0.00 0.00 0.12 0.00 0.00 0.44 0.44
#&gt; TCGA.2G.AALP.01     1  0.0000    0.89920 1.00 0.00 0.00 0.00 0.00 0.00 0.00
#&gt; TCGA.YU.A90P.01     1  0.0000    0.89920 1.00 0.00 0.00 0.00 0.00 0.00 0.00
#&gt; TCGA.2G.AAGS.01     3  0.1433    0.83672 0.00 0.00 0.92 0.00 0.00 0.00 0.08
#&gt; TCGA.W4.A7U3.01     5  0.2081    0.71997 0.00 0.14 0.00 0.00 0.86 0.00 0.00
#&gt; TCGA.2G.AAGF.01     1  0.0000    0.89920 1.00 0.00 0.00 0.00 0.00 0.00 0.00
#&gt; TCGA.2G.AAGE.01     1  0.0000    0.89920 1.00 0.00 0.00 0.00 0.00 0.00 0.00
#&gt; TCGA.2G.AAKL.01     4  0.0000    1.00000 0.00 0.00 0.00 1.00 0.00 0.00 0.00
#&gt; TCGA.2G.AALW.01     2  0.2572    0.78238 0.00 0.80 0.00 0.00 0.20 0.00 0.00
#&gt; TCGA.XE.AAOB.01     5  0.3755    0.49980 0.00 0.00 0.34 0.00 0.64 0.00 0.02
#&gt; TCGA.XE.AAOC.01     2  0.0000    0.90067 0.00 1.00 0.00 0.00 0.00 0.00 0.00
#&gt; TCGA.XE.AANR.01     6  0.0000    0.45623 0.00 0.00 0.00 0.00 0.00 1.00 0.00
#&gt; TCGA.2G.AALS.01     3  0.1363    0.75461 0.00 0.00 0.94 0.00 0.04 0.00 0.02
#&gt; TCGA.2G.AAG3.01     5  0.1166    0.80095 0.00 0.06 0.00 0.00 0.94 0.00 0.00
#&gt; TCGA.2G.AALN.01     3  0.0000    0.81326 0.00 0.00 1.00 0.00 0.00 0.00 0.00
#&gt; TCGA.2G.AAGC.01     3  0.3294    0.58785 0.00 0.00 0.66 0.00 0.00 0.00 0.34
#&gt; TCGA.SN.A84Y.01     4  0.0000    1.00000 0.00 0.00 0.00 1.00 0.00 0.00 0.00
#&gt; TCGA.2G.AAGZ.01     3  0.2832    0.73361 0.00 0.00 0.76 0.00 0.00 0.00 0.24
#&gt; TCGA.2G.AALF.01     2  0.0000    0.90067 0.00 1.00 0.00 0.00 0.00 0.00 0.00
#&gt; TCGA.2G.AAL7.01     4  0.0000    1.00000 0.00 0.00 0.00 1.00 0.00 0.00 0.00
#&gt; TCGA.2G.AALQ.01     2  0.0000    0.90067 0.00 1.00 0.00 0.00 0.00 0.00 0.00
#&gt; TCGA.2G.AAFN.01     4  0.0000    1.00000 0.00 0.00 0.00 1.00 0.00 0.00 0.00
#&gt; TCGA.2G.AAGN.01     1  0.0000    0.89920 1.00 0.00 0.00 0.00 0.00 0.00 0.00
#&gt; TCGA.XY.A8S3.01     1  0.0000    0.89920 1.00 0.00 0.00 0.00 0.00 0.00 0.00
#&gt; TCGA.2G.AAFV.01     2  0.0000    0.90067 0.00 1.00 0.00 0.00 0.00 0.00 0.00
#&gt; TCGA.2G.AAH4.01     2  0.1166    0.87290 0.00 0.94 0.00 0.00 0.06 0.00 0.00
#&gt; TCGA.YU.AA61.01     5  0.1664    0.80465 0.00 0.00 0.06 0.00 0.92 0.00 0.02
#&gt; TCGA.2G.AAG7.01     1  0.0504    0.87674 0.98 0.00 0.00 0.02 0.00 0.00 0.00
#&gt; TCGA.XY.A8S2.01     4  0.0000    1.00000 0.00 0.00 0.00 1.00 0.00 0.00 0.00
#&gt; TCGA.2G.AAKD.01     4  0.0000    1.00000 0.00 0.00 0.00 1.00 0.00 0.00 0.00
#&gt; TCGA.VF.A8AD.01     7  0.3139    0.55656 0.30 0.00 0.00 0.00 0.00 0.00 0.70
#&gt; TCGA.2G.AALR.01     2  0.0000    0.90067 0.00 1.00 0.00 0.00 0.00 0.00 0.00
#&gt; TCGA.2G.AAFM.01     1  0.3546   -0.08492 0.54 0.00 0.00 0.00 0.00 0.00 0.46
#&gt; TCGA.2G.AALG.01     5  0.1433    0.78763 0.00 0.08 0.00 0.00 0.92 0.00 0.00
#&gt; TCGA.XE.AAOJ.01     2  0.0000    0.90067 0.00 1.00 0.00 0.00 0.00 0.00 0.00
#&gt; TCGA.2G.AAGI.01     5  0.1664    0.80465 0.00 0.00 0.06 0.00 0.92 0.00 0.02
#&gt; TCGA.2G.AAGW.01     4  0.0000    1.00000 0.00 0.00 0.00 1.00 0.00 0.00 0.00
#&gt; TCGA.2G.AAGX.01     2  0.3358    0.57316 0.00 0.64 0.00 0.00 0.36 0.00 0.00
</code></pre>

<script>
$('#tab-node-02-get-classes-6-a').parent().next().next().hide();
$('#tab-node-02-get-classes-6-a').click(function(){
  $('#tab-node-02-get-classes-6-a').parent().next().next().toggle();
  return(false);
});
</script>
</div>

<div id='tab-node-02-get-classes-7'>
<p><a id='tab-node-02-get-classes-7-a' style='color:#0366d6' href='#'>show/hide code output</a></p>
<pre><code class="r">cbind(get_classes(res, k = 8), get_membership(res, k = 8))
</code></pre>

<pre><code>#&gt;                 class entropy silhouette   p1   p2   p3   p4   p5   p6   p7   p8
#&gt; TCGA.W4.A7U4.01     4  0.0000      1.000 0.00 0.00 0.00 1.00 0.00 0.00 0.00 0.00
#&gt; TCGA.2G.AAGO.01     4  0.0000      1.000 0.00 0.00 0.00 1.00 0.00 0.00 0.00 0.00
#&gt; TCGA.2G.AALX.01     2  0.0808      0.956 0.00 0.96 0.00 0.00 0.00 0.00 0.00 0.04
#&gt; TCGA.2G.AAGK.01     7  0.2547      0.762 0.12 0.00 0.00 0.00 0.04 0.00 0.84 0.00
#&gt; TCGA.2G.AAGG.01     8  0.0000      0.737 0.00 0.00 0.00 0.00 0.00 0.00 0.00 1.00
#&gt; TCGA.2G.AAGP.01     5  0.2350      0.745 0.00 0.00 0.04 0.00 0.86 0.00 0.00 0.10
#&gt; TCGA.2G.AAKM.01     4  0.0000      1.000 0.00 0.00 0.00 1.00 0.00 0.00 0.00 0.00
#&gt; TCGA.2G.AAFY.01     7  0.2114      0.758 0.16 0.00 0.00 0.00 0.00 0.00 0.84 0.00
#&gt; TCGA.XE.AANI.01     2  0.0471      0.976 0.00 0.98 0.00 0.00 0.00 0.00 0.00 0.02
#&gt; TCGA.YU.AA4L.01     2  0.0000      0.991 0.00 1.00 0.00 0.00 0.00 0.00 0.00 0.00
#&gt; TCGA.2G.AAH2.01     5  0.3015      0.772 0.00 0.00 0.00 0.00 0.68 0.00 0.00 0.32
#&gt; TCGA.2G.AAG6.01     8  0.2938      0.709 0.00 0.30 0.00 0.00 0.00 0.00 0.00 0.70
#&gt; TCGA.2G.AAG0.01     1  0.1341      0.920 0.92 0.00 0.00 0.00 0.00 0.00 0.08 0.00
#&gt; TCGA.2G.AALO.01     8  0.2114      0.792 0.00 0.16 0.00 0.00 0.00 0.00 0.00 0.84
#&gt; TCGA.YU.A94I.01     2  0.0000      0.991 0.00 1.00 0.00 0.00 0.00 0.00 0.00 0.00
#&gt; TCGA.2G.AAM4.01     1  0.0808      0.922 0.96 0.00 0.00 0.00 0.04 0.00 0.00 0.00
#&gt; TCGA.YU.A90Y.01     3  0.0000      0.881 0.00 0.00 1.00 0.00 0.00 0.00 0.00 0.00
#&gt; TCGA.2G.AALZ.01     8  0.2756      0.742 0.00 0.26 0.00 0.00 0.00 0.00 0.00 0.74
#&gt; TCGA.2G.AAGA.01     4  0.0000      1.000 0.00 0.00 0.00 1.00 0.00 0.00 0.00 0.00
#&gt; TCGA.2G.AALY.01     3  0.0000      0.881 0.00 0.00 1.00 0.00 0.00 0.00 0.00 0.00
#&gt; TCGA.2G.AAKG.01     3  0.3757      0.517 0.00 0.00 0.68 0.00 0.06 0.00 0.26 0.00
#&gt; TCGA.2G.AAL5.01     2  0.0000      0.991 0.00 1.00 0.00 0.00 0.00 0.00 0.00 0.00
#&gt; TCGA.YU.A94D.01     2  0.0000      0.991 0.00 1.00 0.00 0.00 0.00 0.00 0.00 0.00
#&gt; TCGA.SN.A84X.01     5  0.2406      0.779 0.00 0.00 0.00 0.00 0.80 0.00 0.00 0.20
#&gt; TCGA.2G.AALT.01     8  0.1765      0.590 0.00 0.00 0.00 0.00 0.12 0.00 0.00 0.88
#&gt; TCGA.2G.AAM2.01     1  0.1887      0.855 0.90 0.00 0.00 0.06 0.04 0.00 0.00 0.00
#&gt; TCGA.2G.AAFI.01     1  0.0000      0.939 1.00 0.00 0.00 0.00 0.00 0.00 0.00 0.00
#&gt; TCGA.2G.AAGT.01     2  0.0000      0.991 0.00 1.00 0.00 0.00 0.00 0.00 0.00 0.00
#&gt; TCGA.2G.AAGJ.01     1  0.1563      0.902 0.90 0.00 0.00 0.00 0.00 0.00 0.10 0.00
#&gt; TCGA.2G.AAGV.01     8  0.1765      0.801 0.00 0.12 0.00 0.00 0.00 0.00 0.00 0.88
#&gt; TCGA.XE.A8H1.01     1  0.1091      0.930 0.94 0.00 0.00 0.00 0.00 0.00 0.06 0.00
#&gt; TCGA.2G.AAFJ.01     2  0.0808      0.956 0.00 0.96 0.00 0.00 0.00 0.00 0.00 0.04
#&gt; TCGA.2G.AAG5.01     8  0.1765      0.801 0.00 0.12 0.00 0.00 0.00 0.00 0.00 0.88
#&gt; TCGA.X3.A8G4.01     3  0.0471      0.873 0.00 0.00 0.98 0.00 0.02 0.00 0.00 0.00
#&gt; TCGA.2G.AAGY.01     2  0.0471      0.976 0.00 0.98 0.00 0.00 0.00 0.00 0.00 0.02
#&gt; TCGA.2G.AAG8.01     1  0.1341      0.920 0.92 0.00 0.00 0.00 0.00 0.00 0.08 0.00
#&gt; TCGA.2G.AAFO.01     7  0.1091      0.626 0.00 0.00 0.00 0.00 0.06 0.00 0.94 0.00
#&gt; TCGA.2G.AAM3.01     8  0.2938      0.709 0.00 0.30 0.00 0.00 0.00 0.00 0.00 0.70
#&gt; TCGA.VF.A8A8.01     4  0.0000      1.000 0.00 0.00 0.00 1.00 0.00 0.00 0.00 0.00
#&gt; TCGA.SN.A84W.01     2  0.0000      0.991 0.00 1.00 0.00 0.00 0.00 0.00 0.00 0.00
#&gt; TCGA.2G.AAFZ.01     8  0.0000      0.737 0.00 0.00 0.00 0.00 0.00 0.00 0.00 1.00
#&gt; TCGA.2G.AAGM.01     2  0.0000      0.991 0.00 1.00 0.00 0.00 0.00 0.00 0.00 0.00
#&gt; TCGA.2G.AAKH.01     7  0.3083      0.593 0.34 0.00 0.00 0.00 0.00 0.00 0.66 0.00
#&gt; TCGA.2G.AAFL.01     7  0.1091      0.626 0.00 0.00 0.00 0.00 0.06 0.00 0.94 0.00
#&gt; TCGA.2G.AAKG.05     6  0.5922      0.435 0.00 0.00 0.20 0.00 0.08 0.46 0.26 0.00
#&gt; TCGA.2G.AALP.01     1  0.0808      0.922 0.96 0.00 0.00 0.00 0.04 0.00 0.00 0.00
#&gt; TCGA.YU.A90P.01     1  0.1091      0.930 0.94 0.00 0.00 0.00 0.00 0.00 0.06 0.00
#&gt; TCGA.2G.AAGS.01     3  0.0000      0.881 0.00 0.00 1.00 0.00 0.00 0.00 0.00 0.00
#&gt; TCGA.W4.A7U3.01     8  0.0808      0.767 0.00 0.04 0.00 0.00 0.00 0.00 0.00 0.96
#&gt; TCGA.2G.AAGF.01     1  0.0000      0.939 1.00 0.00 0.00 0.00 0.00 0.00 0.00 0.00
#&gt; TCGA.2G.AAGE.01     1  0.0000      0.939 1.00 0.00 0.00 0.00 0.00 0.00 0.00 0.00
#&gt; TCGA.2G.AAKL.01     4  0.0000      1.000 0.00 0.00 0.00 1.00 0.00 0.00 0.00 0.00
#&gt; TCGA.2G.AALW.01     8  0.2852      0.727 0.00 0.28 0.00 0.00 0.00 0.00 0.00 0.72
#&gt; TCGA.XE.AAOB.01     5  0.2623      0.706 0.00 0.00 0.10 0.00 0.84 0.00 0.00 0.06
#&gt; TCGA.XE.AAOC.01     2  0.0000      0.991 0.00 1.00 0.00 0.00 0.00 0.00 0.00 0.00
#&gt; TCGA.XE.AANR.01     6  0.0000      0.541 0.00 0.00 0.00 0.00 0.00 1.00 0.00 0.00
#&gt; TCGA.2G.AALS.01     5  0.2650      0.538 0.00 0.00 0.24 0.00 0.76 0.00 0.00 0.00
#&gt; TCGA.2G.AAG3.01     8  0.0471      0.719 0.00 0.00 0.00 0.00 0.02 0.00 0.00 0.98
#&gt; TCGA.2G.AALN.01     3  0.1341      0.819 0.00 0.00 0.92 0.00 0.08 0.00 0.00 0.00
#&gt; TCGA.2G.AAGC.01     3  0.2623      0.768 0.00 0.00 0.84 0.00 0.06 0.00 0.10 0.00
#&gt; TCGA.SN.A84Y.01     4  0.0000      1.000 0.00 0.00 0.00 1.00 0.00 0.00 0.00 0.00
#&gt; TCGA.2G.AAGZ.01     3  0.1275      0.859 0.00 0.00 0.94 0.00 0.02 0.00 0.04 0.00
#&gt; TCGA.2G.AALF.01     2  0.0000      0.991 0.00 1.00 0.00 0.00 0.00 0.00 0.00 0.00
#&gt; TCGA.2G.AAL7.01     4  0.0000      1.000 0.00 0.00 0.00 1.00 0.00 0.00 0.00 0.00
#&gt; TCGA.2G.AALQ.01     2  0.0000      0.991 0.00 1.00 0.00 0.00 0.00 0.00 0.00 0.00
#&gt; TCGA.2G.AAFN.01     4  0.0000      1.000 0.00 0.00 0.00 1.00 0.00 0.00 0.00 0.00
#&gt; TCGA.2G.AAGN.01     1  0.1341      0.920 0.92 0.00 0.00 0.00 0.00 0.00 0.08 0.00
#&gt; TCGA.XY.A8S3.01     1  0.0000      0.939 1.00 0.00 0.00 0.00 0.00 0.00 0.00 0.00
#&gt; TCGA.2G.AAFV.01     2  0.0000      0.991 0.00 1.00 0.00 0.00 0.00 0.00 0.00 0.00
#&gt; TCGA.2G.AAH4.01     8  0.3272      0.501 0.00 0.42 0.00 0.00 0.00 0.00 0.00 0.58
#&gt; TCGA.YU.AA61.01     5  0.3015      0.772 0.00 0.00 0.00 0.00 0.68 0.00 0.00 0.32
#&gt; TCGA.2G.AAG7.01     1  0.0808      0.922 0.96 0.00 0.00 0.00 0.04 0.00 0.00 0.00
#&gt; TCGA.XY.A8S2.01     4  0.0000      1.000 0.00 0.00 0.00 1.00 0.00 0.00 0.00 0.00
#&gt; TCGA.2G.AAKD.01     4  0.0000      1.000 0.00 0.00 0.00 1.00 0.00 0.00 0.00 0.00
#&gt; TCGA.VF.A8AD.01     7  0.1563      0.762 0.10 0.00 0.00 0.00 0.00 0.00 0.90 0.00
#&gt; TCGA.2G.AALR.01     2  0.0000      0.991 0.00 1.00 0.00 0.00 0.00 0.00 0.00 0.00
#&gt; TCGA.2G.AAFM.01     7  0.2756      0.686 0.26 0.00 0.00 0.00 0.00 0.00 0.74 0.00
#&gt; TCGA.2G.AALG.01     8  0.0000      0.737 0.00 0.00 0.00 0.00 0.00 0.00 0.00 1.00
#&gt; TCGA.XE.AAOJ.01     2  0.0000      0.991 0.00 1.00 0.00 0.00 0.00 0.00 0.00 0.00
#&gt; TCGA.2G.AAGI.01     5  0.3015      0.772 0.00 0.00 0.00 0.00 0.68 0.00 0.00 0.32
#&gt; TCGA.2G.AAGW.01     4  0.0000      1.000 0.00 0.00 0.00 1.00 0.00 0.00 0.00 0.00
#&gt; TCGA.2G.AAGX.01     8  0.1765      0.801 0.00 0.12 0.00 0.00 0.00 0.00 0.00 0.88
</code></pre>

<script>
$('#tab-node-02-get-classes-7-a').parent().next().next().hide();
$('#tab-node-02-get-classes-7-a').click(function(){
  $('#tab-node-02-get-classes-7-a').parent().next().next().toggle();
  return(false);
});
</script>
</div>
</div>

Heatmaps for the consensus matrix. It visualizes the probability of two
samples to be in a same group.




<script>
$( function() {
	$( '#tabs-node-02-consensus-heatmap' ).tabs();
} );
</script>
<div id='tabs-node-02-consensus-heatmap'>
<ul>
<li><a href='#tab-node-02-consensus-heatmap-1'>k = 2</a></li>
<li><a href='#tab-node-02-consensus-heatmap-2'>k = 3</a></li>
<li><a href='#tab-node-02-consensus-heatmap-3'>k = 4</a></li>
<li><a href='#tab-node-02-consensus-heatmap-4'>k = 5</a></li>
<li><a href='#tab-node-02-consensus-heatmap-5'>k = 6</a></li>
<li><a href='#tab-node-02-consensus-heatmap-6'>k = 7</a></li>
<li><a href='#tab-node-02-consensus-heatmap-7'>k = 8</a></li>
</ul>
<div id='tab-node-02-consensus-heatmap-1'>
<pre><code class="r">consensus_heatmap(res, k = 2)
</code></pre>

<p><img src="figure_cola/tab-node-02-consensus-heatmap-1-1.png" alt="plot of chunk tab-node-02-consensus-heatmap-1"/></p>

</div>
<div id='tab-node-02-consensus-heatmap-2'>
<pre><code class="r">consensus_heatmap(res, k = 3)
</code></pre>

<p><img src="figure_cola/tab-node-02-consensus-heatmap-2-1.png" alt="plot of chunk tab-node-02-consensus-heatmap-2"/></p>

</div>
<div id='tab-node-02-consensus-heatmap-3'>
<pre><code class="r">consensus_heatmap(res, k = 4)
</code></pre>

<p><img src="figure_cola/tab-node-02-consensus-heatmap-3-1.png" alt="plot of chunk tab-node-02-consensus-heatmap-3"/></p>

</div>
<div id='tab-node-02-consensus-heatmap-4'>
<pre><code class="r">consensus_heatmap(res, k = 5)
</code></pre>

<p><img src="figure_cola/tab-node-02-consensus-heatmap-4-1.png" alt="plot of chunk tab-node-02-consensus-heatmap-4"/></p>

</div>
<div id='tab-node-02-consensus-heatmap-5'>
<pre><code class="r">consensus_heatmap(res, k = 6)
</code></pre>

<p><img src="figure_cola/tab-node-02-consensus-heatmap-5-1.png" alt="plot of chunk tab-node-02-consensus-heatmap-5"/></p>

</div>
<div id='tab-node-02-consensus-heatmap-6'>
<pre><code class="r">consensus_heatmap(res, k = 7)
</code></pre>

<p><img src="figure_cola/tab-node-02-consensus-heatmap-6-1.png" alt="plot of chunk tab-node-02-consensus-heatmap-6"/></p>

</div>
<div id='tab-node-02-consensus-heatmap-7'>
<pre><code class="r">consensus_heatmap(res, k = 8)
</code></pre>

<p><img src="figure_cola/tab-node-02-consensus-heatmap-7-1.png" alt="plot of chunk tab-node-02-consensus-heatmap-7"/></p>

</div>
</div>

Heatmaps for the membership of samples in all partitions to see how consistent they are:





<script>
$( function() {
	$( '#tabs-node-02-membership-heatmap' ).tabs();
} );
</script>
<div id='tabs-node-02-membership-heatmap'>
<ul>
<li><a href='#tab-node-02-membership-heatmap-1'>k = 2</a></li>
<li><a href='#tab-node-02-membership-heatmap-2'>k = 3</a></li>
<li><a href='#tab-node-02-membership-heatmap-3'>k = 4</a></li>
<li><a href='#tab-node-02-membership-heatmap-4'>k = 5</a></li>
<li><a href='#tab-node-02-membership-heatmap-5'>k = 6</a></li>
<li><a href='#tab-node-02-membership-heatmap-6'>k = 7</a></li>
<li><a href='#tab-node-02-membership-heatmap-7'>k = 8</a></li>
</ul>
<div id='tab-node-02-membership-heatmap-1'>
<pre><code class="r">membership_heatmap(res, k = 2)
</code></pre>

<p><img src="figure_cola/tab-node-02-membership-heatmap-1-1.png" alt="plot of chunk tab-node-02-membership-heatmap-1"/></p>

</div>
<div id='tab-node-02-membership-heatmap-2'>
<pre><code class="r">membership_heatmap(res, k = 3)
</code></pre>

<p><img src="figure_cola/tab-node-02-membership-heatmap-2-1.png" alt="plot of chunk tab-node-02-membership-heatmap-2"/></p>

</div>
<div id='tab-node-02-membership-heatmap-3'>
<pre><code class="r">membership_heatmap(res, k = 4)
</code></pre>

<p><img src="figure_cola/tab-node-02-membership-heatmap-3-1.png" alt="plot of chunk tab-node-02-membership-heatmap-3"/></p>

</div>
<div id='tab-node-02-membership-heatmap-4'>
<pre><code class="r">membership_heatmap(res, k = 5)
</code></pre>

<p><img src="figure_cola/tab-node-02-membership-heatmap-4-1.png" alt="plot of chunk tab-node-02-membership-heatmap-4"/></p>

</div>
<div id='tab-node-02-membership-heatmap-5'>
<pre><code class="r">membership_heatmap(res, k = 6)
</code></pre>

<p><img src="figure_cola/tab-node-02-membership-heatmap-5-1.png" alt="plot of chunk tab-node-02-membership-heatmap-5"/></p>

</div>
<div id='tab-node-02-membership-heatmap-6'>
<pre><code class="r">membership_heatmap(res, k = 7)
</code></pre>

<p><img src="figure_cola/tab-node-02-membership-heatmap-6-1.png" alt="plot of chunk tab-node-02-membership-heatmap-6"/></p>

</div>
<div id='tab-node-02-membership-heatmap-7'>
<pre><code class="r">membership_heatmap(res, k = 8)
</code></pre>

<p><img src="figure_cola/tab-node-02-membership-heatmap-7-1.png" alt="plot of chunk tab-node-02-membership-heatmap-7"/></p>

</div>
</div>

As soon as the classes for columns are determined, the signatures
that are significantly different between subgroups can be looked for. 
Following are the heatmaps for signatures.






<script>
$( function() {
	$( '#tabs-node-02-get-signatures' ).tabs();
} );
</script>
<div id='tabs-node-02-get-signatures'>
<ul>
<li><a href='#tab-node-02-get-signatures-1'>k = 2</a></li>
<li><a href='#tab-node-02-get-signatures-2'>k = 3</a></li>
<li><a href='#tab-node-02-get-signatures-3'>k = 4</a></li>
<li><a href='#tab-node-02-get-signatures-4'>k = 5</a></li>
<li><a href='#tab-node-02-get-signatures-5'>k = 6</a></li>
<li><a href='#tab-node-02-get-signatures-6'>k = 7</a></li>
<li><a href='#tab-node-02-get-signatures-7'>k = 8</a></li>
</ul>
<div id='tab-node-02-get-signatures-1'>
<pre><code class="r">get_signatures(res, k = 2)
</code></pre>

<p><img src="figure_cola/tab-node-02-get-signatures-1-1.png" alt="plot of chunk tab-node-02-get-signatures-1"/></p>

</div>
<div id='tab-node-02-get-signatures-2'>
<pre><code class="r">get_signatures(res, k = 3)
</code></pre>

<p><img src="figure_cola/tab-node-02-get-signatures-2-1.png" alt="plot of chunk tab-node-02-get-signatures-2"/></p>

</div>
<div id='tab-node-02-get-signatures-3'>
<pre><code class="r">get_signatures(res, k = 4)
</code></pre>

<p><img src="figure_cola/tab-node-02-get-signatures-3-1.png" alt="plot of chunk tab-node-02-get-signatures-3"/></p>

</div>
<div id='tab-node-02-get-signatures-4'>
<pre><code class="r">get_signatures(res, k = 5)
</code></pre>

<p><img src="figure_cola/tab-node-02-get-signatures-4-1.png" alt="plot of chunk tab-node-02-get-signatures-4"/></p>

</div>
<div id='tab-node-02-get-signatures-5'>
<pre><code class="r">get_signatures(res, k = 6)
</code></pre>

<p><img src="figure_cola/tab-node-02-get-signatures-5-1.png" alt="plot of chunk tab-node-02-get-signatures-5"/></p>

</div>
<div id='tab-node-02-get-signatures-6'>
<pre><code class="r">get_signatures(res, k = 7)
</code></pre>

<p><img src="figure_cola/tab-node-02-get-signatures-6-1.png" alt="plot of chunk tab-node-02-get-signatures-6"/></p>

</div>
<div id='tab-node-02-get-signatures-7'>
<pre><code class="r">get_signatures(res, k = 8)
</code></pre>

<p><img src="figure_cola/tab-node-02-get-signatures-7-1.png" alt="plot of chunk tab-node-02-get-signatures-7"/></p>

</div>
</div>



Compare the overlap of signatures from different k:

```r
compare_signatures(res)
```

![plot of chunk node-02-signature_compare](figure_cola/node-02-signature_compare-1.png)

`get_signature()` returns a data frame invisibly. To get the list of signatures, the function
call should be assigned to a variable explicitly. In following code, if `plot` argument is set
to `FALSE`, no heatmap is plotted while only the differential analysis is performed.

```r
# code only for demonstration
tb = get_signature(res, k = ..., plot = FALSE)
```

An example of the output of `tb` is:

```
#>   which_row         fdr    mean_1    mean_2 scaled_mean_1 scaled_mean_2 km
#> 1        38 0.042760348  8.373488  9.131774    -0.5533452     0.5164555  1
#> 2        40 0.018707592  7.106213  8.469186    -0.6173731     0.5762149  1
#> 3        55 0.019134737 10.221463 11.207825    -0.6159697     0.5749050  1
#> 4        59 0.006059896  5.921854  7.869574    -0.6899429     0.6439467  1
#> 5        60 0.018055526  8.928898 10.211722    -0.6204761     0.5791110  1
#> 6        98 0.009384629 15.714769 14.887706     0.6635654    -0.6193277  2
...
```

The columns in `tb` are:

1. `which_row`: row indices corresponding to the input matrix.
2. `fdr`: FDR for the differential test. 
3. `mean_x`: The mean value in group x.
4. `scaled_mean_x`: The mean value in group x after rows are scaled.
5. `km`: Row groups if k-means clustering is applied to rows (which is done by automatically selecting number of clusters).

If there are too many signatures, `top_signatures = ...` can be set to only show the 
signatures with the highest FDRs:

```r
# code only for demonstration
# e.g. to show the top 500 most significant rows
tb = get_signature(res, k = ..., top_signatures = 500)
```

If the signatures are defined as these which are uniquely high in current group, `diff_method` argument
can be set to `"uniquely_high_in_one_group"`:

```r
# code only for demonstration
tb = get_signature(res, k = ..., diff_method = "uniquely_high_in_one_group")
```




UMAP plot which shows how samples are separated.


<script>
$( function() {
	$( '#tabs-node-02-dimension-reduction' ).tabs();
} );
</script>
<div id='tabs-node-02-dimension-reduction'>
<ul>
<li><a href='#tab-node-02-dimension-reduction-1'>k = 2</a></li>
<li><a href='#tab-node-02-dimension-reduction-2'>k = 3</a></li>
<li><a href='#tab-node-02-dimension-reduction-3'>k = 4</a></li>
<li><a href='#tab-node-02-dimension-reduction-4'>k = 5</a></li>
<li><a href='#tab-node-02-dimension-reduction-5'>k = 6</a></li>
<li><a href='#tab-node-02-dimension-reduction-6'>k = 7</a></li>
<li><a href='#tab-node-02-dimension-reduction-7'>k = 8</a></li>
</ul>
<div id='tab-node-02-dimension-reduction-1'>
<pre><code class="r">dimension_reduction(res, k = 2, method = &quot;UMAP&quot;)
</code></pre>

<p><img src="figure_cola/tab-node-02-dimension-reduction-1-1.png" alt="plot of chunk tab-node-02-dimension-reduction-1"/></p>

</div>
<div id='tab-node-02-dimension-reduction-2'>
<pre><code class="r">dimension_reduction(res, k = 3, method = &quot;UMAP&quot;)
</code></pre>

<p><img src="figure_cola/tab-node-02-dimension-reduction-2-1.png" alt="plot of chunk tab-node-02-dimension-reduction-2"/></p>

</div>
<div id='tab-node-02-dimension-reduction-3'>
<pre><code class="r">dimension_reduction(res, k = 4, method = &quot;UMAP&quot;)
</code></pre>

<p><img src="figure_cola/tab-node-02-dimension-reduction-3-1.png" alt="plot of chunk tab-node-02-dimension-reduction-3"/></p>

</div>
<div id='tab-node-02-dimension-reduction-4'>
<pre><code class="r">dimension_reduction(res, k = 5, method = &quot;UMAP&quot;)
</code></pre>

<p><img src="figure_cola/tab-node-02-dimension-reduction-4-1.png" alt="plot of chunk tab-node-02-dimension-reduction-4"/></p>

</div>
<div id='tab-node-02-dimension-reduction-5'>
<pre><code class="r">dimension_reduction(res, k = 6, method = &quot;UMAP&quot;)
</code></pre>

<p><img src="figure_cola/tab-node-02-dimension-reduction-5-1.png" alt="plot of chunk tab-node-02-dimension-reduction-5"/></p>

</div>
<div id='tab-node-02-dimension-reduction-6'>
<pre><code class="r">dimension_reduction(res, k = 7, method = &quot;UMAP&quot;)
</code></pre>

<p><img src="figure_cola/tab-node-02-dimension-reduction-6-1.png" alt="plot of chunk tab-node-02-dimension-reduction-6"/></p>

</div>
<div id='tab-node-02-dimension-reduction-7'>
<pre><code class="r">dimension_reduction(res, k = 8, method = &quot;UMAP&quot;)
</code></pre>

<p><img src="figure_cola/tab-node-02-dimension-reduction-7-1.png" alt="plot of chunk tab-node-02-dimension-reduction-7"/></p>

</div>
</div>



Following heatmap shows how subgroups are split when increasing `k`:

```r
collect_classes(res)
```

![plot of chunk node-02-collect-classes](figure_cola/node-02-collect-classes-1.png)



If matrix rows can be associated to genes, consider to use `functional_enrichment(res,
...)` to perform function enrichment for the signature genes. See [this vignette](https://jokergoo.github.io/cola_vignettes/functional_enrichment.html) for more detailed explanations.


 

---------------------------------------------------




### Node022


Parent node: [Node02](#Node02).
Child nodes: 
                Node0121-leaf
        ,
                Node0122-leaf
        ,
                Node0123-leaf
        ,
                Node0221-leaf
        ,
                Node0222-leaf
        ,
                Node0223-leaf
        ,
                Node0224-leaf
        ,
                Node0231-leaf
        ,
                Node0232-leaf
        ,
                Node0233-leaf
        ,
                Node0234-leaf
        ,
                Node0241-leaf
        ,
                Node0242-leaf
        ,
                Node0243-leaf
        .







The object with results only for a single top-value method and a single partitioning method 
can be extracted as:

```r
res = res_rh["022"]
```

A summary of `res` and all the functions that can be applied to it:

```r
res
```

```
#> A 'ConsensusPartition' object with k = 2, 3, 4, 5, 6, 7, 8.
#>   On a matrix with 30000 rows and 35 columns.
#>   Top rows (1000) are extracted by 'SD' method.
#>   Subgroups are detected by 'kmeans' method.
#>   Performed in total 350 partitions by row resampling.
#>   Best k for subgroups seems to be 2.
#> 
#> Following methods can be applied to this 'ConsensusPartition' object:
#>  [1] "cola_report"             "collect_classes"         "collect_plots"          
#>  [4] "collect_stats"           "colnames"                "compare_partitions"     
#>  [7] "compare_signatures"      "consensus_heatmap"       "dimension_reduction"    
#> [10] "functional_enrichment"   "get_anno_col"            "get_anno"               
#> [13] "get_classes"             "get_consensus"           "get_matrix"             
#> [16] "get_membership"          "get_param"               "get_signatures"         
#> [19] "get_stats"               "is_best_k"               "is_stable_k"            
#> [22] "membership_heatmap"      "ncol"                    "nrow"                   
#> [25] "plot_ecdf"               "predict_classes"         "rownames"               
#> [28] "select_partition_number" "show"                    "suggest_best_k"         
#> [31] "test_to_known_factors"   "top_rows_heatmap"
```

`collect_plots()` function collects all the plots made from `res` for all `k` (number of subgroups)
into one single page to provide an easy and fast comparison between different `k`.

```r
collect_plots(res)
```

![plot of chunk node-022-collect-plots](figure_cola/node-022-collect-plots-1.png)

The plots are:

- The first row: a plot of the eCDF (empirical cumulative distribution
  function) curves of the consensus matrix for each `k` and the heatmap of
  predicted classes for each `k`.
- The second row: heatmaps of the consensus matrix for each `k`.
- The third row: heatmaps of the membership matrix for each `k`.
- The fouth row: heatmaps of the signatures for each `k`.

All the plots in panels can be made by individual functions and they are
plotted later in this section.

`select_partition_number()` produces several plots showing different
statistics for choosing "optimized" `k`. There are following statistics:

- eCDF curves of the consensus matrix for each `k`;
- 1-PAC. [The PAC score](https://en.wikipedia.org/wiki/Consensus_clustering#Over-interpretation_potential_of_consensus_clustering)
  measures the proportion of the ambiguous subgrouping.
- Mean silhouette score.
- Concordance. The mean probability of fiting the consensus subgroup labels in all
  partitions.
- Area increased. Denote $A_k$ as the area under the eCDF curve for current
  `k`, the area increased is defined as $A_k - A_{k-1}$.
- Rand index. The percent of pairs of samples that are both in a same cluster
  or both are not in a same cluster in the partition of k and k-1.
- Jaccard index. The ratio of pairs of samples are both in a same cluster in
  the partition of k and k-1 and the pairs of samples are both in a same
  cluster in the partition k or k-1.

The detailed explanations of these statistics can be found in [the _cola_
vignette](https://jokergoo.github.io/cola_vignettes/cola.html#toc_13).

Generally speaking, higher 1-PAC score, higher mean silhouette score or higher
concordance corresponds to better partition. Rand index and Jaccard index
measure how similar the current partition is compared to partition with `k-1`.
If they are too similar, we won't accept `k` is better than `k-1`.

```r
select_partition_number(res)
```

![plot of chunk node-022-select-partition-number](figure_cola/node-022-select-partition-number-1.png)

The numeric values for all these statistics can be obtained by `get_stats()`.

```r
get_stats(res)
```

```
#>   k 1-PAC mean_silhouette concordance area_increased  Rand Jaccard
#> 2 2 1.000           1.000       1.000         0.3301 0.671   0.671
#> 3 3 0.661           0.940       0.950         0.8547 0.605   0.452
#> 4 4 0.845           0.973       0.963         0.1968 0.889   0.705
#> 5 5 0.831           0.723       0.876         0.0720 0.950   0.810
#> 6 6 0.772           0.532       0.707         0.0418 0.886   0.553
#> 7 7 0.790           0.716       0.799         0.0215 0.924   0.619
#> 8 8 0.825           0.720       0.839         0.0320 0.993   0.952
```

`suggest_best_k()` suggests the best $k$ based on these statistics. The rules are as follows:

- All $k$ with Jaccard index larger than 0.95 are removed because increasing
  $k$ does not provide enough extra information. If all $k$ are removed, it is
  marked as no subgroup is detected.
- For all $k$ with 1-PAC score larger than 0.9, the maximal $k$ is taken as
  the best $k$, and other $k$ are marked as optional $k$.
- If it does not fit the second rule. The $k$ with the maximal vote of the
  highest 1-PAC score, highest mean silhouette, and highest concordance is
  taken as the best $k$.

```r
suggest_best_k(res)
```

```
#> [1] 2
```


Following is the table of the partitions (You need to click the **show/hide
code output** link to see it). The membership matrix (columns with name `p*`)
is inferred by
[`clue::cl_consensus()`](https://www.rdocumentation.org/link/cl_consensus?package=clue)
function with the `SE` method. Basically the value in the membership matrix
represents the probability to belong to a certain group. The finall subgroup
label for an item is determined with the group with highest probability it
belongs to.

In `get_classes()` function, the entropy is calculated from the membership
matrix and the silhouette score is calculated from the consensus matrix.



<script>
$( function() {
	$( '#tabs-node-022-get-classes' ).tabs();
} );
</script>
<div id='tabs-node-022-get-classes'>
<ul>
<li><a href='#tab-node-022-get-classes-1'>k = 2</a></li>
<li><a href='#tab-node-022-get-classes-2'>k = 3</a></li>
<li><a href='#tab-node-022-get-classes-3'>k = 4</a></li>
<li><a href='#tab-node-022-get-classes-4'>k = 5</a></li>
<li><a href='#tab-node-022-get-classes-5'>k = 6</a></li>
<li><a href='#tab-node-022-get-classes-6'>k = 7</a></li>
<li><a href='#tab-node-022-get-classes-7'>k = 8</a></li>
</ul>

<div id='tab-node-022-get-classes-1'>
<p><a id='tab-node-022-get-classes-1-a' style='color:#0366d6' href='#'>show/hide code output</a></p>
<pre><code class="r">cbind(get_classes(res, k = 2), get_membership(res, k = 2))
</code></pre>

<pre><code>#&gt;                 class entropy silhouette p1 p2
#&gt; TCGA.2G.AALX.01     1       0          1  1  0
#&gt; TCGA.2G.AAGG.01     1       0          1  1  0
#&gt; TCGA.XE.AANI.01     1       0          1  1  0
#&gt; TCGA.YU.AA4L.01     2       0          1  0  1
#&gt; TCGA.2G.AAH2.01     1       0          1  1  0
#&gt; TCGA.2G.AAG6.01     1       0          1  1  0
#&gt; TCGA.2G.AALO.01     1       0          1  1  0
#&gt; TCGA.YU.A94I.01     2       0          1  0  1
#&gt; TCGA.2G.AALZ.01     1       0          1  1  0
#&gt; TCGA.2G.AAL5.01     1       0          1  1  0
#&gt; TCGA.YU.A94D.01     2       0          1  0  1
#&gt; TCGA.2G.AALT.01     1       0          1  1  0
#&gt; TCGA.2G.AAGT.01     2       0          1  0  1
#&gt; TCGA.2G.AAGV.01     1       0          1  1  0
#&gt; TCGA.2G.AAFJ.01     1       0          1  1  0
#&gt; TCGA.2G.AAG5.01     1       0          1  1  0
#&gt; TCGA.2G.AAGY.01     1       0          1  1  0
#&gt; TCGA.2G.AAM3.01     1       0          1  1  0
#&gt; TCGA.SN.A84W.01     1       0          1  1  0
#&gt; TCGA.2G.AAFZ.01     1       0          1  1  0
#&gt; TCGA.2G.AAGM.01     1       0          1  1  0
#&gt; TCGA.W4.A7U3.01     1       0          1  1  0
#&gt; TCGA.2G.AALW.01     1       0          1  1  0
#&gt; TCGA.XE.AAOC.01     1       0          1  1  0
#&gt; TCGA.2G.AAG3.01     1       0          1  1  0
#&gt; TCGA.2G.AALF.01     2       0          1  0  1
#&gt; TCGA.2G.AALQ.01     1       0          1  1  0
#&gt; TCGA.2G.AAFV.01     2       0          1  0  1
#&gt; TCGA.2G.AAH4.01     1       0          1  1  0
#&gt; TCGA.YU.AA61.01     1       0          1  1  0
#&gt; TCGA.2G.AALR.01     2       0          1  0  1
#&gt; TCGA.2G.AALG.01     1       0          1  1  0
#&gt; TCGA.XE.AAOJ.01     1       0          1  1  0
#&gt; TCGA.2G.AAGI.01     1       0          1  1  0
#&gt; TCGA.2G.AAGX.01     1       0          1  1  0
</code></pre>

<script>
$('#tab-node-022-get-classes-1-a').parent().next().next().hide();
$('#tab-node-022-get-classes-1-a').click(function(){
  $('#tab-node-022-get-classes-1-a').parent().next().next().toggle();
  return(false);
});
</script>
</div>

<div id='tab-node-022-get-classes-2'>
<p><a id='tab-node-022-get-classes-2-a' style='color:#0366d6' href='#'>show/hide code output</a></p>
<pre><code class="r">cbind(get_classes(res, k = 3), get_membership(res, k = 3))
</code></pre>

<pre><code>#&gt;                 class entropy silhouette   p1   p2   p3
#&gt; TCGA.2G.AALX.01     1  0.3686      0.916 0.86 0.00 0.14
#&gt; TCGA.2G.AAGG.01     3  0.0892      0.985 0.02 0.00 0.98
#&gt; TCGA.XE.AANI.01     1  0.3686      0.916 0.86 0.00 0.14
#&gt; TCGA.YU.AA4L.01     2  0.0000      1.000 0.00 1.00 0.00
#&gt; TCGA.2G.AAH2.01     3  0.0000      0.987 0.00 0.00 1.00
#&gt; TCGA.2G.AAG6.01     1  0.3686      0.916 0.86 0.00 0.14
#&gt; TCGA.2G.AALO.01     3  0.0000      0.987 0.00 0.00 1.00
#&gt; TCGA.YU.A94I.01     2  0.0000      1.000 0.00 1.00 0.00
#&gt; TCGA.2G.AALZ.01     1  0.3686      0.916 0.86 0.00 0.14
#&gt; TCGA.2G.AAL5.01     1  0.0892      0.865 0.98 0.00 0.02
#&gt; TCGA.YU.A94D.01     1  0.4862      0.704 0.82 0.16 0.02
#&gt; TCGA.2G.AALT.01     3  0.0892      0.985 0.02 0.00 0.98
#&gt; TCGA.2G.AAGT.01     2  0.0000      1.000 0.00 1.00 0.00
#&gt; TCGA.2G.AAGV.01     3  0.0892      0.985 0.02 0.00 0.98
#&gt; TCGA.2G.AAFJ.01     1  0.3686      0.916 0.86 0.00 0.14
#&gt; TCGA.2G.AAG5.01     1  0.3686      0.916 0.86 0.00 0.14
#&gt; TCGA.2G.AAGY.01     1  0.3686      0.916 0.86 0.00 0.14
#&gt; TCGA.2G.AAM3.01     3  0.0892      0.985 0.02 0.00 0.98
#&gt; TCGA.SN.A84W.01     1  0.3686      0.916 0.86 0.00 0.14
#&gt; TCGA.2G.AAFZ.01     1  0.3686      0.916 0.86 0.00 0.14
#&gt; TCGA.2G.AAGM.01     1  0.0000      0.874 1.00 0.00 0.00
#&gt; TCGA.W4.A7U3.01     3  0.0000      0.987 0.00 0.00 1.00
#&gt; TCGA.2G.AALW.01     3  0.0000      0.987 0.00 0.00 1.00
#&gt; TCGA.XE.AAOC.01     1  0.0000      0.874 1.00 0.00 0.00
#&gt; TCGA.2G.AAG3.01     3  0.0000      0.987 0.00 0.00 1.00
#&gt; TCGA.2G.AALF.01     2  0.0000      1.000 0.00 1.00 0.00
#&gt; TCGA.2G.AALQ.01     1  0.0000      0.874 1.00 0.00 0.00
#&gt; TCGA.2G.AAFV.01     2  0.0000      1.000 0.00 1.00 0.00
#&gt; TCGA.2G.AAH4.01     1  0.4002      0.898 0.84 0.00 0.16
#&gt; TCGA.YU.AA61.01     3  0.0000      0.987 0.00 0.00 1.00
#&gt; TCGA.2G.AALR.01     1  0.0892      0.865 0.98 0.00 0.02
#&gt; TCGA.2G.AALG.01     3  0.0000      0.987 0.00 0.00 1.00
#&gt; TCGA.XE.AAOJ.01     1  0.0000      0.874 1.00 0.00 0.00
#&gt; TCGA.2G.AAGI.01     3  0.0892      0.985 0.02 0.00 0.98
#&gt; TCGA.2G.AAGX.01     3  0.0892      0.985 0.02 0.00 0.98
</code></pre>

<script>
$('#tab-node-022-get-classes-2-a').parent().next().next().hide();
$('#tab-node-022-get-classes-2-a').click(function(){
  $('#tab-node-022-get-classes-2-a').parent().next().next().toggle();
  return(false);
});
</script>
</div>

<div id='tab-node-022-get-classes-3'>
<p><a id='tab-node-022-get-classes-3-a' style='color:#0366d6' href='#'>show/hide code output</a></p>
<pre><code class="r">cbind(get_classes(res, k = 4), get_membership(res, k = 4))
</code></pre>

<pre><code>#&gt;                 class entropy silhouette   p1   p2  p3   p4
#&gt; TCGA.2G.AALX.01     1  0.0000      0.987 1.00 0.00 0.0 0.00
#&gt; TCGA.2G.AAGG.01     3  0.2345      0.947 0.00 0.00 0.9 0.10
#&gt; TCGA.XE.AANI.01     1  0.0000      0.987 1.00 0.00 0.0 0.00
#&gt; TCGA.YU.AA4L.01     2  0.0000      1.000 0.00 1.00 0.0 0.00
#&gt; TCGA.2G.AAH2.01     3  0.0000      0.955 0.00 0.00 1.0 0.00
#&gt; TCGA.2G.AAG6.01     1  0.0000      0.987 1.00 0.00 0.0 0.00
#&gt; TCGA.2G.AALO.01     3  0.0000      0.955 0.00 0.00 1.0 0.00
#&gt; TCGA.YU.A94I.01     2  0.0000      1.000 0.00 1.00 0.0 0.00
#&gt; TCGA.2G.AALZ.01     1  0.0000      0.987 1.00 0.00 0.0 0.00
#&gt; TCGA.2G.AAL5.01     4  0.2345      0.994 0.10 0.00 0.0 0.90
#&gt; TCGA.YU.A94D.01     4  0.2706      0.971 0.08 0.02 0.0 0.90
#&gt; TCGA.2G.AALT.01     3  0.2345      0.947 0.00 0.00 0.9 0.10
#&gt; TCGA.2G.AAGT.01     2  0.0000      1.000 0.00 1.00 0.0 0.00
#&gt; TCGA.2G.AAGV.01     3  0.2345      0.947 0.00 0.00 0.9 0.10
#&gt; TCGA.2G.AAFJ.01     1  0.0000      0.987 1.00 0.00 0.0 0.00
#&gt; TCGA.2G.AAG5.01     1  0.0707      0.969 0.98 0.00 0.0 0.02
#&gt; TCGA.2G.AAGY.01     1  0.0000      0.987 1.00 0.00 0.0 0.00
#&gt; TCGA.2G.AAM3.01     3  0.2345      0.947 0.00 0.00 0.9 0.10
#&gt; TCGA.SN.A84W.01     1  0.0000      0.987 1.00 0.00 0.0 0.00
#&gt; TCGA.2G.AAFZ.01     1  0.0000      0.987 1.00 0.00 0.0 0.00
#&gt; TCGA.2G.AAGM.01     4  0.2345      0.994 0.10 0.00 0.0 0.90
#&gt; TCGA.W4.A7U3.01     3  0.0000      0.955 0.00 0.00 1.0 0.00
#&gt; TCGA.2G.AALW.01     3  0.0000      0.955 0.00 0.00 1.0 0.00
#&gt; TCGA.XE.AAOC.01     1  0.0000      0.987 1.00 0.00 0.0 0.00
#&gt; TCGA.2G.AAG3.01     3  0.0000      0.955 0.00 0.00 1.0 0.00
#&gt; TCGA.2G.AALF.01     2  0.0000      1.000 0.00 1.00 0.0 0.00
#&gt; TCGA.2G.AALQ.01     4  0.2345      0.994 0.10 0.00 0.0 0.90
#&gt; TCGA.2G.AAFV.01     2  0.0000      1.000 0.00 1.00 0.0 0.00
#&gt; TCGA.2G.AAH4.01     1  0.2011      0.900 0.92 0.00 0.0 0.08
#&gt; TCGA.YU.AA61.01     3  0.0000      0.955 0.00 0.00 1.0 0.00
#&gt; TCGA.2G.AALR.01     4  0.2345      0.994 0.10 0.00 0.0 0.90
#&gt; TCGA.2G.AALG.01     3  0.0000      0.955 0.00 0.00 1.0 0.00
#&gt; TCGA.XE.AAOJ.01     4  0.2345      0.994 0.10 0.00 0.0 0.90
#&gt; TCGA.2G.AAGI.01     3  0.2345      0.947 0.00 0.00 0.9 0.10
#&gt; TCGA.2G.AAGX.01     3  0.2345      0.947 0.00 0.00 0.9 0.10
</code></pre>

<script>
$('#tab-node-022-get-classes-3-a').parent().next().next().hide();
$('#tab-node-022-get-classes-3-a').click(function(){
  $('#tab-node-022-get-classes-3-a').parent().next().next().toggle();
  return(false);
});
</script>
</div>

<div id='tab-node-022-get-classes-4'>
<p><a id='tab-node-022-get-classes-4-a' style='color:#0366d6' href='#'>show/hide code output</a></p>
<pre><code class="r">cbind(get_classes(res, k = 5), get_membership(res, k = 5))
</code></pre>

<pre><code>#&gt;                 class entropy silhouette   p1   p2   p3   p4   p5
#&gt; TCGA.2G.AALX.01     1  0.2077     0.8911 0.92 0.00 0.00 0.04 0.04
#&gt; TCGA.2G.AAGG.01     3  0.0000     0.6771 0.00 0.00 1.00 0.00 0.00
#&gt; TCGA.XE.AANI.01     1  0.1732     0.8998 0.92 0.00 0.00 0.00 0.08
#&gt; TCGA.YU.AA4L.01     2  0.1043     0.9780 0.00 0.96 0.00 0.00 0.04
#&gt; TCGA.2G.AAH2.01     3  0.4287    -0.5908 0.00 0.00 0.54 0.00 0.46
#&gt; TCGA.2G.AAG6.01     1  0.0000     0.9121 1.00 0.00 0.00 0.00 0.00
#&gt; TCGA.2G.AALO.01     3  0.4060    -0.1502 0.00 0.00 0.64 0.00 0.36
#&gt; TCGA.YU.A94I.01     2  0.0000     0.9854 0.00 1.00 0.00 0.00 0.00
#&gt; TCGA.2G.AALZ.01     1  0.1043     0.9100 0.96 0.00 0.00 0.00 0.04
#&gt; TCGA.2G.AAL5.01     4  0.3513     0.8375 0.02 0.00 0.00 0.80 0.18
#&gt; TCGA.YU.A94D.01     4  0.3895     0.7802 0.00 0.00 0.00 0.68 0.32
#&gt; TCGA.2G.AALT.01     3  0.0000     0.6771 0.00 0.00 1.00 0.00 0.00
#&gt; TCGA.2G.AAGT.01     2  0.1043     0.9780 0.00 0.96 0.00 0.00 0.04
#&gt; TCGA.2G.AAGV.01     3  0.0000     0.6771 0.00 0.00 1.00 0.00 0.00
#&gt; TCGA.2G.AAFJ.01     1  0.2077     0.8911 0.92 0.00 0.00 0.04 0.04
#&gt; TCGA.2G.AAG5.01     1  0.1732     0.8998 0.92 0.00 0.00 0.00 0.08
#&gt; TCGA.2G.AAGY.01     1  0.0609     0.9124 0.98 0.00 0.00 0.00 0.02
#&gt; TCGA.2G.AAM3.01     3  0.0000     0.6771 0.00 0.00 1.00 0.00 0.00
#&gt; TCGA.SN.A84W.01     1  0.0000     0.9121 1.00 0.00 0.00 0.00 0.00
#&gt; TCGA.2G.AAFZ.01     1  0.2754     0.8669 0.88 0.00 0.00 0.08 0.04
#&gt; TCGA.2G.AAGM.01     4  0.0000     0.9100 0.00 0.00 0.00 1.00 0.00
#&gt; TCGA.W4.A7U3.01     5  0.4302     0.6521 0.00 0.00 0.48 0.00 0.52
#&gt; TCGA.2G.AALW.01     3  0.3796     0.0916 0.00 0.00 0.70 0.00 0.30
#&gt; TCGA.XE.AAOC.01     1  0.1732     0.8998 0.92 0.00 0.00 0.00 0.08
#&gt; TCGA.2G.AAG3.01     5  0.4060     0.8218 0.00 0.00 0.36 0.00 0.64
#&gt; TCGA.2G.AALF.01     2  0.0000     0.9854 0.00 1.00 0.00 0.00 0.00
#&gt; TCGA.2G.AALQ.01     4  0.0000     0.9100 0.00 0.00 0.00 1.00 0.00
#&gt; TCGA.2G.AAFV.01     2  0.0000     0.9854 0.00 1.00 0.00 0.00 0.00
#&gt; TCGA.2G.AAH4.01     1  0.6073     0.5801 0.62 0.00 0.26 0.08 0.04
#&gt; TCGA.YU.AA61.01     5  0.4126     0.8402 0.00 0.00 0.38 0.00 0.62
#&gt; TCGA.2G.AALR.01     4  0.1732     0.8921 0.00 0.00 0.00 0.92 0.08
#&gt; TCGA.2G.AALG.01     3  0.4060    -0.1502 0.00 0.00 0.64 0.00 0.36
#&gt; TCGA.XE.AAOJ.01     4  0.0000     0.9100 0.00 0.00 0.00 1.00 0.00
#&gt; TCGA.2G.AAGI.01     3  0.0000     0.6771 0.00 0.00 1.00 0.00 0.00
#&gt; TCGA.2G.AAGX.01     3  0.0000     0.6771 0.00 0.00 1.00 0.00 0.00
</code></pre>

<script>
$('#tab-node-022-get-classes-4-a').parent().next().next().hide();
$('#tab-node-022-get-classes-4-a').click(function(){
  $('#tab-node-022-get-classes-4-a').parent().next().next().toggle();
  return(false);
});
</script>
</div>

<div id='tab-node-022-get-classes-5'>
<p><a id='tab-node-022-get-classes-5-a' style='color:#0366d6' href='#'>show/hide code output</a></p>
<pre><code class="r">cbind(get_classes(res, k = 6), get_membership(res, k = 6))
</code></pre>

<pre><code>#&gt;                 class entropy silhouette   p1   p2   p3   p4   p5   p6
#&gt; TCGA.2G.AALX.01     6  0.3864      0.683 0.48 0.00 0.00 0.00 0.00 0.52
#&gt; TCGA.2G.AAGG.01     3  0.3864     -0.951 0.00 0.00 0.52 0.00 0.48 0.00
#&gt; TCGA.XE.AANI.01     1  0.0000      0.874 1.00 0.00 0.00 0.00 0.00 0.00
#&gt; TCGA.YU.AA4L.01     2  0.3073      0.903 0.00 0.84 0.00 0.00 0.08 0.08
#&gt; TCGA.2G.AAH2.01     3  0.1814      0.441 0.00 0.00 0.90 0.00 0.10 0.00
#&gt; TCGA.2G.AAG6.01     1  0.2048      0.833 0.88 0.00 0.00 0.00 0.00 0.12
#&gt; TCGA.2G.AALO.01     3  0.0000      0.403 0.00 0.00 1.00 0.00 0.00 0.00
#&gt; TCGA.YU.A94I.01     2  0.0000      0.948 0.00 1.00 0.00 0.00 0.00 0.00
#&gt; TCGA.2G.AALZ.01     1  0.1267      0.882 0.94 0.00 0.00 0.00 0.00 0.06
#&gt; TCGA.2G.AAL5.01     4  0.4903      0.705 0.14 0.00 0.00 0.70 0.14 0.02
#&gt; TCGA.YU.A94D.01     4  0.5736      0.522 0.00 0.00 0.00 0.48 0.18 0.34
#&gt; TCGA.2G.AALT.01     5  0.3869      1.000 0.00 0.00 0.50 0.00 0.50 0.00
#&gt; TCGA.2G.AAGT.01     2  0.2474      0.920 0.00 0.88 0.00 0.00 0.04 0.08
#&gt; TCGA.2G.AAGV.01     3  0.4337     -0.959 0.00 0.00 0.50 0.00 0.48 0.02
#&gt; TCGA.2G.AAFJ.01     6  0.3864      0.683 0.48 0.00 0.00 0.00 0.00 0.52
#&gt; TCGA.2G.AAG5.01     1  0.0547      0.883 0.98 0.00 0.00 0.00 0.00 0.02
#&gt; TCGA.2G.AAGY.01     1  0.1814      0.816 0.90 0.00 0.00 0.00 0.00 0.10
#&gt; TCGA.2G.AAM3.01     3  0.4337     -0.959 0.00 0.00 0.50 0.00 0.48 0.02
#&gt; TCGA.SN.A84W.01     1  0.2048      0.833 0.88 0.00 0.00 0.00 0.00 0.12
#&gt; TCGA.2G.AAFZ.01     6  0.4609      0.696 0.42 0.00 0.00 0.04 0.00 0.54
#&gt; TCGA.2G.AAGM.01     4  0.1814      0.816 0.00 0.00 0.00 0.90 0.00 0.10
#&gt; TCGA.W4.A7U3.01     3  0.3315      0.442 0.00 0.00 0.78 0.00 0.20 0.02
#&gt; TCGA.2G.AALW.01     3  0.2350      0.237 0.00 0.00 0.88 0.00 0.10 0.02
#&gt; TCGA.XE.AAOC.01     1  0.0000      0.874 1.00 0.00 0.00 0.00 0.00 0.00
#&gt; TCGA.2G.AAG3.01     3  0.3819      0.423 0.00 0.00 0.70 0.00 0.28 0.02
#&gt; TCGA.2G.AALF.01     2  0.0000      0.948 0.00 1.00 0.00 0.00 0.00 0.00
#&gt; TCGA.2G.AALQ.01     4  0.1267      0.827 0.00 0.00 0.00 0.94 0.00 0.06
#&gt; TCGA.2G.AAFV.01     2  0.0000      0.948 0.00 1.00 0.00 0.00 0.00 0.00
#&gt; TCGA.2G.AAH4.01     6  0.6210      0.492 0.18 0.00 0.00 0.04 0.24 0.54
#&gt; TCGA.YU.AA61.01     3  0.3819      0.423 0.00 0.00 0.70 0.00 0.28 0.02
#&gt; TCGA.2G.AALR.01     4  0.0937      0.812 0.00 0.00 0.00 0.96 0.00 0.04
#&gt; TCGA.2G.AALG.01     3  0.0000      0.403 0.00 0.00 1.00 0.00 0.00 0.00
#&gt; TCGA.XE.AAOJ.01     4  0.1556      0.823 0.00 0.00 0.00 0.92 0.00 0.08
#&gt; TCGA.2G.AAGI.01     3  0.3869     -1.000 0.00 0.00 0.50 0.00 0.50 0.00
#&gt; TCGA.2G.AAGX.01     5  0.3869      1.000 0.00 0.00 0.50 0.00 0.50 0.00
</code></pre>

<script>
$('#tab-node-022-get-classes-5-a').parent().next().next().hide();
$('#tab-node-022-get-classes-5-a').click(function(){
  $('#tab-node-022-get-classes-5-a').parent().next().next().toggle();
  return(false);
});
</script>
</div>

<div id='tab-node-022-get-classes-6'>
<p><a id='tab-node-022-get-classes-6-a' style='color:#0366d6' href='#'>show/hide code output</a></p>
<pre><code class="r">cbind(get_classes(res, k = 7), get_membership(res, k = 7))
</code></pre>

<pre><code>#&gt;                 class entropy silhouette   p1   p2   p3   p4   p5   p6   p7
#&gt; TCGA.2G.AALX.01     6  0.4278      0.771 0.46 0.00 0.00 0.04 0.00 0.50 0.00
#&gt; TCGA.2G.AAGG.01     5  0.1886      0.744 0.00 0.00 0.12 0.00 0.88 0.00 0.00
#&gt; TCGA.XE.AANI.01     1  0.1006      0.913 0.96 0.00 0.00 0.00 0.00 0.02 0.02
#&gt; TCGA.YU.AA4L.01     2  0.3985      0.778 0.00 0.72 0.00 0.00 0.00 0.18 0.10
#&gt; TCGA.2G.AAH2.01     3  0.3606      0.580 0.00 0.00 0.68 0.00 0.30 0.00 0.02
#&gt; TCGA.2G.AAG6.01     1  0.1166      0.895 0.94 0.00 0.00 0.00 0.00 0.06 0.00
#&gt; TCGA.2G.AALO.01     3  0.3546      0.361 0.00 0.00 0.54 0.00 0.46 0.00 0.00
#&gt; TCGA.YU.A94I.01     2  0.0000      0.865 0.00 1.00 0.00 0.00 0.00 0.00 0.00
#&gt; TCGA.2G.AALZ.01     1  0.0504      0.920 0.98 0.00 0.00 0.00 0.00 0.02 0.00
#&gt; TCGA.2G.AAL5.01     4  0.6548      0.324 0.06 0.00 0.14 0.56 0.00 0.14 0.10
#&gt; TCGA.YU.A94D.01     7  0.2912      0.000 0.00 0.00 0.04 0.14 0.00 0.00 0.82
#&gt; TCGA.2G.AALT.01     5  0.0000      0.858 0.00 0.00 0.00 0.00 1.00 0.00 0.00
#&gt; TCGA.2G.AAGT.01     2  0.3617      0.802 0.00 0.76 0.00 0.00 0.00 0.16 0.08
#&gt; TCGA.2G.AAGV.01     5  0.0000      0.858 0.00 0.00 0.00 0.00 1.00 0.00 0.00
#&gt; TCGA.2G.AAFJ.01     6  0.4278      0.771 0.46 0.00 0.00 0.04 0.00 0.50 0.00
#&gt; TCGA.2G.AAG5.01     1  0.0000      0.924 1.00 0.00 0.00 0.00 0.00 0.00 0.00
#&gt; TCGA.2G.AAGY.01     1  0.1664      0.903 0.92 0.00 0.00 0.00 0.00 0.06 0.02
#&gt; TCGA.2G.AAM3.01     5  0.0000      0.858 0.00 0.00 0.00 0.00 1.00 0.00 0.00
#&gt; TCGA.SN.A84W.01     1  0.1166      0.895 0.94 0.00 0.00 0.00 0.00 0.06 0.00
#&gt; TCGA.2G.AAFZ.01     6  0.4692      0.772 0.42 0.00 0.00 0.08 0.00 0.50 0.00
#&gt; TCGA.2G.AAGM.01     4  0.0000      0.838 0.00 0.00 0.00 1.00 0.00 0.00 0.00
#&gt; TCGA.W4.A7U3.01     3  0.4308      0.662 0.00 0.00 0.72 0.00 0.16 0.10 0.02
#&gt; TCGA.2G.AALW.01     5  0.3496     -0.136 0.00 0.00 0.42 0.00 0.58 0.00 0.00
#&gt; TCGA.XE.AAOC.01     1  0.1006      0.913 0.96 0.00 0.00 0.00 0.00 0.02 0.02
#&gt; TCGA.2G.AAG3.01     3  0.4340      0.623 0.00 0.00 0.72 0.00 0.12 0.14 0.02
#&gt; TCGA.2G.AALF.01     2  0.0000      0.865 0.00 1.00 0.00 0.00 0.00 0.00 0.00
#&gt; TCGA.2G.AALQ.01     4  0.0000      0.838 0.00 0.00 0.00 1.00 0.00 0.00 0.00
#&gt; TCGA.2G.AAFV.01     2  0.1006      0.847 0.00 0.96 0.02 0.00 0.00 0.02 0.00
#&gt; TCGA.2G.AAH4.01     6  0.6094      0.549 0.20 0.00 0.00 0.08 0.20 0.52 0.00
#&gt; TCGA.YU.AA61.01     3  0.4340      0.623 0.00 0.00 0.72 0.00 0.12 0.14 0.02
#&gt; TCGA.2G.AALR.01     4  0.1928      0.765 0.00 0.00 0.02 0.90 0.00 0.00 0.08
#&gt; TCGA.2G.AALG.01     3  0.3546      0.361 0.00 0.00 0.54 0.00 0.46 0.00 0.00
#&gt; TCGA.XE.AAOJ.01     4  0.0000      0.838 0.00 0.00 0.00 1.00 0.00 0.00 0.00
#&gt; TCGA.2G.AAGI.01     5  0.0504      0.849 0.00 0.00 0.00 0.00 0.98 0.02 0.00
#&gt; TCGA.2G.AAGX.01     5  0.0504      0.849 0.00 0.00 0.00 0.00 0.98 0.02 0.00
</code></pre>

<script>
$('#tab-node-022-get-classes-6-a').parent().next().next().hide();
$('#tab-node-022-get-classes-6-a').click(function(){
  $('#tab-node-022-get-classes-6-a').parent().next().next().toggle();
  return(false);
});
</script>
</div>

<div id='tab-node-022-get-classes-7'>
<p><a id='tab-node-022-get-classes-7-a' style='color:#0366d6' href='#'>show/hide code output</a></p>
<pre><code class="r">cbind(get_classes(res, k = 8), get_membership(res, k = 8))
</code></pre>

<pre><code>#&gt;                 class entropy silhouette   p1   p2   p3   p4   p5   p6   p7   p8
#&gt; TCGA.2G.AALX.01     6  0.3337      0.905 0.16 0.00 0.00 0.04 0.00 0.78 0.00 0.02
#&gt; TCGA.2G.AAGG.01     5  0.2267      0.693 0.00 0.00 0.00 0.00 0.82 0.00 0.00 0.18
#&gt; TCGA.XE.AANI.01     1  0.1947      0.788 0.86 0.00 0.00 0.00 0.00 0.00 0.00 0.14
#&gt; TCGA.YU.AA4L.01     2  0.3843      0.759 0.00 0.70 0.00 0.00 0.00 0.02 0.04 0.24
#&gt; TCGA.2G.AAH2.01     3  0.3934      0.683 0.00 0.00 0.70 0.00 0.14 0.00 0.00 0.16
#&gt; TCGA.2G.AAG6.01     1  0.2547      0.804 0.84 0.00 0.04 0.00 0.00 0.12 0.00 0.00
#&gt; TCGA.2G.AALO.01     3  0.4904      0.480 0.00 0.00 0.50 0.00 0.32 0.00 0.00 0.18
#&gt; TCGA.YU.A94I.01     2  0.0000      0.858 0.00 1.00 0.00 0.00 0.00 0.00 0.00 0.00
#&gt; TCGA.2G.AALZ.01     1  0.1563      0.822 0.90 0.00 0.00 0.00 0.00 0.10 0.00 0.00
#&gt; TCGA.2G.AAL5.01     8  0.6716      0.000 0.10 0.00 0.04 0.32 0.00 0.10 0.02 0.42
#&gt; TCGA.YU.A94D.01     7  0.0808      0.000 0.00 0.00 0.00 0.04 0.00 0.00 0.96 0.00
#&gt; TCGA.2G.AALT.01     5  0.0000      0.826 0.00 0.00 0.00 0.00 1.00 0.00 0.00 0.00
#&gt; TCGA.2G.AAGT.01     2  0.3095      0.784 0.00 0.74 0.00 0.00 0.00 0.00 0.02 0.24
#&gt; TCGA.2G.AAGV.01     5  0.1275      0.821 0.00 0.00 0.00 0.00 0.94 0.04 0.00 0.02
#&gt; TCGA.2G.AAFJ.01     6  0.3337      0.905 0.16 0.00 0.00 0.04 0.00 0.78 0.00 0.02
#&gt; TCGA.2G.AAG5.01     1  0.0471      0.829 0.98 0.00 0.00 0.00 0.00 0.02 0.00 0.00
#&gt; TCGA.2G.AAGY.01     1  0.3434      0.764 0.76 0.00 0.00 0.00 0.00 0.10 0.00 0.14
#&gt; TCGA.2G.AAM3.01     5  0.1275      0.821 0.00 0.00 0.00 0.00 0.94 0.04 0.00 0.02
#&gt; TCGA.SN.A84W.01     1  0.2547      0.804 0.84 0.00 0.04 0.00 0.00 0.12 0.00 0.00
#&gt; TCGA.2G.AAFZ.01     6  0.3054      0.896 0.12 0.00 0.00 0.08 0.00 0.80 0.00 0.00
#&gt; TCGA.2G.AAGM.01     4  0.0471      0.918 0.00 0.00 0.00 0.98 0.00 0.02 0.00 0.00
#&gt; TCGA.W4.A7U3.01     3  0.1341      0.694 0.00 0.00 0.92 0.00 0.08 0.00 0.00 0.00
#&gt; TCGA.2G.AALW.01     5  0.5622     -0.110 0.00 0.00 0.30 0.00 0.46 0.04 0.00 0.20
#&gt; TCGA.XE.AAOC.01     1  0.1947      0.788 0.86 0.00 0.00 0.00 0.00 0.00 0.00 0.14
#&gt; TCGA.2G.AAG3.01     3  0.2914      0.672 0.00 0.00 0.84 0.00 0.08 0.04 0.00 0.04
#&gt; TCGA.2G.AALF.01     2  0.0000      0.858 0.00 1.00 0.00 0.00 0.00 0.00 0.00 0.00
#&gt; TCGA.2G.AALQ.01     4  0.0000      0.934 0.00 0.00 0.00 1.00 0.00 0.00 0.00 0.00
#&gt; TCGA.2G.AAFV.01     2  0.0471      0.849 0.00 0.98 0.00 0.00 0.00 0.00 0.00 0.02
#&gt; TCGA.2G.AAH4.01     6  0.3421      0.807 0.04 0.00 0.00 0.08 0.08 0.80 0.00 0.00
#&gt; TCGA.YU.AA61.01     3  0.2914      0.672 0.00 0.00 0.84 0.00 0.08 0.04 0.00 0.04
#&gt; TCGA.2G.AALR.01     4  0.1804      0.823 0.00 0.00 0.00 0.90 0.00 0.00 0.08 0.02
#&gt; TCGA.2G.AALG.01     3  0.4904      0.480 0.00 0.00 0.50 0.00 0.32 0.00 0.00 0.18
#&gt; TCGA.XE.AAOJ.01     4  0.0000      0.934 0.00 0.00 0.00 1.00 0.00 0.00 0.00 0.00
#&gt; TCGA.2G.AAGI.01     5  0.0000      0.826 0.00 0.00 0.00 0.00 1.00 0.00 0.00 0.00
#&gt; TCGA.2G.AAGX.01     5  0.0808      0.801 0.00 0.00 0.04 0.00 0.96 0.00 0.00 0.00
</code></pre>

<script>
$('#tab-node-022-get-classes-7-a').parent().next().next().hide();
$('#tab-node-022-get-classes-7-a').click(function(){
  $('#tab-node-022-get-classes-7-a').parent().next().next().toggle();
  return(false);
});
</script>
</div>
</div>

Heatmaps for the consensus matrix. It visualizes the probability of two
samples to be in a same group.




<script>
$( function() {
	$( '#tabs-node-022-consensus-heatmap' ).tabs();
} );
</script>
<div id='tabs-node-022-consensus-heatmap'>
<ul>
<li><a href='#tab-node-022-consensus-heatmap-1'>k = 2</a></li>
<li><a href='#tab-node-022-consensus-heatmap-2'>k = 3</a></li>
<li><a href='#tab-node-022-consensus-heatmap-3'>k = 4</a></li>
<li><a href='#tab-node-022-consensus-heatmap-4'>k = 5</a></li>
<li><a href='#tab-node-022-consensus-heatmap-5'>k = 6</a></li>
<li><a href='#tab-node-022-consensus-heatmap-6'>k = 7</a></li>
<li><a href='#tab-node-022-consensus-heatmap-7'>k = 8</a></li>
</ul>
<div id='tab-node-022-consensus-heatmap-1'>
<pre><code class="r">consensus_heatmap(res, k = 2)
</code></pre>

<p><img src="figure_cola/tab-node-022-consensus-heatmap-1-1.png" alt="plot of chunk tab-node-022-consensus-heatmap-1"/></p>

</div>
<div id='tab-node-022-consensus-heatmap-2'>
<pre><code class="r">consensus_heatmap(res, k = 3)
</code></pre>

<p><img src="figure_cola/tab-node-022-consensus-heatmap-2-1.png" alt="plot of chunk tab-node-022-consensus-heatmap-2"/></p>

</div>
<div id='tab-node-022-consensus-heatmap-3'>
<pre><code class="r">consensus_heatmap(res, k = 4)
</code></pre>

<p><img src="figure_cola/tab-node-022-consensus-heatmap-3-1.png" alt="plot of chunk tab-node-022-consensus-heatmap-3"/></p>

</div>
<div id='tab-node-022-consensus-heatmap-4'>
<pre><code class="r">consensus_heatmap(res, k = 5)
</code></pre>

<p><img src="figure_cola/tab-node-022-consensus-heatmap-4-1.png" alt="plot of chunk tab-node-022-consensus-heatmap-4"/></p>

</div>
<div id='tab-node-022-consensus-heatmap-5'>
<pre><code class="r">consensus_heatmap(res, k = 6)
</code></pre>

<p><img src="figure_cola/tab-node-022-consensus-heatmap-5-1.png" alt="plot of chunk tab-node-022-consensus-heatmap-5"/></p>

</div>
<div id='tab-node-022-consensus-heatmap-6'>
<pre><code class="r">consensus_heatmap(res, k = 7)
</code></pre>

<p><img src="figure_cola/tab-node-022-consensus-heatmap-6-1.png" alt="plot of chunk tab-node-022-consensus-heatmap-6"/></p>

</div>
<div id='tab-node-022-consensus-heatmap-7'>
<pre><code class="r">consensus_heatmap(res, k = 8)
</code></pre>

<p><img src="figure_cola/tab-node-022-consensus-heatmap-7-1.png" alt="plot of chunk tab-node-022-consensus-heatmap-7"/></p>

</div>
</div>

Heatmaps for the membership of samples in all partitions to see how consistent they are:





<script>
$( function() {
	$( '#tabs-node-022-membership-heatmap' ).tabs();
} );
</script>
<div id='tabs-node-022-membership-heatmap'>
<ul>
<li><a href='#tab-node-022-membership-heatmap-1'>k = 2</a></li>
<li><a href='#tab-node-022-membership-heatmap-2'>k = 3</a></li>
<li><a href='#tab-node-022-membership-heatmap-3'>k = 4</a></li>
<li><a href='#tab-node-022-membership-heatmap-4'>k = 5</a></li>
<li><a href='#tab-node-022-membership-heatmap-5'>k = 6</a></li>
<li><a href='#tab-node-022-membership-heatmap-6'>k = 7</a></li>
<li><a href='#tab-node-022-membership-heatmap-7'>k = 8</a></li>
</ul>
<div id='tab-node-022-membership-heatmap-1'>
<pre><code class="r">membership_heatmap(res, k = 2)
</code></pre>

<p><img src="figure_cola/tab-node-022-membership-heatmap-1-1.png" alt="plot of chunk tab-node-022-membership-heatmap-1"/></p>

</div>
<div id='tab-node-022-membership-heatmap-2'>
<pre><code class="r">membership_heatmap(res, k = 3)
</code></pre>

<p><img src="figure_cola/tab-node-022-membership-heatmap-2-1.png" alt="plot of chunk tab-node-022-membership-heatmap-2"/></p>

</div>
<div id='tab-node-022-membership-heatmap-3'>
<pre><code class="r">membership_heatmap(res, k = 4)
</code></pre>

<p><img src="figure_cola/tab-node-022-membership-heatmap-3-1.png" alt="plot of chunk tab-node-022-membership-heatmap-3"/></p>

</div>
<div id='tab-node-022-membership-heatmap-4'>
<pre><code class="r">membership_heatmap(res, k = 5)
</code></pre>

<p><img src="figure_cola/tab-node-022-membership-heatmap-4-1.png" alt="plot of chunk tab-node-022-membership-heatmap-4"/></p>

</div>
<div id='tab-node-022-membership-heatmap-5'>
<pre><code class="r">membership_heatmap(res, k = 6)
</code></pre>

<p><img src="figure_cola/tab-node-022-membership-heatmap-5-1.png" alt="plot of chunk tab-node-022-membership-heatmap-5"/></p>

</div>
<div id='tab-node-022-membership-heatmap-6'>
<pre><code class="r">membership_heatmap(res, k = 7)
</code></pre>

<p><img src="figure_cola/tab-node-022-membership-heatmap-6-1.png" alt="plot of chunk tab-node-022-membership-heatmap-6"/></p>

</div>
<div id='tab-node-022-membership-heatmap-7'>
<pre><code class="r">membership_heatmap(res, k = 8)
</code></pre>

<p><img src="figure_cola/tab-node-022-membership-heatmap-7-1.png" alt="plot of chunk tab-node-022-membership-heatmap-7"/></p>

</div>
</div>

As soon as the classes for columns are determined, the signatures
that are significantly different between subgroups can be looked for. 
Following are the heatmaps for signatures.






<script>
$( function() {
	$( '#tabs-node-022-get-signatures' ).tabs();
} );
</script>
<div id='tabs-node-022-get-signatures'>
<ul>
<li><a href='#tab-node-022-get-signatures-1'>k = 2</a></li>
<li><a href='#tab-node-022-get-signatures-2'>k = 3</a></li>
<li><a href='#tab-node-022-get-signatures-3'>k = 4</a></li>
<li><a href='#tab-node-022-get-signatures-4'>k = 5</a></li>
<li><a href='#tab-node-022-get-signatures-5'>k = 6</a></li>
<li><a href='#tab-node-022-get-signatures-6'>k = 7</a></li>
<li><a href='#tab-node-022-get-signatures-7'>k = 8</a></li>
</ul>
<div id='tab-node-022-get-signatures-1'>
<pre><code class="r">get_signatures(res, k = 2)
</code></pre>

<p><img src="figure_cola/tab-node-022-get-signatures-1-1.png" alt="plot of chunk tab-node-022-get-signatures-1"/></p>

</div>
<div id='tab-node-022-get-signatures-2'>
<pre><code class="r">get_signatures(res, k = 3)
</code></pre>

<p><img src="figure_cola/tab-node-022-get-signatures-2-1.png" alt="plot of chunk tab-node-022-get-signatures-2"/></p>

</div>
<div id='tab-node-022-get-signatures-3'>
<pre><code class="r">get_signatures(res, k = 4)
</code></pre>

<p><img src="figure_cola/tab-node-022-get-signatures-3-1.png" alt="plot of chunk tab-node-022-get-signatures-3"/></p>

</div>
<div id='tab-node-022-get-signatures-4'>
<pre><code class="r">get_signatures(res, k = 5)
</code></pre>

<p><img src="figure_cola/tab-node-022-get-signatures-4-1.png" alt="plot of chunk tab-node-022-get-signatures-4"/></p>

</div>
<div id='tab-node-022-get-signatures-5'>
<pre><code class="r">get_signatures(res, k = 6)
</code></pre>

<p><img src="figure_cola/tab-node-022-get-signatures-5-1.png" alt="plot of chunk tab-node-022-get-signatures-5"/></p>

</div>
<div id='tab-node-022-get-signatures-6'>
<pre><code class="r">get_signatures(res, k = 7)
</code></pre>

<p><img src="figure_cola/tab-node-022-get-signatures-6-1.png" alt="plot of chunk tab-node-022-get-signatures-6"/></p>

</div>
<div id='tab-node-022-get-signatures-7'>
<pre><code class="r">get_signatures(res, k = 8)
</code></pre>

<p><img src="figure_cola/tab-node-022-get-signatures-7-1.png" alt="plot of chunk tab-node-022-get-signatures-7"/></p>

</div>
</div>



Compare the overlap of signatures from different k:

```r
compare_signatures(res)
```

![plot of chunk node-022-signature_compare](figure_cola/node-022-signature_compare-1.png)

`get_signature()` returns a data frame invisibly. To get the list of signatures, the function
call should be assigned to a variable explicitly. In following code, if `plot` argument is set
to `FALSE`, no heatmap is plotted while only the differential analysis is performed.

```r
# code only for demonstration
tb = get_signature(res, k = ..., plot = FALSE)
```

An example of the output of `tb` is:

```
#>   which_row         fdr    mean_1    mean_2 scaled_mean_1 scaled_mean_2 km
#> 1        38 0.042760348  8.373488  9.131774    -0.5533452     0.5164555  1
#> 2        40 0.018707592  7.106213  8.469186    -0.6173731     0.5762149  1
#> 3        55 0.019134737 10.221463 11.207825    -0.6159697     0.5749050  1
#> 4        59 0.006059896  5.921854  7.869574    -0.6899429     0.6439467  1
#> 5        60 0.018055526  8.928898 10.211722    -0.6204761     0.5791110  1
#> 6        98 0.009384629 15.714769 14.887706     0.6635654    -0.6193277  2
...
```

The columns in `tb` are:

1. `which_row`: row indices corresponding to the input matrix.
2. `fdr`: FDR for the differential test. 
3. `mean_x`: The mean value in group x.
4. `scaled_mean_x`: The mean value in group x after rows are scaled.
5. `km`: Row groups if k-means clustering is applied to rows (which is done by automatically selecting number of clusters).

If there are too many signatures, `top_signatures = ...` can be set to only show the 
signatures with the highest FDRs:

```r
# code only for demonstration
# e.g. to show the top 500 most significant rows
tb = get_signature(res, k = ..., top_signatures = 500)
```

If the signatures are defined as these which are uniquely high in current group, `diff_method` argument
can be set to `"uniquely_high_in_one_group"`:

```r
# code only for demonstration
tb = get_signature(res, k = ..., diff_method = "uniquely_high_in_one_group")
```




UMAP plot which shows how samples are separated.


<script>
$( function() {
	$( '#tabs-node-022-dimension-reduction' ).tabs();
} );
</script>
<div id='tabs-node-022-dimension-reduction'>
<ul>
<li><a href='#tab-node-022-dimension-reduction-1'>k = 2</a></li>
<li><a href='#tab-node-022-dimension-reduction-2'>k = 3</a></li>
<li><a href='#tab-node-022-dimension-reduction-3'>k = 4</a></li>
<li><a href='#tab-node-022-dimension-reduction-4'>k = 5</a></li>
<li><a href='#tab-node-022-dimension-reduction-5'>k = 6</a></li>
<li><a href='#tab-node-022-dimension-reduction-6'>k = 7</a></li>
<li><a href='#tab-node-022-dimension-reduction-7'>k = 8</a></li>
</ul>
<div id='tab-node-022-dimension-reduction-1'>
<pre><code class="r">dimension_reduction(res, k = 2, method = &quot;UMAP&quot;)
</code></pre>

<p><img src="figure_cola/tab-node-022-dimension-reduction-1-1.png" alt="plot of chunk tab-node-022-dimension-reduction-1"/></p>

</div>
<div id='tab-node-022-dimension-reduction-2'>
<pre><code class="r">dimension_reduction(res, k = 3, method = &quot;UMAP&quot;)
</code></pre>

<p><img src="figure_cola/tab-node-022-dimension-reduction-2-1.png" alt="plot of chunk tab-node-022-dimension-reduction-2"/></p>

</div>
<div id='tab-node-022-dimension-reduction-3'>
<pre><code class="r">dimension_reduction(res, k = 4, method = &quot;UMAP&quot;)
</code></pre>

<p><img src="figure_cola/tab-node-022-dimension-reduction-3-1.png" alt="plot of chunk tab-node-022-dimension-reduction-3"/></p>

</div>
<div id='tab-node-022-dimension-reduction-4'>
<pre><code class="r">dimension_reduction(res, k = 5, method = &quot;UMAP&quot;)
</code></pre>

<p><img src="figure_cola/tab-node-022-dimension-reduction-4-1.png" alt="plot of chunk tab-node-022-dimension-reduction-4"/></p>

</div>
<div id='tab-node-022-dimension-reduction-5'>
<pre><code class="r">dimension_reduction(res, k = 6, method = &quot;UMAP&quot;)
</code></pre>

<p><img src="figure_cola/tab-node-022-dimension-reduction-5-1.png" alt="plot of chunk tab-node-022-dimension-reduction-5"/></p>

</div>
<div id='tab-node-022-dimension-reduction-6'>
<pre><code class="r">dimension_reduction(res, k = 7, method = &quot;UMAP&quot;)
</code></pre>

<p><img src="figure_cola/tab-node-022-dimension-reduction-6-1.png" alt="plot of chunk tab-node-022-dimension-reduction-6"/></p>

</div>
<div id='tab-node-022-dimension-reduction-7'>
<pre><code class="r">dimension_reduction(res, k = 8, method = &quot;UMAP&quot;)
</code></pre>

<p><img src="figure_cola/tab-node-022-dimension-reduction-7-1.png" alt="plot of chunk tab-node-022-dimension-reduction-7"/></p>

</div>
</div>



Following heatmap shows how subgroups are split when increasing `k`:

```r
collect_classes(res)
```

![plot of chunk node-022-collect-classes](figure_cola/node-022-collect-classes-1.png)



If matrix rows can be associated to genes, consider to use `functional_enrichment(res,
...)` to perform function enrichment for the signature genes. See [this vignette](https://jokergoo.github.io/cola_vignettes/functional_enrichment.html) for more detailed explanations.


 

---------------------------------------------------




### Node023


Parent node: [Node02](#Node02).
Child nodes: 
                Node0121-leaf
        ,
                Node0122-leaf
        ,
                Node0123-leaf
        ,
                Node0221-leaf
        ,
                Node0222-leaf
        ,
                Node0223-leaf
        ,
                Node0224-leaf
        ,
                Node0231-leaf
        ,
                Node0232-leaf
        ,
                Node0233-leaf
        ,
                Node0234-leaf
        ,
                Node0241-leaf
        ,
                Node0242-leaf
        ,
                Node0243-leaf
        .







The object with results only for a single top-value method and a single partitioning method 
can be extracted as:

```r
res = res_rh["023"]
```

A summary of `res` and all the functions that can be applied to it:

```r
res
```

```
#> A 'ConsensusPartition' object with k = 2, 3, 4, 5, 6, 7, 8.
#>   On a matrix with 30000 rows and 14 columns.
#>   Top rows (1000) are extracted by 'SD' method.
#>   Subgroups are detected by 'kmeans' method.
#>   Performed in total 350 partitions by row resampling.
#>   Best k for subgroups seems to be 5.
#> 
#> Following methods can be applied to this 'ConsensusPartition' object:
#>  [1] "cola_report"             "collect_classes"         "collect_plots"          
#>  [4] "collect_stats"           "colnames"                "compare_partitions"     
#>  [7] "compare_signatures"      "consensus_heatmap"       "dimension_reduction"    
#> [10] "functional_enrichment"   "get_anno_col"            "get_anno"               
#> [13] "get_classes"             "get_consensus"           "get_matrix"             
#> [16] "get_membership"          "get_param"               "get_signatures"         
#> [19] "get_stats"               "is_best_k"               "is_stable_k"            
#> [22] "membership_heatmap"      "ncol"                    "nrow"                   
#> [25] "plot_ecdf"               "predict_classes"         "rownames"               
#> [28] "select_partition_number" "show"                    "suggest_best_k"         
#> [31] "test_to_known_factors"   "top_rows_heatmap"
```

`collect_plots()` function collects all the plots made from `res` for all `k` (number of subgroups)
into one single page to provide an easy and fast comparison between different `k`.

```r
collect_plots(res)
```

![plot of chunk node-023-collect-plots](figure_cola/node-023-collect-plots-1.png)

The plots are:

- The first row: a plot of the eCDF (empirical cumulative distribution
  function) curves of the consensus matrix for each `k` and the heatmap of
  predicted classes for each `k`.
- The second row: heatmaps of the consensus matrix for each `k`.
- The third row: heatmaps of the membership matrix for each `k`.
- The fouth row: heatmaps of the signatures for each `k`.

All the plots in panels can be made by individual functions and they are
plotted later in this section.

`select_partition_number()` produces several plots showing different
statistics for choosing "optimized" `k`. There are following statistics:

- eCDF curves of the consensus matrix for each `k`;
- 1-PAC. [The PAC score](https://en.wikipedia.org/wiki/Consensus_clustering#Over-interpretation_potential_of_consensus_clustering)
  measures the proportion of the ambiguous subgrouping.
- Mean silhouette score.
- Concordance. The mean probability of fiting the consensus subgroup labels in all
  partitions.
- Area increased. Denote $A_k$ as the area under the eCDF curve for current
  `k`, the area increased is defined as $A_k - A_{k-1}$.
- Rand index. The percent of pairs of samples that are both in a same cluster
  or both are not in a same cluster in the partition of k and k-1.
- Jaccard index. The ratio of pairs of samples are both in a same cluster in
  the partition of k and k-1 and the pairs of samples are both in a same
  cluster in the partition k or k-1.

The detailed explanations of these statistics can be found in [the _cola_
vignette](https://jokergoo.github.io/cola_vignettes/cola.html#toc_13).

Generally speaking, higher 1-PAC score, higher mean silhouette score or higher
concordance corresponds to better partition. Rand index and Jaccard index
measure how similar the current partition is compared to partition with `k-1`.
If they are too similar, we won't accept `k` is better than `k-1`.

```r
select_partition_number(res)
```

![plot of chunk node-023-select-partition-number](figure_cola/node-023-select-partition-number-1.png)

The numeric values for all these statistics can be obtained by `get_stats()`.

```r
get_stats(res)
```

```
#>   k 1-PAC mean_silhouette concordance area_increased  Rand Jaccard
#> 2 2 1.000           1.000       1.000         0.2645 0.736   0.736
#> 3 3 0.473           0.874       0.906         1.3454 0.615   0.478
#> 4 4 0.824           0.962       0.934         0.2252 0.780   0.444
#> 5 5 0.945           0.894       0.949         0.0646 0.956   0.800
#> 6 6 0.934           0.790       0.921         0.0462 1.000   1.000
#> 7 7 0.868           0.684       0.889         0.0337 0.978   0.875
#> 8 8 0.835           0.519       0.764         0.0302 0.934   0.571
```

`suggest_best_k()` suggests the best $k$ based on these statistics. The rules are as follows:

- All $k$ with Jaccard index larger than 0.95 are removed because increasing
  $k$ does not provide enough extra information. If all $k$ are removed, it is
  marked as no subgroup is detected.
- For all $k$ with 1-PAC score larger than 0.9, the maximal $k$ is taken as
  the best $k$, and other $k$ are marked as optional $k$.
- If it does not fit the second rule. The $k$ with the maximal vote of the
  highest 1-PAC score, highest mean silhouette, and highest concordance is
  taken as the best $k$.

```r
suggest_best_k(res)
```

```
#> [1] 5
#> attr(,"optional")
#> [1] 2
```

There is also optional best $k$ = 2 that is worth to check.

Following is the table of the partitions (You need to click the **show/hide
code output** link to see it). The membership matrix (columns with name `p*`)
is inferred by
[`clue::cl_consensus()`](https://www.rdocumentation.org/link/cl_consensus?package=clue)
function with the `SE` method. Basically the value in the membership matrix
represents the probability to belong to a certain group. The finall subgroup
label for an item is determined with the group with highest probability it
belongs to.

In `get_classes()` function, the entropy is calculated from the membership
matrix and the silhouette score is calculated from the consensus matrix.



<script>
$( function() {
	$( '#tabs-node-023-get-classes' ).tabs();
} );
</script>
<div id='tabs-node-023-get-classes'>
<ul>
<li><a href='#tab-node-023-get-classes-1'>k = 2</a></li>
<li><a href='#tab-node-023-get-classes-2'>k = 3</a></li>
<li><a href='#tab-node-023-get-classes-3'>k = 4</a></li>
<li><a href='#tab-node-023-get-classes-4'>k = 5</a></li>
<li><a href='#tab-node-023-get-classes-5'>k = 6</a></li>
<li><a href='#tab-node-023-get-classes-6'>k = 7</a></li>
<li><a href='#tab-node-023-get-classes-7'>k = 8</a></li>
</ul>

<div id='tab-node-023-get-classes-1'>
<p><a id='tab-node-023-get-classes-1-a' style='color:#0366d6' href='#'>show/hide code output</a></p>
<pre><code class="r">cbind(get_classes(res, k = 2), get_membership(res, k = 2))
</code></pre>

<pre><code>#&gt;                 class entropy silhouette p1 p2
#&gt; TCGA.2G.AAGP.01     1       0          1  1  0
#&gt; TCGA.YU.A90Y.01     1       0          1  1  0
#&gt; TCGA.2G.AALY.01     1       0          1  1  0
#&gt; TCGA.2G.AAKG.01     1       0          1  1  0
#&gt; TCGA.SN.A84X.01     2       0          1  0  1
#&gt; TCGA.X3.A8G4.01     1       0          1  1  0
#&gt; TCGA.2G.AAKG.05     1       0          1  1  0
#&gt; TCGA.2G.AAGS.01     1       0          1  1  0
#&gt; TCGA.XE.AAOB.01     1       0          1  1  0
#&gt; TCGA.XE.AANR.01     2       0          1  0  1
#&gt; TCGA.2G.AALS.01     1       0          1  1  0
#&gt; TCGA.2G.AALN.01     1       0          1  1  0
#&gt; TCGA.2G.AAGC.01     1       0          1  1  0
#&gt; TCGA.2G.AAGZ.01     1       0          1  1  0
</code></pre>

<script>
$('#tab-node-023-get-classes-1-a').parent().next().next().hide();
$('#tab-node-023-get-classes-1-a').click(function(){
  $('#tab-node-023-get-classes-1-a').parent().next().next().toggle();
  return(false);
});
</script>
</div>

<div id='tab-node-023-get-classes-2'>
<p><a id='tab-node-023-get-classes-2-a' style='color:#0366d6' href='#'>show/hide code output</a></p>
<pre><code class="r">cbind(get_classes(res, k = 3), get_membership(res, k = 3))
</code></pre>

<pre><code>#&gt;                 class entropy silhouette   p1   p2   p3
#&gt; TCGA.2G.AAGP.01     1  0.2066      0.861 0.94 0.00 0.06
#&gt; TCGA.YU.A90Y.01     3  0.2537      0.929 0.08 0.00 0.92
#&gt; TCGA.2G.AALY.01     1  0.4291      0.802 0.82 0.00 0.18
#&gt; TCGA.2G.AAKG.01     3  0.2537      0.929 0.08 0.00 0.92
#&gt; TCGA.SN.A84X.01     2  0.0000      0.989 0.00 1.00 0.00
#&gt; TCGA.X3.A8G4.01     3  0.2537      0.929 0.08 0.00 0.92
#&gt; TCGA.2G.AAKG.05     3  0.4555      0.694 0.20 0.00 0.80
#&gt; TCGA.2G.AAGS.01     1  0.4291      0.802 0.82 0.00 0.18
#&gt; TCGA.XE.AAOB.01     1  0.2066      0.861 0.94 0.00 0.06
#&gt; TCGA.XE.AANR.01     2  0.0892      0.989 0.00 0.98 0.02
#&gt; TCGA.2G.AALS.01     1  0.2066      0.861 0.94 0.00 0.06
#&gt; TCGA.2G.AALN.01     1  0.4291      0.802 0.82 0.00 0.18
#&gt; TCGA.2G.AAGC.01     3  0.2537      0.929 0.08 0.00 0.92
#&gt; TCGA.2G.AAGZ.01     1  0.2066      0.861 0.94 0.00 0.06
</code></pre>

<script>
$('#tab-node-023-get-classes-2-a').parent().next().next().hide();
$('#tab-node-023-get-classes-2-a').click(function(){
  $('#tab-node-023-get-classes-2-a').parent().next().next().toggle();
  return(false);
});
</script>
</div>

<div id='tab-node-023-get-classes-3'>
<p><a id='tab-node-023-get-classes-3-a' style='color:#0366d6' href='#'>show/hide code output</a></p>
<pre><code class="r">cbind(get_classes(res, k = 4), get_membership(res, k = 4))
</code></pre>

<pre><code>#&gt;                 class entropy silhouette   p1   p2   p3   p4
#&gt; TCGA.2G.AAGP.01     1  0.3606      0.939 0.84 0.00 0.02 0.14
#&gt; TCGA.YU.A90Y.01     3  0.0000      1.000 0.00 0.00 1.00 0.00
#&gt; TCGA.2G.AALY.01     4  0.1637      1.000 0.00 0.00 0.06 0.94
#&gt; TCGA.2G.AAKG.01     3  0.0000      1.000 0.00 0.00 1.00 0.00
#&gt; TCGA.SN.A84X.01     2  0.0000      0.987 0.00 1.00 0.00 0.00
#&gt; TCGA.X3.A8G4.01     3  0.0000      1.000 0.00 0.00 1.00 0.00
#&gt; TCGA.2G.AAKG.05     1  0.2830      0.743 0.90 0.00 0.04 0.06
#&gt; TCGA.2G.AAGS.01     4  0.1637      1.000 0.00 0.00 0.06 0.94
#&gt; TCGA.XE.AAOB.01     1  0.3606      0.939 0.84 0.00 0.02 0.14
#&gt; TCGA.XE.AANR.01     2  0.0707      0.987 0.02 0.98 0.00 0.00
#&gt; TCGA.2G.AALS.01     1  0.3606      0.939 0.84 0.00 0.02 0.14
#&gt; TCGA.2G.AALN.01     4  0.1637      1.000 0.00 0.00 0.06 0.94
#&gt; TCGA.2G.AAGC.01     3  0.0000      1.000 0.00 0.00 1.00 0.00
#&gt; TCGA.2G.AAGZ.01     1  0.3606      0.939 0.84 0.00 0.02 0.14
</code></pre>

<script>
$('#tab-node-023-get-classes-3-a').parent().next().next().hide();
$('#tab-node-023-get-classes-3-a').click(function(){
  $('#tab-node-023-get-classes-3-a').parent().next().next().toggle();
  return(false);
});
</script>
</div>

<div id='tab-node-023-get-classes-4'>
<p><a id='tab-node-023-get-classes-4-a' style='color:#0366d6' href='#'>show/hide code output</a></p>
<pre><code class="r">cbind(get_classes(res, k = 5), get_membership(res, k = 5))
</code></pre>

<pre><code>#&gt;                 class entropy silhouette   p1   p2 p3   p4   p5
#&gt; TCGA.2G.AAGP.01     1   0.000      1.000 1.00 0.00  0 0.00 0.00
#&gt; TCGA.YU.A90Y.01     3   0.000      1.000 0.00 0.00  1 0.00 0.00
#&gt; TCGA.2G.AALY.01     4   0.173      0.965 0.08 0.00  0 0.92 0.00
#&gt; TCGA.2G.AAKG.01     3   0.000      1.000 0.00 0.00  1 0.00 0.00
#&gt; TCGA.SN.A84X.01     2   0.228      0.831 0.00 0.88  0 0.00 0.12
#&gt; TCGA.X3.A8G4.01     3   0.000      1.000 0.00 0.00  1 0.00 0.00
#&gt; TCGA.2G.AAKG.05     5   0.311      0.000 0.20 0.00  0 0.00 0.80
#&gt; TCGA.2G.AAGS.01     4   0.342      0.928 0.08 0.00  0 0.84 0.08
#&gt; TCGA.XE.AAOB.01     1   0.000      1.000 1.00 0.00  0 0.00 0.00
#&gt; TCGA.XE.AANR.01     2   0.173      0.831 0.00 0.92  0 0.08 0.00
#&gt; TCGA.2G.AALS.01     1   0.000      1.000 1.00 0.00  0 0.00 0.00
#&gt; TCGA.2G.AALN.01     4   0.173      0.965 0.08 0.00  0 0.92 0.00
#&gt; TCGA.2G.AAGC.01     3   0.000      1.000 0.00 0.00  1 0.00 0.00
#&gt; TCGA.2G.AAGZ.01     1   0.000      1.000 1.00 0.00  0 0.00 0.00
</code></pre>

<script>
$('#tab-node-023-get-classes-4-a').parent().next().next().hide();
$('#tab-node-023-get-classes-4-a').click(function(){
  $('#tab-node-023-get-classes-4-a').parent().next().next().toggle();
  return(false);
});
</script>
</div>

<div id='tab-node-023-get-classes-5'>
<p><a id='tab-node-023-get-classes-5-a' style='color:#0366d6' href='#'>show/hide code output</a></p>
<pre><code class="r">cbind(get_classes(res, k = 6), get_membership(res, k = 6))
</code></pre>

<pre><code>#&gt;                 class entropy silhouette   p1   p2   p3   p4   p5   p6
#&gt; TCGA.2G.AAGP.01     1  0.0937      0.942 0.96 0.04 0.00 0.00 0.00 0.00
#&gt; TCGA.YU.A90Y.01     3  0.0000      0.941 0.00 0.00 1.00 0.00 0.00 0.00
#&gt; TCGA.2G.AALY.01     4  0.0000      0.779 0.00 0.00 0.00 1.00 0.00 0.00
#&gt; TCGA.2G.AAKG.01     3  0.0000      0.941 0.00 0.00 1.00 0.00 0.00 0.00
#&gt; TCGA.SN.A84X.01     6  0.0000      0.751 0.00 0.00 0.00 0.00 0.00 1.00
#&gt; TCGA.X3.A8G4.01     3  0.2631      0.834 0.00 0.18 0.82 0.00 0.00 0.00
#&gt; TCGA.2G.AAKG.05     5  0.4246      0.000 0.02 0.40 0.00 0.00 0.58 0.00
#&gt; TCGA.2G.AAGS.01     4  0.3797      0.543 0.00 0.00 0.00 0.58 0.42 0.00
#&gt; TCGA.XE.AAOB.01     1  0.0937      0.962 0.96 0.04 0.00 0.00 0.00 0.00
#&gt; TCGA.XE.AANR.01     6  0.3309      0.751 0.00 0.28 0.00 0.00 0.00 0.72
#&gt; TCGA.2G.AALS.01     1  0.0937      0.962 0.96 0.04 0.00 0.00 0.00 0.00
#&gt; TCGA.2G.AALN.01     4  0.0937      0.771 0.00 0.04 0.00 0.96 0.00 0.00
#&gt; TCGA.2G.AAGC.01     3  0.0547      0.938 0.00 0.02 0.98 0.00 0.00 0.00
#&gt; TCGA.2G.AAGZ.01     1  0.0547      0.952 0.98 0.02 0.00 0.00 0.00 0.00
</code></pre>

<script>
$('#tab-node-023-get-classes-5-a').parent().next().next().hide();
$('#tab-node-023-get-classes-5-a').click(function(){
  $('#tab-node-023-get-classes-5-a').parent().next().next().toggle();
  return(false);
});
</script>
</div>

<div id='tab-node-023-get-classes-6'>
<p><a id='tab-node-023-get-classes-6-a' style='color:#0366d6' href='#'>show/hide code output</a></p>
<pre><code class="r">cbind(get_classes(res, k = 7), get_membership(res, k = 7))
</code></pre>

<pre><code>#&gt;                 class entropy silhouette   p1   p2   p3   p4 p5   p6   p7
#&gt; TCGA.2G.AAGP.01     1  0.2912      0.831 0.82 0.14 0.00 0.00  0 0.00 0.04
#&gt; TCGA.YU.A90Y.01     3  0.3546      0.838 0.00 0.46 0.54 0.00  0 0.00 0.00
#&gt; TCGA.2G.AALY.01     4  0.1166      0.767 0.00 0.00 0.00 0.94  0 0.00 0.06
#&gt; TCGA.2G.AAKG.01     3  0.4244      0.832 0.00 0.42 0.54 0.00  0 0.00 0.04
#&gt; TCGA.SN.A84X.01     6  0.2422      0.844 0.00 0.18 0.00 0.00  0 0.82 0.00
#&gt; TCGA.X3.A8G4.01     3  0.0000      0.490 0.00 0.00 1.00 0.00  0 0.00 0.00
#&gt; TCGA.2G.AAKG.05     5  0.0000      0.000 0.00 0.00 0.00 0.00  1 0.00 0.00
#&gt; TCGA.2G.AAGS.01     7  0.2422      0.000 0.00 0.00 0.00 0.18  0 0.00 0.82
#&gt; TCGA.XE.AAOB.01     1  0.0504      0.866 0.98 0.00 0.00 0.00  0 0.00 0.02
#&gt; TCGA.XE.AANR.01     6  0.0000      0.844 0.00 0.00 0.00 0.00  0 1.00 0.00
#&gt; TCGA.2G.AALS.01     1  0.0000      0.866 1.00 0.00 0.00 0.00  0 0.00 0.00
#&gt; TCGA.2G.AALN.01     4  0.2081      0.775 0.00 0.14 0.00 0.86  0 0.00 0.00
#&gt; TCGA.2G.AAGC.01     3  0.3525      0.838 0.00 0.44 0.56 0.00  0 0.00 0.00
#&gt; TCGA.2G.AAGZ.01     1  0.4030      0.777 0.72 0.16 0.00 0.00  0 0.00 0.12
</code></pre>

<script>
$('#tab-node-023-get-classes-6-a').parent().next().next().hide();
$('#tab-node-023-get-classes-6-a').click(function(){
  $('#tab-node-023-get-classes-6-a').parent().next().next().toggle();
  return(false);
});
</script>
</div>

<div id='tab-node-023-get-classes-7'>
<p><a id='tab-node-023-get-classes-7-a' style='color:#0366d6' href='#'>show/hide code output</a></p>
<pre><code class="r">cbind(get_classes(res, k = 8), get_membership(res, k = 8))
</code></pre>

<pre><code>#&gt;                 class entropy silhouette   p1   p2   p3   p4 p5  p6   p7   p8
#&gt; TCGA.2G.AAGP.01     1  0.4022      0.484 0.74 0.04 0.00 0.00  0 0.0 0.12 0.10
#&gt; TCGA.YU.A90Y.01     3  0.2407      0.786 0.00 0.00 0.86 0.00  0 0.0 0.08 0.06
#&gt; TCGA.2G.AALY.01     4  0.3263      0.665 0.00 0.12 0.00 0.78  0 0.0 0.00 0.10
#&gt; TCGA.2G.AAKG.01     3  0.2350      0.786 0.00 0.00 0.86 0.00  0 0.0 0.10 0.04
#&gt; TCGA.SN.A84X.01     6  0.0000      0.731 0.00 0.00 0.00 0.00  0 1.0 0.00 0.00
#&gt; TCGA.X3.A8G4.01     2  0.2267      0.000 0.00 0.82 0.18 0.00  0 0.0 0.00 0.00
#&gt; TCGA.2G.AAKG.05     5  0.0000      0.000 0.00 0.00 0.00 0.00  1 0.0 0.00 0.00
#&gt; TCGA.2G.AAGS.01     7  0.3237      0.000 0.00 0.00 0.00 0.40  0 0.0 0.60 0.00
#&gt; TCGA.XE.AAOB.01     1  0.0000      0.791 1.00 0.00 0.00 0.00  0 0.0 0.00 0.00
#&gt; TCGA.XE.AANR.01     6  0.4169      0.731 0.00 0.02 0.00 0.00  0 0.7 0.10 0.18
#&gt; TCGA.2G.AALS.01     1  0.0000      0.791 1.00 0.00 0.00 0.00  0 0.0 0.00 0.00
#&gt; TCGA.2G.AALN.01     4  0.0000      0.665 0.00 0.00 0.00 1.00  0 0.0 0.00 0.00
#&gt; TCGA.2G.AAGC.01     3  0.0471      0.831 0.00 0.02 0.98 0.00  0 0.0 0.00 0.00
#&gt; TCGA.2G.AAGZ.01     8  0.3193      0.000 0.38 0.00 0.00 0.00  0 0.0 0.00 0.62
</code></pre>

<script>
$('#tab-node-023-get-classes-7-a').parent().next().next().hide();
$('#tab-node-023-get-classes-7-a').click(function(){
  $('#tab-node-023-get-classes-7-a').parent().next().next().toggle();
  return(false);
});
</script>
</div>
</div>

Heatmaps for the consensus matrix. It visualizes the probability of two
samples to be in a same group.




<script>
$( function() {
	$( '#tabs-node-023-consensus-heatmap' ).tabs();
} );
</script>
<div id='tabs-node-023-consensus-heatmap'>
<ul>
<li><a href='#tab-node-023-consensus-heatmap-1'>k = 2</a></li>
<li><a href='#tab-node-023-consensus-heatmap-2'>k = 3</a></li>
<li><a href='#tab-node-023-consensus-heatmap-3'>k = 4</a></li>
<li><a href='#tab-node-023-consensus-heatmap-4'>k = 5</a></li>
<li><a href='#tab-node-023-consensus-heatmap-5'>k = 6</a></li>
<li><a href='#tab-node-023-consensus-heatmap-6'>k = 7</a></li>
<li><a href='#tab-node-023-consensus-heatmap-7'>k = 8</a></li>
</ul>
<div id='tab-node-023-consensus-heatmap-1'>
<pre><code class="r">consensus_heatmap(res, k = 2)
</code></pre>

<p><img src="figure_cola/tab-node-023-consensus-heatmap-1-1.png" alt="plot of chunk tab-node-023-consensus-heatmap-1"/></p>

</div>
<div id='tab-node-023-consensus-heatmap-2'>
<pre><code class="r">consensus_heatmap(res, k = 3)
</code></pre>

<p><img src="figure_cola/tab-node-023-consensus-heatmap-2-1.png" alt="plot of chunk tab-node-023-consensus-heatmap-2"/></p>

</div>
<div id='tab-node-023-consensus-heatmap-3'>
<pre><code class="r">consensus_heatmap(res, k = 4)
</code></pre>

<p><img src="figure_cola/tab-node-023-consensus-heatmap-3-1.png" alt="plot of chunk tab-node-023-consensus-heatmap-3"/></p>

</div>
<div id='tab-node-023-consensus-heatmap-4'>
<pre><code class="r">consensus_heatmap(res, k = 5)
</code></pre>

<p><img src="figure_cola/tab-node-023-consensus-heatmap-4-1.png" alt="plot of chunk tab-node-023-consensus-heatmap-4"/></p>

</div>
<div id='tab-node-023-consensus-heatmap-5'>
<pre><code class="r">consensus_heatmap(res, k = 6)
</code></pre>

<p><img src="figure_cola/tab-node-023-consensus-heatmap-5-1.png" alt="plot of chunk tab-node-023-consensus-heatmap-5"/></p>

</div>
<div id='tab-node-023-consensus-heatmap-6'>
<pre><code class="r">consensus_heatmap(res, k = 7)
</code></pre>

<p><img src="figure_cola/tab-node-023-consensus-heatmap-6-1.png" alt="plot of chunk tab-node-023-consensus-heatmap-6"/></p>

</div>
<div id='tab-node-023-consensus-heatmap-7'>
<pre><code class="r">consensus_heatmap(res, k = 8)
</code></pre>

<p><img src="figure_cola/tab-node-023-consensus-heatmap-7-1.png" alt="plot of chunk tab-node-023-consensus-heatmap-7"/></p>

</div>
</div>

Heatmaps for the membership of samples in all partitions to see how consistent they are:





<script>
$( function() {
	$( '#tabs-node-023-membership-heatmap' ).tabs();
} );
</script>
<div id='tabs-node-023-membership-heatmap'>
<ul>
<li><a href='#tab-node-023-membership-heatmap-1'>k = 2</a></li>
<li><a href='#tab-node-023-membership-heatmap-2'>k = 3</a></li>
<li><a href='#tab-node-023-membership-heatmap-3'>k = 4</a></li>
<li><a href='#tab-node-023-membership-heatmap-4'>k = 5</a></li>
<li><a href='#tab-node-023-membership-heatmap-5'>k = 6</a></li>
<li><a href='#tab-node-023-membership-heatmap-6'>k = 7</a></li>
<li><a href='#tab-node-023-membership-heatmap-7'>k = 8</a></li>
</ul>
<div id='tab-node-023-membership-heatmap-1'>
<pre><code class="r">membership_heatmap(res, k = 2)
</code></pre>

<p><img src="figure_cola/tab-node-023-membership-heatmap-1-1.png" alt="plot of chunk tab-node-023-membership-heatmap-1"/></p>

</div>
<div id='tab-node-023-membership-heatmap-2'>
<pre><code class="r">membership_heatmap(res, k = 3)
</code></pre>

<p><img src="figure_cola/tab-node-023-membership-heatmap-2-1.png" alt="plot of chunk tab-node-023-membership-heatmap-2"/></p>

</div>
<div id='tab-node-023-membership-heatmap-3'>
<pre><code class="r">membership_heatmap(res, k = 4)
</code></pre>

<p><img src="figure_cola/tab-node-023-membership-heatmap-3-1.png" alt="plot of chunk tab-node-023-membership-heatmap-3"/></p>

</div>
<div id='tab-node-023-membership-heatmap-4'>
<pre><code class="r">membership_heatmap(res, k = 5)
</code></pre>

<p><img src="figure_cola/tab-node-023-membership-heatmap-4-1.png" alt="plot of chunk tab-node-023-membership-heatmap-4"/></p>

</div>
<div id='tab-node-023-membership-heatmap-5'>
<pre><code class="r">membership_heatmap(res, k = 6)
</code></pre>

<p><img src="figure_cola/tab-node-023-membership-heatmap-5-1.png" alt="plot of chunk tab-node-023-membership-heatmap-5"/></p>

</div>
<div id='tab-node-023-membership-heatmap-6'>
<pre><code class="r">membership_heatmap(res, k = 7)
</code></pre>

<p><img src="figure_cola/tab-node-023-membership-heatmap-6-1.png" alt="plot of chunk tab-node-023-membership-heatmap-6"/></p>

</div>
<div id='tab-node-023-membership-heatmap-7'>
<pre><code class="r">membership_heatmap(res, k = 8)
</code></pre>

<p><img src="figure_cola/tab-node-023-membership-heatmap-7-1.png" alt="plot of chunk tab-node-023-membership-heatmap-7"/></p>

</div>
</div>

As soon as the classes for columns are determined, the signatures
that are significantly different between subgroups can be looked for. 
Following are the heatmaps for signatures.






<script>
$( function() {
	$( '#tabs-node-023-get-signatures' ).tabs();
} );
</script>
<div id='tabs-node-023-get-signatures'>
<ul>
<li><a href='#tab-node-023-get-signatures-1'>k = 2</a></li>
<li><a href='#tab-node-023-get-signatures-2'>k = 3</a></li>
<li><a href='#tab-node-023-get-signatures-3'>k = 4</a></li>
<li><a href='#tab-node-023-get-signatures-4'>k = 5</a></li>
<li><a href='#tab-node-023-get-signatures-5'>k = 6</a></li>
<li><a href='#tab-node-023-get-signatures-6'>k = 7</a></li>
<li><a href='#tab-node-023-get-signatures-7'>k = 8</a></li>
</ul>
<div id='tab-node-023-get-signatures-1'>
<pre><code class="r">get_signatures(res, k = 2)
</code></pre>

<p><img src="figure_cola/tab-node-023-get-signatures-1-1.png" alt="plot of chunk tab-node-023-get-signatures-1"/></p>

</div>
<div id='tab-node-023-get-signatures-2'>
<pre><code class="r">get_signatures(res, k = 3)
</code></pre>

<p><img src="figure_cola/tab-node-023-get-signatures-2-1.png" alt="plot of chunk tab-node-023-get-signatures-2"/></p>

</div>
<div id='tab-node-023-get-signatures-3'>
<pre><code class="r">get_signatures(res, k = 4)
</code></pre>

<p><img src="figure_cola/tab-node-023-get-signatures-3-1.png" alt="plot of chunk tab-node-023-get-signatures-3"/></p>

</div>
<div id='tab-node-023-get-signatures-4'>
<pre><code class="r">get_signatures(res, k = 5)
</code></pre>

<p><img src="figure_cola/tab-node-023-get-signatures-4-1.png" alt="plot of chunk tab-node-023-get-signatures-4"/></p>

</div>
<div id='tab-node-023-get-signatures-5'>
<pre><code class="r">get_signatures(res, k = 6)
</code></pre>

<p><img src="figure_cola/tab-node-023-get-signatures-5-1.png" alt="plot of chunk tab-node-023-get-signatures-5"/></p>

</div>
<div id='tab-node-023-get-signatures-6'>
<pre><code class="r">get_signatures(res, k = 7)
</code></pre>

<p><img src="figure_cola/tab-node-023-get-signatures-6-1.png" alt="plot of chunk tab-node-023-get-signatures-6"/></p>

</div>
<div id='tab-node-023-get-signatures-7'>
<pre><code class="r">get_signatures(res, k = 8)
</code></pre>

<p><img src="figure_cola/tab-node-023-get-signatures-7-1.png" alt="plot of chunk tab-node-023-get-signatures-7"/></p>

</div>
</div>



Compare the overlap of signatures from different k:

```r
compare_signatures(res)
```

![plot of chunk node-023-signature_compare](figure_cola/node-023-signature_compare-1.png)

`get_signature()` returns a data frame invisibly. To get the list of signatures, the function
call should be assigned to a variable explicitly. In following code, if `plot` argument is set
to `FALSE`, no heatmap is plotted while only the differential analysis is performed.

```r
# code only for demonstration
tb = get_signature(res, k = ..., plot = FALSE)
```

An example of the output of `tb` is:

```
#>   which_row         fdr    mean_1    mean_2 scaled_mean_1 scaled_mean_2 km
#> 1        38 0.042760348  8.373488  9.131774    -0.5533452     0.5164555  1
#> 2        40 0.018707592  7.106213  8.469186    -0.6173731     0.5762149  1
#> 3        55 0.019134737 10.221463 11.207825    -0.6159697     0.5749050  1
#> 4        59 0.006059896  5.921854  7.869574    -0.6899429     0.6439467  1
#> 5        60 0.018055526  8.928898 10.211722    -0.6204761     0.5791110  1
#> 6        98 0.009384629 15.714769 14.887706     0.6635654    -0.6193277  2
...
```

The columns in `tb` are:

1. `which_row`: row indices corresponding to the input matrix.
2. `fdr`: FDR for the differential test. 
3. `mean_x`: The mean value in group x.
4. `scaled_mean_x`: The mean value in group x after rows are scaled.
5. `km`: Row groups if k-means clustering is applied to rows (which is done by automatically selecting number of clusters).

If there are too many signatures, `top_signatures = ...` can be set to only show the 
signatures with the highest FDRs:

```r
# code only for demonstration
# e.g. to show the top 500 most significant rows
tb = get_signature(res, k = ..., top_signatures = 500)
```

If the signatures are defined as these which are uniquely high in current group, `diff_method` argument
can be set to `"uniquely_high_in_one_group"`:

```r
# code only for demonstration
tb = get_signature(res, k = ..., diff_method = "uniquely_high_in_one_group")
```




UMAP plot which shows how samples are separated.


<script>
$( function() {
	$( '#tabs-node-023-dimension-reduction' ).tabs();
} );
</script>
<div id='tabs-node-023-dimension-reduction'>
<ul>
<li><a href='#tab-node-023-dimension-reduction-1'>k = 2</a></li>
<li><a href='#tab-node-023-dimension-reduction-2'>k = 3</a></li>
<li><a href='#tab-node-023-dimension-reduction-3'>k = 4</a></li>
<li><a href='#tab-node-023-dimension-reduction-4'>k = 5</a></li>
<li><a href='#tab-node-023-dimension-reduction-5'>k = 6</a></li>
<li><a href='#tab-node-023-dimension-reduction-6'>k = 7</a></li>
<li><a href='#tab-node-023-dimension-reduction-7'>k = 8</a></li>
</ul>
<div id='tab-node-023-dimension-reduction-1'>
<pre><code class="r">dimension_reduction(res, k = 2, method = &quot;UMAP&quot;)
</code></pre>

<p><img src="figure_cola/tab-node-023-dimension-reduction-1-1.png" alt="plot of chunk tab-node-023-dimension-reduction-1"/></p>

</div>
<div id='tab-node-023-dimension-reduction-2'>
<pre><code class="r">dimension_reduction(res, k = 3, method = &quot;UMAP&quot;)
</code></pre>

<p><img src="figure_cola/tab-node-023-dimension-reduction-2-1.png" alt="plot of chunk tab-node-023-dimension-reduction-2"/></p>

</div>
<div id='tab-node-023-dimension-reduction-3'>
<pre><code class="r">dimension_reduction(res, k = 4, method = &quot;UMAP&quot;)
</code></pre>

<p><img src="figure_cola/tab-node-023-dimension-reduction-3-1.png" alt="plot of chunk tab-node-023-dimension-reduction-3"/></p>

</div>
<div id='tab-node-023-dimension-reduction-4'>
<pre><code class="r">dimension_reduction(res, k = 5, method = &quot;UMAP&quot;)
</code></pre>

<p><img src="figure_cola/tab-node-023-dimension-reduction-4-1.png" alt="plot of chunk tab-node-023-dimension-reduction-4"/></p>

</div>
<div id='tab-node-023-dimension-reduction-5'>
<pre><code class="r">dimension_reduction(res, k = 6, method = &quot;UMAP&quot;)
</code></pre>

<p><img src="figure_cola/tab-node-023-dimension-reduction-5-1.png" alt="plot of chunk tab-node-023-dimension-reduction-5"/></p>

</div>
<div id='tab-node-023-dimension-reduction-6'>
<pre><code class="r">dimension_reduction(res, k = 7, method = &quot;UMAP&quot;)
</code></pre>

<p><img src="figure_cola/tab-node-023-dimension-reduction-6-1.png" alt="plot of chunk tab-node-023-dimension-reduction-6"/></p>

</div>
<div id='tab-node-023-dimension-reduction-7'>
<pre><code class="r">dimension_reduction(res, k = 8, method = &quot;UMAP&quot;)
</code></pre>

<p><img src="figure_cola/tab-node-023-dimension-reduction-7-1.png" alt="plot of chunk tab-node-023-dimension-reduction-7"/></p>

</div>
</div>



Following heatmap shows how subgroups are split when increasing `k`:

```r
collect_classes(res)
```

![plot of chunk node-023-collect-classes](figure_cola/node-023-collect-classes-1.png)



If matrix rows can be associated to genes, consider to use `functional_enrichment(res,
...)` to perform function enrichment for the signature genes. See [this vignette](https://jokergoo.github.io/cola_vignettes/functional_enrichment.html) for more detailed explanations.


 

---------------------------------------------------




### Node024


Parent node: [Node02](#Node02).
Child nodes: 
                Node0121-leaf
        ,
                Node0122-leaf
        ,
                Node0123-leaf
        ,
                Node0221-leaf
        ,
                Node0222-leaf
        ,
                Node0223-leaf
        ,
                Node0224-leaf
        ,
                Node0231-leaf
        ,
                Node0232-leaf
        ,
                Node0233-leaf
        ,
                Node0234-leaf
        ,
                Node0241-leaf
        ,
                Node0242-leaf
        ,
                Node0243-leaf
        .







The object with results only for a single top-value method and a single partitioning method 
can be extracted as:

```r
res = res_rh["024"]
```

A summary of `res` and all the functions that can be applied to it:

```r
res
```

```
#> A 'ConsensusPartition' object with k = 2, 3, 4, 5, 6, 7, 8.
#>   On a matrix with 30000 rows and 14 columns.
#>   Top rows (1000) are extracted by 'ATC' method.
#>   Subgroups are detected by 'skmeans' method.
#>   Performed in total 350 partitions by row resampling.
#>   Best k for subgroups seems to be 3.
#> 
#> Following methods can be applied to this 'ConsensusPartition' object:
#>  [1] "cola_report"             "collect_classes"         "collect_plots"          
#>  [4] "collect_stats"           "colnames"                "compare_partitions"     
#>  [7] "compare_signatures"      "consensus_heatmap"       "dimension_reduction"    
#> [10] "functional_enrichment"   "get_anno_col"            "get_anno"               
#> [13] "get_classes"             "get_consensus"           "get_matrix"             
#> [16] "get_membership"          "get_param"               "get_signatures"         
#> [19] "get_stats"               "is_best_k"               "is_stable_k"            
#> [22] "membership_heatmap"      "ncol"                    "nrow"                   
#> [25] "plot_ecdf"               "predict_classes"         "rownames"               
#> [28] "select_partition_number" "show"                    "suggest_best_k"         
#> [31] "test_to_known_factors"   "top_rows_heatmap"
```

`collect_plots()` function collects all the plots made from `res` for all `k` (number of subgroups)
into one single page to provide an easy and fast comparison between different `k`.

```r
collect_plots(res)
```

![plot of chunk node-024-collect-plots](figure_cola/node-024-collect-plots-1.png)

The plots are:

- The first row: a plot of the eCDF (empirical cumulative distribution
  function) curves of the consensus matrix for each `k` and the heatmap of
  predicted classes for each `k`.
- The second row: heatmaps of the consensus matrix for each `k`.
- The third row: heatmaps of the membership matrix for each `k`.
- The fouth row: heatmaps of the signatures for each `k`.

All the plots in panels can be made by individual functions and they are
plotted later in this section.

`select_partition_number()` produces several plots showing different
statistics for choosing "optimized" `k`. There are following statistics:

- eCDF curves of the consensus matrix for each `k`;
- 1-PAC. [The PAC score](https://en.wikipedia.org/wiki/Consensus_clustering#Over-interpretation_potential_of_consensus_clustering)
  measures the proportion of the ambiguous subgrouping.
- Mean silhouette score.
- Concordance. The mean probability of fiting the consensus subgroup labels in all
  partitions.
- Area increased. Denote $A_k$ as the area under the eCDF curve for current
  `k`, the area increased is defined as $A_k - A_{k-1}$.
- Rand index. The percent of pairs of samples that are both in a same cluster
  or both are not in a same cluster in the partition of k and k-1.
- Jaccard index. The ratio of pairs of samples are both in a same cluster in
  the partition of k and k-1 and the pairs of samples are both in a same
  cluster in the partition k or k-1.

The detailed explanations of these statistics can be found in [the _cola_
vignette](https://jokergoo.github.io/cola_vignettes/cola.html#toc_13).

Generally speaking, higher 1-PAC score, higher mean silhouette score or higher
concordance corresponds to better partition. Rand index and Jaccard index
measure how similar the current partition is compared to partition with `k-1`.
If they are too similar, we won't accept `k` is better than `k-1`.

```r
select_partition_number(res)
```

![plot of chunk node-024-select-partition-number](figure_cola/node-024-select-partition-number-1.png)

The numeric values for all these statistics can be obtained by `get_stats()`.

```r
get_stats(res)
```

```
#>   k 1-PAC mean_silhouette concordance area_increased  Rand Jaccard
#> 2 2 1.000           1.000       1.000         0.4950 0.505   0.505
#> 3 3 1.000           0.977       0.987         0.4366 0.780   0.565
#> 4 4 0.736           0.754       0.899         0.0630 0.967   0.885
#> 5 5 0.703           0.479       0.797         0.0799 0.901   0.625
#> 6 6 0.725           0.549       0.839         0.0458 0.923   0.611
#> 7 7 0.780           0.486       0.834         0.0407 0.967   0.769
#> 8 8 0.868           0.498       0.877         0.0249 0.978   0.800
```

`suggest_best_k()` suggests the best $k$ based on these statistics. The rules are as follows:

- All $k$ with Jaccard index larger than 0.95 are removed because increasing
  $k$ does not provide enough extra information. If all $k$ are removed, it is
  marked as no subgroup is detected.
- For all $k$ with 1-PAC score larger than 0.9, the maximal $k$ is taken as
  the best $k$, and other $k$ are marked as optional $k$.
- If it does not fit the second rule. The $k$ with the maximal vote of the
  highest 1-PAC score, highest mean silhouette, and highest concordance is
  taken as the best $k$.

```r
suggest_best_k(res)
```

```
#> [1] 3
#> attr(,"optional")
#> [1] 2
```

There is also optional best $k$ = 2 that is worth to check.

Following is the table of the partitions (You need to click the **show/hide
code output** link to see it). The membership matrix (columns with name `p*`)
is inferred by
[`clue::cl_consensus()`](https://www.rdocumentation.org/link/cl_consensus?package=clue)
function with the `SE` method. Basically the value in the membership matrix
represents the probability to belong to a certain group. The finall subgroup
label for an item is determined with the group with highest probability it
belongs to.

In `get_classes()` function, the entropy is calculated from the membership
matrix and the silhouette score is calculated from the consensus matrix.



<script>
$( function() {
	$( '#tabs-node-024-get-classes' ).tabs();
} );
</script>
<div id='tabs-node-024-get-classes'>
<ul>
<li><a href='#tab-node-024-get-classes-1'>k = 2</a></li>
<li><a href='#tab-node-024-get-classes-2'>k = 3</a></li>
<li><a href='#tab-node-024-get-classes-3'>k = 4</a></li>
<li><a href='#tab-node-024-get-classes-4'>k = 5</a></li>
<li><a href='#tab-node-024-get-classes-5'>k = 6</a></li>
<li><a href='#tab-node-024-get-classes-6'>k = 7</a></li>
<li><a href='#tab-node-024-get-classes-7'>k = 8</a></li>
</ul>

<div id='tab-node-024-get-classes-1'>
<p><a id='tab-node-024-get-classes-1-a' style='color:#0366d6' href='#'>show/hide code output</a></p>
<pre><code class="r">cbind(get_classes(res, k = 2), get_membership(res, k = 2))
</code></pre>

<pre><code>#&gt;                 class entropy silhouette p1 p2
#&gt; TCGA.W4.A7U4.01     1       0          1  1  0
#&gt; TCGA.2G.AAGO.01     1       0          1  1  0
#&gt; TCGA.2G.AAKM.01     1       0          1  1  0
#&gt; TCGA.2G.AAGA.01     1       0          1  1  0
#&gt; TCGA.2G.AAM2.01     2       0          1  0  1
#&gt; TCGA.VF.A8A8.01     2       0          1  0  1
#&gt; TCGA.2G.AAKL.01     1       0          1  1  0
#&gt; TCGA.SN.A84Y.01     1       0          1  1  0
#&gt; TCGA.2G.AAL7.01     1       0          1  1  0
#&gt; TCGA.2G.AAFN.01     1       0          1  1  0
#&gt; TCGA.2G.AAG7.01     2       0          1  0  1
#&gt; TCGA.XY.A8S2.01     1       0          1  1  0
#&gt; TCGA.2G.AAKD.01     2       0          1  0  1
#&gt; TCGA.2G.AAGW.01     2       0          1  0  1
</code></pre>

<script>
$('#tab-node-024-get-classes-1-a').parent().next().next().hide();
$('#tab-node-024-get-classes-1-a').click(function(){
  $('#tab-node-024-get-classes-1-a').parent().next().next().toggle();
  return(false);
});
</script>
</div>

<div id='tab-node-024-get-classes-2'>
<p><a id='tab-node-024-get-classes-2-a' style='color:#0366d6' href='#'>show/hide code output</a></p>
<pre><code class="r">cbind(get_classes(res, k = 3), get_membership(res, k = 3))
</code></pre>

<pre><code>#&gt;                 class entropy silhouette   p1   p2   p3
#&gt; TCGA.W4.A7U4.01     3  0.0892      0.975 0.02 0.00 0.98
#&gt; TCGA.2G.AAGO.01     3  0.0000      0.980 0.00 0.00 1.00
#&gt; TCGA.2G.AAKM.01     3  0.1529      0.960 0.04 0.00 0.96
#&gt; TCGA.2G.AAGA.01     1  0.0000      0.995 1.00 0.00 0.00
#&gt; TCGA.2G.AAM2.01     2  0.0000      0.974 0.00 1.00 0.00
#&gt; TCGA.VF.A8A8.01     2  0.0000      0.974 0.00 1.00 0.00
#&gt; TCGA.2G.AAKL.01     1  0.0000      0.995 1.00 0.00 0.00
#&gt; TCGA.SN.A84Y.01     1  0.0892      0.978 0.98 0.02 0.00
#&gt; TCGA.2G.AAL7.01     3  0.0000      0.980 0.00 0.00 1.00
#&gt; TCGA.2G.AAFN.01     1  0.0000      0.995 1.00 0.00 0.00
#&gt; TCGA.2G.AAG7.01     2  0.0000      0.974 0.00 1.00 0.00
#&gt; TCGA.XY.A8S2.01     1  0.0000      0.995 1.00 0.00 0.00
#&gt; TCGA.2G.AAKD.01     2  0.2066      0.948 0.06 0.94 0.00
#&gt; TCGA.2G.AAGW.01     2  0.1529      0.962 0.04 0.96 0.00
</code></pre>

<script>
$('#tab-node-024-get-classes-2-a').parent().next().next().hide();
$('#tab-node-024-get-classes-2-a').click(function(){
  $('#tab-node-024-get-classes-2-a').parent().next().next().toggle();
  return(false);
});
</script>
</div>

<div id='tab-node-024-get-classes-3'>
<p><a id='tab-node-024-get-classes-3-a' style='color:#0366d6' href='#'>show/hide code output</a></p>
<pre><code class="r">cbind(get_classes(res, k = 4), get_membership(res, k = 4))
</code></pre>

<pre><code>#&gt;                 class entropy silhouette   p1   p2   p3   p4
#&gt; TCGA.W4.A7U4.01     4  0.3172      0.000 0.00 0.00 0.16 0.84
#&gt; TCGA.2G.AAGO.01     3  0.1211      0.720 0.00 0.00 0.96 0.04
#&gt; TCGA.2G.AAKM.01     3  0.2345      0.682 0.00 0.00 0.90 0.10
#&gt; TCGA.2G.AAGA.01     1  0.1637      0.911 0.94 0.00 0.00 0.06
#&gt; TCGA.2G.AAM2.01     2  0.0000      0.856 0.00 1.00 0.00 0.00
#&gt; TCGA.VF.A8A8.01     2  0.0000      0.856 0.00 1.00 0.00 0.00
#&gt; TCGA.2G.AAKL.01     1  0.2335      0.932 0.92 0.00 0.06 0.02
#&gt; TCGA.SN.A84Y.01     1  0.0707      0.935 0.98 0.00 0.00 0.02
#&gt; TCGA.2G.AAL7.01     3  0.4406      0.472 0.00 0.00 0.70 0.30
#&gt; TCGA.2G.AAFN.01     1  0.0707      0.943 0.98 0.00 0.02 0.00
#&gt; TCGA.2G.AAG7.01     2  0.0000      0.856 0.00 1.00 0.00 0.00
#&gt; TCGA.XY.A8S2.01     1  0.2335      0.932 0.92 0.00 0.06 0.02
#&gt; TCGA.2G.AAKD.01     2  0.6286      0.674 0.20 0.66 0.00 0.14
#&gt; TCGA.2G.AAGW.01     2  0.4894      0.782 0.10 0.78 0.00 0.12
</code></pre>

<script>
$('#tab-node-024-get-classes-3-a').parent().next().next().hide();
$('#tab-node-024-get-classes-3-a').click(function(){
  $('#tab-node-024-get-classes-3-a').parent().next().next().toggle();
  return(false);
});
</script>
</div>

<div id='tab-node-024-get-classes-4'>
<p><a id='tab-node-024-get-classes-4-a' style='color:#0366d6' href='#'>show/hide code output</a></p>
<pre><code class="r">cbind(get_classes(res, k = 5), get_membership(res, k = 5))
</code></pre>

<pre><code>#&gt;                 class entropy silhouette   p1   p2   p3   p4   p5
#&gt; TCGA.W4.A7U4.01     4  0.6054     0.0000 0.00 0.00 0.28 0.56 0.16
#&gt; TCGA.2G.AAGO.01     3  0.3521     0.5924 0.00 0.00 0.82 0.14 0.04
#&gt; TCGA.2G.AAKM.01     3  0.5457     0.2877 0.06 0.00 0.48 0.46 0.00
#&gt; TCGA.2G.AAGA.01     5  0.4829    -0.2258 0.48 0.00 0.00 0.02 0.50
#&gt; TCGA.2G.AAM2.01     2  0.0000     0.8195 0.00 1.00 0.00 0.00 0.00
#&gt; TCGA.VF.A8A8.01     2  0.0000     0.8195 0.00 1.00 0.00 0.00 0.00
#&gt; TCGA.2G.AAKL.01     1  0.2754     0.7393 0.88 0.00 0.00 0.08 0.04
#&gt; TCGA.SN.A84Y.01     1  0.4254     0.6387 0.74 0.00 0.00 0.04 0.22
#&gt; TCGA.2G.AAL7.01     3  0.0000     0.5571 0.00 0.00 1.00 0.00 0.00
#&gt; TCGA.2G.AAFN.01     1  0.2012     0.7986 0.92 0.00 0.00 0.02 0.06
#&gt; TCGA.2G.AAG7.01     2  0.0000     0.8195 0.00 1.00 0.00 0.00 0.00
#&gt; TCGA.XY.A8S2.01     1  0.0609     0.8022 0.98 0.00 0.00 0.02 0.00
#&gt; TCGA.2G.AAKD.01     5  0.3895    -0.0987 0.00 0.32 0.00 0.00 0.68
#&gt; TCGA.2G.AAGW.01     2  0.5267     0.1587 0.02 0.56 0.00 0.02 0.40
</code></pre>

<script>
$('#tab-node-024-get-classes-4-a').parent().next().next().hide();
$('#tab-node-024-get-classes-4-a').click(function(){
  $('#tab-node-024-get-classes-4-a').parent().next().next().toggle();
  return(false);
});
</script>
</div>

<div id='tab-node-024-get-classes-5'>
<p><a id='tab-node-024-get-classes-5-a' style='color:#0366d6' href='#'>show/hide code output</a></p>
<pre><code class="r">cbind(get_classes(res, k = 6), get_membership(res, k = 6))
</code></pre>

<pre><code>#&gt;                 class entropy silhouette   p1   p2   p3   p4   p5   p6
#&gt; TCGA.W4.A7U4.01     4  0.0000     0.0000 0.00 0.00 0.00 1.00 0.00 0.00
#&gt; TCGA.2G.AAGO.01     3  0.0000     0.7858 0.00 0.00 1.00 0.00 0.00 0.00
#&gt; TCGA.2G.AAKM.01     6  0.4574     0.0000 0.02 0.00 0.26 0.04 0.00 0.68
#&gt; TCGA.2G.AAGA.01     5  0.5626    -0.0526 0.34 0.00 0.00 0.02 0.54 0.10
#&gt; TCGA.2G.AAM2.01     2  0.0000     0.9877 0.00 1.00 0.00 0.00 0.00 0.00
#&gt; TCGA.VF.A8A8.01     2  0.0547     0.9751 0.00 0.98 0.00 0.00 0.02 0.00
#&gt; TCGA.2G.AAKL.01     1  0.3572     0.6596 0.82 0.00 0.00 0.02 0.06 0.10
#&gt; TCGA.SN.A84Y.01     1  0.5490     0.3601 0.56 0.00 0.00 0.00 0.26 0.18
#&gt; TCGA.2G.AAL7.01     3  0.3111     0.7912 0.02 0.00 0.84 0.12 0.02 0.00
#&gt; TCGA.2G.AAFN.01     1  0.2190     0.7170 0.90 0.00 0.00 0.00 0.04 0.06
#&gt; TCGA.2G.AAG7.01     2  0.0000     0.9877 0.00 1.00 0.00 0.00 0.00 0.00
#&gt; TCGA.XY.A8S2.01     1  0.0547     0.7312 0.98 0.00 0.00 0.00 0.02 0.00
#&gt; TCGA.2G.AAKD.01     5  0.2048     0.4741 0.00 0.12 0.00 0.00 0.88 0.00
#&gt; TCGA.2G.AAGW.01     5  0.5324     0.2752 0.00 0.34 0.00 0.00 0.54 0.12
</code></pre>

<script>
$('#tab-node-024-get-classes-5-a').parent().next().next().hide();
$('#tab-node-024-get-classes-5-a').click(function(){
  $('#tab-node-024-get-classes-5-a').parent().next().next().toggle();
  return(false);
});
</script>
</div>

<div id='tab-node-024-get-classes-6'>
<p><a id='tab-node-024-get-classes-6-a' style='color:#0366d6' href='#'>show/hide code output</a></p>
<pre><code class="r">cbind(get_classes(res, k = 7), get_membership(res, k = 7))
</code></pre>

<pre><code>#&gt;                 class entropy silhouette   p1   p2   p3   p4   p5   p6   p7
#&gt; TCGA.W4.A7U4.01     4  0.0000      0.000 0.00 0.00 0.00 1.00 0.00 0.00 0.00
#&gt; TCGA.2G.AAGO.01     3  0.3315      0.592 0.00 0.00 0.82 0.00 0.02 0.08 0.08
#&gt; TCGA.2G.AAKM.01     6  0.2512      0.000 0.00 0.00 0.10 0.04 0.00 0.86 0.00
#&gt; TCGA.2G.AAGA.01     5  0.5779      0.246 0.12 0.00 0.00 0.00 0.52 0.06 0.30
#&gt; TCGA.2G.AAM2.01     2  0.0000      1.000 0.00 1.00 0.00 0.00 0.00 0.00 0.00
#&gt; TCGA.VF.A8A8.01     2  0.0000      1.000 0.00 1.00 0.00 0.00 0.00 0.00 0.00
#&gt; TCGA.2G.AAKL.01     1  0.4785      0.445 0.68 0.00 0.00 0.04 0.02 0.04 0.22
#&gt; TCGA.SN.A84Y.01     7  0.3909      0.000 0.40 0.00 0.00 0.00 0.02 0.00 0.58
#&gt; TCGA.2G.AAL7.01     3  0.2912      0.609 0.00 0.00 0.82 0.14 0.00 0.04 0.00
#&gt; TCGA.2G.AAFN.01     1  0.1433      0.571 0.92 0.00 0.00 0.00 0.00 0.00 0.08
#&gt; TCGA.2G.AAG7.01     2  0.0000      1.000 0.00 1.00 0.00 0.00 0.00 0.00 0.00
#&gt; TCGA.XY.A8S2.01     1  0.0000      0.635 1.00 0.00 0.00 0.00 0.00 0.00 0.00
#&gt; TCGA.2G.AAKD.01     5  0.0504      0.462 0.00 0.02 0.00 0.00 0.98 0.00 0.00
#&gt; TCGA.2G.AAGW.01     5  0.6035      0.251 0.00 0.18 0.00 0.00 0.50 0.06 0.26
</code></pre>

<script>
$('#tab-node-024-get-classes-6-a').parent().next().next().hide();
$('#tab-node-024-get-classes-6-a').click(function(){
  $('#tab-node-024-get-classes-6-a').parent().next().next().toggle();
  return(false);
});
</script>
</div>

<div id='tab-node-024-get-classes-7'>
<p><a id='tab-node-024-get-classes-7-a' style='color:#0366d6' href='#'>show/hide code output</a></p>
<pre><code class="r">cbind(get_classes(res, k = 8), get_membership(res, k = 8))
</code></pre>

<pre><code>#&gt;                 class entropy silhouette   p1   p2   p3   p4   p5   p6   p7   p8
#&gt; TCGA.W4.A7U4.01     4  0.0000      0.000 0.00 0.00 0.00 1.00 0.00 0.00 0.00 0.00
#&gt; TCGA.2G.AAGO.01     3  0.0808      0.567 0.00 0.00 0.96 0.00 0.00 0.04 0.00 0.00
#&gt; TCGA.2G.AAKM.01     6  0.0000      0.000 0.00 0.00 0.00 0.00 0.00 1.00 0.00 0.00
#&gt; TCGA.2G.AAGA.01     8  0.2623      0.000 0.10 0.00 0.00 0.00 0.06 0.00 0.00 0.84
#&gt; TCGA.2G.AAM2.01     2  0.0000      0.990 0.00 1.00 0.00 0.00 0.00 0.00 0.00 0.00
#&gt; TCGA.VF.A8A8.01     2  0.0471      0.980 0.00 0.98 0.00 0.00 0.02 0.00 0.00 0.00
#&gt; TCGA.2G.AAKL.01     1  0.3444      0.641 0.78 0.00 0.00 0.02 0.00 0.00 0.14 0.06
#&gt; TCGA.SN.A84Y.01     7  0.3744      0.000 0.18 0.00 0.00 0.00 0.02 0.00 0.74 0.06
#&gt; TCGA.2G.AAL7.01     3  0.5897      0.534 0.02 0.00 0.60 0.12 0.02 0.00 0.12 0.12
#&gt; TCGA.2G.AAFN.01     1  0.3036      0.551 0.78 0.00 0.00 0.00 0.00 0.00 0.18 0.04
#&gt; TCGA.2G.AAG7.01     2  0.0000      0.990 0.00 1.00 0.00 0.00 0.00 0.00 0.00 0.00
#&gt; TCGA.XY.A8S2.01     1  0.0000      0.718 1.00 0.00 0.00 0.00 0.00 0.00 0.00 0.00
#&gt; TCGA.2G.AAKD.01     5  0.3015      0.448 0.00 0.00 0.00 0.00 0.68 0.00 0.00 0.32
#&gt; TCGA.2G.AAGW.01     5  0.1607      0.554 0.00 0.04 0.00 0.00 0.92 0.00 0.04 0.00
</code></pre>

<script>
$('#tab-node-024-get-classes-7-a').parent().next().next().hide();
$('#tab-node-024-get-classes-7-a').click(function(){
  $('#tab-node-024-get-classes-7-a').parent().next().next().toggle();
  return(false);
});
</script>
</div>
</div>

Heatmaps for the consensus matrix. It visualizes the probability of two
samples to be in a same group.




<script>
$( function() {
	$( '#tabs-node-024-consensus-heatmap' ).tabs();
} );
</script>
<div id='tabs-node-024-consensus-heatmap'>
<ul>
<li><a href='#tab-node-024-consensus-heatmap-1'>k = 2</a></li>
<li><a href='#tab-node-024-consensus-heatmap-2'>k = 3</a></li>
<li><a href='#tab-node-024-consensus-heatmap-3'>k = 4</a></li>
<li><a href='#tab-node-024-consensus-heatmap-4'>k = 5</a></li>
<li><a href='#tab-node-024-consensus-heatmap-5'>k = 6</a></li>
<li><a href='#tab-node-024-consensus-heatmap-6'>k = 7</a></li>
<li><a href='#tab-node-024-consensus-heatmap-7'>k = 8</a></li>
</ul>
<div id='tab-node-024-consensus-heatmap-1'>
<pre><code class="r">consensus_heatmap(res, k = 2)
</code></pre>

<p><img src="figure_cola/tab-node-024-consensus-heatmap-1-1.png" alt="plot of chunk tab-node-024-consensus-heatmap-1"/></p>

</div>
<div id='tab-node-024-consensus-heatmap-2'>
<pre><code class="r">consensus_heatmap(res, k = 3)
</code></pre>

<p><img src="figure_cola/tab-node-024-consensus-heatmap-2-1.png" alt="plot of chunk tab-node-024-consensus-heatmap-2"/></p>

</div>
<div id='tab-node-024-consensus-heatmap-3'>
<pre><code class="r">consensus_heatmap(res, k = 4)
</code></pre>

<p><img src="figure_cola/tab-node-024-consensus-heatmap-3-1.png" alt="plot of chunk tab-node-024-consensus-heatmap-3"/></p>

</div>
<div id='tab-node-024-consensus-heatmap-4'>
<pre><code class="r">consensus_heatmap(res, k = 5)
</code></pre>

<p><img src="figure_cola/tab-node-024-consensus-heatmap-4-1.png" alt="plot of chunk tab-node-024-consensus-heatmap-4"/></p>

</div>
<div id='tab-node-024-consensus-heatmap-5'>
<pre><code class="r">consensus_heatmap(res, k = 6)
</code></pre>

<p><img src="figure_cola/tab-node-024-consensus-heatmap-5-1.png" alt="plot of chunk tab-node-024-consensus-heatmap-5"/></p>

</div>
<div id='tab-node-024-consensus-heatmap-6'>
<pre><code class="r">consensus_heatmap(res, k = 7)
</code></pre>

<p><img src="figure_cola/tab-node-024-consensus-heatmap-6-1.png" alt="plot of chunk tab-node-024-consensus-heatmap-6"/></p>

</div>
<div id='tab-node-024-consensus-heatmap-7'>
<pre><code class="r">consensus_heatmap(res, k = 8)
</code></pre>

<p><img src="figure_cola/tab-node-024-consensus-heatmap-7-1.png" alt="plot of chunk tab-node-024-consensus-heatmap-7"/></p>

</div>
</div>

Heatmaps for the membership of samples in all partitions to see how consistent they are:





<script>
$( function() {
	$( '#tabs-node-024-membership-heatmap' ).tabs();
} );
</script>
<div id='tabs-node-024-membership-heatmap'>
<ul>
<li><a href='#tab-node-024-membership-heatmap-1'>k = 2</a></li>
<li><a href='#tab-node-024-membership-heatmap-2'>k = 3</a></li>
<li><a href='#tab-node-024-membership-heatmap-3'>k = 4</a></li>
<li><a href='#tab-node-024-membership-heatmap-4'>k = 5</a></li>
<li><a href='#tab-node-024-membership-heatmap-5'>k = 6</a></li>
<li><a href='#tab-node-024-membership-heatmap-6'>k = 7</a></li>
<li><a href='#tab-node-024-membership-heatmap-7'>k = 8</a></li>
</ul>
<div id='tab-node-024-membership-heatmap-1'>
<pre><code class="r">membership_heatmap(res, k = 2)
</code></pre>

<p><img src="figure_cola/tab-node-024-membership-heatmap-1-1.png" alt="plot of chunk tab-node-024-membership-heatmap-1"/></p>

</div>
<div id='tab-node-024-membership-heatmap-2'>
<pre><code class="r">membership_heatmap(res, k = 3)
</code></pre>

<p><img src="figure_cola/tab-node-024-membership-heatmap-2-1.png" alt="plot of chunk tab-node-024-membership-heatmap-2"/></p>

</div>
<div id='tab-node-024-membership-heatmap-3'>
<pre><code class="r">membership_heatmap(res, k = 4)
</code></pre>

<p><img src="figure_cola/tab-node-024-membership-heatmap-3-1.png" alt="plot of chunk tab-node-024-membership-heatmap-3"/></p>

</div>
<div id='tab-node-024-membership-heatmap-4'>
<pre><code class="r">membership_heatmap(res, k = 5)
</code></pre>

<p><img src="figure_cola/tab-node-024-membership-heatmap-4-1.png" alt="plot of chunk tab-node-024-membership-heatmap-4"/></p>

</div>
<div id='tab-node-024-membership-heatmap-5'>
<pre><code class="r">membership_heatmap(res, k = 6)
</code></pre>

<p><img src="figure_cola/tab-node-024-membership-heatmap-5-1.png" alt="plot of chunk tab-node-024-membership-heatmap-5"/></p>

</div>
<div id='tab-node-024-membership-heatmap-6'>
<pre><code class="r">membership_heatmap(res, k = 7)
</code></pre>

<p><img src="figure_cola/tab-node-024-membership-heatmap-6-1.png" alt="plot of chunk tab-node-024-membership-heatmap-6"/></p>

</div>
<div id='tab-node-024-membership-heatmap-7'>
<pre><code class="r">membership_heatmap(res, k = 8)
</code></pre>

<p><img src="figure_cola/tab-node-024-membership-heatmap-7-1.png" alt="plot of chunk tab-node-024-membership-heatmap-7"/></p>

</div>
</div>

As soon as the classes for columns are determined, the signatures
that are significantly different between subgroups can be looked for. 
Following are the heatmaps for signatures.






<script>
$( function() {
	$( '#tabs-node-024-get-signatures' ).tabs();
} );
</script>
<div id='tabs-node-024-get-signatures'>
<ul>
<li><a href='#tab-node-024-get-signatures-1'>k = 2</a></li>
<li><a href='#tab-node-024-get-signatures-2'>k = 3</a></li>
<li><a href='#tab-node-024-get-signatures-3'>k = 4</a></li>
<li><a href='#tab-node-024-get-signatures-4'>k = 5</a></li>
<li><a href='#tab-node-024-get-signatures-5'>k = 6</a></li>
<li><a href='#tab-node-024-get-signatures-6'>k = 7</a></li>
<li><a href='#tab-node-024-get-signatures-7'>k = 8</a></li>
</ul>
<div id='tab-node-024-get-signatures-1'>
<pre><code class="r">get_signatures(res, k = 2)
</code></pre>

<p><img src="figure_cola/tab-node-024-get-signatures-1-1.png" alt="plot of chunk tab-node-024-get-signatures-1"/></p>

</div>
<div id='tab-node-024-get-signatures-2'>
<pre><code class="r">get_signatures(res, k = 3)
</code></pre>

<p><img src="figure_cola/tab-node-024-get-signatures-2-1.png" alt="plot of chunk tab-node-024-get-signatures-2"/></p>

</div>
<div id='tab-node-024-get-signatures-3'>
<pre><code class="r">get_signatures(res, k = 4)
</code></pre>

<p><img src="figure_cola/tab-node-024-get-signatures-3-1.png" alt="plot of chunk tab-node-024-get-signatures-3"/></p>

</div>
<div id='tab-node-024-get-signatures-4'>
<pre><code class="r">get_signatures(res, k = 5)
</code></pre>

<p><img src="figure_cola/tab-node-024-get-signatures-4-1.png" alt="plot of chunk tab-node-024-get-signatures-4"/></p>

</div>
<div id='tab-node-024-get-signatures-5'>
<pre><code class="r">get_signatures(res, k = 6)
</code></pre>

<p><img src="figure_cola/tab-node-024-get-signatures-5-1.png" alt="plot of chunk tab-node-024-get-signatures-5"/></p>

</div>
<div id='tab-node-024-get-signatures-6'>
<pre><code class="r">get_signatures(res, k = 7)
</code></pre>

<p><img src="figure_cola/tab-node-024-get-signatures-6-1.png" alt="plot of chunk tab-node-024-get-signatures-6"/></p>

</div>
<div id='tab-node-024-get-signatures-7'>
<pre><code class="r">get_signatures(res, k = 8)
</code></pre>

<p><img src="figure_cola/tab-node-024-get-signatures-7-1.png" alt="plot of chunk tab-node-024-get-signatures-7"/></p>

</div>
</div>



Compare the overlap of signatures from different k:

```r
compare_signatures(res)
```

![plot of chunk node-024-signature_compare](figure_cola/node-024-signature_compare-1.png)

`get_signature()` returns a data frame invisibly. To get the list of signatures, the function
call should be assigned to a variable explicitly. In following code, if `plot` argument is set
to `FALSE`, no heatmap is plotted while only the differential analysis is performed.

```r
# code only for demonstration
tb = get_signature(res, k = ..., plot = FALSE)
```

An example of the output of `tb` is:

```
#>   which_row         fdr    mean_1    mean_2 scaled_mean_1 scaled_mean_2 km
#> 1        38 0.042760348  8.373488  9.131774    -0.5533452     0.5164555  1
#> 2        40 0.018707592  7.106213  8.469186    -0.6173731     0.5762149  1
#> 3        55 0.019134737 10.221463 11.207825    -0.6159697     0.5749050  1
#> 4        59 0.006059896  5.921854  7.869574    -0.6899429     0.6439467  1
#> 5        60 0.018055526  8.928898 10.211722    -0.6204761     0.5791110  1
#> 6        98 0.009384629 15.714769 14.887706     0.6635654    -0.6193277  2
...
```

The columns in `tb` are:

1. `which_row`: row indices corresponding to the input matrix.
2. `fdr`: FDR for the differential test. 
3. `mean_x`: The mean value in group x.
4. `scaled_mean_x`: The mean value in group x after rows are scaled.
5. `km`: Row groups if k-means clustering is applied to rows (which is done by automatically selecting number of clusters).

If there are too many signatures, `top_signatures = ...` can be set to only show the 
signatures with the highest FDRs:

```r
# code only for demonstration
# e.g. to show the top 500 most significant rows
tb = get_signature(res, k = ..., top_signatures = 500)
```

If the signatures are defined as these which are uniquely high in current group, `diff_method` argument
can be set to `"uniquely_high_in_one_group"`:

```r
# code only for demonstration
tb = get_signature(res, k = ..., diff_method = "uniquely_high_in_one_group")
```




UMAP plot which shows how samples are separated.


<script>
$( function() {
	$( '#tabs-node-024-dimension-reduction' ).tabs();
} );
</script>
<div id='tabs-node-024-dimension-reduction'>
<ul>
<li><a href='#tab-node-024-dimension-reduction-1'>k = 2</a></li>
<li><a href='#tab-node-024-dimension-reduction-2'>k = 3</a></li>
<li><a href='#tab-node-024-dimension-reduction-3'>k = 4</a></li>
<li><a href='#tab-node-024-dimension-reduction-4'>k = 5</a></li>
<li><a href='#tab-node-024-dimension-reduction-5'>k = 6</a></li>
<li><a href='#tab-node-024-dimension-reduction-6'>k = 7</a></li>
<li><a href='#tab-node-024-dimension-reduction-7'>k = 8</a></li>
</ul>
<div id='tab-node-024-dimension-reduction-1'>
<pre><code class="r">dimension_reduction(res, k = 2, method = &quot;UMAP&quot;)
</code></pre>

<p><img src="figure_cola/tab-node-024-dimension-reduction-1-1.png" alt="plot of chunk tab-node-024-dimension-reduction-1"/></p>

</div>
<div id='tab-node-024-dimension-reduction-2'>
<pre><code class="r">dimension_reduction(res, k = 3, method = &quot;UMAP&quot;)
</code></pre>

<p><img src="figure_cola/tab-node-024-dimension-reduction-2-1.png" alt="plot of chunk tab-node-024-dimension-reduction-2"/></p>

</div>
<div id='tab-node-024-dimension-reduction-3'>
<pre><code class="r">dimension_reduction(res, k = 4, method = &quot;UMAP&quot;)
</code></pre>

<p><img src="figure_cola/tab-node-024-dimension-reduction-3-1.png" alt="plot of chunk tab-node-024-dimension-reduction-3"/></p>

</div>
<div id='tab-node-024-dimension-reduction-4'>
<pre><code class="r">dimension_reduction(res, k = 5, method = &quot;UMAP&quot;)
</code></pre>

<p><img src="figure_cola/tab-node-024-dimension-reduction-4-1.png" alt="plot of chunk tab-node-024-dimension-reduction-4"/></p>

</div>
<div id='tab-node-024-dimension-reduction-5'>
<pre><code class="r">dimension_reduction(res, k = 6, method = &quot;UMAP&quot;)
</code></pre>

<p><img src="figure_cola/tab-node-024-dimension-reduction-5-1.png" alt="plot of chunk tab-node-024-dimension-reduction-5"/></p>

</div>
<div id='tab-node-024-dimension-reduction-6'>
<pre><code class="r">dimension_reduction(res, k = 7, method = &quot;UMAP&quot;)
</code></pre>

<p><img src="figure_cola/tab-node-024-dimension-reduction-6-1.png" alt="plot of chunk tab-node-024-dimension-reduction-6"/></p>

</div>
<div id='tab-node-024-dimension-reduction-7'>
<pre><code class="r">dimension_reduction(res, k = 8, method = &quot;UMAP&quot;)
</code></pre>

<p><img src="figure_cola/tab-node-024-dimension-reduction-7-1.png" alt="plot of chunk tab-node-024-dimension-reduction-7"/></p>

</div>
</div>



Following heatmap shows how subgroups are split when increasing `k`:

```r
collect_classes(res)
```

![plot of chunk node-024-collect-classes](figure_cola/node-024-collect-classes-1.png)



If matrix rows can be associated to genes, consider to use `functional_enrichment(res,
...)` to perform function enrichment for the signature genes. See [this vignette](https://jokergoo.github.io/cola_vignettes/functional_enrichment.html) for more detailed explanations.


 

---------------------------------------------------




### Node03


Parent node: [Node0](#Node0).
Child nodes: 
                Node011-leaf
        ,
                [Node012](#Node012)
        ,
                Node013-leaf
        ,
                Node021-leaf
        ,
                [Node022](#Node022)
        ,
                [Node023](#Node023)
        ,
                [Node024](#Node024)
        ,
                Node031-leaf
        ,
                Node032-leaf
        ,
                Node033-leaf
        ,
                Node034-leaf
        .







The object with results only for a single top-value method and a single partitioning method 
can be extracted as:

```r
res = res_rh["03"]
```

A summary of `res` and all the functions that can be applied to it:

```r
res
```

```
#> A 'ConsensusPartition' object with k = 2, 3, 4, 5, 6, 7, 8.
#>   On a matrix with 30000 rows and 23 columns.
#>   Top rows (1000) are extracted by 'ATC' method.
#>   Subgroups are detected by 'kmeans' method.
#>   Performed in total 350 partitions by row resampling.
#>   Best k for subgroups seems to be 4.
#> 
#> Following methods can be applied to this 'ConsensusPartition' object:
#>  [1] "cola_report"             "collect_classes"         "collect_plots"          
#>  [4] "collect_stats"           "colnames"                "compare_partitions"     
#>  [7] "compare_signatures"      "consensus_heatmap"       "dimension_reduction"    
#> [10] "functional_enrichment"   "get_anno_col"            "get_anno"               
#> [13] "get_classes"             "get_consensus"           "get_matrix"             
#> [16] "get_membership"          "get_param"               "get_signatures"         
#> [19] "get_stats"               "is_best_k"               "is_stable_k"            
#> [22] "membership_heatmap"      "ncol"                    "nrow"                   
#> [25] "plot_ecdf"               "predict_classes"         "rownames"               
#> [28] "select_partition_number" "show"                    "suggest_best_k"         
#> [31] "test_to_known_factors"   "top_rows_heatmap"
```

`collect_plots()` function collects all the plots made from `res` for all `k` (number of subgroups)
into one single page to provide an easy and fast comparison between different `k`.

```r
collect_plots(res)
```

![plot of chunk node-03-collect-plots](figure_cola/node-03-collect-plots-1.png)

The plots are:

- The first row: a plot of the eCDF (empirical cumulative distribution
  function) curves of the consensus matrix for each `k` and the heatmap of
  predicted classes for each `k`.
- The second row: heatmaps of the consensus matrix for each `k`.
- The third row: heatmaps of the membership matrix for each `k`.
- The fouth row: heatmaps of the signatures for each `k`.

All the plots in panels can be made by individual functions and they are
plotted later in this section.

`select_partition_number()` produces several plots showing different
statistics for choosing "optimized" `k`. There are following statistics:

- eCDF curves of the consensus matrix for each `k`;
- 1-PAC. [The PAC score](https://en.wikipedia.org/wiki/Consensus_clustering#Over-interpretation_potential_of_consensus_clustering)
  measures the proportion of the ambiguous subgrouping.
- Mean silhouette score.
- Concordance. The mean probability of fiting the consensus subgroup labels in all
  partitions.
- Area increased. Denote $A_k$ as the area under the eCDF curve for current
  `k`, the area increased is defined as $A_k - A_{k-1}$.
- Rand index. The percent of pairs of samples that are both in a same cluster
  or both are not in a same cluster in the partition of k and k-1.
- Jaccard index. The ratio of pairs of samples are both in a same cluster in
  the partition of k and k-1 and the pairs of samples are both in a same
  cluster in the partition k or k-1.

The detailed explanations of these statistics can be found in [the _cola_
vignette](https://jokergoo.github.io/cola_vignettes/cola.html#toc_13).

Generally speaking, higher 1-PAC score, higher mean silhouette score or higher
concordance corresponds to better partition. Rand index and Jaccard index
measure how similar the current partition is compared to partition with `k-1`.
If they are too similar, we won't accept `k` is better than `k-1`.

```r
select_partition_number(res)
```

![plot of chunk node-03-select-partition-number](figure_cola/node-03-select-partition-number-1.png)

The numeric values for all these statistics can be obtained by `get_stats()`.

```r
get_stats(res)
```

```
#>   k 1-PAC mean_silhouette concordance area_increased  Rand Jaccard
#> 2 2 1.000           1.000       1.000         0.5143 0.486   0.486
#> 3 3 1.000           0.975       0.987         0.3371 0.727   0.489
#> 4 4 0.943           0.963       0.963         0.0873 0.905   0.707
#> 5 5 0.900           0.874       0.909         0.0458 0.953   0.810
#> 6 6 0.924           0.848       0.926         0.0422 0.976   0.885
#> 7 7 0.834           0.695       0.878         0.0254 0.996   0.978
#> 8 8 0.870           0.685       0.849         0.0216 0.976   0.867
```

`suggest_best_k()` suggests the best $k$ based on these statistics. The rules are as follows:

- All $k$ with Jaccard index larger than 0.95 are removed because increasing
  $k$ does not provide enough extra information. If all $k$ are removed, it is
  marked as no subgroup is detected.
- For all $k$ with 1-PAC score larger than 0.9, the maximal $k$ is taken as
  the best $k$, and other $k$ are marked as optional $k$.
- If it does not fit the second rule. The $k$ with the maximal vote of the
  highest 1-PAC score, highest mean silhouette, and highest concordance is
  taken as the best $k$.

```r
suggest_best_k(res)
```

```
#> [1] 4
#> attr(,"optional")
#> [1] 2 3
```

There is also optional best $k$ = 2 3 that is worth to check.

Following is the table of the partitions (You need to click the **show/hide
code output** link to see it). The membership matrix (columns with name `p*`)
is inferred by
[`clue::cl_consensus()`](https://www.rdocumentation.org/link/cl_consensus?package=clue)
function with the `SE` method. Basically the value in the membership matrix
represents the probability to belong to a certain group. The finall subgroup
label for an item is determined with the group with highest probability it
belongs to.

In `get_classes()` function, the entropy is calculated from the membership
matrix and the silhouette score is calculated from the consensus matrix.



<script>
$( function() {
	$( '#tabs-node-03-get-classes' ).tabs();
} );
</script>
<div id='tabs-node-03-get-classes'>
<ul>
<li><a href='#tab-node-03-get-classes-1'>k = 2</a></li>
<li><a href='#tab-node-03-get-classes-2'>k = 3</a></li>
<li><a href='#tab-node-03-get-classes-3'>k = 4</a></li>
<li><a href='#tab-node-03-get-classes-4'>k = 5</a></li>
<li><a href='#tab-node-03-get-classes-5'>k = 6</a></li>
<li><a href='#tab-node-03-get-classes-6'>k = 7</a></li>
<li><a href='#tab-node-03-get-classes-7'>k = 8</a></li>
</ul>

<div id='tab-node-03-get-classes-1'>
<p><a id='tab-node-03-get-classes-1-a' style='color:#0366d6' href='#'>show/hide code output</a></p>
<pre><code class="r">cbind(get_classes(res, k = 2), get_membership(res, k = 2))
</code></pre>

<pre><code>#&gt;                 class entropy silhouette p1 p2
#&gt; TCGA.XE.AANV.01     2       0          1  0  1
#&gt; TCGA.2G.AAHA.01     2       0          1  0  1
#&gt; TCGA.WZ.A7V3.01     2       0          1  0  1
#&gt; TCGA.XE.A8H5.01     1       0          1  1  0
#&gt; TCGA.SO.A8JP.01     1       0          1  1  0
#&gt; TCGA.XE.AAOL.01     1       0          1  1  0
#&gt; TCGA.2G.AAHT.01     2       0          1  0  1
#&gt; TCGA.YU.A90W.01     2       0          1  0  1
#&gt; TCGA.S6.A8JW.01     1       0          1  1  0
#&gt; TCGA.2G.AAEW.01     2       0          1  0  1
#&gt; TCGA.YU.A912.01     1       0          1  1  0
#&gt; TCGA.S6.A8JX.01     1       0          1  1  0
#&gt; TCGA.2G.AAHL.01     2       0          1  0  1
#&gt; TCGA.4K.AA1G.01     1       0          1  1  0
#&gt; TCGA.2G.AAFE.01     2       0          1  0  1
#&gt; TCGA.2G.AAGY.05     1       0          1  1  0
#&gt; TCGA.2G.AAG9.01     2       0          1  0  1
#&gt; TCGA.4K.AAAL.01     2       0          1  0  1
#&gt; TCGA.YU.A90Q.01     1       0          1  1  0
#&gt; TCGA.SB.A76C.01     1       0          1  1  0
#&gt; TCGA.2G.AAHG.01     1       0          1  1  0
#&gt; TCGA.S6.A8JY.01     1       0          1  1  0
#&gt; TCGA.2G.AAH8.01     1       0          1  1  0
</code></pre>

<script>
$('#tab-node-03-get-classes-1-a').parent().next().next().hide();
$('#tab-node-03-get-classes-1-a').click(function(){
  $('#tab-node-03-get-classes-1-a').parent().next().next().toggle();
  return(false);
});
</script>
</div>

<div id='tab-node-03-get-classes-2'>
<p><a id='tab-node-03-get-classes-2-a' style='color:#0366d6' href='#'>show/hide code output</a></p>
<pre><code class="r">cbind(get_classes(res, k = 3), get_membership(res, k = 3))
</code></pre>

<pre><code>#&gt;                 class entropy silhouette   p1 p2   p3
#&gt; TCGA.XE.AANV.01     2  0.0000      1.000 0.00  1 0.00
#&gt; TCGA.2G.AAHA.01     2  0.0000      1.000 0.00  1 0.00
#&gt; TCGA.WZ.A7V3.01     3  0.0000      0.949 0.00  0 1.00
#&gt; TCGA.XE.A8H5.01     1  0.0000      0.997 1.00  0 0.00
#&gt; TCGA.SO.A8JP.01     1  0.0000      0.997 1.00  0 0.00
#&gt; TCGA.XE.AAOL.01     1  0.0000      0.997 1.00  0 0.00
#&gt; TCGA.2G.AAHT.01     2  0.0000      1.000 0.00  1 0.00
#&gt; TCGA.YU.A90W.01     3  0.0000      0.949 0.00  0 1.00
#&gt; TCGA.S6.A8JW.01     3  0.3686      0.864 0.14  0 0.86
#&gt; TCGA.2G.AAEW.01     2  0.0000      1.000 0.00  1 0.00
#&gt; TCGA.YU.A912.01     3  0.0000      0.949 0.00  0 1.00
#&gt; TCGA.S6.A8JX.01     1  0.0000      0.997 1.00  0 0.00
#&gt; TCGA.2G.AAHL.01     3  0.0000      0.949 0.00  0 1.00
#&gt; TCGA.4K.AA1G.01     3  0.3686      0.864 0.14  0 0.86
#&gt; TCGA.2G.AAFE.01     2  0.0000      1.000 0.00  1 0.00
#&gt; TCGA.2G.AAGY.05     1  0.0000      0.997 1.00  0 0.00
#&gt; TCGA.2G.AAG9.01     2  0.0000      1.000 0.00  1 0.00
#&gt; TCGA.4K.AAAL.01     2  0.0000      1.000 0.00  1 0.00
#&gt; TCGA.YU.A90Q.01     1  0.0000      0.997 1.00  0 0.00
#&gt; TCGA.SB.A76C.01     3  0.0000      0.949 0.00  0 1.00
#&gt; TCGA.2G.AAHG.01     1  0.0892      0.978 0.98  0 0.02
#&gt; TCGA.S6.A8JY.01     1  0.0000      0.997 1.00  0 0.00
#&gt; TCGA.2G.AAH8.01     1  0.0000      0.997 1.00  0 0.00
</code></pre>

<script>
$('#tab-node-03-get-classes-2-a').parent().next().next().hide();
$('#tab-node-03-get-classes-2-a').click(function(){
  $('#tab-node-03-get-classes-2-a').parent().next().next().toggle();
  return(false);
});
</script>
</div>

<div id='tab-node-03-get-classes-3'>
<p><a id='tab-node-03-get-classes-3-a' style='color:#0366d6' href='#'>show/hide code output</a></p>
<pre><code class="r">cbind(get_classes(res, k = 4), get_membership(res, k = 4))
</code></pre>

<pre><code>#&gt;                 class entropy silhouette   p1   p2   p3   p4
#&gt; TCGA.XE.AANV.01     2   0.000      0.977 0.00 1.00 0.00 0.00
#&gt; TCGA.2G.AAHA.01     2   0.382      0.853 0.00 0.84 0.04 0.12
#&gt; TCGA.WZ.A7V3.01     4   0.265      1.000 0.00 0.00 0.12 0.88
#&gt; TCGA.XE.A8H5.01     1   0.000      1.000 1.00 0.00 0.00 0.00
#&gt; TCGA.SO.A8JP.01     1   0.000      1.000 1.00 0.00 0.00 0.00
#&gt; TCGA.XE.AAOL.01     1   0.000      1.000 1.00 0.00 0.00 0.00
#&gt; TCGA.2G.AAHT.01     2   0.000      0.977 0.00 1.00 0.00 0.00
#&gt; TCGA.YU.A90W.01     4   0.265      1.000 0.00 0.00 0.12 0.88
#&gt; TCGA.S6.A8JW.01     3   0.121      0.918 0.04 0.00 0.96 0.00
#&gt; TCGA.2G.AAEW.01     2   0.000      0.977 0.00 1.00 0.00 0.00
#&gt; TCGA.YU.A912.01     3   0.121      0.902 0.00 0.00 0.96 0.04
#&gt; TCGA.S6.A8JX.01     1   0.000      1.000 1.00 0.00 0.00 0.00
#&gt; TCGA.2G.AAHL.01     4   0.265      1.000 0.00 0.00 0.12 0.88
#&gt; TCGA.4K.AA1G.01     3   0.121      0.918 0.04 0.00 0.96 0.00
#&gt; TCGA.2G.AAFE.01     2   0.000      0.977 0.00 1.00 0.00 0.00
#&gt; TCGA.2G.AAGY.05     1   0.000      1.000 1.00 0.00 0.00 0.00
#&gt; TCGA.2G.AAG9.01     2   0.000      0.977 0.00 1.00 0.00 0.00
#&gt; TCGA.4K.AAAL.01     2   0.000      0.977 0.00 1.00 0.00 0.00
#&gt; TCGA.YU.A90Q.01     1   0.000      1.000 1.00 0.00 0.00 0.00
#&gt; TCGA.SB.A76C.01     3   0.121      0.902 0.00 0.00 0.96 0.04
#&gt; TCGA.2G.AAHG.01     3   0.317      0.783 0.16 0.00 0.84 0.00
#&gt; TCGA.S6.A8JY.01     1   0.000      1.000 1.00 0.00 0.00 0.00
#&gt; TCGA.2G.AAH8.01     1   0.000      1.000 1.00 0.00 0.00 0.00
</code></pre>

<script>
$('#tab-node-03-get-classes-3-a').parent().next().next().hide();
$('#tab-node-03-get-classes-3-a').click(function(){
  $('#tab-node-03-get-classes-3-a').parent().next().next().toggle();
  return(false);
});
</script>
</div>

<div id='tab-node-03-get-classes-4'>
<p><a id='tab-node-03-get-classes-4-a' style='color:#0366d6' href='#'>show/hide code output</a></p>
<pre><code class="r">cbind(get_classes(res, k = 5), get_membership(res, k = 5))
</code></pre>

<pre><code>#&gt;                 class entropy silhouette   p1   p2   p3   p4   p5
#&gt; TCGA.XE.AANV.01     2   0.173      0.899 0.00 0.92 0.08 0.00 0.00
#&gt; TCGA.2G.AAHA.01     2   0.426      0.546 0.00 0.56 0.00 0.00 0.44
#&gt; TCGA.WZ.A7V3.01     4   0.000      0.985 0.00 0.00 0.00 1.00 0.00
#&gt; TCGA.XE.A8H5.01     1   0.000      1.000 1.00 0.00 0.00 0.00 0.00
#&gt; TCGA.SO.A8JP.01     1   0.000      1.000 1.00 0.00 0.00 0.00 0.00
#&gt; TCGA.XE.AAOL.01     1   0.000      1.000 1.00 0.00 0.00 0.00 0.00
#&gt; TCGA.2G.AAHT.01     2   0.000      0.901 0.00 1.00 0.00 0.00 0.00
#&gt; TCGA.YU.A90W.01     4   0.104      0.970 0.00 0.00 0.00 0.96 0.04
#&gt; TCGA.S6.A8JW.01     3   0.262      0.974 0.02 0.00 0.88 0.10 0.00
#&gt; TCGA.2G.AAEW.01     2   0.000      0.901 0.00 1.00 0.00 0.00 0.00
#&gt; TCGA.YU.A912.01     3   0.228      0.974 0.00 0.00 0.88 0.12 0.00
#&gt; TCGA.S6.A8JX.01     1   0.000      1.000 1.00 0.00 0.00 0.00 0.00
#&gt; TCGA.2G.AAHL.01     4   0.000      0.985 0.00 0.00 0.00 1.00 0.00
#&gt; TCGA.4K.AA1G.01     3   0.262      0.974 0.02 0.00 0.88 0.10 0.00
#&gt; TCGA.2G.AAFE.01     2   0.173      0.899 0.00 0.92 0.08 0.00 0.00
#&gt; TCGA.2G.AAGY.05     1   0.000      1.000 1.00 0.00 0.00 0.00 0.00
#&gt; TCGA.2G.AAG9.01     2   0.000      0.901 0.00 1.00 0.00 0.00 0.00
#&gt; TCGA.4K.AAAL.01     2   0.228      0.886 0.00 0.88 0.12 0.00 0.00
#&gt; TCGA.YU.A90Q.01     1   0.000      1.000 1.00 0.00 0.00 0.00 0.00
#&gt; TCGA.SB.A76C.01     3   0.228      0.974 0.00 0.00 0.88 0.12 0.00
#&gt; TCGA.2G.AAHG.01     5   0.598      0.171 0.12 0.00 0.36 0.00 0.52
#&gt; TCGA.S6.A8JY.01     5   0.430      0.168 0.48 0.00 0.00 0.00 0.52
#&gt; TCGA.2G.AAH8.01     1   0.000      1.000 1.00 0.00 0.00 0.00 0.00
</code></pre>

<script>
$('#tab-node-03-get-classes-4-a').parent().next().next().hide();
$('#tab-node-03-get-classes-4-a').click(function(){
  $('#tab-node-03-get-classes-4-a').parent().next().next().toggle();
  return(false);
});
</script>
</div>

<div id='tab-node-03-get-classes-5'>
<p><a id='tab-node-03-get-classes-5-a' style='color:#0366d6' href='#'>show/hide code output</a></p>
<pre><code class="r">cbind(get_classes(res, k = 6), get_membership(res, k = 6))
</code></pre>

<pre><code>#&gt;                 class entropy silhouette   p1   p2   p3   p4   p5   p6
#&gt; TCGA.XE.AANV.01     2  0.0547      0.932 0.00 0.98 0.00 0.00 0.02 0.00
#&gt; TCGA.2G.AAHA.01     6  0.3797      0.000 0.00 0.42 0.00 0.00 0.00 0.58
#&gt; TCGA.WZ.A7V3.01     4  0.0000      0.975 0.00 0.00 0.00 1.00 0.00 0.00
#&gt; TCGA.XE.A8H5.01     1  0.3499      0.527 0.68 0.00 0.00 0.00 0.00 0.32
#&gt; TCGA.SO.A8JP.01     1  0.0000      0.941 1.00 0.00 0.00 0.00 0.00 0.00
#&gt; TCGA.XE.AAOL.01     1  0.0000      0.941 1.00 0.00 0.00 0.00 0.00 0.00
#&gt; TCGA.2G.AAHT.01     2  0.0937      0.930 0.00 0.96 0.00 0.00 0.04 0.00
#&gt; TCGA.YU.A90W.01     4  0.1480      0.950 0.00 0.00 0.00 0.94 0.02 0.04
#&gt; TCGA.S6.A8JW.01     3  0.0000      0.981 0.00 0.00 1.00 0.00 0.00 0.00
#&gt; TCGA.2G.AAEW.01     2  0.0000      0.931 0.00 1.00 0.00 0.00 0.00 0.00
#&gt; TCGA.YU.A912.01     3  0.0000      0.981 0.00 0.00 1.00 0.00 0.00 0.00
#&gt; TCGA.S6.A8JX.01     1  0.0000      0.941 1.00 0.00 0.00 0.00 0.00 0.00
#&gt; TCGA.2G.AAHL.01     4  0.0000      0.975 0.00 0.00 0.00 1.00 0.00 0.00
#&gt; TCGA.4K.AA1G.01     3  0.0000      0.981 0.00 0.00 1.00 0.00 0.00 0.00
#&gt; TCGA.2G.AAFE.01     2  0.1267      0.925 0.00 0.94 0.00 0.00 0.06 0.00
#&gt; TCGA.2G.AAGY.05     1  0.0000      0.941 1.00 0.00 0.00 0.00 0.00 0.00
#&gt; TCGA.2G.AAG9.01     2  0.0000      0.931 0.00 1.00 0.00 0.00 0.00 0.00
#&gt; TCGA.4K.AAAL.01     2  0.2048      0.857 0.00 0.88 0.00 0.00 0.12 0.00
#&gt; TCGA.YU.A90Q.01     1  0.0000      0.941 1.00 0.00 0.00 0.00 0.00 0.00
#&gt; TCGA.SB.A76C.01     3  0.1267      0.943 0.00 0.00 0.94 0.00 0.00 0.06
#&gt; TCGA.2G.AAHG.01     5  0.2260      0.508 0.00 0.00 0.14 0.00 0.86 0.00
#&gt; TCGA.S6.A8JY.01     5  0.5428      0.525 0.14 0.00 0.00 0.00 0.54 0.32
#&gt; TCGA.2G.AAH8.01     1  0.0000      0.941 1.00 0.00 0.00 0.00 0.00 0.00
</code></pre>

<script>
$('#tab-node-03-get-classes-5-a').parent().next().next().hide();
$('#tab-node-03-get-classes-5-a').click(function(){
  $('#tab-node-03-get-classes-5-a').parent().next().next().toggle();
  return(false);
});
</script>
</div>

<div id='tab-node-03-get-classes-6'>
<p><a id='tab-node-03-get-classes-6-a' style='color:#0366d6' href='#'>show/hide code output</a></p>
<pre><code class="r">cbind(get_classes(res, k = 7), get_membership(res, k = 7))
</code></pre>

<pre><code>#&gt;                 class entropy silhouette   p1   p2   p3   p4   p5   p6   p7
#&gt; TCGA.XE.AANV.01     2  0.1166     0.7065 0.00 0.94 0.00 0.00 0.06 0.00 0.00
#&gt; TCGA.2G.AAHA.01     6  0.3047     0.0000 0.00 0.28 0.00 0.00 0.00 0.72 0.00
#&gt; TCGA.WZ.A7V3.01     4  0.0000     0.9392 0.00 0.00 0.00 1.00 0.00 0.00 0.00
#&gt; TCGA.XE.A8H5.01     1  0.4783     0.0475 0.54 0.00 0.00 0.00 0.00 0.10 0.36
#&gt; TCGA.SO.A8JP.01     1  0.0000     0.9106 1.00 0.00 0.00 0.00 0.00 0.00 0.00
#&gt; TCGA.XE.AAOL.01     1  0.0000     0.9106 1.00 0.00 0.00 0.00 0.00 0.00 0.00
#&gt; TCGA.2G.AAHT.01     2  0.2832     0.7206 0.00 0.76 0.00 0.00 0.24 0.00 0.00
#&gt; TCGA.YU.A90W.01     4  0.2769     0.8742 0.00 0.00 0.00 0.86 0.08 0.04 0.02
#&gt; TCGA.S6.A8JW.01     3  0.0000     0.9335 0.00 0.00 1.00 0.00 0.00 0.00 0.00
#&gt; TCGA.2G.AAEW.01     2  0.3139     0.7186 0.00 0.70 0.00 0.00 0.30 0.00 0.00
#&gt; TCGA.YU.A912.01     3  0.0504     0.9289 0.00 0.00 0.98 0.00 0.02 0.00 0.00
#&gt; TCGA.S6.A8JX.01     1  0.0000     0.9106 1.00 0.00 0.00 0.00 0.00 0.00 0.00
#&gt; TCGA.2G.AAHL.01     4  0.0000     0.9392 0.00 0.00 0.00 1.00 0.00 0.00 0.00
#&gt; TCGA.4K.AA1G.01     3  0.0000     0.9335 0.00 0.00 1.00 0.00 0.00 0.00 0.00
#&gt; TCGA.2G.AAFE.01     2  0.0504     0.6912 0.00 0.98 0.00 0.00 0.02 0.00 0.00
#&gt; TCGA.2G.AAGY.05     1  0.0000     0.9106 1.00 0.00 0.00 0.00 0.00 0.00 0.00
#&gt; TCGA.2G.AAG9.01     2  0.3139     0.7186 0.00 0.70 0.00 0.00 0.30 0.00 0.00
#&gt; TCGA.4K.AAAL.01     2  0.3058     0.5529 0.00 0.82 0.00 0.00 0.08 0.00 0.10
#&gt; TCGA.YU.A90Q.01     1  0.0000     0.9106 1.00 0.00 0.00 0.00 0.00 0.00 0.00
#&gt; TCGA.SB.A76C.01     3  0.2912     0.8058 0.00 0.00 0.82 0.00 0.04 0.14 0.00
#&gt; TCGA.2G.AAHG.01     5  0.5016     0.0000 0.00 0.00 0.12 0.00 0.46 0.00 0.42
#&gt; TCGA.S6.A8JY.01     7  0.1886     0.0000 0.12 0.00 0.00 0.00 0.00 0.00 0.88
#&gt; TCGA.2G.AAH8.01     1  0.0000     0.9106 1.00 0.00 0.00 0.00 0.00 0.00 0.00
</code></pre>

<script>
$('#tab-node-03-get-classes-6-a').parent().next().next().hide();
$('#tab-node-03-get-classes-6-a').click(function(){
  $('#tab-node-03-get-classes-6-a').parent().next().next().toggle();
  return(false);
});
</script>
</div>

<div id='tab-node-03-get-classes-7'>
<p><a id='tab-node-03-get-classes-7-a' style='color:#0366d6' href='#'>show/hide code output</a></p>
<pre><code class="r">cbind(get_classes(res, k = 8), get_membership(res, k = 8))
</code></pre>

<pre><code>#&gt;                 class entropy silhouette   p1   p2   p3   p4   p5   p6   p7   p8
#&gt; TCGA.XE.AANV.01     2  0.3589      0.677 0.00 0.74 0.00 0.00 0.00 0.00 0.10 0.16
#&gt; TCGA.2G.AAHA.01     6  0.2406      0.000 0.00 0.20 0.00 0.00 0.00 0.80 0.00 0.00
#&gt; TCGA.WZ.A7V3.01     4  0.0000      0.873 0.00 0.00 0.00 1.00 0.00 0.00 0.00 0.00
#&gt; TCGA.XE.A8H5.01     8  0.3142      0.000 0.36 0.00 0.00 0.00 0.00 0.00 0.00 0.64
#&gt; TCGA.SO.A8JP.01     1  0.0000      0.977 1.00 0.00 0.00 0.00 0.00 0.00 0.00 0.00
#&gt; TCGA.XE.AAOL.01     1  0.0000      0.977 1.00 0.00 0.00 0.00 0.00 0.00 0.00 0.00
#&gt; TCGA.2G.AAHT.01     2  0.2132      0.701 0.00 0.88 0.00 0.00 0.00 0.00 0.04 0.08
#&gt; TCGA.YU.A90W.01     4  0.4188      0.727 0.00 0.00 0.00 0.72 0.00 0.04 0.14 0.10
#&gt; TCGA.S6.A8JW.01     3  0.0000      0.918 0.00 0.00 1.00 0.00 0.00 0.00 0.00 0.00
#&gt; TCGA.2G.AAEW.01     2  0.0471      0.712 0.00 0.98 0.00 0.00 0.02 0.00 0.00 0.00
#&gt; TCGA.YU.A912.01     3  0.1275      0.902 0.00 0.00 0.94 0.00 0.04 0.00 0.02 0.00
#&gt; TCGA.S6.A8JX.01     1  0.0000      0.977 1.00 0.00 0.00 0.00 0.00 0.00 0.00 0.00
#&gt; TCGA.2G.AAHL.01     4  0.0000      0.873 0.00 0.00 0.00 1.00 0.00 0.00 0.00 0.00
#&gt; TCGA.4K.AA1G.01     3  0.0000      0.918 0.00 0.00 1.00 0.00 0.00 0.00 0.00 0.00
#&gt; TCGA.2G.AAFE.01     2  0.4299      0.656 0.00 0.64 0.00 0.00 0.00 0.00 0.14 0.22
#&gt; TCGA.2G.AAGY.05     1  0.0808      0.954 0.96 0.00 0.00 0.00 0.00 0.04 0.00 0.00
#&gt; TCGA.2G.AAG9.01     2  0.0471      0.713 0.00 0.98 0.00 0.00 0.00 0.00 0.00 0.02
#&gt; TCGA.4K.AAAL.01     2  0.4849      0.476 0.00 0.54 0.00 0.00 0.24 0.00 0.22 0.00
#&gt; TCGA.YU.A90Q.01     1  0.0000      0.977 1.00 0.00 0.00 0.00 0.00 0.00 0.00 0.00
#&gt; TCGA.SB.A76C.01     3  0.3586      0.789 0.00 0.00 0.78 0.00 0.04 0.12 0.06 0.00
#&gt; TCGA.2G.AAHG.01     5  0.3083      0.000 0.00 0.00 0.00 0.00 0.66 0.00 0.34 0.00
#&gt; TCGA.S6.A8JY.01     7  0.3299      0.000 0.00 0.00 0.00 0.00 0.00 0.00 0.56 0.44
#&gt; TCGA.2G.AAH8.01     1  0.0808      0.954 0.96 0.00 0.00 0.00 0.00 0.04 0.00 0.00
</code></pre>

<script>
$('#tab-node-03-get-classes-7-a').parent().next().next().hide();
$('#tab-node-03-get-classes-7-a').click(function(){
  $('#tab-node-03-get-classes-7-a').parent().next().next().toggle();
  return(false);
});
</script>
</div>
</div>

Heatmaps for the consensus matrix. It visualizes the probability of two
samples to be in a same group.




<script>
$( function() {
	$( '#tabs-node-03-consensus-heatmap' ).tabs();
} );
</script>
<div id='tabs-node-03-consensus-heatmap'>
<ul>
<li><a href='#tab-node-03-consensus-heatmap-1'>k = 2</a></li>
<li><a href='#tab-node-03-consensus-heatmap-2'>k = 3</a></li>
<li><a href='#tab-node-03-consensus-heatmap-3'>k = 4</a></li>
<li><a href='#tab-node-03-consensus-heatmap-4'>k = 5</a></li>
<li><a href='#tab-node-03-consensus-heatmap-5'>k = 6</a></li>
<li><a href='#tab-node-03-consensus-heatmap-6'>k = 7</a></li>
<li><a href='#tab-node-03-consensus-heatmap-7'>k = 8</a></li>
</ul>
<div id='tab-node-03-consensus-heatmap-1'>
<pre><code class="r">consensus_heatmap(res, k = 2)
</code></pre>

<p><img src="figure_cola/tab-node-03-consensus-heatmap-1-1.png" alt="plot of chunk tab-node-03-consensus-heatmap-1"/></p>

</div>
<div id='tab-node-03-consensus-heatmap-2'>
<pre><code class="r">consensus_heatmap(res, k = 3)
</code></pre>

<p><img src="figure_cola/tab-node-03-consensus-heatmap-2-1.png" alt="plot of chunk tab-node-03-consensus-heatmap-2"/></p>

</div>
<div id='tab-node-03-consensus-heatmap-3'>
<pre><code class="r">consensus_heatmap(res, k = 4)
</code></pre>

<p><img src="figure_cola/tab-node-03-consensus-heatmap-3-1.png" alt="plot of chunk tab-node-03-consensus-heatmap-3"/></p>

</div>
<div id='tab-node-03-consensus-heatmap-4'>
<pre><code class="r">consensus_heatmap(res, k = 5)
</code></pre>

<p><img src="figure_cola/tab-node-03-consensus-heatmap-4-1.png" alt="plot of chunk tab-node-03-consensus-heatmap-4"/></p>

</div>
<div id='tab-node-03-consensus-heatmap-5'>
<pre><code class="r">consensus_heatmap(res, k = 6)
</code></pre>

<p><img src="figure_cola/tab-node-03-consensus-heatmap-5-1.png" alt="plot of chunk tab-node-03-consensus-heatmap-5"/></p>

</div>
<div id='tab-node-03-consensus-heatmap-6'>
<pre><code class="r">consensus_heatmap(res, k = 7)
</code></pre>

<p><img src="figure_cola/tab-node-03-consensus-heatmap-6-1.png" alt="plot of chunk tab-node-03-consensus-heatmap-6"/></p>

</div>
<div id='tab-node-03-consensus-heatmap-7'>
<pre><code class="r">consensus_heatmap(res, k = 8)
</code></pre>

<p><img src="figure_cola/tab-node-03-consensus-heatmap-7-1.png" alt="plot of chunk tab-node-03-consensus-heatmap-7"/></p>

</div>
</div>

Heatmaps for the membership of samples in all partitions to see how consistent they are:





<script>
$( function() {
	$( '#tabs-node-03-membership-heatmap' ).tabs();
} );
</script>
<div id='tabs-node-03-membership-heatmap'>
<ul>
<li><a href='#tab-node-03-membership-heatmap-1'>k = 2</a></li>
<li><a href='#tab-node-03-membership-heatmap-2'>k = 3</a></li>
<li><a href='#tab-node-03-membership-heatmap-3'>k = 4</a></li>
<li><a href='#tab-node-03-membership-heatmap-4'>k = 5</a></li>
<li><a href='#tab-node-03-membership-heatmap-5'>k = 6</a></li>
<li><a href='#tab-node-03-membership-heatmap-6'>k = 7</a></li>
<li><a href='#tab-node-03-membership-heatmap-7'>k = 8</a></li>
</ul>
<div id='tab-node-03-membership-heatmap-1'>
<pre><code class="r">membership_heatmap(res, k = 2)
</code></pre>

<p><img src="figure_cola/tab-node-03-membership-heatmap-1-1.png" alt="plot of chunk tab-node-03-membership-heatmap-1"/></p>

</div>
<div id='tab-node-03-membership-heatmap-2'>
<pre><code class="r">membership_heatmap(res, k = 3)
</code></pre>

<p><img src="figure_cola/tab-node-03-membership-heatmap-2-1.png" alt="plot of chunk tab-node-03-membership-heatmap-2"/></p>

</div>
<div id='tab-node-03-membership-heatmap-3'>
<pre><code class="r">membership_heatmap(res, k = 4)
</code></pre>

<p><img src="figure_cola/tab-node-03-membership-heatmap-3-1.png" alt="plot of chunk tab-node-03-membership-heatmap-3"/></p>

</div>
<div id='tab-node-03-membership-heatmap-4'>
<pre><code class="r">membership_heatmap(res, k = 5)
</code></pre>

<p><img src="figure_cola/tab-node-03-membership-heatmap-4-1.png" alt="plot of chunk tab-node-03-membership-heatmap-4"/></p>

</div>
<div id='tab-node-03-membership-heatmap-5'>
<pre><code class="r">membership_heatmap(res, k = 6)
</code></pre>

<p><img src="figure_cola/tab-node-03-membership-heatmap-5-1.png" alt="plot of chunk tab-node-03-membership-heatmap-5"/></p>

</div>
<div id='tab-node-03-membership-heatmap-6'>
<pre><code class="r">membership_heatmap(res, k = 7)
</code></pre>

<p><img src="figure_cola/tab-node-03-membership-heatmap-6-1.png" alt="plot of chunk tab-node-03-membership-heatmap-6"/></p>

</div>
<div id='tab-node-03-membership-heatmap-7'>
<pre><code class="r">membership_heatmap(res, k = 8)
</code></pre>

<p><img src="figure_cola/tab-node-03-membership-heatmap-7-1.png" alt="plot of chunk tab-node-03-membership-heatmap-7"/></p>

</div>
</div>

As soon as the classes for columns are determined, the signatures
that are significantly different between subgroups can be looked for. 
Following are the heatmaps for signatures.






<script>
$( function() {
	$( '#tabs-node-03-get-signatures' ).tabs();
} );
</script>
<div id='tabs-node-03-get-signatures'>
<ul>
<li><a href='#tab-node-03-get-signatures-1'>k = 2</a></li>
<li><a href='#tab-node-03-get-signatures-2'>k = 3</a></li>
<li><a href='#tab-node-03-get-signatures-3'>k = 4</a></li>
<li><a href='#tab-node-03-get-signatures-4'>k = 5</a></li>
<li><a href='#tab-node-03-get-signatures-5'>k = 6</a></li>
<li><a href='#tab-node-03-get-signatures-6'>k = 7</a></li>
<li><a href='#tab-node-03-get-signatures-7'>k = 8</a></li>
</ul>
<div id='tab-node-03-get-signatures-1'>
<pre><code class="r">get_signatures(res, k = 2)
</code></pre>

<p><img src="figure_cola/tab-node-03-get-signatures-1-1.png" alt="plot of chunk tab-node-03-get-signatures-1"/></p>

</div>
<div id='tab-node-03-get-signatures-2'>
<pre><code class="r">get_signatures(res, k = 3)
</code></pre>

<p><img src="figure_cola/tab-node-03-get-signatures-2-1.png" alt="plot of chunk tab-node-03-get-signatures-2"/></p>

</div>
<div id='tab-node-03-get-signatures-3'>
<pre><code class="r">get_signatures(res, k = 4)
</code></pre>

<p><img src="figure_cola/tab-node-03-get-signatures-3-1.png" alt="plot of chunk tab-node-03-get-signatures-3"/></p>

</div>
<div id='tab-node-03-get-signatures-4'>
<pre><code class="r">get_signatures(res, k = 5)
</code></pre>

<p><img src="figure_cola/tab-node-03-get-signatures-4-1.png" alt="plot of chunk tab-node-03-get-signatures-4"/></p>

</div>
<div id='tab-node-03-get-signatures-5'>
<pre><code class="r">get_signatures(res, k = 6)
</code></pre>

<p><img src="figure_cola/tab-node-03-get-signatures-5-1.png" alt="plot of chunk tab-node-03-get-signatures-5"/></p>

</div>
<div id='tab-node-03-get-signatures-6'>
<pre><code class="r">get_signatures(res, k = 7)
</code></pre>

<p><img src="figure_cola/tab-node-03-get-signatures-6-1.png" alt="plot of chunk tab-node-03-get-signatures-6"/></p>

</div>
<div id='tab-node-03-get-signatures-7'>
<pre><code class="r">get_signatures(res, k = 8)
</code></pre>

<p><img src="figure_cola/tab-node-03-get-signatures-7-1.png" alt="plot of chunk tab-node-03-get-signatures-7"/></p>

</div>
</div>



Compare the overlap of signatures from different k:

```r
compare_signatures(res)
```

![plot of chunk node-03-signature_compare](figure_cola/node-03-signature_compare-1.png)

`get_signature()` returns a data frame invisibly. To get the list of signatures, the function
call should be assigned to a variable explicitly. In following code, if `plot` argument is set
to `FALSE`, no heatmap is plotted while only the differential analysis is performed.

```r
# code only for demonstration
tb = get_signature(res, k = ..., plot = FALSE)
```

An example of the output of `tb` is:

```
#>   which_row         fdr    mean_1    mean_2 scaled_mean_1 scaled_mean_2 km
#> 1        38 0.042760348  8.373488  9.131774    -0.5533452     0.5164555  1
#> 2        40 0.018707592  7.106213  8.469186    -0.6173731     0.5762149  1
#> 3        55 0.019134737 10.221463 11.207825    -0.6159697     0.5749050  1
#> 4        59 0.006059896  5.921854  7.869574    -0.6899429     0.6439467  1
#> 5        60 0.018055526  8.928898 10.211722    -0.6204761     0.5791110  1
#> 6        98 0.009384629 15.714769 14.887706     0.6635654    -0.6193277  2
...
```

The columns in `tb` are:

1. `which_row`: row indices corresponding to the input matrix.
2. `fdr`: FDR for the differential test. 
3. `mean_x`: The mean value in group x.
4. `scaled_mean_x`: The mean value in group x after rows are scaled.
5. `km`: Row groups if k-means clustering is applied to rows (which is done by automatically selecting number of clusters).

If there are too many signatures, `top_signatures = ...` can be set to only show the 
signatures with the highest FDRs:

```r
# code only for demonstration
# e.g. to show the top 500 most significant rows
tb = get_signature(res, k = ..., top_signatures = 500)
```

If the signatures are defined as these which are uniquely high in current group, `diff_method` argument
can be set to `"uniquely_high_in_one_group"`:

```r
# code only for demonstration
tb = get_signature(res, k = ..., diff_method = "uniquely_high_in_one_group")
```




UMAP plot which shows how samples are separated.


<script>
$( function() {
	$( '#tabs-node-03-dimension-reduction' ).tabs();
} );
</script>
<div id='tabs-node-03-dimension-reduction'>
<ul>
<li><a href='#tab-node-03-dimension-reduction-1'>k = 2</a></li>
<li><a href='#tab-node-03-dimension-reduction-2'>k = 3</a></li>
<li><a href='#tab-node-03-dimension-reduction-3'>k = 4</a></li>
<li><a href='#tab-node-03-dimension-reduction-4'>k = 5</a></li>
<li><a href='#tab-node-03-dimension-reduction-5'>k = 6</a></li>
<li><a href='#tab-node-03-dimension-reduction-6'>k = 7</a></li>
<li><a href='#tab-node-03-dimension-reduction-7'>k = 8</a></li>
</ul>
<div id='tab-node-03-dimension-reduction-1'>
<pre><code class="r">dimension_reduction(res, k = 2, method = &quot;UMAP&quot;)
</code></pre>

<p><img src="figure_cola/tab-node-03-dimension-reduction-1-1.png" alt="plot of chunk tab-node-03-dimension-reduction-1"/></p>

</div>
<div id='tab-node-03-dimension-reduction-2'>
<pre><code class="r">dimension_reduction(res, k = 3, method = &quot;UMAP&quot;)
</code></pre>

<p><img src="figure_cola/tab-node-03-dimension-reduction-2-1.png" alt="plot of chunk tab-node-03-dimension-reduction-2"/></p>

</div>
<div id='tab-node-03-dimension-reduction-3'>
<pre><code class="r">dimension_reduction(res, k = 4, method = &quot;UMAP&quot;)
</code></pre>

<p><img src="figure_cola/tab-node-03-dimension-reduction-3-1.png" alt="plot of chunk tab-node-03-dimension-reduction-3"/></p>

</div>
<div id='tab-node-03-dimension-reduction-4'>
<pre><code class="r">dimension_reduction(res, k = 5, method = &quot;UMAP&quot;)
</code></pre>

<p><img src="figure_cola/tab-node-03-dimension-reduction-4-1.png" alt="plot of chunk tab-node-03-dimension-reduction-4"/></p>

</div>
<div id='tab-node-03-dimension-reduction-5'>
<pre><code class="r">dimension_reduction(res, k = 6, method = &quot;UMAP&quot;)
</code></pre>

<p><img src="figure_cola/tab-node-03-dimension-reduction-5-1.png" alt="plot of chunk tab-node-03-dimension-reduction-5"/></p>

</div>
<div id='tab-node-03-dimension-reduction-6'>
<pre><code class="r">dimension_reduction(res, k = 7, method = &quot;UMAP&quot;)
</code></pre>

<p><img src="figure_cola/tab-node-03-dimension-reduction-6-1.png" alt="plot of chunk tab-node-03-dimension-reduction-6"/></p>

</div>
<div id='tab-node-03-dimension-reduction-7'>
<pre><code class="r">dimension_reduction(res, k = 8, method = &quot;UMAP&quot;)
</code></pre>

<p><img src="figure_cola/tab-node-03-dimension-reduction-7-1.png" alt="plot of chunk tab-node-03-dimension-reduction-7"/></p>

</div>
</div>



Following heatmap shows how subgroups are split when increasing `k`:

```r
collect_classes(res)
```

![plot of chunk node-03-collect-classes](figure_cola/node-03-collect-classes-1.png)



If matrix rows can be associated to genes, consider to use `functional_enrichment(res,
...)` to perform function enrichment for the signature genes. See [this vignette](https://jokergoo.github.io/cola_vignettes/functional_enrichment.html) for more detailed explanations.


 

## Session info


```r
sessionInfo()
```

```
#> R version 4.1.0 (2021-05-18)
#> Platform: x86_64-pc-linux-gnu (64-bit)
#> Running under: CentOS Linux 7 (Core)
#> 
#> Matrix products: default
#> BLAS/LAPACK: /usr/lib64/libopenblas-r0.3.3.so
#> 
#> locale:
#>  [1] LC_CTYPE=en_US.UTF-8       LC_NUMERIC=C               LC_TIME=en_US.UTF-8       
#>  [4] LC_COLLATE=en_US.UTF-8     LC_MONETARY=en_US.UTF-8    LC_MESSAGES=en_US.UTF-8   
#>  [7] LC_PAPER=en_US.UTF-8       LC_NAME=C                  LC_ADDRESS=C              
#> [10] LC_TELEPHONE=C             LC_MEASUREMENT=en_US.UTF-8 LC_IDENTIFICATION=C       
#> 
#> attached base packages:
#> [1] grid      stats     graphics  grDevices utils     datasets  methods   base     
#> 
#> other attached packages:
#> [1] genefilter_1.74.0    ComplexHeatmap_2.8.0 markdown_1.1         knitr_1.33          
#> [5] matrixStats_0.59.0   cola_1.9.4          
#> 
#> loaded via a namespace (and not attached):
#>   [1] bitops_1.0-7           bit64_4.0.5            doParallel_1.0.16      RColorBrewer_1.1-2    
#>   [5] httr_1.4.2             GenomeInfoDb_1.28.1    data.tree_1.0.0        tools_4.1.0           
#>   [9] utf8_1.2.1             R6_2.5.0               irlba_2.3.3            DBI_1.1.1             
#>  [13] BiocGenerics_0.38.0    colorspace_2.0-2       GetoptLong_1.0.5       gridExtra_2.3         
#>  [17] tidyselect_1.1.1       bit_4.0.4              compiler_4.1.0         Biobase_2.52.0        
#>  [21] Cairo_1.5-12.2         xml2_1.3.2             microbenchmark_1.4-7   slam_0.1-48           
#>  [25] scales_1.1.1           askpass_1.1            stringr_1.4.0          digest_0.6.27         
#>  [29] XVector_0.32.0         pkgconfig_2.0.3        umap_0.2.7.0           fastmap_1.1.0         
#>  [33] highr_0.9              rlang_0.4.11           GlobalOptions_0.1.2    rstudioapi_0.13       
#>  [37] RSQLite_2.2.7          impute_1.66.0          generics_0.1.0         shape_1.4.6           
#>  [41] jsonlite_1.7.2         mclust_5.4.7           dplyr_1.0.7            dendextend_1.15.1     
#>  [45] RCurl_1.98-1.3         magrittr_2.0.1         GenomeInfoDbData_1.2.6 Matrix_1.3-4          
#>  [49] fansi_0.5.0            Rcpp_1.0.7             munsell_0.5.0          S4Vectors_0.30.0      
#>  [53] viridis_0.6.1          reticulate_1.20        lifecycle_1.0.0        scatterplot3d_0.3-41  
#>  [57] stringi_1.7.3          zlibbioc_1.38.0        blob_1.2.1             parallel_4.1.0        
#>  [61] crayon_1.4.1           lattice_0.20-44        Biostrings_2.60.1      splines_4.1.0         
#>  [65] annotate_1.70.0        circlize_0.4.13        KEGGREST_1.32.0        polylabelr_0.2.0      
#>  [69] pillar_1.6.1           rjson_0.2.20           codetools_0.2-18       stats4_4.1.0          
#>  [73] XML_3.99-0.6           glue_1.4.2             evaluate_0.14          png_0.1-7             
#>  [77] vctrs_0.3.8            foreach_1.5.1          polyclip_1.10-0        purrr_0.3.4           
#>  [81] gtable_0.3.0           openssl_1.4.4          assertthat_0.2.1       clue_0.3-59           
#>  [85] cachem_1.0.5           ggplot2_3.3.5          xfun_0.24              eulerr_6.1.0          
#>  [89] xtable_1.8-4           skmeans_0.2-13         RSpectra_0.16-0        viridisLite_0.4.0     
#>  [93] survival_3.2-11        tibble_3.1.2           Polychrome_1.3.1       iterators_1.0.13      
#>  [97] AnnotationDbi_1.54.1   memoise_2.0.0          IRanges_2.26.0         cluster_2.1.2         
#> [101] ellipsis_0.3.2         brew_1.0-6
```




