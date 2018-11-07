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
>topWordCount.take(10).foreach(x=>println(x))
```

## Results
The results I obtained from the previous commands are as follows:

| Count | Word |
|-------|------|
| 482   | the  |
| 412   | I    |
| 365   | and  |
| 270   | to   |
| 248   | of   |
| 233   | a    |
| 205   | in   |
| 184   | And  |
| 179   | you  |
| 176   | my   |

The most frequently used word is "the" and the 10th most frequently used word was "my." The corresponding numbers equivalate to the number of times that word appears in the text. "The" is used 482 times.

