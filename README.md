#README:

Task: 
A social media company wants to provide information to its advertisers on how often people click
on their ads. You work for an advertiser. Each hour, the company gives you the demographic profile
of one user who saw your ad. This demographic profile is rich enough for you to identify the user
in your own database. They also give you a running count of the number of users who have actually
clicked on your ad. They add a little bit of noise “to protect users’ privacy”, but you suspect that you
can derive a good guess as to who, exactly clicked on your ads.

We’ll model this as follows: there is a sequence x of secret bits, x1, x2, x3, ..., xn ∈ {0, 1}. The bit xi
indicates that the ith user clicked on the ad.
The mechanism for releasing the running counter works as follows: At each time step i = 1, 2, ..., n,
select a uniformly random bit zi (independently of previous ones) and output ai = sum of al x's from 0 to i + zi

(In other words, at each step, we flip a coin to decide whether we should add one fake person to the
counter or not).
How well can one recover the vector x from the sequence of outputs a? The answer depends on
what we know about x ahead of time. We will consider two situations:
(a) The bits of x are uniformly random and independent. The only input to the attacker is a (the
vector of noisy counters).
(b) The bits of x are uniformly random and independent, but the attacker has some extra information. For each i, the attacker has a guess wi which is equal to xi with probability 2/3, independently for each i. The attacker’s inputs consist of a and the vector of guesses w.
