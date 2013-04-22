Writing R function
===========

## R codes
ani_hist_Density <- function(variable,data_set,colHist='yellow',colLine='blue'){
  key_variable <- as.character(variable)
	data <- data_set
	attach(data)
	mainT=paste("histogram for ",key_variable,sep="")
	hist(data[,key_variable],prob=TRUE,
         main=mainT,col=colHist,breaks=25)	
	lines(density(data[,key_variable]),lwd=1,col=colLine)
	detach(data)
	
}

ani_hist_Density("Sepal.Length",Data,colHist='yellow',colLine='black')
