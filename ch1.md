## ��һ���֣�������Ϣ

�����У����������Ÿ��ָ��������ݣ�������ĳɼ��������繫˾�Ĳ��񱨱���������Ȧ��һЩ״̬������΢�����һ������������������Ĵ�����ʱ����һ����Ҫ�����������ݵĶ�������variety����  
Ҳ�����ڴ��������������ģ�

```
##   Sepal.Length Sepal.Width Petal.Length Petal.Width Species
## 1          5.1         3.5          1.4         0.2  setosa
## 2          4.9         3.0          1.4         0.2  setosa
## 3          4.7         3.2          1.3         0.2  setosa
## 4          4.6         3.1          1.5         0.2  setosa
## 5          5.0         3.6          1.4         0.2  setosa
```
Ȼ����ʵ���������ٵ�����ȷʵ�����ģ�
```
@HWI-EAS121:4:100:1783:550#0/1
CGTTACGAGATCGGAAGAGCGGTTCAGCAGGAATGCCGAGACGGATCTCGTATGCGGTCTGCTGCGTGACAAGACAGGGG
+HWI-EAS121:4:100:1783:550#0/1
aaaaa`b_aa`aa`YaX]aZ`aZM^Z]YRa]YSG[[ZREQLHESDHNDDHNMEEDDMPENITKFLFEEDDDHEJQMEDDD
@HWI-EAS121:4:100:1783:1611#0/1
GGGTGGGCATTTCCACTCGCAGTATGGGTTGCCGCACGACAGGCAGCGGTCAGCCTGCGCTTTGGCCTGGCCTTCGGAAA
+HWI-EAS121:4:100:1783:1611#0/1
a``^\__`_```^a``a`^a_^__]a_]\]`a______`_^^`]X]_]XTV_\]]NX_XVX]]_TTTTG[VTHPN]VFDZ
@HWI-EAS121:4:100:1783:322#0/1
CGTTTATGTTTTTGAATATGTCTTATCTTAACGGTTATATTTTAGATGTTGGTCTTATTCTAACGGTCATATATTTTCTA

```
���������ģ�
```
{
    "uid": 10438,
    "result": [
        {
            "day": "2011-12-12",
            "followers_count": "63",   //��˿��
            "v_followers_count": "18", //V��˿��
            "daren_followers_count": "18", //���˷�˿��
            "friends_count": "58",    //��ע��
            "v_friends_count": "58",  //V��ע��
            "statuses_count": "258",   //΢����
            "bi_followers_count": "18",  //������
            "repost_count": "115", //ת����
            "comments_count": "178",   //������
        },
        ...
    ]
}

```
��ô�������ȥ������Щ���ݣ�������η�����Щ���ݣ����������ҵ�������Ҫ�Ķ����أ����ǽ�����ν���Щ���ݵ���R�п�ʼ������ѧϰ��δ�������������ߵĴ����ݡ�  
# ��һ�� ���ݵĵ���
��Ը��ָ������ӵ����ݣ����Ƿ����ĵ�һ�����ǻ�ȡ���ݲ����䵼��R�С�

### �����ϻ�ȡ����

�����ݵ�һ����Ҫ����Դ���ǻ��������������ϻ�ȡ���ݲ����������Ƿǳ���Ҫ�ġ�Ϊ�˵õ���Щ���ݣ�һ����ͨ�����������������һ����վ���ҵ��������ӣ�Ȼ���Ҽ�->Ŀ�����Ϊ�����ӱ����ļ����е���R���������Ҫ���ص������ļ���Ŀ�Ƚ϶࣬����ô���ʹ�һ����ͨ���꽵��Ϊ�˶������ꡣ  
Ϊ��Ӧ����Ҫ���ض���ļ��������R�ṩ�˺���download.file()��ʹ��R���Դӻ�������ֱ�Ӱ�����ק����������ø�ʽΪ��
```
download.file(url, destfile, method, quiet = FALSE, mode = "w",
              cacheOK = TRUE,
              extra = getOption("download.file.extra"))

```
��Ҫ�Ĳ���Ϊ��  
+ url:�ļ������ڵ�ַ
+ destfile:���غ��ļ��ı����ַ��Ĭ��Ϊ����Ŀ¼
+ method:  �ṩ"internal", "wget", "curl" �� "lynx"����method����windows��ͨ��internal���ܽ������������⣬�����㲻������Cygwin, gnuwin32���ֵ�"wget"�Ϳ��Ը㶨��windows�Ķ������ļ��á�curl�������method����Mac���û���˵�Ƕ�Ҫ���õģ���lynx����Ҫ���historical interest��  

##### �÷���������ȡ���й�˾�ʲ���ծ��
����˵����Ҫ��ȡһϵ�е����й�˾�������ݣ����Ǿ�Ҫ�õ����ǵ��ʲ���ծ����Ȼ�������Ǯ��wind���ݿ⣬һ��Ҳ�Ͳ��ò����ˡ������������ѧУ���ò������ݿ�Ļ���һ����������İ취���Ǵ����˲ƾ�����ק���ݣ��԰�������(600816) �ʲ���ծ��Ϊ��������Է���[���˲ƾ�](http://vip.stock.finance.sina.com.cn/corp/go.php/vFD_BalanceSheet/stockid/600816/ctrl/part/displaytype/4.phtml)���ܿ������ף����������ء����������Ҫ�����Ĺ�Ʊ�����Ƕ������編���ơ���ô����ͨ��R��download.fileдһ��������ʵ�������Ʊ���룬���ʲ���ծ�����ص�ָ��Ŀ¼��

```r
getbalancesheets=function(symbol,file){
pre="http://money.finance.sina.com.cn/corp/go.php/vDOWN_BalanceSheet/displaytype/4/stockid/";
end="/ctrl/all.phtml";

url=paste(pre,symbol,end,sep="");
destfile=paste(file,"BalanceSheet_",symbol,".xls",sep="");

download.file(url, destfile);
}
```
ֵ��ע����ǣ�  
+ ������http��ͷ�ģ����Ĵ󵨵�ʹ��download.file()
+ ������https��ͷ�ģ������������ʧЧ
+ ������·��ʱ����ͨ��file.exists���鿴�ļ����Ƿ���ڣ���������ڿ���ʹ��dir.create���������������Ҳ���·���ķ��ա�
+ ʹ��getwd��ȡ��ǰ����·����setwd���Ըı���

### ���뱾������
�ļ��������������Ǳ���Ҫ������Щ���ݡ���������Щ���ݵ����������������scan,read.table,read.csv���ر�Ļ������ܶ��ĸ�ʽ��������txt,csv,�������е�һЩ��������ȴ�Ǿ����������������ʽ�ļ���Ҳ�õõ��ġ�  
�����������������������Ļ������ø�ʽ��
```
scan(file = "", what = double(), nmax = -1, n = -1, sep = "",
     quote = if(identical(sep, "\n")) "" else "'\"", dec = ".",
     skip = 0, nlines = 0, na.strings = "NA",
     flush = FALSE, fill = FALSE, strip.white = FALSE,
     quiet = FALSE, blank.lines.skip = TRUE, multi.line = TRUE,
     comment.char = "", allowEscapes = FALSE,
     fileEncoding = "", encoding = "unknown", text)
read.table(file, header = FALSE, sep = "", quote = "\"'",
           dec = ".", row.names, col.names,
           as.is = !stringsAsFactors,
           na.strings = "NA", colClasses = NA, nrows = -1,
           skip = 0, check.names = TRUE, fill = !blank.lines.skip,
           strip.white = FALSE, blank.lines.skip = TRUE,
           comment.char = "#",
           allowEscapes = FALSE, flush = FALSE,
           stringsAsFactors = default.stringsAsFactors(),
           fileEncoding = "", encoding = "unknown", text)

read.csv(file, header = TRUE, sep = ",", quote = "\"",
         dec = ".", fill = TRUE, comment.char = "", ...)

read.csv2(file, header = TRUE, sep = ";", quote = "\"",
          dec = ",", fill = TRUE, comment.char = "", ...)

```
������Ҫ�������Ǽ�����£�   
+ file:�ļ���·��
+ header:�Ƿ񽫵�һ�ж���������
+ sep:��ʲôΪ�ָ������硰�������� ����
+ row.names:����Ը�ÿһ��ָ�����֣�col.names�Ǹ�ÿһ��ָ������
+ nrows:��ȡǰn�У�Ĭ��Ϊ���������ļ�
+ skip:�ӵ�n�п�ʼ����
+ na.strings��ȱʧֵ�ķ��ţ����硰NA�������������� ���ȡ�


### ����Excel�ļ�
Excel����Ŀǰ����ʹ��ʮ�ֹ㷺��С���ݴ洢��ʽ����֮ǰ���ǵĲ��񱨱����һ������ô��ζ���Excel�����أ�  
����Excel����һ�����õİ취���ǽ���ת��Ϊcsv��ʽ����ͻ��鵽����ǰһ�����⡣  
��һ���취�ǽ�excel�����ݷ��ڼ������У�ͨ��read.delim��clipbroad������ȡ��
����R�е�gdata����read.xls����Ҳ���Խ������һ�����⡣  
����Excel��������Excel�ĸ�ʽ����Ϊ��.xlsx��RҲ�Ƴ���xlsx��.���÷����£�
```
read.xlsx(file, sheetIndex, sheetName=NULL, rowIndex=NULL,
  startRow=NULL, endRow=NULL, colIndex=NULL,
  as.data.frame=TRUE, header=TRUE, colClasses=NA,
  keepFormulas=FALSE, encoding="unknown", ...)

read.xlsx2(file, sheetIndex, sheetName=NULL, startRow=1,
  colIndex=NULL, endRow=NULL, as.data.frame=TRUE, header=TRUE,
  colClasses="character", ...)

```
��Ҫ����Ϊ��  
+ file:�ļ�·��
+ sheetIndex:Excel�ڲ��ı���Ŀ
+ rowIndex:��ȡExcelָ����������Ӧ��colIndexΪ��ȡָ������  

  
  
ע�����  

1�� write.xlsx�����������ƣ����԰�����дΪExcel�ļ������Ǳ���csv,txt��ʽ�����ǲ��Ƽ�����ô����  

2�� read.xlsx2��ȡ���ݷ����ƺ�Ҫ��read.xlsx��һЩ�����Ǿ�˵��ȡָ��������Ŀʱ����ô�ȶ���  

3�� ��װ�����xlsxʱ�������ú�Java����ػ���  

### �����������ݷ������������
�Դ���foreign������ʵ��s-plus��sas��spss��stata�����ݶ��롣  

### ����XML  

XML����˵�����Ƿǳ���Ϥ��һ�����ݡ�����ͨ�������Ͽ����ĵ��ӱ�����XML�ļ���һ���֡����ǿ��Կ���XML�ļ�����ǳ�[����](http://www.w3schools.com/xml/simple.xml)��.��δ�������һ���ļ�����ʵ��򵥵ľ�����EXCEL�����ˣ�����ֻҪ�ڴ��ļ�ʱ��Ϊ XML �б���ļ������� XML Դʱ��Excel ����� XML ��ʽ�� (XSL) �ı�ǡ�XSL ˵�����ݵ���ʾ��ʽ�����������Ӧ�ı�ǣ�Excel ������ʾ��ѡ���Ƿ�Ӧ����ʽ�����ѡ��Ӧ�� XSL���� XSL ��ָʾ���ݵ���ʾ��ʽ��  

����XML���ֿ���չ�Ա�����ԣ����ǲ���׸�������Բ���[wiki](http://en.wikipedia.org/wiki/XML).�������ǹ�ע�����ڵõ�XML�ļ�����η�������  

R�ṩ��XML������������ȡ����һ���ļ������ǽ�XML������Ҫ�����������£�  

```
xmlTreeParse(file, ignoreBlanks=TRUE, handlers=NULL, replaceEntities=FALSE,
             asText=FALSE, trim=TRUE, validate=FALSE, getDTD=TRUE,
             isURL=FALSE, asTree = FALSE, addAttributeNamespaces = FALSE,
             useInternalNodes = FALSE, isSchema = FALSE,
             fullNamespaceInfo = FALSE, encoding = character(),
             useDotNames = length(grep("^\\.", names(handlers))) > 0,
             xinclude = TRUE, addFinalizer = TRUE, error = xmlErrorCumulator(),
             isHTML = FALSE, options = integer(), parentFirst = FALSE)
             
xmlRoot(x, skip = TRUE, ...)
## S3 method for class 'XMLDocumentContent'
xmlRoot(x, skip = TRUE, ...)
## S3 method for class 'XMLInternalDocument'
xmlRoot(x, skip = TRUE, addFinalizer = NA, ...)
## S3 method for class 'HTMLDocument'
xmlRoot(x, skip = TRUE, ...)

```

+ xmlTreeParse������Ҫ�����ڽ���XML��HTML�ļ�����XML / HTML���ݻ��ַ���,������һ��R����XML / HTML���ṹ��  
+ xmlRoot������Ҫ�������ṩ����ط����ɽ���һ��XML�ĵ������Ķ���XMLNode����.  


�����������һ��һ���ķ�����ζ�ȡһ��XML����HTML�ļ���  
+ ��ȡ��ҳ����  

��ʱ����Ҫ�õ�RCurl����getURL���������������ҳ�����������BBC������[Robin Williams��һ������](http://www.bbc.com/news/entertainment-arts-28761353)Ϊ��˵˵������ȡHTML�ļ�(��Ϊ������Щ��վ��������룬Ϊ�˱��ⲻ��Ҫ���鷳��������ʱʹ��Ӣ����վ���Ժ�����ӻ������ĵ�):

```r
library(RCurl)
library(XML)

url <- "http://www.bbc.com/news/entertainment-arts-28761353"
SOURCE <-  getURL(url,encoding="UTF-8") #Download the page
#this is a very very long line. Let's not print it. Instead:
substring (SOURCE,1,200)
```

```
## [1] "<!DOCTYPE html PUBLIC \"-//W3C//DTD XHTML+RDFa 1.0//EN\" \"http://www.w3.org/MarkUp/DTD/xhtml-rdfa-1.dtd\">\n\n\n<html xmlns=\"http://www.w3.org/1999/xhtml\" xmlns:og=\"http://opengraphprotocol.org/schema/\" xml"
```

```r
PARSED <- htmlParse(SOURCE) #Format the html code d
```
+ ��ȡHTML��Ԫ��   

���ǿ���ͨ��XPath����غ�������ȡHTML�������Ϣ��

```r
xpathSApply(PARSED, "//h1")
```

```
## [[1]]
## <h1 class="story-header">Robin Williams: Obama leads tributes to actor, dead at 63</h1>
```
�����ı������ں���HTML��ǣ������Ǻܲ�ˬ�����ǿ���ͨ�����溯����ȥ������

```r
xpathSApply(PARSED, "//h1",xmlValue)
```

```
## [1] "Robin Williams: Obama leads tributes to actor, dead at 63"
```
��Ӧ�ĺ������ø�ʽ���£�
```
xpathApply(doc, path, fun, ... ,
            namespaces =  xmlNamespaceDefinitions(doc, simplify = TRUE),
              resolveNamespaces = TRUE, addFinalizer = NA)
xpathSApply(doc, path, fun = NULL, ... ,
             namespaces = xmlNamespaceDefinitions(doc, simplify = TRUE),
               resolveNamespaces = TRUE, simplify = TRUE, addFinalizer = NA)

```
��Ҫ������  
+ doc:XMLInternalDocument���͵����ݣ�htmlParse���������Ķ���
+ path:XPath ���ʽ�����õ��� "/" ��ʾ���ڵ㴦Ѱ��;"//"��ʾ�ĵ����⴦Ѱ��;"@"��ʾѡ����Ӧ������

���ǿ���ͨ��ץȡHTML��Ĺؼ��������ֺܶණ��������������֪�����ҳ���ж��������ӣ�����ֻ��Ҫ���У�
```
length(xpathSApply(PARSED, "//a/@href"))
```
�ٱ���������Ҫ֪�����ŵ����ڣ����ǿ������У�
```
xpathSApply(PARSED, "//span[@class='date']",xmlValue)
```
���Ҫ˵���ǣ�����ھ�һ��Ҫ��HTML�Ľṹʮ�ֵ���Ϥ������ҳ������ЩԪ�أ����ǵڼ����Ľṹ�ȣ�������ʹ��@ʱȷ�����ҵ��й����ԣ�����˵����֪��BBC��������Щ����Ĺ����й������ţ����ǾͿ����������´��룺

```r
url="http://www.bbc.co.uk/search/news/?q=China&search_form=in-page-search-form"
SOURCE <-  getURL(url,encoding="UTF-8")
PARSED <- htmlParse(SOURCE)
targets <- unique(xpathSApply(PARSED, "//a[@class='title linktrack-title']/@href"))
head(targets)
```

```
## [1] "http://www.bbc.co.uk/news/blogs-echochambers-28747713" 
## [2] "http://www.bbc.co.uk/news/uk-scotland-22207042"        
## [3] "http://www.bbc.co.uk/news/in-pictures-28743753"        
## [4] "http://www.bbc.co.uk/news/science-environment-28744469"
## [5] "http://www.bbc.co.uk/news/technology-28754235"         
## [6] "http://www.bbc.co.uk/news/world-europe-28755656"
```
Ȼ��������������ƪ���£�"//a[@class='title linktrack-title']/@href"���Ҳ����κζ����ġ���һ���أ�����ÿһ�����ӣ�������ǻ���֪�����������ڣ����ǿ���ʹ��sapply������

```r
bbcScraper2 <- function(url){
  title=date=NA #Return empty values in case field not found
  SOURCE <-  getURL(url,encoding="UTF-8") 
  PARSED <- htmlParse(SOURCE)
  title=(xpathSApply(PARSED, "//h1[@class='story-header']",xmlValue))
  date=(xpathSApply(PARSED, "//meta[@name='OriginalPublicationDate']/@content"))
  if (is.null(date)){
    date=(xpathSApply(PARSED, "//span[@class='date']",xmlValue))
  }
  return(c(title,as.character(date)))
}
targets<-as.data.frame(targets)
t(sapply(targets[1:5,],bbcScraper2))
```

```
##      [,1]                                                   
## [1,] "Conservatives misguided after Ferguson shooting"      
## [2,] "Q&A: Edinburgh's giant pandas"                        
## [3,] "In pictures: Framing Hope"                            
## [4,] "Rising economies 'ahead on climate'"                  
## [5,] "Google helps build 'Faster' cable under Pacific Ocean"
##      [,2]                 
## [1,] "2014/08/12 17:05:25"
## [2,] "2014/08/12 16:00:21"
## [3,] "2014/08/12 14:55:21"
## [4,] "2014/08/12 12:16:23"
## [5,] "2014/08/12 11:54:11"
```
+ Useful link��
 - [Xpath����ؽ���](http://www.w3schools.com/xpath/default.asp)
 - [XML����ؽ���](http://www.w3school.com.cn/xml/index.asp)
 - [HTML����ؽ���](http://www.w3school.com.cn/html/index.asp)








##### Ӧ�þ�������ȡ��������ͼ�鶨��

�ڱȼ۵Ĺ����У�������Ҫ��������Ǵ����ϻ�ȡ�۸����ݡ����Ǹ���δ�[����](http://category.dangdang.com/pg1-cp01.00.00.00.00.00.html)��ͼ��ҳ���ȡ�۸������أ�


```r
library(XML)
library(RCurl)
book_price=NULL
for(i in 1:2){
    url_i<-paste0("http://category.dangdang.com/pg",i,"-cp01.00.00.00.00.00.html",sep="")
    url_i<-htmlParse(url_i,encoding="GBK")    #asText=TRUE,
    node_i<-getNodeSet(url_i,"//li[@class]/div[@class=\"inner\"]/a")
    Attr_i<-sapply(node_i,xmlGetAttr,name="href")

    for(j in Attr_i){
        url_j=htmlParse(j,encoding="GBK")
        node_title=getNodeSet(url_j,"//div[@class]/img[@id]")
        if(length(node_title)>0){
            title=xmlGetAttr(node_title[[1]],"alt")
            title=iconv(title,"UTF-8","gbk")
        }
        else{
            next
        }

        node_price=getNodeSet(url_j,"//span[@id=\"salePriceTag\"]")
        if (length(node_price)>0){
            price=as.numeric(xmlValue(node_price[[1]]))
            }
        else{
            next
        }
        book_price=rbind(book_price,cbind(j,title,price))
    }
}
colnames(book_price)=c("URL","����","�۸�")
write.csv(book_price,"F:/book_price.csv")
```

### ����json ����

json���ݵ�һ�����͵Ĵ������΢�����ݣ�Ȼ������΢����Ҳ�кܶ���������վ��Ϊjson������ȫ���������Ե��ı���ʽ������Ҳʹ����������C���Լ����ϰ��ʹJSON��Ϊ��������ݽ������Ա�����APIʹ�á�����github�����ݣ�Wikipedia article traffic statistics������Ҳ������json��ʽ��  
������github��API����Ϊ�����������ҵ�github�Ĵ���ֿⲿ�����ݵ�json��ʽ��Ϣ�������汾��[����](https://api.github.com/users/yujunbeta/repos)
```
 {
    "id": 20472818,
    "name": "courses",
    "full_name": "yujunbeta/courses",
    "owner": {
      "login": "yujunbeta",
      "id": 7315956,
      "avatar_url": "https://avatars.githubusercontent.com/u/7315956?v=2",
      "gravatar_id": "e8569ebac320c9aed1764a7d693e5a87",
      "url": "https://api.github.com/users/yujunbeta",
      "html_url": "https://github.com/yujunbeta",
      "followers_url": "https://api.github.com/users/yujunbeta/followers",
      "following_url": "https://api.github.com/users/yujunbeta/following{/other_user}",
      "gists_url": "https://api.github.com/users/yujunbeta/gists{/gist_id}",
      "starred_url": "https://api.github.com/users/yujunbeta/starred{/owner}{/repo}",
      "subscriptions_url": "https://api.github.com/users/yujunbeta/subscriptions",
      "organizations_url": "https://api.github.com/users/yujunbeta/orgs",
      "repos_url": "https://api.github.com/users/yujunbeta/repos",
      "events_url": "https://api.github.com/users/yujunbeta/events{/privacy}",
      "received_events_url": "https://api.github.com/users/yujunbeta/received_events",
      "type": "User",
      "site_admin": false
    },
    "private": false,
    "html_url": "https://github.com/yujunbeta/courses",
    "description": "Course materials for the Data Science Specialization: https://www.coursera.org/specialization/jhudatascience/1",
    "fork": true,
    "url": "https://api.github.com/repos/yujunbeta/courses",
    "forks_url": "https://api.github.com/repos/yujunbeta/courses/forks",
    "keys_url": "https://api.github.com/repos/yujunbeta/courses/keys{/key_id}",
```
R��jsonlite���ṩ�˺���fromJSON����ȡJSON���ݡ����ҵ�github��JSON����Ϊ����

```r
library(jsonlite)
jsonData <- fromJSON("https://api.github.com/users/yujunbeta/repos")
```
���ǿ���ͨ������jsonData����ȡ�ҵ�github����Ӧ��Ϣ��

```r
names(jsonData)#��ȡJSON���ݵ�һ���ṹ��������hush��Ĺؼ���
```

```
##  [1] "id"                "name"              "full_name"        
##  [4] "owner"             "private"           "html_url"         
##  [7] "description"       "fork"              "url"              
## [10] "forks_url"         "keys_url"          "collaborators_url"
## [13] "teams_url"         "hooks_url"         "issue_events_url" 
## [16] "events_url"        "assignees_url"     "branches_url"     
## [19] "tags_url"          "blobs_url"         "git_tags_url"     
## [22] "git_refs_url"      "trees_url"         "statuses_url"     
## [25] "languages_url"     "stargazers_url"    "contributors_url" 
## [28] "subscribers_url"   "subscription_url"  "commits_url"      
## [31] "git_commits_url"   "comments_url"      "issue_comment_url"
## [34] "contents_url"      "compare_url"       "merges_url"       
## [37] "archive_url"       "downloads_url"     "issues_url"       
## [40] "pulls_url"         "milestones_url"    "notifications_url"
## [43] "labels_url"        "releases_url"      "created_at"       
## [46] "updated_at"        "pushed_at"         "git_url"          
## [49] "ssh_url"           "clone_url"         "svn_url"          
## [52] "homepage"          "size"              "stargazers_count" 
## [55] "watchers_count"    "language"          "has_issues"       
## [58] "has_downloads"     "has_wiki"          "forks_count"      
## [61] "mirror_url"        "open_issues_count" "forks"            
## [64] "open_issues"       "watchers"          "default_branch"
```

```r
names(jsonData$owner)#��ȡ�����ߵĻ�����Ϣ
```

```
##  [1] "login"               "id"                  "avatar_url"         
##  [4] "gravatar_id"         "url"                 "html_url"           
##  [7] "followers_url"       "following_url"       "gists_url"          
## [10] "starred_url"         "subscriptions_url"   "organizations_url"  
## [13] "repos_url"           "events_url"          "received_events_url"
## [16] "type"                "site_admin"
```

```r
jsonData$owner$login#��ȡ��½��Ϣ
```

```
##  [1] "yujunbeta" "yujunbeta" "yujunbeta" "yujunbeta" "yujunbeta"
##  [6] "yujunbeta" "yujunbeta" "yujunbeta" "yujunbeta" "yujunbeta"
## [11] "yujunbeta" "yujunbeta" "yujunbeta" "yujunbeta" "yujunbeta"
## [16] "yujunbeta" "yujunbeta" "yujunbeta"
```
##### Ӧ�þ���������Wikipedia������������
�ڹ�Ʊ���������Ǿ���������������ɡ�����һ�����ʣ���ôʲô���ĸ���������ߺ죬ʲô���ĸ�������п��ܻ�ö�������Ĺ����أ���Ȼ���Ǳ����۵����ģ���������ĵģ�����ϰ�����̨ʱ��ġ������й����ڵ�ʱ���Ǻ����������������ἰ�ġ����ڸĸ����Ҳ���Ϊ�µĹ��г����  

��������ʹ��[Wikipedia article traffic statistics](http://stats.grok.se/)�ṩ������������������Ƕ�ĳһ����Ĺ�ע�̶���Ρ���Ȼ��Ҫ������ǹ�עʲô��ʲô�����ڹ��������𣬿�wiki������ָ����ԶԶ�����ģ�������ĳ���׬Ǯ���ǹ�Ǻ��  

��������������ȽϺ������ݿ�ѧ��һ����Ϊ�����������������Ƕ����Ĺ�ע�̶ȣ�

```r
url <- "http://stats.grok.se/json/en/latest90/data%20science"
raw.data <- readLines(url, warn = "F")
library(rjson)
rd <- fromJSON(raw.data)
rd.views <- rd$daily_views
rd.views <- unlist(rd.views)
df <- as.data.frame(rd.views)
head(df)
```

```
##            rd.views
## 2014-06-30      620
## 2014-06-21      355
## 2014-06-20      474
## 2014-06-23      621
## 2014-06-22      390
## 2014-06-25      616
```

```r
library(ggplot2)
df$date <- as.Date(rownames(df))
colnames(df) <- c("views", "date")
ggplot(df, aes(date, views)) + geom_line() + geom_smooth() + theme_bw(base_size = 20)
```

<img src="figure/unnamed-chunk-16.png" title="plot of chunk unnamed-chunk-16" alt="plot of chunk unnamed-chunk-16" style="display: block; margin: auto;" />

��ͼ�����ǿ��Կ���data science�������Ǻ��Ĳ��У�Ȼ����������������ص�statistic�����ǹ�ע�ĳ̶���Σ�

```
##            rd.views
## 2014-06-30      288
## 2014-06-21      212
## 2014-06-20      233
## 2014-06-23      258
## 2014-06-22      236
## 2014-06-25      319
```

<img src="figure/unnamed-chunk-17.png" title="plot of chunk unnamed-chunk-17" alt="plot of chunk unnamed-chunk-17" style="display: block; margin: auto;" />
  

��Ȼstatistic���˹�ע�ĳ̶������ٵĿ��������Ƶ����ǻ����Կ���big data��machine learning��statistical learning��Щ����Ĵʻ�Ĺ�ע�ȣ��������ǲ���׸����

##### Ӧ�þ�������������ڡ���ͳ��ʲô?
������������һ������˼�����ۣ����ǿ���ͨ��ͳ�ƹۿ���Сʱ������������ͳ�ƾ����ж����ԲС���Ȼ����ֻ��һ��֮�ԡ�����������Ȼ�������ù��������˼�룺�����Сʱ������״̬����֡��ԲС��ĸ��ʺܸߣ���ô�ͻ����Ͽ��������������ۺ��е���  

Ϊ�˱���һЩ����Ҫ�����ˣ����ǲ�������΢���������������������ġ�������ڡ�������ʲô��أ���Ӱ�������ܴ���ʲô��   

������������lijian�����Rweibo����������

```r
require(Rweibo)
res <- web.search.content("�������", page = 20, sleepmean = 10, sleepsd = 1)$Weibo

require(Rwordseg)
insertWords("�������")
n <- length(res)
res <- res[res != " "]
words <- unlist(lapply(X = res, FUN = segmentCN))
word <- lapply(X = words, FUN = strsplit, " ")
wordfreq <- table(unlist(word))
wordfreq <- sort(wordfreq, decreasing = TRUE)
```

��������������ȥ��һЩ���ִʻ㣨�硰�㡱�����ǡ�֮�ࣩ��Ĵʻ�Ƶ�ʳ���20�Ĵ���У�
```
  TFBOYS     ����     ����     ��Ӱ     ż��     �ּ�     ̨�� �������     ң��     ���     ���� 
      64       39       33       32       32       32       32       28       26       24       24 
    һ��     սʿ     ����   ��һ��     ����     ��Ʒ     ʲô     ֪��       cn     http       ln 
      24       24       22       22       22       22       22       22       21       21       20 
      RP     ÿ��     �ع�     ����     �ȵ�     ��Ϸ   ��Ӣ��     ���      
      20       20       20       20       20       20       20       20       

```
����Щ�����ʻ����������������ġ�������ڡ����ڱ������ͷ������TFBOYS�ݳ��ġ�������ڡ�ȡ����TFBOYS�ġ�������ڡ������µ����š������Ͼ���������Ѿ���������ô����ʱ�䣬û���˻�ȥ��ϰ��Щ����ġ���������Ϊ��Ҷ�֪����������֪�����ٵ������п��ܹ�������һ������ôĿǰ����Ӱ��������ڡ���صĶ������Կ϶��ľ�ֻ�С���Ӱ�������Լ���Ӱ9�µġ�̨�塰֮�С�  
+ Useful link:
  - [Rwordseg�������Ϣ������](http://jliblog.com/app/rwordseg/comment-page-1)
  - [Rweibo�������Ϣ������](http://jliblog.com/app/rweibo/comment-page-3#comment-396518)


���ǲ������Զ���JSON����Ҳ����ͨ������toJSON�����ݿ�дΪJSON��ʽ�����罫�β�����ݼ�дΪJSON��ʽ(�������ϳ����ڴ˴���)��
```
data(iris)
toJSON(iris, pretty=TRUE)

```
### �������ݿ�
���ڴ����ݣ�������Ȼ������Excel֮����ţ�ͨ�����ǽ����Ǵ������ݿ��У�һ���Ƚ���������ݿ��������MySQL�����������Ƕ�ȡ��ѯ���ݿ��е�������ݡ�R�е�RMySQL���ṩ����ôһ����ȡMySQL���ݵİ취��������ʹ��SQL�������ݽ��в�ѯ��  
һЩ���õĺ�����  
+ dbConnect���������ݿ�
+ dbDisconnect��ȡ�����ݿ�����
+ dbGetQuery��ִ��һ��SQL��䣬����ѯ���дΪһ�����ݿ�
+ dbListTables���г����ݿ��еı������
+ dbListFields����ȡ�б��ÿһ�е�����
+ dbReadTable����ȡ���ݿ��е�һ�ű�
+ dbSendQuery��ִ��һ��SQL��䣬����һ�����ݿ����  


+ Useful link: 
  - [RMySQL���ݿ���ָ��](http://blog.fens.me/r-mysql-rmysql/)

