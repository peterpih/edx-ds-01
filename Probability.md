<h2>sample</h2>
<pre>
 result <- <b>sample</b>(<em>from array</em>, <em>sample size</em>, <b>replace</b>=<b>TRUE</b>|<b>FALSE</b>)
</pre>

<h2>duplicated</h2>
Are any values in an array duplicated?
<pre>
<b>duplicated</b>(<em>array of values</em>)
</pre>

<h2>any</h2>
Are any values in an array TRUE
<pre>
<b>any(<em>array of values</em>)
</pre>

<h2>duplicate</h2>
For running Monte Carlo simulations
<pre>
<b>duplicate</b>(<em>number of times</em>, 
<b>{</b>
<em>code to repeat</em>
  ...
 <b>}</b>)
</pre>


<h2>sapply</h2>
Apply a function element w3ise to a vector

<pre>
# Birthday example
compute_prob <- function(n, B=10000){
 same_day <- replicate(B, {
   bdays <- sample(1:365, n, replace=TRUE)
    any(duplicated(bdays))
 })
 mean(same_day)
}

n <- seq(1, 60)

<pre>
