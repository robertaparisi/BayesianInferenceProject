To knit the project in a pdf file install tinytex packages in R, following the code below: 




``` 
install.packages('tinytex')
tinytex:::install_prebuilt()
```



And then test it: 



```
writeLines(c(
  '\\documentclass{article}',
  '\\begin{document}', 'Hello world!', '\\end{document}'
), 'test.tex')
tinytex::pdflatex('test.tex')
```
