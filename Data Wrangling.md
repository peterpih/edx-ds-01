- Change a Column  

<pre>
<b>mutate</b> - mutate(<em>data frame</em>, <em>column</em> = <em>formula/value</em>)

murders <- mutate(murders, rate = total / population *100000)
</pre>

- Filter Columns

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
install.packages("dyplr")
library(dplyr)
<em>statement</em> <b>%>%</b> </em>statement</em>

murders %>% select(state, region, rate) %>% filter(rate <= 0.71)
</pre>
