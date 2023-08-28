# ML Practice: Arm Distribution or Actions
Practicing Machine Learning by creating a distribution reward matrix with normally distributed rewards with a small variance that is ideal with normal distribution rewards and simulating the data using R language.

## Creating the Matrix Being Used
Instead of finding a dataset to use, I am creating my own matrix that starts with 3, increasing the number by 1.5 until we have 10 numbers. After, I created the reward distribution before preparing my data simulation. See screenshot.

![Screenshot of arm distribution or actions with normally distributed rewards with small variance.](https://github.com/CrawleyM29/ML_Practice/blob/data-engineering/Arm%20Distribution%20ML/Beginning%20Code.JPG)

I then viewed my dataset to make sure it was clean and correct for my simulation. I only took a screenshot of the first 13 rows, it does have 10,000 lines with various outcomes.

![View of dataset](https://github.com/CrawleyM29/ML_Practice/blob/data-engineering/Arm%20Distribution%20ML/Dataset%20View.JPG)

## Creating Dataset with Arm and Reward Combination 

After creating the dataset and making sure it was clean and created it, I assigned column names from V1 - V10 to 1-10. In my first dataset picture, you don't see V1 to V10 as I completed my project prior to putting it up on GitHub. 

![Assigning column names and creating a reward combiniation](https://github.com/CrawleyM29/ML_Practice/blob/data-engineering/Arm%20Distribution%20ML/data%20prep.JPG)

### Plot-I Code and Visual

The following is the plot for the distributions of rewards from Bandits

![Code for Plot I](https://github.com/CrawleyM29/ML_Practice/blob/data-engineering/Arm%20Distribution%20ML/Plot1.JPG)

### Plot-I Outcome

![Different Bandits Rewards](https://github.com/CrawleyM29/ML_Practice/blob/data-engineering/Arm%20Distribution%20ML/Plot%20Bandits%20distribution.JPG)

As we can see, the different Bandit rewards for 1 to 10 are near 0.15 in density, with 4 being less in density, barely hitting 0.15. The highest density in rewards is with Bandit 10, Bandit 9 being in close 2nd. This is prior to putting in the Upper Confidence Bound Algorithm (CBA).

## Upper Confidence Bound Algorithm

I created a function to have 1000 rewards, and the reward total is 0.  This is to put in some statistics for our max upper bound where if it's greater than 0, we calculate the square root (2 x log(1 + n x log(n)^2 / selection of numbers.  This will get our average reward. 

If it's not greater than 0, our upper bound will equal 1e400. I will be honest, it took me a little bit to troubleshoot my errors, but we got there (never give up) See the following:

![UCB Code](https://github.com/CrawleyM29/ML_Practice/blob/data-engineering/Arm%20Distribution%20ML/Upper%20Confidence%20bound%20Algorithm.JPG)

## Simulation Data Preparation and Plotting

It's time to prepare the simulation data to see if there are any changes between our simulation and the 'Different Bandits Rewards' visual. Starting out with a matrix of 10,000 rows and 10 columns, we want our columns  to say "Bandit" and "Rewards" so we see the difference visually.  Creating a different dataset ('dataset_r for dataset reward) showcases 100,000 observations and 2 variables where we will factor our rewards with Bandits. Next we plot.

### Simulation Data Prep Code

![Simulation Prep Code](https://github.com/CrawleyM29/ML_Practice/blob/data-engineering/Arm%20Distribution%20ML/Simulation%20data%20prep.JPG)

![Simulation Reward from Different Bandits](https://github.com/CrawleyM29/ML_Practice/blob/data-engineering/Arm%20Distribution%20ML/Reward%20from%20different%20Bandits.JPG)

We can see that Bandit 10 no longer has the highest density but Bandit 9 along with Bandit 1 and 2. Bandit 4 is not the lowest density, bandit 3 is.  I also noticed that the reward is greater.  The Reward of the bandits is greater than before, Bandit 10 is now past Reward 40.

## Conclusion

Putting in simulation for our Bandits caused a flux for all of the Bandits versus reward and density now passing 0.16. Statistics is pretty important for everyone to understand judging by our simulation.  We now know that the rewards for the Bandits can fluctuate with a small different in numbers.






