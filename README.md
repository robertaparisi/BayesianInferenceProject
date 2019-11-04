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



## PROJECT

----------------------------------------------------------------------------

This project try to highlight some evidence for a anti-epileptic drug (progabide). The data that I am using are count data: the response variable represent the number of seizure occurs in a two weeks period, for both people who are treated with progabide and placebo as well. 



Count data are usually modeled with a poisson distribution, in this case the data presented heavy over-dispersion, for this reason I used 5 different models:


1. Basic Poisson;

2. Negative Binomial, where the parameter *r* represent the overdispersion terms (the lower is this parameter, the highest is the overdispersion);

3. Negative Binomial with Random Effects, in the data are present also some random effects due to the variability between the patients and between the patients over the visit period, as well;

4. Poisson with Random Effects;

5. Zero-Inflated Poisson with Random Effects (since there is also some over-representation of zero value wrt to a Poisson distribution);

6. Zero-Inflated Negative Binomial with Random effects.


In every model the Treatment variable had a really important and significative effect, with a negative association with the number of seizure (if using the progabide the number of seizure are lower). The basic poisson have a DIC value higher than the other, confirming that the over-dispersion is an important aspect to understand the variabiliyu of the data. 







