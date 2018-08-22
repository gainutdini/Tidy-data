1) load the X_train.txt and X_test.txt:
        tr <- read.table(file.path("train", "X_train.txt"), header = FALSE, sep = "")
        ts <- read.table(file.path("test", "X_test.txt"), header = FALSE, sep = "")
2) calculate standart deviation and mean for each:
        tr_sd <- data.frame() # empty data frame
        for (i in 1:561) {tr_sd <- rbind(tr_sd, sd(tr[,i]))} # calculates standart deviation for each column in tr, and adds to tr_sd 
        
        ts_sd <- data.frame() # empty data frame
        for (i in 1:561) {ts_sd <- rbind(tr_sd, sd(ts[,i]))} # calculates standart deviation for each column in ts, and adds to ts_sd 
        
        tr_mean <- data.frame() # empty data frame
        for (i in 1:561) {tr_mean <- rbind(tr_mean, mean(tr[,i]))} # calculates average for each column in tr, and adds to tr_mean 
        
        ts_mean <- data.frame() # empty data frame
        for (i in 1:561) {ts_mean <- rbind(ts_mean, mean(ts[,i]))} # calculates average for each column in tr, and adds to ts_mean 
3) making a tidy data:
        all <- cbind(tr_sd, ts_sd, tr_mean, ts_mean) # collects each data.frame to one table
        names(all) <- c("tr_sd", "ts_sd", "tr_mean", "ts_mean") # gives the names to each column
