# Data-Analysis-with-R

library(datasets)
data(iris)

iris2 <- datasets::iris

# View the data
View(iris)

# Data summary statistics

head(iris, 5)
tail(iris, 5)


# summary()
summary(iris)
summary(iris$Sepal.Length)


# Check if there are missing data?
sum(is.na(iris))


install.packages("skimr")

library(skimr)

skim(iris)


# Data visualization
# R base plot()


# Panel plots
plot(iris)
plot(iris, col = "red")

# Scatter plot
plot(iris$Sepal.Width, iris$Sepal.Length)

plot(iris$Sepal.Width, iris$Sepal.Length, col = "red")     # Makes red circles

plot(iris$Sepal.Width, iris$Sepal.Length, col = "red",     # Makes red circles + Adds x and y axis labels
     xlab = "Sepal width", ylab = "Sepal length")

# Histogram
hist(iris$Sepal.Width)
hist(iris$Sepal.Width, col = "red")   # Makes red bars

# Feature plots
# https://www.machinelearningplus.com/machine-learning/caret-package/
featurePlot(x = iris[,1:4], 
            y = iris$Species, 
            plot = "box",
            strip=strip.custom(par.strip.text=list(cex=.7)),
            scales = list(x = list(relation="free"), 
                          y = list(relation="free")))
