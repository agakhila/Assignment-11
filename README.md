# Assignment-11
In the below give code the 'deliberate' bug is the && operator in R is used for scalar logical AND operation, meaning it evaluates only the first element of each vector or array being compared. On the other hand, the & operator is used for element-wise logical AND operation within vectors or arrays.So, the bug fix involves replacing && with & to ensure that the logical operation is applied element-wise across the arrays.
Here is the corrected code :
tukey_multiple <- function(x) {
   outliers <- array(TRUE,dim=dim(x))
   for (j in 1:ncol(x))
    {
    outliers[,j] <- outliers[,j] & tukey.outlier(x[,j])
    }
outlier.vec <- vector(length=nrow(x))
    for (i in 1:nrow(x))
    { outlier.vec[i] <- all(outliers[i,]) } return(outlier.vec) }
