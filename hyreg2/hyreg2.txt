# Olah Data Semarang
# WhatsApp : +6285227746673
# IG : @olahdatasemarang_
# Estimation of hybrid model using continuous and dichotomous data e.g. EQ-5D data Use hyreg2 With (In) R Software
install.packages("hyreg2")
library("hyreg2")
# Estimate Estimation of hybrid model using continuous and dichotomous data e.g. EQ-5D data Use hyreg2 With (In) R Software
hyreg2 = read.csv("https://raw.githubusercontent.com/timbulwidodostp/hyreg2/main/hyreg2/hyreg2.csv",sep = ";")
formula <- y ~  -1 + x1 + x2 + x3 | id
k <- 2
stv <- setNames(c(0.2,0,1,1,1),c(colnames(hyreg2)[4:6],c("sigma","theta")))
control = list(iter.max = 1000, verbose = 4)
hyreg2 <- hyreg2(formula = formula, data =  hyreg2, type = hyreg2$type, stv = stv, k = k, type_cont = "TTO", 
type_dich = "DCE_A", opt_method = "L-BFGS-B", control = control, latent = "cont", id_col = "id")
summary_hyreg2(hyreg2)
# Estimation of hybrid model using continuous and dichotomous data e.g. EQ-5D data Use hyreg2 With (In) R Software
# Olah Data Semarang
# WhatsApp : +6285227746673
# IG : @olahdatasemarang_
# Finished