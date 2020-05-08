# OmicPath: an R package for gene set enrichment analysis and pathway network analysis 
#### Install the package
```r
library(devtools)
install_github("CBIIT-CGR/OmicPath")
``` 
 
 
# Examples
### do GSEA
```r
set.seed(1234);
## get some genes from KEGG 
dat   <- read.table(system.file("extdata/biosystems_hs.txt", package = "OmicPath"));
genes <- sample(dat[,1], 200);

## select databases (GO) from the package
db  <- db_names()[1];
## do GSEA
out <- doGSEA(db=db, gene=genes, filter.num=2, fdr=T);
``` 
 
### map gene information on pathway
<img src="examples/02do_KEGGplot.png" width="800" height="800">
  
[code](examples/02do_KEGGplot.R)

### get pathway gene relationships and plot pathway as network
<img src="examples/03data_network.png" width="400" height="800">  <img src="examples/03plot_network.png" width="800" height="800">
  
[code](examples/03plot_network.R)


### Option: cluster algorithms in igraph
<img src="examples/04do_igraph_cluster.png" width="800" height="800">
  
[code](examples/04do_igraph_cluster.R)
