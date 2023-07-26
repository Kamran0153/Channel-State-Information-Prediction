# Channel State Information Generation and Prediction

We consider a non-reciprocal wireless link between a Base Station (BS) and a user, where a Base Station (BS) transmits information to a mobile user. The mobile user obtains samples of the downlink channel conditions and reports the noisy channel state information to the BS. However, due to communication errors or delay, the received channel information in the BS is not fresh. BS uses the stale and noise channel state information to predict the current channel state information. We consider a Rayleigh feading channel model. In this notebook, we will generate Rayleigh fading channel. Then, using the noisy sequence of stale channels, we will predict current channel state information.

# Dataset Generation
The Rayleigh fading process with unit variance is generated by using sum of sinusoids method described in https://ieeexplore.ieee.org/stamp/stamp.jsp?tp=&arnumber=1512123

# System Model and Objective
Let $h[j]=h_{re}[j]+i h_{im}[j]$ be the channel state information at time $j$. Target variables at time $j$ is $y[j]=h[j]$ and the feature variable $X[j]$ is the sequence of channel state informations. Let $X[j]=(h[j]+n[j], h[j-1]+n[j-1], \ldots, h[j-u+1]+n[j-u+1])$ be the sequence of channel information, where $n[j]$ is the noise signal and $u$ is called feature length. Our goal is to predict $y[j]$ based on $X[j-\delta]$, where $\delta$ is the age of infroamtion. We will use quadratic loss function. Because $y[j]$ and $X[j-\delta]$ are jointy Gaussian, linear regression is the optimal choice among the supervised learning algorithms.

# Impact of age of information and feature length on the inference error

<figure><img width="500" id="_x0000_i1025" src="[./wiopt2023.png](https://github.com/Kamran0153/Channel-State-Information-Prediction/blob/main/CSIInferenceError.jpg)https://github.com/Kamran0153/Channel-State-Information-Prediction/blob/main/CSIInferenceError.jpg" alt="test" title=" "> 
        </figure> 

