# �ڶ��� ���ݵ�����
�����Ҳ���רҵ����������ģ�������Ҳ��֪����ʵ�е�������ϴ���Ҫ�Ľ����ʲô���ġ�������ͬ�з��ж�˹̩��˵�����������Ҹ��ļ�ͥ�������Ƶģ����ҵļ�ͥ���и��Ĳ��ҡ������Ķ��ĵ����ݸ��и������֮�����õ����ݼ��������Ƶġ�һ�ݺõģ��ɾ���������������ٰ������¼���Ҫ�أ�  
1��ÿһ���۲��������һ��  
2��ÿһ���۲���󹹳�һ��  
3��ÿһ�����͵Ĺ۲ⵥԪ����һ����  
����������Ӵ����β�����ݣ�

```
##   Sepal.Length Sepal.Width Petal.Length Petal.Width Species
## 1          5.1         3.5          1.4         0.2  setosa
## 2          4.9         3.0          1.4         0.2  setosa
## 3          4.7         3.2          1.3         0.2  setosa
## 4          4.6         3.1          1.5         0.2  setosa
## 5          5.0         3.6          1.4         0.2  setosa
```
ÿһ�о��ǹ۲��ָ�꣺���곤�ȣ������ȣ���Ƭ���ȣ���Ƭ��ȣ����ࣻÿһ�о���һ���β���Ĺ۲�ֵ���������ű��Ԫ�ؾ����ĸ���ֵ������һ��������������  

Ȼ�������Ű�Ŀ�������ץ��������������������ô���Ѻã�����˵���ǿ��Կ���������ͨ���������ģ�

```
##   religion <10k 10k-50k 50k-100k
## 1 Agnostic   12      31       23
## 2 Buddhist   58      43       43
## 3 Catholic   79      56       23
```
�����ǣ�

```
##   religion   income freq
## 1 Agnostic     <10k   12
## 2 Agnostic  10k-50k   58
## 3 Agnostic 50k-100k   79
## 4 Buddhist     <10k   31
## 5 Buddhist  10k-50k   43
## 6 Buddhist 50k-100k   56
## 7 Catholic     <10k   23
## 8 Catholic  10k-50k   43
## 9 Catholic 50k-100k   23
```
��Ȼ���������ְ��б�ÿһ�д���һЩ��ֵ��������⣬���ж����������Ϊһ��(�����б�����"<10k","10k-50k","50k-100k"����ͷ�������������Ա���Ϣ"m<10k","m10k-50k","m50k-100k"��"f<10k","f10k-50k","f50k-100k",����m�������ԣ�f����Ů��)�����и����ֵĽ��б�ı����������������У�����Ҳ��ͳ�Ʊ�����  

�����Щ���õ�table����������Ҫ���ľ������ݹ�������������Ϊһ���ɾ������ݼ���  

## ���ݹ���
����en:DAMA�Ķ��壺��������Դ���������ڷ�չ������ҵ�����������ڵ��ʵ��Ľ��������ԡ�ʵ���ͳ��򡱡�����һ���߲�������㷺�Ķ��壬������һ��ֱ���漰���ݹ���ľ�����������ϵ���ݿ�ļ�������ϵĹ���������������Ҫ�����������ݵı������������ݵĺϲ���ּ�ڷ������ݹ���  

���ݹ�������Ҫ���ľ��Ǵ������˽�������ݣ�������ʲô���ı�����ÿһ�д��³���ʲô������õľ���head(),tail().  
����Ҫ���Ļ����Ͼ�����ô�������  
+ ��ÿһ������������������V1��V2������б�Ҫ���Ը���code book��
+ ÿ����������þ��пɶ��ԣ����ǹ���������Ҫ����д������AgeAtDiagnosis�������Զ����AgeDx��
+ ͨ����˵����ý����ݷ���һ�ű����棬�����Ϊ���ݹ��࣬��Ŀ���ӣ��ֳ��˼��ű���ôһ����Ҫ��һ��ʹ����Щ��֮���ܹ�����������������������������  

������UCI��[Human Activity Recognition Using Smartphones Data Set](http://archive.ics.uci.edu/ml/datasets/Human+Activity+Recognition+Using+Smartphones) Ϊ����������������α��һ����������Ҫ������ݡ�������������Ѿ����������ˣ����й������ݵ���ϸ��Ϣ���Բ���read me�ĵ�������UCI������ͨ������һ�������Ϻ��淶�����ݼ�����Ҫ��ָ�������ݼ��ı�����������V1��V2�������ģ�����һ��code book����ô���ǿ����������ݵ����ƣ���feature�ļ��

```r
setwd("F:/coursera/Data Science/peer assignment/get clean and tidy data/UCI HAR Dataset")
name <- read.table("./features.txt", stringsAsFactors = F)
head(name)
```

```
##   V1                V2
## 1  1 tBodyAcc-mean()-X
## 2  2 tBodyAcc-mean()-Y
## 3  3 tBodyAcc-mean()-Z
## 4  4  tBodyAcc-std()-X
## 5  5  tBodyAcc-std()-Y
## 6  6  tBodyAcc-std()-Z
```
���ǿ��Կ�����������������ֱ�ӱ����������Ƿǳ������Ƶģ�����Ϊ���������пɶ��ԣ�������չʾ��������ǰ��6������Ϊ����

```r
variablename <- head(name)
# ����ǩ�еĴ�д��ĸתΪСд����������û�����Բ��ٸ�ֵ�������Ҫȫ��Ϊ��д������ʹ��toupper
tolower(variablename$V2)
```

```
## [1] "tbodyacc-mean()-x" "tbodyacc-mean()-y" "tbodyacc-mean()-z"
## [4] "tbodyacc-std()-x"  "tbodyacc-std()-y"  "tbodyacc-std()-z"
```

```r
# �������������3����
splitNames <- strsplit(variablename$V2, "-")
splitNames[[1]]
```

```
## [1] "tBodyAcc" "mean()"   "X"
```

```r
# ���������ϳ����������
named <- function(x) {
    rr <- paste(x[2], x[1], "-", x[3], sep = "")
    chartr("()", "of", rr)
}
sapply(splitNames, named)
```

```
## [1] "meanoftBodyAcc-X" "meanoftBodyAcc-Y" "meanoftBodyAcc-Z"
## [4] "stdoftBodyAcc-X"  "stdoftBodyAcc-Y"  "stdoftBodyAcc-Z"
```
�����������ָ����ݼ������͸о�������ˣ����ǽ�һЩR�ж��ַ������õĲ��������ܽ����£��������Ƕ��������Ƶ��޸ģ�  
+ sub���滻�ַ����еĵ�һ��ģʽΪ�趨ģʽ(pattern).
+ gsub:ȫ���滻�ַ����е���Ӧģʽ
+ grep,grepl:������������������ˮƽ��ƥ������grep������ƥ������±꣬��grepl�������еĲ�ѯ����������߼�������ʾ��û���ҵ�ƥ�䡣
+ nchar:ͳ���ַ���������Ŀ
+ substr:ȡ�Ӵ�
+ paste:���ַ�������������sep���������������ӷ�
+ str_trim:ȥ���ַ����ո�
  
���������ƽ�����������Ҫ��  
+ Ӣ�ı�������������Сд
+ �����ܵ���������������� (Diagnosis versus Dx)
+ ��Ҫ̫����
+ ��Ҫ���»��ߡ��㡢�ո�  

�ַ��ͱ���Ӧ�����㣺
+ ���������͵�Ӧ��ת��Ϊfactor
+ ���Ӿ����ܾ���һ���������� (���磺���0/1��ʾ��٣���ô��TRUE/FALSE����0/1���ڱ�ʾ�Ա�ʱ��Male/Female����M/F)  

+ Useful link��
 - [R�ַ�������](http://blog.csdn.net/duqi_yc/article/details/9817243)
 
�����������������ݼ��ĺϲ�����Ҫʹ�ú���merge��  
�����������������ݼ��ĺϲ�Ϊ����

```r
df1 <- data.frame(id = sample(1:10), reviewer_id = sample(5:14), time_left = sample(1321:1330), 
    x = rnorm(10))
df2 <- data.frame(id = sample(1:10), answer = rep("B", 10), time_left = sample(321:330), 
    y = rnorm(10))
head(df1, n = 3)
```

```
##   id reviewer_id time_left       x
## 1  3           9      1326 -0.9232
## 2 10           5      1322  2.5069
## 3  1          14      1330  2.2478
```

```r
head(df2, n = 3)
```

```
##   id answer time_left      y
## 1  1      B       329 0.8180
## 2 10      B       327 1.4639
## 3  9      B       323 0.8141
```
merge�������ø�ʽΪ��
```
merge(x, y, by = intersect(names(x), names(y)),
      by.x = by, by.y = by, all = FALSE, all.x = all, all.y = all,
      sort = TRUE, suffixes = c(".x",".y"),
      incomparables = NULL, ...)
```
����˵����  
+ x,y:�������ݿ�
+ by, by.x, by.y:ָ�����ںϲ����е����ơ�
+ all,all.x,all.y:Ĭ�ϵ�all = FALSE�൱����Ȼ����, ����˵���ڲ�����. all.x = TRUE��һ��������, all.y = TRUE��һ��������, all = TRUE �൱��һ���ⲿ����.
  
��ϸ�۲�����3��������ͻᷢ�����еİ��أ�  

```r
mergedData <- merge(df1,df2,by.x="reviewer_id",by.y="id",all=TRUE)
head(mergedData)
```

```
##   reviewer_id id time_left.x      x answer time_left.y       y
## 1           1 NA          NA     NA      B         329  0.8180
## 2           2 NA          NA     NA      B         330 -0.7706
## 3           3 NA          NA     NA      B         325 -0.4851
## 4           4 NA          NA     NA      B         322  0.1801
## 5           5 10        1322 2.5069      B         328 -1.1717
## 6           6  5        1328 0.7141      B         321 -0.4009
```

```r
mergedData <- merge(df1,df2,by.x="id",by.y="id",all=TRUE)
head(mergedData)
```

```
##   id reviewer_id time_left.x        x answer time_left.y       y
## 1  1          14        1330  2.24783      B         329  0.8180
## 2  2          12        1324  1.03181      B         330 -0.7706
## 3  3           9        1326 -0.92317      B         325 -0.4851
## 4  4           7        1321 -0.07841      B         322  0.1801
## 5  5           6        1328  0.71411      B         328 -1.1717
## 6  6          10        1323  0.65413      B         321 -0.4009
```

```r
mergedData2 <- merge(df1,df2,all=TRUE)
head(mergedData2)
```

```
##   id time_left reviewer_id       x answer       y
## 1  1       329          NA      NA      B  0.8180
## 2  1      1330          14  2.2478   <NA>      NA
## 3  2       330          NA      NA      B -0.7706
## 4  2      1324          12  1.0318   <NA>      NA
## 5  3       325          NA      NA      B -0.4851
## 6  3      1326           9 -0.9232   <NA>      NA
```

��plyr���л��ṩ��join��join_all��arrange�Ⱥ�����ʵ�ֱ�����ӣ�������merge��������Ѿ��㹻���ˣ��������ǲ��ڶ�˵����Ȼ���ڼ������ر�õ�����£������еı�����һ�µģ������еĹ۲������һ�µ�ʱ��rbind,cbindҲ�����õġ�   

��Щʱ�����ǻ�����һЩ������ַ��������ڡ�R���ṩ�˸�ʽ�����ĺ���������ʱ�䣺

```r
Sys.setlocale("LC_TIME", "C")
```

```
## [1] "C"
```

```r
x <- c("1jan1960", "2jan1960", "31mar1960", "30jul1960")
z <- as.Date(x, "%d%b%Y")
format(z, "%a %b %d")
```

```
## [1] "Fri Jan 01" "Sat Jan 02" "Thu Mar 31" "Sat Jul 30"
```

```r
weekdays(z)
```

```
## [1] "Friday"   "Saturday" "Thursday" "Saturday"
```

```r
julian(z)
```

```
## [1] -3653 -3652 -3563 -3442
## attr(,"origin")
## [1] "1970-01-01"
```

```r
transform(z, weekend = as.POSIXlt(z, format = "%Y/%m/%d")$wday %in% c(0, 6))
```

```
##       X_data weekend
## 1 1960-01-01   FALSE
## 2 1960-01-02    TRUE
## 3 1960-03-31   FALSE
## 4 1960-07-30    TRUE
```


## ���ݲ���������
˵�����ݲ�������Ҳ��һ��ʮ�ֿ��Ļ��⣬���������Ǿ�����4��������н��ܣ�  
+ ���ݵ�ɸѡ�����ˣ�����һЩ�ض�����ѡ������ɾ��һЩ�۲�
+ ���ݵı任�����ӻ����޸ı���
+ ���ݵĻ��ܣ�����������ݵĺͻ��߾�ֵ
+ ���ݵ����򣺸ı�۲������˳��  

Ȼ���ڽ�����һ��֮ǰ����Ҫ���ľ����˽�������ݣ��������������е�����[Millennium Development Goals](http://databank.worldbank.org/data/views/variableselection/selectvariables.aspx?source=millennium-development-goals)Ϊ������һ������ʾ��ν������ݲ�����

```r
if (!file.exists("C:/Users/yujun/Documents/MDG_Data.csv")) {
  download.file("http://databank.worldbank.org/data/download/MDG_csv.zip","F:/MDG.zip")
  unzip("F:/MDG.zip")
}
MDstats<-read.csv("C:/Users/yujun/Documents/MDG_Data.csv")
```
����������һ�������ݣ�

```r
head(MDstats)
```

```
##   Country.Name Country.Code
## 1  Afghanistan          AFG
## 2  Afghanistan          AFG
## 3  Afghanistan          AFG
## 4  Afghanistan          AFG
## 5  Afghanistan          AFG
## 6  Afghanistan          AFG
##                                                              Indicator.Name
## 1             Adolescent fertility rate (births per 1,000 women ages 15-19)
## 2                                  Agricultural support estimate (% of GDP)
## 3                                  AIDS estimated deaths (UNAIDS estimates)
## 4            Annual freshwater withdrawals, total (% of internal resources)
## 5 Antiretroviral therapy coverage (% of people with advanced HIV infection)
## 6          ARI treatment (% of children under 5 taken to a health provider)
##      Indicator.Code X1990 X1991 X1992 X1993 X1994 X1995 X1996  X1997 X1998
## 1       SP.ADO.TFRT 167.5 168.1 168.7   169 169.3 169.5 169.8 170.06 166.1
## 2 NY.AGR.SUBS.GD.ZS    NA    NA    NA    NA    NA    NA    NA     NA    NA
## 3    SH.DYN.AIDS.DH 100.0 100.0 100.0   100 100.0 100.0 100.0 100.00 100.0
## 4    ER.H2O.FWTL.ZS    NA    NA    NA    NA    NA    NA    NA  55.38    NA
## 5    SH.HIV.ARTC.ZS    NA    NA    NA    NA    NA    NA    NA     NA    NA
## 6    SH.STA.ARIC.ZS    NA    NA    NA    NA    NA    NA    NA     NA    NA
##   X1999 X2000 X2001  X2002 X2003 X2004 X2005 X2006  X2007 X2008 X2009
## 1 162.2 158.3 154.4 150.50 143.9 137.3 130.7 124.1 117.47 111.3 105.2
## 2    NA    NA    NA     NA    NA    NA    NA    NA     NA    NA    NA
## 3 100.0 100.0 200.0 200.00 200.0 200.0 200.0 200.0 200.00 200.0 500.0
## 4    NA    NA    NA  43.01    NA    NA    NA    NA  43.01    NA    NA
## 5    NA    NA    NA     NA    NA    NA    NA    NA     NA    NA   1.0
## 6    NA    NA    NA     NA    NA    NA    NA    NA     NA    NA    NA
##   X2010  X2011  X2012 X2013
## 1  99.1  92.97  86.84    NA
## 2    NA     NA     NA    NA
## 3 500.0 500.00 500.00    NA
## 4    NA  43.01     NA    NA
## 5   4.0   9.00   8.00    NA
## 6    NA  60.50     NA    NA
```

```r
tail(MDstats)
```

```
##       Country.Name Country.Code
## 33093     Zimbabwe          ZWE
## 33094     Zimbabwe          ZWE
## 33095     Zimbabwe          ZWE
## 33096     Zimbabwe          ZWE
## 33097     Zimbabwe          ZWE
## 33098     Zimbabwe          ZWE
##                                                      Indicator.Name
## 33093   Tuberculosis treatment success rate (% of registered cases)
## 33094  Unmet need for contraception (% of married women ages 15-49)
## 33095 Use of insecticide-treated bed nets (% of under-5 population)
## 33096        Vulnerable employment, female (% of female employment)
## 33097            Vulnerable employment, male (% of male employment)
## 33098          Vulnerable employment, total (% of total employment)
##          Indicator.Code X1990 X1991 X1992 X1993 X1994 X1995 X1996 X1997
## 33093    SH.TBS.CURE.ZS    NA    NA    NA    NA  52.0    53    32  69.0
## 33094       SP.UWT.TFRT    NA    NA    NA    NA    NA    NA    NA    NA
## 33095    SH.MLR.NETS.ZS    NA    NA    NA    NA    NA    NA    NA    NA
## 33096 SL.EMP.VULN.FE.ZS    NA    NA    NA    NA  81.6    NA    NA  77.4
## 33097 SL.EMP.VULN.MA.ZS    NA    NA    NA    NA  46.5    NA    NA  43.3
## 33098    SL.EMP.VULN.ZS    NA    NA    NA    NA  63.6    NA    NA  60.3
##       X1998 X1999 X2000 X2001 X2002 X2003 X2004 X2005 X2006 X2007 X2008
## 33093    70  73.0    69    71  67.0    66    54    68  60.0    78    74
## 33094    NA    NA    NA    NA    NA    NA    NA    NA  12.8    NA    NA
## 33095    NA    NA    NA    NA    NA    NA    NA    NA   2.9    NA    NA
## 33096    NA  76.8    NA    NA  76.5    NA    NA    NA    NA    NA    NA
## 33097    NA  44.5    NA    NA  48.4    NA    NA    NA    NA    NA    NA
## 33098    NA  60.3    NA    NA  61.9    NA    NA    NA    NA    NA    NA
##       X2009 X2010 X2011 X2012 X2013
## 33093  78.0    81  81.0    NA    NA
## 33094    NA    NA  14.6    NA    NA
## 33095  17.3    NA   9.7    NA    NA
## 33096    NA    NA    NA    NA    NA
## 33097    NA    NA    NA    NA    NA
## 33098    NA    NA    NA    NA    NA
```
������Ȼ�������ⲻ��һ��tidy data����ô�����Ƚ���任Ϊ����ϲ����tidy data��֮���ٿ�������ժҪ�����ݼ�����Ԫ�����ԣ�

```
##   countryname countrycode
## 1 Afghanistan         AFG
## 2 Afghanistan         AFG
## 3 Afghanistan         AFG
## 4 Afghanistan         AFG
## 5 Afghanistan         AFG
## 6 Afghanistan         AFG
##                                                               indicatorname
## 1             Adolescent fertility rate (births per 1,000 women ages 15-19)
## 2                                  Agricultural support estimate (% of GDP)
## 3                                  AIDS estimated deaths (UNAIDS estimates)
## 4            Annual freshwater withdrawals, total (% of internal resources)
## 5 Antiretroviral therapy coverage (% of people with advanced HIV infection)
## 6          ARI treatment (% of children under 5 taken to a health provider)
##       indicatorcode  year value
## 1       SP.ADO.TFRT X1990 167.5
## 2 NY.AGR.SUBS.GD.ZS X1990    NA
## 3    SH.DYN.AIDS.DH X1990 100.0
## 4    ER.H2O.FWTL.ZS X1990    NA
## 5    SH.HIV.ARTC.ZS X1990    NA
## 6    SH.STA.ARIC.ZS X1990    NA
```


```r
summary(MDstatsMelt)
```

```
##          countryname      countrycode    
##  Afghanistan   :  3216   ABW    :  3216  
##  Albania       :  3216   ADO    :  3216  
##  Algeria       :  3216   AFG    :  3216  
##  American Samoa:  3216   AGO    :  3216  
##  Andorra       :  3216   ALB    :  3216  
##  Angola        :  3216   ARB    :  3216  
##  (Other)       :775056   (Other):775056  
##                                                                    indicatorname   
##  Adolescent fertility rate (births per 1,000 women ages 15-19)            :  5928  
##  Agricultural support estimate (% of GDP)                                 :  5928  
##  AIDS estimated deaths (UNAIDS estimates)                                 :  5928  
##  Annual freshwater withdrawals, total (% of internal resources)           :  5928  
##  Antiretroviral therapy coverage (% of people with advanced HIV infection):  5928  
##  ARI treatment (% of children under 5 taken to a health provider)         :  5928  
##  (Other)                                                                  :758784  
##            indicatorcode         year            value          
##  AG.LND.FRST.K2   :  5928   X1990  : 33098   Min.   :-9.43e+08  
##  AG.LND.FRST.ZS   :  5928   X1991  : 33098   1st Qu.: 1.10e+01  
##  DC.ODA.COMM.CD   :  5928   X1992  : 33098   Median : 5.10e+01  
##  DC.ODA.COMM.SA.CD:  5928   X1993  : 33098   Mean   : 2.26e+10  
##  DC.ODA.SOCL.CD   :  5928   X1994  : 33098   3rd Qu.: 9.80e+01  
##  DC.ODA.SOCL.ZS   :  5928   X1995  : 33098   Max.   : 7.53e+13  
##  (Other)          :758784   (Other):595764   NA's   :495519
```

```r
str(MDstatsMelt)
```

```
## 'data.frame':	794352 obs. of  6 variables:
##  $ countryname  : Factor w/ 247 levels "Afghanistan",..: 1 1 1 1 1 1 1 1 1 1 ...
##  $ countrycode  : Factor w/ 247 levels "ABW","ADO","AFG",..: 3 3 3 3 3 3 3 3 3 3 ...
##  $ indicatorname: Factor w/ 134 levels "Adolescent fertility rate (births per 1,000 women ages 15-19)",..: 1 2 3 4 5 6 7 8 9 10 ...
##  $ indicatorcode: Factor w/ 134 levels "AG.LND.FRST.K2",..: 120 39 64 30 72 82 129 130 131 132 ...
##  $ year         : Factor w/ 24 levels "X1990","X1991",..: 1 1 1 1 1 1 1 1 1 1 ...
##  $ value        : num  168 NA 100 NA NA ...
```
���ǿ��Կ���������ֵ���ݵķ�λ����

```r
quantile(MDstatsMelt$value,na.rm=TRUE)
```

```
##         0%        25%        50%        75%       100% 
## -9.431e+08  1.054e+01  5.060e+01  9.843e+01  7.526e+13
```
�����������ҵ�ͳ�������ж��٣�

```r
table(MDstatsMelt$countrycode)
```

```
## 
##  ABW  ADO  AFG  AGO  ALB  ARB  ARE  ARG  ARM  ASM  ATG  AUS  AUT  AZE  BDI 
## 3216 3216 3216 3216 3216 3216 3216 3216 3216 3216 3216 3216 3216 3216 3216 
##  BEL  BEN  BFA  BGD  BGR  BHR  BHS  BIH  BLR  BLZ  BMU  BOL  BRA  BRB  BRN 
## 3216 3216 3216 3216 3216 3216 3216 3216 3216 3216 3216 3216 3216 3216 3216 
##  BTN  BWA  CAF  CAN  CEB  CHE  CHI  CHL  CHN  CIV  CMR  COG  COL  COM  CPV 
## 3216 3216 3216 3216 3216 3216 3216 3216 3216 3216 3216 3216 3216 3216 3216 
##  CRI  CSS  CUB  CUW  CYM  CYP  CZE  DEU  DJI  DMA  DNK  DOM  DZA  EAP  EAS 
## 3216 3216 3216 3216 3216 3216 3216 3216 3216 3216 3216 3216 3216 3216 3216 
##  ECA  ECS  ECU  EGY  EMU  ERI  ESP  EST  ETH  EUU  FCS  FIN  FJI  FRA  FRO 
## 3216 3216 3216 3216 3216 3216 3216 3216 3216 3216 3216 3216 3216 3216 3216 
##  FSM  GAB  GBR  GEO  GHA  GIN  GMB  GNB  GNQ  GRC  GRD  GRL  GTM  GUM  GUY 
## 3216 3216 3216 3216 3216 3216 3216 3216 3216 3216 3216 3216 3216 3216 3216 
##  HIC  HKG  HND  HPC  HRV  HTI  HUN  IDN  IMY  IND  IRL  IRN  IRQ  ISL  ISR 
## 3216 3216 3216 3216 3216 3216 3216 3216 3216 3216 3216 3216 3216 3216 3216 
##  ITA  JAM  JOR  JPN  KAZ  KEN  KGZ  KHM  KIR  KNA  KOR  KSV  KWT  LAC  LAO 
## 3216 3216 3216 3216 3216 3216 3216 3216 3216 3216 3216 3216 3216 3216 3216 
##  LBN  LBR  LBY  LCA  LCN  LDC  LIC  LIE  LKA  LMC  LMY  LSO  LTU  LUX  LVA 
## 3216 3216 3216 3216 3216 3216 3216 3216 3216 3216 3216 3216 3216 3216 3216 
##  MAC  MAF  MAR  MCO  MDA  MDG  MDV  MEA  MEX  MHL  MIC  MKD  MLI  MLT  MMR 
## 3216 3216 3216 3216 3216 3216 3216 3216 3216 3216 3216 3216 3216 3216 3216 
##  MNA  MNE  MNG  MNP  MOZ  MRT  MUS  MWI  MYS  NAC  NAM  NCL  NER  NGA  NIC 
## 3216 3216 3216 3216 3216 3216 3216 3216 3216 3216 3216 3216 3216 3216 3216 
##  NLD  NOC  NOR  NPL  NZL  OEC  OED  OMN  OSS  PAK  PAN  PER  PHL  PLW  PNG 
## 3216 3216 3216 3216 3216 3216 3216 3216 3216 3216 3216 3216 3216 3216 3216 
##  POL  PRI  PRK  PRT  PRY  PSS  PYF  QAT  ROM  RUS  RWA  SAS  SAU  SDN  SEN 
## 3216 3216 3216 3216 3216 3216 3216 3216 3216 3216 3216 3216 3216 3216 3216 
##  SGP  SLB  SLE  SLV  SMR  SOM  SRB  SSA  SSD  SSF  SST  STP  SUR  SVK  SVN 
## 3216 3216 3216 3216 3216 3216 3216 3216 3216 3216 3216 3216 3216 3216 3216 
##  SWE  SWZ  SXM  SYC  SYR  TCA  TCD  TGO  THA  TJK  TKM  TMP  TON  TTO  TUN 
## 3216 3216 3216 3216 3216 3216 3216 3216 3216 3216 3216 3216 3216 3216 3216 
##  TUR  TUV  TZA  UGA  UKR  UMC  URY  USA  UZB  VCT  VEN  VIR  VNM  VUT  WBG 
## 3216 3216 3216 3216 3216 3216 3216 3216 3216 3216 3216 3216 3216 3216 3216 
##  WLD  WSM  YEM  ZAF  ZAR  ZMB  ZWE 
## 3216 3216 3216 3216 3216 3216 3216
```
����ȱʧֵ��

```r
sum(is.na(MDstatsMelt$value))  #�ܵ�ȱʧֵ
```

```
## [1] 495519
```

```r
colSums(is.na(MDstatsMelt))  #ÿһ�е�ȱʧֵ
```

```
##   countryname   countrycode indicatorname indicatorcode          year 
##             0             0             0             0             0 
##         value 
##        495519
```

```r
# ��������û�tidyǰ�����ݼ�����ô����������ԵñȽ�����
colSums(is.na(MDstats))
```

```
##   Country.Name   Country.Code Indicator.Name Indicator.Code          X1990 
##              0              0              0              0          23059 
##          X1991          X1992          X1993          X1994          X1995 
##          22293          21672          21753          21491          20970 
##          X1996          X1997          X1998          X1999          X2000 
##          20680          20448          20419          19933          18822 
##          X2001          X2002          X2003          X2004          X2005 
##          19598          19119          19478          19269          18704 
##          X2006          X2007          X2008          X2009          X2010 
##          19044          18641          19256          19162          18756 
##          X2011          X2012          X2013 
##          20360          21967          30625
```

```r
# �ȼ۵Ĵ���ʽ
stat <- function(x) {
    sum(is.na(x))
}
tapply(MDstatsMelt$value, MDstatsMelt$year, stat)
```

```
## X1990 X1991 X1992 X1993 X1994 X1995 X1996 X1997 X1998 X1999 X2000 X2001 
## 23059 22293 21672 21753 21491 20970 20680 20448 20419 19933 18822 19598 
## X2002 X2003 X2004 X2005 X2006 X2007 X2008 X2009 X2010 X2011 X2012 X2013 
## 19119 19478 19269 18704 19044 18641 19256 19162 18756 20360 21967 30625
```
ͳ��ĳ�����ҵ�ͳ������ռ��ͳ����Ŀ�Ķ���

```r
table(MDstatsMelt$countryname %in% c("China"))
```

```
## 
##  FALSE   TRUE 
## 791136   3216
```

```r
prop <- table(MDstatsMelt$countryname %in% c("China"))[2]/sum(table(MDstatsMelt$countryname %in% c("China")))
prop
```

```
##     TRUE 
## 0.004049
```

�������ݼ��Ĵ�С��

```r
object.size(MDstatsMelt)
```

```
## 22301832 bytes
```

```r
print(object.size(MDstatsMelt),units="Mb")
```

```
## 21.3 Mb
```
���ˣ����ǿ���˵���Ƕ���������һ�����˽⡣����ֵ��һ����ǣ�����ĳЩ�ض������ݣ�Ҳ��xtabs��ftable�����õġ�  

### ���ݵ�ɸѡ
Ҫ��ȡ��Ӧ���ݵ����ݣ���Ϊ���õľ�����ȡ��ӦԪ�أ�������ȡĳ��Ԫ�أ���ȡĳһ�У�ĳһ�С�����ͨ�����������������ѧϰ��

```r
data<-data.frame(a=sample(1:10),b=rep(c("a","b"),each=5),cdf=rnorm(10))
data
```

```
##     a b     cdf
## 1   1 a  0.5755
## 2  10 a  0.8087
## 3   2 a  0.9810
## 4   7 a -0.4635
## 5   4 a  0.5094
## 6   6 b  1.0514
## 7   5 b -1.5338
## 8   9 b  1.0047
## 9   3 b  1.0004
## 10  8 b -1.3566
```

```r
#��ȡ��ӦԪ��
data[2,1]
```

```
## [1] 10
```

```r
data[[1]][[2]]
```

```
## [1] 10
```

```r
data[[c(1,2)]]
```

```
## [1] 10
```

```r
data$a[2]
```

```
## [1] 10
```

```r
#��ȡĳһ��
data[[3]]
```

```
##  [1]  0.5755  0.8087  0.9810 -0.4635  0.5094  1.0514 -1.5338  1.0047
##  [9]  1.0004 -1.3566
```

```r
data$cdf
```

```
##  [1]  0.5755  0.8087  0.9810 -0.4635  0.5094  1.0514 -1.5338  1.0047
##  [9]  1.0004 -1.3566
```

```r
data$c
```

```
##  [1]  0.5755  0.8087  0.9810 -0.4635  0.5094  1.0514 -1.5338  1.0047
##  [9]  1.0004 -1.3566
```

```r
data[["c"]]
```

```
## NULL
```

```r
data[["c", exact = FALSE]]
```

```
##  [1]  0.5755  0.8087  0.9810 -0.4635  0.5094  1.0514 -1.5338  1.0047
##  [9]  1.0004 -1.3566
```
���ݵ�ɸѡ����һ����Ϊ���õĵľ����Ƴ�ȱʧֵ��

```r
data<-data.frame(a=c(sample(1:5),NA,NA,sample(6:10)),b=c(rep(c("a","b"),each=5),NA,NA),cdf=rnorm(12))
data
```

```
##     a    b       cdf
## 1   5    a -0.276400
## 2   1    a -1.861240
## 3   3    a -2.028003
## 4   4    a -0.348072
## 5   2    a  0.937975
## 6  NA    b -1.220922
## 7  NA    b  0.004012
## 8   9    b -0.133295
## 9   7    b -0.596801
## 10  8    b  1.233629
## 11 10 <NA>  0.762653
## 12  6 <NA>  0.162045
```

```r
good <- complete.cases(data)
data[good, ]
```

```
##    a b     cdf
## 1  5 a -0.2764
## 2  1 a -1.8612
## 3  3 a -2.0280
## 4  4 a -0.3481
## 5  2 a  0.9380
## 8  9 b -0.1333
## 9  7 b -0.5968
## 10 8 b  1.2336
```

```r
bad <- as.data.frame(is.na(data))
data[!(bad$a|bad$b|bad$c),]
```

```
##    a b     cdf
## 1  5 a -0.2764
## 2  1 a -1.8612
## 3  3 a -2.0280
## 4  4 a -0.3481
## 5  2 a  0.9380
## 8  9 b -0.1333
## 9  7 b -0.5968
## 10 8 b  1.2336
```

����ɸѡ��ʱ��Ϊ�˻�÷������������ݣ�

```r
X <- data.frame("var1"=sample(1:5),"var2"=sample(6:10),"var3"=sample(11:15))
X <- X[sample(1:5),]; X$var2[c(1,3)] = NA
X
```

```
##   var1 var2 var3
## 2    5   NA   13
## 5    3    6   15
## 1    2   NA   12
## 3    1    8   11
## 4    4    9   14
```

```r
X[(X$var1 <= 3 & X$var3 > 11),]
```

```
##   var1 var2 var3
## 5    3    6   15
## 1    2   NA   12
```

```r
subset(X,(X$var1 <= 3 & X$var3 > 11))
```

```
##   var1 var2 var3
## 5    3    6   15
## 1    2   NA   12
```

```r
X[(X$var1 <= 3 | X$var3 > 15),]
```

```
##   var1 var2 var3
## 5    3    6   15
## 1    2   NA   12
## 3    1    8   11
```

```r
X[which(X$var1 <= 3 | X$var3 > 15),]
```

```
##   var1 var2 var3
## 5    3    6   15
## 1    2   NA   12
## 3    1    8   11
```

����ȡ�Ӽ��ĺ���subset���ڰ����ĵ�����һ��warning��ֵ������ע��ģ���This is a convenience function intended for use interactively. For programming it is better to use the standard subsetting functions like [, and in particular the non-standard evaluation of argument subset can have unanticipated consequences."

### ���ݵı任
���������ݱ任�����У�  
+ abs(x) ����ֵ
+ sqrt(x) ������
+ ceiling(x) �����ߣ�����ceiling(3.475) = 4
+ floor(x) �����ߣ�����floor(3.475) = 3
+ round(x,digits=n) �������룬����round(3.475,digits=2) = 3.48
+ signif(x,digits=n) �������룬����signif(3.475,digits=2) = 3.5
+ cos(x), sin(x) etc.���Ǳ任
+ log(x) �����任
+ log2(x), log10(x) ��2��10Ϊ�׵Ķ����任
+ exp(x) ָ���任  


�������⣬���ǻ����������ݼӱ�ǩ�������ڻع��в�����ЧӦ��������MASS����shuttle���ݼ�Ϊ��,��֪����ͬ���͵ķ�(wind)�Ƿ���Ҫʹ�ò�ͬ��װ�ػ�(use)����������ϣ����head wind���Ϊ1��auto useҲ��Ϊ1�����ǿ��԰������°취�������������

```r
library(MASS)
data(shuttle)
head(shuttle)
```

```
##   stability error sign wind   magn vis  use
## 1     xstab    LX   pp head  Light  no auto
## 2     xstab    LX   pp head Medium  no auto
## 3     xstab    LX   pp head Strong  no auto
## 4     xstab    LX   pp tail  Light  no auto
## 5     xstab    LX   pp tail Medium  no auto
## 6     xstab    LX   pp tail Strong  no auto
```

```r
## Make our own variables just for illustration
shuttle$auto <- 1 * (shuttle$use == "auto")
shuttle$headwind <- 1 * (shuttle$wind == "head")
head(shuttle)
```

```
##   stability error sign wind   magn vis  use auto headwind
## 1     xstab    LX   pp head  Light  no auto    1        1
## 2     xstab    LX   pp head Medium  no auto    1        1
## 3     xstab    LX   pp head Strong  no auto    1        1
## 4     xstab    LX   pp tail  Light  no auto    1        0
## 5     xstab    LX   pp tail Medium  no auto    1        0
## 6     xstab    LX   pp tail Strong  no auto    1        0
```
��Ȼ�����������ͱ�����relevel����������ģ�͵ķ�����Ҳ����ȡ�õȼ�Ч���ġ�  

��Щʱ�����ǻ�����������������ɢ������ʱ������Ҫ�õ�����cut��

```r
data <- rnorm(1000)
table(cut(data, breaks = quantile(data)))
```

```
## 
##  (-3.28,-0.637] (-0.637,0.0321]  (0.0321,0.672]    (0.672,3.37] 
##             249             250             250             250
```

```r
library(Hmisc)
table(cut2(data, g = 4))
```

```
## 
## [-3.2847,-0.6372) [-0.6372, 0.0334) [ 0.0334, 0.6829) [ 0.6829, 3.3704] 
##               250               250               250               250
```

```r
detach("package:Hmisc", unload = TRUE)
```
��÷������������ֻ��Ҫ������������������ͳɹ���ʵ�������ݵ���ɢ����

### ���ݵĻ���
�����ݽ��л��ܣ��������������Ҳ�Ƚϳ��õģ�������л�����ͣ����ֵ�����λ����

```r
data <- matrix(1:16, 4, 4)
data
```

```
##      [,1] [,2] [,3] [,4]
## [1,]    1    5    9   13
## [2,]    2    6   10   14
## [3,]    3    7   11   15
## [4,]    4    8   12   16
```

```r
apply(data, 2, mean)
```

```
## [1]  2.5  6.5 10.5 14.5
```

```r
apply(data, 1, sum)
```

```
## [1] 28 32 36 40
```

```r
apply(data, 1, quantile, probs = c(0.25, 0.75))
```

```
##     [,1] [,2] [,3] [,4]
## 25%    4    5    6    7
## 75%   10   11   12   13
```

```r
apply(data, 2, quantile, probs = c(0.25, 0.75))
```

```
##     [,1] [,2]  [,3]  [,4]
## 25% 1.75 5.75  9.75 13.75
## 75% 3.25 7.25 11.25 15.25
```
��ʱ��Ϊ�˸���Щ�����ǻ���һЩ�������apply��
+ rowSums = apply(x, 1, sum)
+ rowMeans = apply(x, 1, mean)
+ colSums = apply(x, 2, sum)
+ colMeans = apply(x, 2, mean)
  
������ʱҲ�ᴦ��һЩ�б����б�ķ���������ǻ��õ�sapply,lapply����ͬ����ǰ�߷���һ����������󣬺��߷���һ���б�����

```r
x <- list(a = 1:10, beta = exp(-3:3), logic = c(TRUE,FALSE,FALSE,TRUE))
lapply(x, mean)
```

```
## $a
## [1] 5.5
## 
## $beta
## [1] 4.535
## 
## $logic
## [1] 0.5
```

```r
sapply(x, mean)
```

```
##     a  beta logic 
## 5.500 4.535 0.500
```

```r
# median and quartiles for each list element
lapply(x, quantile, probs = 1:3/4)
```

```
## $a
##  25%  50%  75% 
## 3.25 5.50 7.75 
## 
## $beta
##    25%    50%    75% 
## 0.2516 1.0000 5.0537 
## 
## $logic
## 25% 50% 75% 
## 0.0 0.5 1.0
```

```r
sapply(x, quantile)
```

```
##          a     beta logic
## 0%    1.00  0.04979   0.0
## 25%   3.25  0.25161   0.0
## 50%   5.50  1.00000   0.5
## 75%   7.75  5.05367   1.0
## 100% 10.00 20.08554   1.0
```

��ʱ�����ǻ�����з�����ܣ���ͳ����Ů���ʾ�ֵ,��ʱ�������tapply��

```r
group <- (rbinom(32, n = 20, prob = 0.4))
groups <- factor(rep(1:2,10))
tapply(group, groups, length) 
```

```
##  1  2 
## 10 10
```

```r
tapply(group, groups, sum)
```

```
##   1   2 
## 135 122
```

```r
tapply(group, groups, mean)
```

```
##    1    2 
## 13.5 12.2
```

### ���ݵ�����
���ݵ�������Ҫ�õ��ĺ�����������sort��order������sort��������Ľ����order���ض�Ӧ���ݵ�����������

```r
X <- data.frame("var1"=sample(1:5),"var2"=sample(6:10),"var3"=sample(11:15))
X <- X[sample(1:5),]
X$var2[c(1,3)] <- NA
sort(X$var2,decreasing=TRUE)
```

```
## [1] 9 8 6
```

```r
sort(X$var2,decreasing=TRUE,na.last=TRUE)
```

```
## [1]  9  8  6 NA NA
```

```r
order(X$var2,decreasing=TRUE)
```

```
## [1] 2 5 4 1 3
```

```r
order(X$var2,decreasing=TRUE,na.last=TRUE)
```

```
## [1] 2 5 4 1 3
```

```r
X[order(X$var2),]
```

```
##   var1 var2 var3
## 2    1    6   13
## 5    5    8   15
## 4    4    9   11
## 1    2   NA   14
## 3    3   NA   12
```

```r
#deal with the link
X$var2[c(1)] <- sample(na.omit(X$var2),1)
X[order(X$var2,X$var3),]
```

```
##   var1 var2 var3
## 2    1    6   13
## 5    5    8   15
## 4    4    9   11
## 1    2    9   14
## 3    3   NA   12
```
��Щʱ�򣬸�Ϊǿ���aggregate������������Ҫ�ģ�������R���������ݼ�state.x77Ϊ����

```r
aggregate(state.x77,
          list(Region = state.region,
               Cold = state.x77[,"Frost"] > 130),
          mean)
```

```
##          Region  Cold Population Income Illiteracy Life Exp Murder HS Grad
## 1     Northeast FALSE     8802.8   4780     1.1800    71.13  5.580   52.06
## 2         South FALSE     4208.1   4012     1.7375    69.71 10.581   44.34
## 3 North Central FALSE     7233.8   4633     0.7833    70.96  8.283   53.37
## 4          West FALSE     4582.6   4550     1.2571    71.70  6.829   60.11
## 5     Northeast  TRUE     1360.5   4308     0.7750    71.44  3.650   56.35
## 6 North Central  TRUE     2372.2   4589     0.6167    72.58  2.267   55.67
## 7          West  TRUE      970.2   4880     0.7500    70.69  7.667   64.20
##    Frost   Area
## 1 110.60  21839
## 2  64.62  54605
## 3 120.00  56737
## 4  51.00  91864
## 5 160.50  13519
## 6 157.67  68568
## 7 161.83 184162
```
��Ȼ�����ﻹ��һ����Ϊ���������ĺ�����split�����԰����㽫���ݷ�Ϊ������������������ı������һ��һ�ŵĴ������ǣ�

```r
library(datasets)
head(airquality)
```

```
##   Ozone Solar.R Wind Temp Month Day
## 1    41     190  7.4   67     5   1
## 2    36     118  8.0   72     5   2
## 3    12     149 12.6   74     5   3
## 4    18     313 11.5   62     5   4
## 5    NA      NA 14.3   56     5   5
## 6    28      NA 14.9   66     5   6
```

```r
s <- split(airquality, airquality$Month)
lapply(s, function(x) colMeans(x[, c("Ozone", "Solar.R", "Wind")]))
```

```
## $`5`
##   Ozone Solar.R    Wind 
##      NA      NA   11.62 
## 
## $`6`
##   Ozone Solar.R    Wind 
##      NA  190.17   10.27 
## 
## $`7`
##   Ozone Solar.R    Wind 
##      NA 216.484   8.942 
## 
## $`8`
##   Ozone Solar.R    Wind 
##      NA      NA   8.794 
## 
## $`9`
##   Ozone Solar.R    Wind 
##      NA  167.43   10.18
```

## Useful link��
  - Hadley Wickham��[Tidy Data](http://vita.had.co.nz/papers/tidy-data.pdf)
  - Phil Spector��[Data Manipulation with R](http://link.springer.com/book/10.1007/978-0-387-74731-6)
  - coursera  material:[How to share data with a statistician](https://github.com/yujunbeta/datasharing)











