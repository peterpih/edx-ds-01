
```R
index <- heights$sex == "Male"
x <- heights$height[index]

# calculate mean and standard deviation manually
average <- sum(x) / length(x)
SD <- sqrt(sum(x-average)^2/length(x)

# built-in mean and sd functions
average <- mean(x)
SD <- sd(x)

# calculate standard units
z <- scale(x)

# calculate proportion of values within 2 SD of mean
mean(abs(x) < 2)

# make QQ-plot with scaled values
p <- seq(0.05, 0.95, 0.05)
observed_quantiles <- quantile(z, p)
theoretical_quantiles <- qnorm(p) 
plot(theoretical_quantiles, observed_quantiles)
abline(0,1)
