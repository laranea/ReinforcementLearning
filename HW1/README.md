# Excercise 2.6

### The results shown in Figure 2.3 should be quite reliable because they are averages over 2000 individual, randomly chosen 10-armed bandit tasks. Why, then, are there oscillations and spikes in the early part of the curve for the optimistic method? In other words, what might make this method perform particularly better or worse, on average, on particular early steps?


https://github.com/vduddu/RL-M2018/blob/master/HW1/Figures/fig23_sta.png


The intitial spike is because of the optimisitic q() values that were assigned for each of the bandits. Since, in the simulation, we give the initial optimistic value of 5, the optimisim of the agent to achieve the optimal bandit arm results in the spike. 

Oscillation: Once, the agent realises that the actual rewards obtained and the estimated q() values are different than the optimisitc value, the agent tries to correct its estimation of the estimated q() values. Till then, we see the oscillations after the spike.

The optimisitc intital values allows a opportunity to try all the arms out. Hence, over time, the performance of the optimistic approach is better than assuming all 0 intital values since the estimated q() values in case of optimistic assumption is more closer to the true value.



#### Nonstationary

https://github.com/vduddu/RL-M2018/blob/master/HW1/Figures/fig23_nonsta.png



### Repeat the excercise for Non-Stationary case

On repeating the exercise with changing values of the true q values, the agents requires to keep exploring more. As a result, a high optimistic value does not neccasry help the agent. This can be seen in the graph, where the changing true estimates result in the optimistic approach to perform poorly compared to the Stationary case.



### Compare UCB, Optimistic Initital Value and E-Greedy for Stationary and Non-Stationary case

### Stationary

https://github.com/vduddu/RL-M2018/blob/master/HW1/Figures/compare_stationary.png

### Non Stationary

https://github.com/vduddu/RL-M2018/blob/master/HW1/Figures/compare_nonstationary.png

UCB seems to outperform both Optimistic apprach and the E Greedy appooach for both the stationary and non-stationary cases. UCB gives weightage to all the actions that have been previously unexplored and as a result, it shows a higher % of finding the optimal action. Optimal approach is also quite close to the UCB approach but however, eGreedy does not perform well and takes a lot of iterations to achieve the performance of UCB or optimal value approach.



### Excercise 2.5: Why does Averaging Techniques not work well in Non-Stationary situations?

https://github.com/vduddu/RL-M2018/blob/master/HW1/Figures/avg1.png

https://github.com/vduddu/RL-M2018/blob/master/HW1/Figures/avg2.png

In non-stationary conditions, the true estimates and the probability distrbution for receiving a particular reward are varying. In such a situation, the latest past rewards are important as compared to older rewards. This however, is not captured by aversaging methods like sample average. As a result we see in the graphs that the performance of the sample averaging is not as good as incremental approach with constant step size. Incremental apporach with constant step size gives more weightage to recent rewards compared to older rewards, due to which its performance improves significantly better than averaging techniques.



### Excercise 2.7: Performance Analysis of Cnstant step size q() estimation in Non-Stationary Conditions

https://github.com/vduddu/RL-M2018/blob/master/HW1/Figures/ex27.png



We see that on taking an incremental implementation with constant step size, the % of achiveing the optimal action in a non stationary condition is about 80%. Averaging techniques do not work well in non stationary conditions which has also been shown in the precious excercise above.
