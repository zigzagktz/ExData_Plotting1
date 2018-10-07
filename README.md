power <- read.csv("household_power_consumption.txt",sep=";",header=T)
View(power)
realdate <- power[ power$Date %in% c("2/12/2007","1/12/2007") ,]
View(realdate)
datetime <- strptime(paste(power$Date,power$Time,sep=""),"%d/%m/%Y %H:%M:%S")
realpower <- cbind(power,datetime)
realpower$Global_active_power <- as.numeric(realpower$Global_active_power)
hist(realpower$Global_active_power,col="red")

