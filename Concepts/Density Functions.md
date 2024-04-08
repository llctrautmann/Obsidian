---
title: Density Functions
date: 20-05-2023
time: 14:54
author: Luca Trautmann
tags: []
series: "Probability Theory"
chapter: 3
---
# Density Functions
In probability theory, probability functions are used to describe the likelihood of a random variable taking on a certain value or range of values. These functions can be categorized as either <mark style="background: #FFB8EBA6;">probability mass functions (PMFs)</mark> or <mark style="background: #FFB8EBA6;">probability density functions (PDFs)</mark>, depending on whether the random variable is discrete or continuous, respectively. 
## Cummulative Distribution Function
The cumulative distribution function (CDF) is used in both cases and gives the probability that a random variable takes on a value less than or equal to a certain point. For a discrete random variable, the CDF is the sum of the probabilities of all values less than or equal to the given point. For a continuous random variable, the CDF is the integral of the PDF up to the given point. 

The cumulative distribution over the random variable $X$ is defined as follows:

$$P(x) = P(X \leq x)$$
So we can define the probability of $X$ being between $a$ and $b$ as:

$$P(a \leq X \leq b) = P(b) - P(a)$$

### Plot

```chartsview
#-----------------#
#- chart type    -#
#-----------------#
type: Area

#-----------------#
#- chart data    -#
#-----------------#
data:
  - label: "-5.        "
    value: 0.00669285
  - label: " -4.8989899 "
    value: 0.00739896
  - label: " -4.7979798 "
    value: 0.00817894
  - label: " -4.6969697 "
    value: 0.00904041
  - label: " -4.5959596 "
    value: 0.00999169
  - label: "        -4.49494949"
    value: 0.01104196
  - label: " -4.39393939"
    value: 0.01220126
  - label: " -4.29292929"
    value: 0.01348063
  - label: " -4.19191919"
    value: 0.01489212
  - label: " -4.09090909"
    value: 0.01644893
  - label: "        -3.98989899"
    value: 0.01816549
  - label: " -3.88888889"
    value: 0.02005754
  - label: " -3.78787879"
    value: 0.0221422
  - label: " -3.68686869"
    value: 0.02443814
  - label: " -3.58585859"
    value: 0.02696557
  - label: "        -3.48484848"
    value: 0.02974643
  - label: " -3.38383838"
    value: 0.03280439
  - label: " -3.28282828"
    value: 0.036165
  - label: " -3.18181818"
    value: 0.0398557
  - label: " -3.08080808"
    value: 0.04390588
  - label: "        -2.97979798"
    value: 0.04834692
  - label: " -2.87878788"
    value: 0.05321217
  - label: " -2.77777778"
    value: 0.0585369
  - label: " -2.67676768"
    value: 0.06435824
  - label: " -2.57575758"
    value: 0.07071501
  - label: "        -2.47474747"
    value: 0.07764755
  - label: " -2.37373737"
    value: 0.0851974
  - label: " -2.27272727"
    value: 0.093407
  - label: " -2.17171717"
    value: 0.1023192
  - label: " -2.07070707"
    value: 0.11197671
  - label: "        -1.96969697"
    value: 0.12242144
  - label: " -1.86868687"
    value: 0.13369374
  - label: " -1.76767677"
    value: 0.14583148
  - label: " -1.66666667"
    value: 0.1588691
  - label: " -1.56565657"
    value: 0.17283646
  - label: "        -1.46464646"
    value: 0.18775769
  - label: " -1.36363636"
    value: 0.20364993
  - label: " -1.26262626"
    value: 0.22052213
  - label: " -1.16161616"
    value: 0.23837374
  - label: " -1.06060606"
    value: 0.25719365
  - label: "        -0.95959596"
    value: 0.2769591
  - label: " -0.85858586"
    value: 0.29763488
  - label: " -0.75757576"
    value: 0.31917283
  - label: " -0.65656566"
    value: 0.34151151
  - label: " -0.55555556"
    value: 0.36457644
  - label: "        -0.45454545"
    value: 0.38828059
  - label: " -0.35353535"
    value: 0.41252537
  - label: " -0.25252525"
    value: 0.43720205
  - label: " -0.15151515"
    value: 0.46219351
  - label: " -0.05050505"
    value: 0.48737642
  - label: "         0.05050505"
    value: 0.51262358
  - label: "  0.15151515"
    value: 0.53780649
  - label: "  0.25252525"
    value: 0.56279795
  - label: "  0.35353535"
    value: 0.58747463
  - label: "  0.45454545"
    value: 0.61171941
  - label: "         0.55555556"
    value: 0.63542356
  - label: "  0.65656566"
    value: 0.65848849
  - label: "  0.75757576"
    value: 0.68082717
  - label: "  0.85858586"
    value: 0.70236512
  - label: "  0.95959596"
    value: 0.7230409
  - label: "         1.06060606"
    value: 0.74280635
  - label: "  1.16161616"
    value: 0.76162626
  - label: "  1.26262626"
    value: 0.77947787
  - label: "  1.36363636"
    value: 0.79635007
  - label: "  1.46464646"
    value: 0.81224231
  - label: "         1.56565657"
    value: 0.82716354
  - label: "  1.66666667"
    value: 0.8411309
  - label: "  1.76767677"
    value: 0.85416852
  - label: "  1.86868687"
    value: 0.86630626
  - label: "  1.96969697"
    value: 0.87757856
  - label: "         2.07070707"
    value: 0.88802329
  - label: "  2.17171717"
    value: 0.8976808
  - label: "  2.27272727"
    value: 0.906593
  - label: "  2.37373737"
    value: 0.9148026
  - label: "  2.47474747"
    value: 0.92235245
  - label: "         2.57575758"
    value: 0.92928499
  - label: "  2.67676768"
    value: 0.93564176
  - label: "  2.77777778"
    value: 0.9414631
  - label: "  2.87878788"
    value: 0.94678783
  - label: "  2.97979798"
    value: 0.95165308
  - label: "         3.08080808"
    value: 0.95609412
  - label: "  3.18181818"
    value: 0.9601443
  - label: "  3.28282828"
    value: 0.963835
  - label: "  3.38383838"
    value: 0.96719561
  - label: "  3.48484848"
    value: 0.97025357
  - label: "         3.58585859"
    value: 0.97303443
  - label: "  3.68686869"
    value: 0.97556186
  - label: "  3.78787879"
    value: 0.9778578
  - label: "  3.88888889"
    value: 0.97994246
  - label: "  3.98989899"
    value: 0.98183451
  - label: "         4.09090909"
    value: 0.98355107
  - label: "  4.19191919"
    value: 0.98510788
  - label: "  4.29292929"
    value: 0.98651937
  - label: "  4.39393939"
    value: 0.98779874
  - label: "  4.49494949"
    value: 0.98895804
  - label: "         4.5959596 "
    value: 0.99000831
  - label: "  4.6969697 "
    value: 0.99095959
  - label: "  4.7979798 "
    value: 0.99182106
  - label: "  4.8989899 "
    value: 0.99260104
  - label: "  5.        "
    value: 0.99330715

#-----------------#
#- chart options -#
#-----------------#
options:
  xField: label
  yField: value
```



## Probability Density Function
The Probability Density Function (PDF) represents the relative likelihood for a continuous random variable to take on a given value. The key concept of PDF is density rather than probability. The value of the PDF at any two different sample points can be different and may not equal the probability of obtaining those sample points.

Given that it’s a continuous random variable, the probability of the variable taking on any specific value is technically 0, since there are an infinite number of possible values. Instead, the value of the PDF at two different points can be used to compute the probability of falling within a certain range of values. Mathematically, the PDF is defined as the derivative of the CDF. Hence:

$$p(x) = \frac{d}{dx}P(x)$$
From the PDF we can calculate the probability of an event in within a range of the sample space as:

$$P(a \leq X \leq b) = \int^b_ap(x)dx = P(b) - P(a)$$
Intuitively, this says the probability of X being in a small interval around x is the density at x times the width of the interval. To visualize, consider the PDF of a standard normal distribution. The PDF of a standard normal distribution is given by:

$$f(x) = \frac{1}{\sqrt{2\pi}}e^{-x^2/2}$$

where e is Euler's number and x is the point up to which we want to find the probability. This PDF gives a bell-shaped curve, centered at zero and with standard deviation of 1. Now suppose we want to find the probability of the random variable falling between -1 and 1. This would be represented by the area under the PDF curve between -1 and 1 and would be computed as:

$$P(-1 \leq X \leq 1) = \int^1_{-1}f(x)dx = P(1) - P(-1)$$

This integral can be computed either by using numerical methods or using a Z-table which provides precomputed values for standard normal distributions. 

So, in summary, while the PDF gives you the relative likelihood of a continuous random variable assuming a particular value, it's really used for getting the probability that the variable falls within a certain range of values.

### Plot
```chartsview
#-----------------#
#- chart type    -#
#-----------------#
type: Area

#-----------------#
#- chart data    -#
#-----------------#
data:
  - label: "-4.18567861"
    value: 0.0000783263481
  - label: " -4.09621612"
    value: 0.000112647926
  - label: " -4.00675363"
    value: 0.000160732373
  - label: " -3.91729114"
    value: 0.000227535072
  - label: " -3.82782865"
    value: 0.000319564239
  - label: "         -3.73836615"
    value: 0.000445279636
  - label: " -3.64890366"
    value: 0.000615562746
  - label: " -3.55944117"
    value: 0.000844260864
  - label: " -3.46997868"
    value: 0.00114880369
  - label: " -3.38051619"
    value: 0.00155088581
  - label: "         -3.2910537 "
    value: 0.00207720163
  - label: " -3.2015912 "
    value: 0.00276021126
  - label: " -3.11212871"
    value: 0.0036389059
  - label: " -3.02266622"
    value: 0.00475953104
  - label: " -2.93320373"
    value: 0.006176214
  - label: "         -2.84374124"
    value: 0.00795143187
  - label: " -2.75427875"
    value: 0.0101562453
  - label: " -2.66481625"
    value: 0.0128702167
  - label: " -2.57535376"
    value: 0.0161809259
  - label: " -2.48589127"
    value: 0.0201829998
  - label: "         -2.39642878"
    value: 0.0249765757
  - label: " -2.30696629"
    value: 0.030665137
  - label: " -2.2175038 "
    value: 0.0373526793
  - label: " -2.1280413 "
    value: 0.0451401963
  - label: " -2.03857881"
    value: 0.0541215171
  - label: "         -1.94911632"
    value: 0.0643785684
  - label: " -1.85965383"
    value: 0.0759761885
  - label: " -1.77019134"
    value: 0.0889566716
  - label: " -1.68072885"
    value: 0.103334272
  - label: " -1.59126635"
    value: 0.119089939
  - label: "         -1.50180386"
    value: 0.136166602
  - label: " -1.41234137"
    value: 0.15446531
  - label: " -1.32287888"
    value: 0.173842579
  - label: " -1.23341639"
    value: 0.19410923
  - label: " -1.1439539 "
    value: 0.215030989
  - label: "         -1.0544914 "
    value: 0.236331032
  - label: " -0.96502891"
    value: 0.257694581
  - label: " -0.87556642"
    value: 0.278775533
  - label: " -0.78610393"
    value: 0.299205008
  - label: " -0.69664144"
    value: 0.318601559
  - label: "         -0.60717895"
    value: 0.336582685
  - label: " -0.51771645"
    value: 0.352777175
  - label: " -0.42825396"
    value: 0.366837749
  - label: " -0.33879147"
    value: 0.378453387
  - label: " -0.24932898"
    value: 0.387360746
  - label: "         -0.15986649"
    value: 0.393354075
  - label: " -0.070404  "
    value: 0.396293122
  - label: "  0.0190585 "
    value: 0.39610858
  - label: "  0.10852099"
    value: 0.392804813
  - label: "  0.19798348"
    value: 0.386459675
  - label: "          0.28744597"
    value: 0.377221471
  - label: "  0.37690846"
    value: 0.365303184
  - label: "  0.46637095"
    value: 0.350974324
  - label: "  0.55583345"
    value: 0.334550798
  - label: "  0.64529594"
    value: 0.316383356
  - label: "          0.73475843"
    value: 0.296845193
  - label: "  0.82422092"
    value: 0.276319318
  - label: "  0.91368341"
    value: 0.255186273
  - label: "  1.0031459 "
    value: 0.233812759
  - label: "  1.09260839"
    value: 0.212541596
  - label: "          1.18207089"
    value: 0.191683399
  - label: "  1.27153338"
    value: 0.17151018
  - label: "  1.36099587"
    value: 0.152250995
  - label: "  1.45045836"
    value: 0.134089635
  - label: "  1.53992085"
    value: 0.117164249
  - label: "          1.62938334"
    value: 0.10156869
  - label: "  1.71884584"
    value: 0.0873553333
  - label: "  1.80830833"
    value: 0.0745390465
  - label: "  1.89777082"
    value: 0.063101993
  - label: "  1.98723331"
    value: 0.0529989364
  - label: "          2.0766958 "
    value: 0.0441627456
  - label: "  2.16615829"
    value: 0.0365098302
  - label: "  2.25562079"
    value: 0.0299452811
  - label: "  2.34508328"
    value: 0.0243675469
  - label: "  2.43454577"
    value: 0.019672523
  - label: "          2.52400826"
    value: 0.0157569859
  - label: "  2.61347075"
    value: 0.0125213475
  - label: "  2.70293324"
    value: 0.00987174257
  - label: "  2.79239574"
    value: 0.00772149529
  - label: "  2.88185823"
    value: 0.00599202801
  - label: "          2.97132072"
    value: 0.00461329359
  - label: "  3.06078321"
    value: 0.00352381571
  - label: "  3.1502457 "
    value: 0.00267042334
  - label: "  3.23970819"
    value: 0.00200776037
  - label: "  3.32917069"
    value: 0.0014976436
  - label: "          3.41863318"
    value: 0.00110833209
  - label: "  3.50809567"
    value: 0.00081375969
  - label: "  3.59755816"
    value: 0.000592771445
  - label: "  3.68702065"
    value: 0.000428393833
  - label: "  3.77648314"
    value: 0.00030715952
  - label: "          3.86594564"
    value: 0.000218499066
  - label: "  3.95540813"
    value: 0.000154205557
  - label: "  4.04487062"
    value: 0.000107973033
  - label: "  4.13433311"
    value: 0.000075005897
  - label: "  4.2237956 "
    value: 0.0000516940255
  - label: " 4.31325809"
    value: 0.0000353468023
  - label: "  4.40272059"
    value: 0.0000239786509
  - label: "  4.49218308"
    value: 0.0000161385381
  - label: "  4.58164557"
    value: 0.0000107762702
  - label: "  4.67110806"
    value: 0.00000713900343

#-----------------#
#- chart options -#
#-----------------#
options:
  xField: label
  yField: value
```


## Probability Mass Function
A probability mass function is used to describe the probability distribution of a discrete random variable, which can only take on a finite or countably infinite number of values. The PMF gives the probability of the random variable taking on each possible value, and the sum of all probabilities is equal to 1. 


