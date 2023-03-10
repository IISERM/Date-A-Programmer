<style>
  .poster {
    max-height: 100vh;
  }
</style>

<p align="center">
  <b>Let's indulge our hearts into the sea of love and romance!</b><br><br>
  <img src="poster.jpeg" class="poster"/>
</p>

# [♥ Click here for Rules ♥](./rules)

<hr color="black">

## Question 1) Valentine's week  [20 Marks]

Your task is to take a date from the user that lies in the Valentine's week and return the name of the day that falls on it. The following are the anticipated date formats-

```
07/02/2023
07-02-2023
7-2-2023
7th Feb 2023
7 Feb 2023
7th Feb
7 Feb
7th February
7 February
```

Print `invalid` if the date doesn't life in the Valentine's week. By now, you are supposed to know what day falls on what date.

### Input

07/02/2023

### Output

Rose Day

<hr color="black">

## Question 2) Love Calculator [30 Marks]

a) You are working as a Love Guru/Astrologer (and a part time data analyst). Your clients come and ask you their compatibility with some prospective partners.

You bunked your classes at the Indian Institute of Astrological Science, not that attending them would have made a difference. But you did a data analysis course at Coursera and know how to convert the characters into Binary.

So, you have come up with the following ~~scam~~ scheme. You take both their names and convert it to binary. Then, you predict their compatibility by comparing the percentage similarity between the 2 binaries.


(b) You later coded this calculator and deployed it on a website. A multi-national company loved your ideas and paid you $10 million to acquire the model. Now, the company plans to create a simple love-letter based on your model's compatibility score.

You now have a job in the same company and you need to build this model which takes the compatibility score and accordingly designs a love letter with loving emojis, quotes, etc. (Remember more the compatibility score, more romantic the letter it would be.)

### Input

`Name of partner A`, `Name of partner B`

### Output

The percentage of love between them. And the love letter.

<hr color="black">

## Question 3) Draw a heart [50 Marks]

a) It's Valentine week and you (as a biology major) have to plot a 2D heart to impress your valentine.

Draw a heart using just the character `*`. Take an input `n` from the user, which is a measure of the size of the heart, say, the number of rows. You are free to decide how you do it, whether you draw a filled one, or a hollow one. The following is an example-

```
For n = 8

  *   *   *   *   
*       *       * 
*               * 
*              * 
  *           *   
    *       *     
      *   *       
        *
```

### Input

`n`

### Output

A heart printed on screen

(b) But your valentine (being a physics major and data science minor nerd) feels like 2D heart is for Nibba-Nibbi and now you need to upgrade your plot into a 3-D heart (can't buy gifts kyuki INSPIRE nhi milta).

Equation of the heart:  
```math
 Heart(x,y,z) = (x^2 + (9/4)(y^2) + z^2 -1)^3 - (x^2)(z^3) -(9/200)(y^2)(z^3) 
```
### Input

No input for this part

### Output

A 3D heart printed on screen

<p>
  <b>Example!!</b><br><br>
  <img src="3D-heart.png" width="450" height="400">
</p>

<hr color="black">



## Question 4) Secret Love Messages [40 Marks]

Your parents check your phone very frequently. They don't know you are dating someone. So, you have come up with a way to encrypt and decrypt the messages you send to your loved one. Here's the proposed scheme that you have to implement-

Write a function `encrypt(message, key)` that takes a message and a key, which is an integer. It uses this key as a seed and uses a randomizing function in the language of your choice to shuffle the characters in the message. You have to shuffle the original string based on the key, using a shuffling function. The function returns the encrypted message.

Write a function `decrypt(encrypted_message, key)` that takes the encrypted message and the same key and decrypts the message and returns the decrypted message.


<hr color="black">

## Question 5) Movie Matching [60 Marks]

You are making a Tinder app, where you want to calculate the compatibility based on the difference between the rating each partner gives to movie genres. The following model has been proposed for the compatibility (which is measured through a survey of couples)-

1. Each partner rates the genre of the movie. 
2. Their compatibility is calculated in the following manner-

$$n = (\beta_1 \times x1 + \beta_2 \times x2 + \beta_3 \times x3)$$


$$x_i$$ is the square of the difference between the ratings. 

$$\text{Compatibility} = \beta_4/(1+e^n)$$

Fit the model using the data to learn the given parameter. 

Just in case you are wondering, what if $$\beta_4$$ greater than 1 and the compatibility overshoots- supercompatibility is a thing.

**You are not allowed to use any optimizer from any library, say scipy's curve_fit() or numpy's polyfit()**

### Input

Use the given [CSV](./data_movie_genre.csv)

### Output

Compatibility

<hr color="black">

## Bonus Question) Love Necklace [Not counted in the final scoring.]

**The team that solves this first gets a prize.**

You want to gift a necklace to your special someone. You have 18 pearls, 6 blue, 6 green and 6 red. Find the total number of unique necklaces that you can make. Final answer is must for the prize. Submitting the code is not sufficient albeit necessary.

### Input

No input

### Output

The total number of unique necklaces possible


# Done!

- Rename all your files as `Qx.ext`
- Put them into a zip/tar file with name `DAP-<teamname>.zip`/`DAP-<teamname>.tar`
- Mail them to `turingclub@iisermohali.ac.in`

# Enjoy!

Good Luck!


{% include mathjax.html %}
