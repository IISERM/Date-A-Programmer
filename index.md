# Vision

This is a Valentine's day themed event with questions based on the theme of love and romance.

Feel free to contact the organizers if you need additional information.

# [Click here for Rules](./rules)


# Questions

## Question 1) Love Calculator [20 Marks]

You have to build a love calculator. The calculator works in the following manner- it takes the name of 2 partners and converts their name to ASCII and then converts the ASCII to binary. The calculator claims this percentage to be the percentage of love between the 2 programmers.

### Input

`Name of partner A`, `Name of partner B`

### Output

The percentage of love between them. And a short lovely message for them.


## Question 2) Draw a heart [40 Marks]

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


## Question 3)  [100 Marks]


### Input

A given image.

### Output

An image showing the final state after 420 iterations.


## Question 4) Secret Love Messages [60 Marks]

Your parents check your phone very frequently. They don't you are dating someone. So, you have come up with a way to encrypt and decrypt the messages you send to your loved one. Here's the proposed scheme that you have to implement-

Write a function `encrypt(message, key)` that takes a message and a key, which is an integer. It uses this key as a seed and uses a randomizing function in the language of your choice to shuffle the characters in the message. The function returns the encrypted message.

Write a function `decrypt(encrypted_message, key)` that takes the encrypted message and the same key and decrypts the message and returns the decrypted message.



## Question 5[100 Marks]

A new species of bacteria named "Isingotetragonous" has been discovered recently. The bacteria live in colonies that are roughly square in shape. An individual bacteria doesn't survive for long if it's separated from its colony. Each bacteria has a structure called "Spink Filament" on it's surface that comes in 2 shapes. The bacteria can change the shape of "Spink Filament" from one form to the other. Depending on the shape of the "Spink Filament" on the bacteria in it's immediate vicinity(the 8 bacteria around it) and the bacteria next to them(the 16 bacteria surrounding these 8 bacteria), the bacteria secretes a chemical called "Hamiltonine" responsible for strengthening the integrity of the colony. However, the strength of the colony is also temperature dependent and too much of "Hamiltonine" at a low temperature can cause disintegration of the colony. So, as the temperature changes, the bacteria change the structure of the "Spink Filament" in such a manner that the concentration of "Hamiltonine" is optimum for maintaining the structural integrity of the colony. However, the process of changing the structure of the "Spink Filament" is not perfect, hence the concentration of "Hamiltonine" is not definite at a given temperature. There are small fluctuations. 

Dr. Jay Joseph has proposed the following mathematical model for this-

For a colony of $$N\times N$$ bacteria,

$$\text{Concentration of Hamiltonine}(H)=\sum\limits_{i=1}^{N\times N}\left(-J\sum\limits_{j=1}^{8}\sigma_i\sigma_j -K \sum\limits_{k=1}^{16}\sigma_i\sigma_k \right)$$

where $$\sigma_l = \pm 1$$ represents the 2 shapes of the filament. You need to deal with the summation at the edges in the following manner: During the loop over the bacteria cells, let each bacteria interact with every cell near it and the cells next to the neighboring cell.

$$\text{Probability of having H amount of Hamiltonine at a given temperature T}(P(H, T))\propto e^{-\frac{H}{kT}}$$

Here, `J`, `K` and `k` are constants whose value has been proposed by Dr. Anand. Your job as an intern in his lab is to calculate the average value of "Hamiltonine" for the given probability distribution and generate a few probable configurations for the bacterial colony on the basis of the shape of filaments. 


Since the probability distribution is Boltzmannian, we can use the following algorithm to simulate it-
* Take a random $$N\times N$$ matrix consisting of -1 and +1. Take this as your initial configuration.
* Generate a new configuration $$\nu'$$ by changing the shape of a few "Spink filaments" in the matrix. This change of configurations would cause a change in the concentration of "Hamiltonine". 

$$\Delta H_{\nu\nu'}=H_{\nu'}-H_{\nu}$$

* If $$\Delta H_{\nu\nu'}$$ is negative or zero, accept this change of configurations. Else, draw a random number u between 0 and 1. If $$\Delta H_{\nu\nu'}\geq u$$, accept the change, else reject it. In simpler terms-

$$
\nu(t) = \nu,\\
\nu(t+1) = \nu' \text{ when } \Delta H_{\nu\nu'}\leq 0,\\
\nu(t+1) =
\left\{
	\begin{array}{ll}
		\nu'  & \mbox{if } e^{-\frac{\Delta H_{\nu\nu'}}{kT}} \geq u \\
		\nu & \mbox{if } e^{-\frac{\Delta H_{\nu\nu'}}{kT}} < u
	\end{array}
\right.
$$

* Repeat this process for a few thousands steps. This will cause the configuration to settle down around a more probable value. Remember that initially, we started in some random configuration which may not be very probable at a given temperature.
* Now, continue this process for a few thousand steps more, but this time take the average of concentration at, say every 100 steps. Make sure that more than 40% percent of the configurations are being accepted.
* This average is the average value of the concentration. You can display the configuration at the end of the simulation as a probable configuration. Use black and white colors to represent +1 and -1 in the matrix.

Note that the configuration you attain at the end is not the most probably configuration, but a highly likely one.

You can use these values for testing your code-
`N=500`
`J=2 units`
`K=0.5 units`
`T=3 units`
`k=1 units`

### Input

`N`, `J`, `K`, `T` and `k`

### Output

1. Average concentration of Hamiltonine.
2. The configuration at the end of the simulations represented by an image.


## Question 6[120 Marks]

Remember those 50 students who birded **diligently and honestly** at the newly discovered islands. 30 of them caught the same disease(unnamed as of now) during their stay at the islands. A team of experts at the Pacific Institute has determined the cause of the disease to be bites from a new species of mosquitos found only on these islands. Some of these students were still infected when they returned to the campus and have now caused an outbreak in the city. It has been discovered that `Anopheles stephensi`(Malaria Vector) is the vector of this newly discovered disease too. Dr. Parul Ghara has proposed the following model has been proposed to model the spread of this disease-

Human population is an `nXn` grid with each cell having `h` humans(hosts) some Anopheles Stephensi mosquitoes(vector). Assume that the number of infected humans in each cell is drawn from a uniform distribution between `0` and `h` and the number of mosquitoes in each cell is drawn from a uniform distribution between `0` and `m`. All vectors are initially uninfected. The host and the vector grids are updated in the following manner:

* The probability of a mosquito biting a human in a grid cell is `α`. We assume that the mosquito is not able to travel much in its lifetime so it cannot infect hosts outside its grid cell.
* The probability of a human getting infected is `β` and the chance of other mosquitoes getting infected is `γ`.
* Human death and birth rate per capita is `δ` and the mosquito death and birth rate per capita is `η`.
* To simulate the micromovement in humans we assume that `θ%` of humans in the neighbouring cells interact with the mosquito in a cell.
* The probability of a human recovering is `λ`.

Each timestep is 1 day. Your job is to simulate this like a discrete time model and make 2 gifs, one of the host and the other of the vector grid for 150 timesteps.

For testing the code, use these values-
`n=300`
`h=500`
`m=1000`
`α=0.35`
`β=0.4`
`γ=0.75`
`δ=0.000039`
`η=0.4`
`θ=10`
`λ=0.07`


### Input

`n`, `h`, `m`, `α`, `β`, `γ`, `δ`, `η`, `θ`, `λ`

### Output

A gif showing the evolution for 150 steps.


# Done!

- Rename all your files as `Qx.ext`
- Put them into a zip/tar file with name `DWH-<teamname>.zip`/`DWH-<teamname>.tar`
- Mail them to `turingclub@iisermohali.ac.in`

# Enjoy!

Good Luck!

# Want a look at the earlier hackathons. Here they are-

- [DWH 2020](2020)
- [DWH 2021](2021)

{% include mathjax.html %}
