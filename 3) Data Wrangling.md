Using the dyplr package  

<pre>
<b>install.packages("dyplr")
library(dplyr)</b>
</pre>

- Change/Add Columns  

<pre>
<b>mutate</b> - mutate(<em>data frame</em>, <em>column</em> = <em>formula/value</em>)

murders <- mutate(murders, rate = total / population *100000)
</pre>

- Filter Rows

<pre>
<b>filter</b> - filter(<em>data frame</em>, <em>condition</em>)

filter(murders, rate <= 0.71)
</pre>

- Select Columns  

<pre>
<b>select</b> - select(<em>data set</em>, <em>column1</em>, <em>column2</em>)

new_table <- select(murders, state, region, rate)
</pre>

- Pipe (connect statements)

<pre>
<em>statement</em> <b>%>%</b> </em>statement</em>

murders %>% select(state, region, rate) %>% filter(rate <= 0.71)
</pre>

- nrow (number of rows)

<pre>
<b>nrow</b>(<em>data frame</em>)

nrow(murders)
</pre>

- In

<pre>
<em>column</em> <b>%in%</b> c(<em>list</em>)

filter(murders, state %in% c("New York", "Texas"))
</pre>
</pre>
