<h2>Summarize</h2>

```R
s <- heights %>% filter(sex == "Male") %>% summarize(average = mean(height), standard_deviation = sd(height))

s$average
s$standard_deviation

# compute median, min and max
heights %>% filter(sex = "Male") %>% summarize(median = median(height), minimum = min(height), maximum = max(height))

#alternate way to get min, median, max ni base R
quantile(heights$height, c(0, 0.5, 1))

# generates an error: sumarize can only take functions that return a single value
heights %>% filter(sex = "Male") %>% summarize(range = quantile(height, c(0, 0.5, 1)))
```
