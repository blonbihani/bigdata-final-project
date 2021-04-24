# Tamang's Big Data Final Project
PySpark Text Processing for the words used in the play 'Hints for Lovers'

## Author: Bihani Tamang
<table>
  <tr>
   <td align="center"><a href="https://github.com/blonbihani"><img src="https://avatars.githubusercontent.com/blonbihani" width="200px;" alt=""/><br /><sub><b>Bihani Tamang</b></sub></a><br /><a href="https://github.com/blonbihani" title="Code"></a></td>
  </tr>
  </table>

## Text Data Source
I took the text file for my Project's data from 

- [Hints for Lovers](https://www.gutenberg.org/cache/epub/14255/pg14255.txt)

## Steps involved:

### Get and store the data
1) At first, we shall request or pull the text data from given URL into the urllib library.
```
import urllib.request
stringInURL = "https://www.gutenberg.org/cache/epub/14255/pg14255.txt"
```
Then we shall store the data in temporary file and name it love.txt.
```
urllib.request.urlretrieve(stringInURL, "/tmp/love.txt")
```
2) We shall move the data from the temporary data to a new location using dbutils.fs.mv
```
dbutils.fs.mv("file:/tmp/love.txt","dbfs:/data/love.txt")
```

3) 
```
LoverawRDD = sc.textFile("dbfs:/data/love.txt")
```
