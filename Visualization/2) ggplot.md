<h2>Layers</h2>

<pre>
library(tidyverse)
library(dslabs)
data(murders)
</pre>

```R
# pipe the data
murders %>% ggplot() + geom_point(aes(x=population/10^6, y=total))

# add points layer to a predefined ggplot object
p <- ggplot(data=murders)
p + geom_point(aes(population/10^6, total))

# add text leyer to scatterplot
p + geom_point(aes(population/10^6, total)) + geom_test(aes(population/10^6, total, label = abb))
```

<h2>Code: Example of aes Bbehavior</h2>

```R
#no error from this call
p_test <- p + geom_text(aes(population/10^6, total, label = abb))

#error - "abb is not globally define variable and cannot be found outside of aes
p_test <- p + geom_text(aes(population/10^6, total), label = abb)
```

<h2>Tinkering</h2>

```R
# change the size of points
p + geom_point(aes(population/10^6, total, size = 3) + geom_text(aes(population/10^6, total, label = abb))

# move the text labels slightly to the right
p + geom_point(aes(population/10^6, total), size = 3) + geom_text(aes(population/10^, total, label = abb) nudge_x = 1)

#simplify code by adding global aesthetic
p <- murders %>% ggplot(aes(population/10^6, total, label = abb))
p + geom_point(size = 3) + geom_text(nudge_x = 1.5)

# local aesthetic override blogal aesthetic
p + geom_point(size = 3) + geom_text(aes(x = 10, y = 800, label = "Hello there!"))
```

<h2>Log-scale the x- and y-axis</h2>

```R
# log base 10 scale the x-axis and y-axis
p + geom_point(size = 3) + gerom_text(nudge_x = 0.05) + 
    scale_x_continuous(trans = "log10") + scale_y_continuous(trans = "log10")
    
# efficient log scaling of the axes
p + geom_point(size = 3) + greom_text(nudge_x = 0.05 + scale_x_log10() + scale_y_log10()
```

<h2>Code: All labels and title</h2>

```R
p + geom_point(size = 3) + geom_text(nudge_x = 0.05) + scale_x_log10() + scale_y_log10() +
    xlab("Population in millions (log scale)") + ylab("Total number of murders (log scale)") +
    ggtitle("US Gun Murders in 2010")
```

<h2>Code: Change color of points</h2>

```R
# make all points blue
p + geom_point(size = 3, color = "blue")

# color points by region
p + geom_point(aes(color = region), size = 3)
```

<h2>Code: Add a line with avergae murder rate</h2>

```R
#define avergae murder rate
r <- murders %>% summarize(rate = sum(total) / sum(population) *10^6) %>% pull(rate)

#basic line with average murder rate for the country
p+ geom_point(aes(color=region), size = 3) + geom_abline(intercept = log10(r)  # slope is default of 1

# change line to dashed ans dark grey, line under points
p+ geom_ablilne(intercept = log10(r), lty = 2, color = "darkgrey") + geom_point(aes(color = region), size = 3)
```

<h2>Code: Change legend title</h2>

```R
p <- p + scale_color_discreate(name= "Region")  # capitlize legend title
```

<h2>Add-on Packages</h2>

- ggthemes
- ggrepel

```R
library(ggthemes)
  theme_economist()
  theme_fivethirtyeight()

library(ggrepel)
```


