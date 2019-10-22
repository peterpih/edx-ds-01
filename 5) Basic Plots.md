- Plot (scatterplot)

<pre>
<b>plot</b>(<em>column</em>, <em>column</em>)

population_in_millions <- murders$population/10^6
total_gun_murders <- murders$total
plot(population_in_millions, total_gun_murders)
</pre>

- Histograms

<pre>
<b>hist</b>(<em>column</em>)

hist(murders$rate)
</pre>

- Boxplots

<pre>
<b>boxplot</b>(<em>column</em>~<em>column</em>, data = <em>dataframe</em>)

boxplot(rate~region, data = murders)
</pre>
