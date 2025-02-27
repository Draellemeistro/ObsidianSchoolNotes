[(interessant lille video der kommer ind på kryptering og frequency analysis til at cracke sådanne ting)](https://www.youtube.com/watch?v=z16rzIF5J40&t=6s)
# Definition 

> [!NOTE] Definition
> Frequency analysis is based on the fact that, **==in any given stretch of written language, certain letters and combinations of letters occur with varying frequencies==**. Moreover, there is a **characteristic distribution of letters that is roughly the same for almost all samples of that language**.

Frequency Analysis is a part of descriptive statistics. In statistics, frequency is the number of times an event occurs. Frequency Analysis is an important area of statistics that deals with the number of occurrences (frequency) and analyzes measures of central tendency, dispersion, percentiles, etc.

## Fra Hjemmeside: [The frequency of the letters of the alphabet in English](https://www3.nd.edu/~busiforc/handouts/cryptography/letterfrequencies.html)
The inventor of Morse code, Samuel Morse (1791-1872), needed to know this so that he could give the simplest codes to the most frequently used letters. He did it simply by counting the number of letters in sets of printers' type. The figures he came up with were:

| number | letter | number | letter |
| ---- | ---- | ---- | ---- |
| 12 000 | E | 2 500 | F |
| 9 000 | T | 2 00 | W, Y |
| 8 000 | A, I, N, O, S | 1 700 | G, P |
| 6 400 | H | 1 600 | B |
| 6 200 | R | 1 200 | V |
| 4 400 | D | 800 | K |
| 4 000 | L | 500 | Q |
| 3 400 | U | 400 | J, X |
| 3 000 | C, M | 200 | Z |
However, this gives the frequency of letters in English text, which is dominated by a relatively small number of common words . For word games, it is often the frequency of letters in English vocabulary, regardless of word frequency, which is of more interest. The following is a result of an analysis of the letters occurring in the words listed in the main entries of the _**Concise Oxford Dictionary**_ (9th edition, 1995) and came up with the following table:

	![[Pasted image 20240220124833.png]]

The third column represents proportions, taking the least common letter (q) as equal to 1. The letter E is over 56 times more common than Q in forming individual English words.

The frequency of letters at the beginnings of words is different again. There are more English words beginning with the letter 's' than with any other letter. (This is mainly because clusters such as 'sc', 'sh', 'sp', and 'st' act almost like independent letters.) The letter 'e' only comes about halfway down the order, and the letter 'x' unsurprisingly comes last.

A visual representation of relative frequencies is shown below:
![[Pasted image 20240220124909.png]]

## Types of measures
Frequency Analysis usually deals with three types of measures
### 1.  Measures of Central Tendency
It is a single measure that tries to describe the set of data through a value that represents the central position within that data set. Most popular measures of central tendency used for frequency analysis are Mean, Median and Mode. While the mean is the average value of the data set, the median is the middle observation (observation which has an equal number of values lying above and below it) in the data set. Mode is the value that occurs the most number of times in a data set.

While Mean has been calculated by mathematicians and astrologers since ages, Median was first introduced by Edward Wright in his book on navigation in 1599; and Mode originated in 1895 by Karl Pearson's efforts.
### 2.  Measures of Dispersion
These reflect the spread or variability of data within a data set. Most popular measures of dispersion used for frequency analysis are Standard Deviation, Variance and Range.

While Standard Deviation had been around for a long time and had been used by others with different names (like 'mean error' by Gauss); Karl Pearson first used the term Standard Deviation in 1894. Variance was first used by Ronald Fisher in 1918.
### 3. Percentile Values
A percentile value shows what percent of values in a data set fall below a certain percent. Frequency Analysis commonly uses percentile values like Quartiles, Deciles, Percentiles, etc. While the 10th percentile value shows that 10% of the observations fall below it in a data set, it is also called the 1st Decile (where the data set is divided into 10 Deciles at intervals of 10% each). Similarly the 25th, 50th and 75th percentiles are also called the 1st, 2nd and 3rd Quartile respectively (where the data set is divided into 4 Quartiles at intervals of 25% each).

# ifht kryptering
If you have the frequency analysis on the ciphertext, you can guess what combination in the ciphertext mapped to the origin text.
- Think about the frequencies of letters in [[Frequency analysis|English]]: **E T A O I N S** are the most frequently used letters
- Some short words area frequent and easy to recognize: **a, I, to, on, the**... etc
- Use this knowledge to progressively figure out the key
## Let’s try Frequency analysis (Independent work)
- Ciphertext file: **ciphertext.txt**
- Calculate frequency: python **frequency.py**
Replace the characters to find the plaintext:
**==Example==**: tr ntyhqu EHTRSN < **ciphertext.txt**
 
> [!NOTE] filer
> Ligger på Moodle under Theme 3: encryption ([link til scripts](https://www.moodle.aau.dk/mod/resource/view.php?id=1713387))

