# ConardSparkProject

## Links
- [Webpage](https://s523286.github.io/ConardSparkProject/ "Conard Spark Project Webpage")
- [Source](https://github.com/s523286/ConardSparkProject "Conard Spark Project Source")

## About Me & Objective
My name is Liz Conard and I am a student at Northwest Missouri State University. I am a senior studying mathematics and computer science. I am currently working on this project for my "Big Data" class. The objective of this assignment is to use Spark to find the most frequent words within the text by Shakespeare, A Midsummer Night's Dream. 

## Data
I used a .txt file of A Midsummer Night's Dream. I created the .txt file by copying and pasting the text from the following website:
- [A Midsummer Night's Dream](http://shakespeare.mit.edu/midsummer/full.html "Website With Full Text")

## Scala Commands
```Scala
> val inputFile = sc.textFile("C:/44517/ConardSparkWordCount/AMSND.txt")
> val topWordCount = inputFile.
flatMap(str=>str.split(" ")).
filter(!_.isEmpty).
map(word=>(word,1)).
reduceByKey(_+_).
map{case (word, count) => (count, word)}.
sortByKey(false)
topWordCount.take(10).foreach(x=>println(x))
```
