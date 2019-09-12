正则化
================
李家翔
2019-03-16

> 家翔哥啊，有关正则的问题，我现在有一个长字符串（由字母和数字组成），要提取某个标识符（AA2）后面的三个字符，额外的条件是标识符（AA2）前面紧挨着的一个字符不能是任何字母，除“ADD”之外，如果不符合上述条件，则返回NA。比如“asdfADDAA2123”=\>123,
> “asdADAA2123”=\>NA。 我只需要这个正则表达式。

``` r
suppressMessages(library(tidyverse))
c("asdfADDAA2123","asdADAA2123") %>% 
    str_match('ADDAA2(\\w{3})') %>% 
    .[,2]
```

    ## [1] "123" NA