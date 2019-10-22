data.frame

<pre>
grades <- data.frame(names=c("John", "Juan", "Jean", "Yao"),
                      exam_1 = c(95, 80, 90, 85),
                      exam_2 = c(90, 85, 85, 90))
</pre>

<b>data.frame</b> will automatically make strings into <b>factors</b>, to avoid this

<pre>
grades <- data.frame(names=c("John", "Juan", "Jean", "Yao"),
                      exam_1 = c(95, 80, 90, 85),
                      exam_2 = c(90, 85, 85, 90),
                      <b>stringsAsFactors = FALSE</b>)
</pre>
