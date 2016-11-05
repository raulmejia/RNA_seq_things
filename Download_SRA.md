There are a R package in bioconductor to Download SRA's from NCBI (I don't know if the other sites too)

# A Rscript for such task is:  


`source("http://bioconductor.org/biocLite.R")`  
`biocLite("SRAdb")`  
`biocLite("DBI")`  
`library(SRAdb)`      
`library(DBI)`  
`srafile = getSRAdbFile()`
`con = dbConnect(RSQLite::SQLite(), srafile)` 
`getSRAfile(c("SRR1246789","SRR1246790","SRR1246791","SRR1246792","SRR1240812","SRR1240813","SRR3341749","SRR3341750","SRR3341751","SRR3341752","SRR3713945","SRR3713946","SRR3188100","SRR3188101","SRR2084359","SRR1910728","SRR580377","SRR580378","SRR580374","SRR580375","SRR580376","SRR580373","SRR679322","SRR679323","SRR679324","SRR679325","SRR679326","SRR679327","SRR531465","SRR531469"),con,fileType='sra')`  
`dbDisconnect()`



