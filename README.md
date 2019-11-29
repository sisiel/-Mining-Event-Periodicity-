# -Mining-Event-Periodicity-
The main algorithm of this paper is to read the paper "ePeriodicity: Mining Event Periodicity from Incomplete Observations", and implement the code implementation of python and make corresponding improvements. The main function of this algorithm is to get users to supervise an event (can It is the behavior cycle and confidence of using an APP or going to a physical location); the characteristic of this algorithm is that even if the data is missing a lot, it can get better results. The use scenario can be based on the geographical location to determine whether the user works in a certain place (there is a cycle), and the cycle situation (shift shift or five days off on two days, etc.); determine the user's habits of APP, when found to be different from the usual habits Stay alert and stay in time
***
The algorithm is roughly divided into two steps:

1. Calculation of all candidate periods (thesis part)

1.1 The input data is serialized data and it is set to S1. For example, if a person stays in an app in 30 days, the length of time spent in an app is 1 when not in use, 0 if not in use, and -1 if the data is missing. 24 long sequence: [1,0,0, -1 ... 1,0,0,0]

1.2 The output data is a list of the user's possible periods and corresponding probabilities on this event: [(T1, P1), (T2, P2) .... (Tn, Pn)]

2. Most probable behavior cycle calculation: (improve part by yourself)

Theoretically, after obtaining the sequence of the probability-period relationship of the first step, extract the peaks. For example, if 3 days is the period when you browse an APP, then 6 days are also, so 3, 6, 9 are likely to be the output of the first step. Extract the user's most probable event period based on the divisive scoring rule

after run the code I upoad,we can see the Output result is score:2, T:7
Since our example data is (ls1 * 5 + ls2 * 2) * 10, that is, the result is also 7 days, and the result meets expectations
