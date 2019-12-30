## 实验1

Regular exp->NFA->DFA的过程被工具自动化了。

而我们所需要做的，仅仅是为工具提供作为词法规范的正则表达式。



>   简单来说，flex 会将两个%%之间的内容翻译成一个名为 **yylex** 的函数，该函数的作用就是扫描输入文件（默认情况下为标准输入），当扫描到一个完整的、最长的、可以和某条规则的正则表达式所匹配的字符串时，该函数会执行此规则后面的 C 代码。如果这些 C 代码中没有 **return** 语句，则执行完这些 C 代码后， **yylex** 函数会继续运行，开始下一轮的扫描和匹配。
>
>   当有多条规则的模式被匹配到时， **yylex** 会选择匹配长度最长的那条规则，如果有匹配长度相等的规则，则选择排在最前面的规则。

为了处理```/**/```形式的注释，参考[这里](https://stackoverflow.com/questions/2130097/difficulty-getting-c-style-comments-in-flex-lex)和[这里](https://westes.github.io/flex/manual/Start-Conditions.html)。