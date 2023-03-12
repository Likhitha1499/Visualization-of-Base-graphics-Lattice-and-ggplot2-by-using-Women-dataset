# Visualization-of-Base-graphics-Lattice-and-ggplot2-by-using-Women-dataset
data(women)

#BASE GRAPHICS#

plot(women$height, women$weight,
     xlab = "Height (inches)",
     ylab = "Weight (lbs)")

#LATTICE#

library(lattice)
splom(women[, c("height", "weight")], col = "red",
      main = "Scatter Plot Matrix of Height and Weight")


#ggplot2#

library(ggplot2)
ggplot(data = women, aes(x = height, y = weight)) +
  geom_point() +
  geom_smooth(method = "lm", formula = "y ~ poly(x, 2)", se = FALSE) +
  labs(title = "Scatter Plot of Height and Weight with Quadratic Regression Line",
       x = "Height (inches)", y = "Weight (lbs)")
