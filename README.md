# r-project
title: "Medical Charge Predictions"
output: html_document
data: "2022-08-25"


{r setup, include-FLASE}
knitr::opts_chunk$set(echo = TRUE)

#Libraries




##load the data 
df=read.csv("C:/Users/HP/Downloads/Medical cost/insurance.csv",stringsAsFactors=TRUE)
num_cols <- unlist(lapply(df, is.numeric))
plot(df[,num_cols])

-----{r}
round(cor(df[,num_cols]),2)
-------
  
  
  
-------{r}
# Create factors
smoker <- as.factor(df$smoker)
boxplot(charges ~ smoker, data = df, main = "Charges by Smoker")
-------
sex <- as.factor(df$sex)
boxplot(charges ~ sex, data = df, main = "Charges by Sex")
-------
region <- as.factor(df$region)
boxplot(charges ~ region, data = df, main = "Charges by Region")

  
  
-----{r}
model1 = lm(charges ~.,data =df)
-----
  
  

------{r}
summary(model1)
------
  

