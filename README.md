# JavaScript-in-Power-Query

Challenge 70: Coin change problem!
Consider a set of coin denominations as: {1$, 2$, 5$, 10$}.
Determine the number of ways to make 11$ using different combinations of these coins like result table.

For example, the highlighted row means using eleven 1$ coins to make a total of 11$.

[Challenge code](https://www.linkedin.com/posts/omid-motamedisedeh-74aba166_excelchallenge-powerquerychllenge-excel-activity-7209298915345539073-gXKT?utm_source=share&utm_medium=member_desktop)


 JavaScript= Web.Page(
        "<script>
            var output = '{';
            var first = true;
            for (var i = 0; i <= 11; i++) {
                for (var j = 0; j <= 5; j++) {
                    for (var k = 0; k <= 2; k++) {
                        for (var z = 0; z <= 1; z++) {
                            if (i + 2 * j + 5 * k + 10 * z === 11) {
                                if (!first) {
                                    output += ', ';
                                }
                                output += '{' + i + ',' + j + ',' + k + ',' + z + '}';
                                first = false;
                            }
                        }
                    }
                }
            }
            output += '}';
            document.write(output);
        </script>"
    ),
     Result = Table.FromRows(Expression.Evaluate(JavaScript{0}[Data]{0}[Children]{1}[Children]{0}[Text]),{"1$","2$","5$","10$"})
in
 Result
```


