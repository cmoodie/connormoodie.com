# Always Restrict Solution Space
```query
children:.
```
---

Every condition restricts the solution space, i.e. if any condition is removed the solution space should increase in size.

## How Much do Conditions Restrict?
The house in decorum has 12 object slots with 5 possibilities each (all 4 colours and empty) and 4 wall painting slots with 4 options each (all 4 colours). Therefore, the number of total configurations is:

$$5^{12} \times 4^{4} = 6.25 \times 10^{10}$$

Now let's consider a simple condition: "Condition C_{0}: The **House** must contain no **Red Lamps**". The proportion of configurations that include no red lamps is

$$P(C_{0}) = (4/5)^{4} = 0.4096$$

Here's another easily calculated condition: "Condition C_{1}: The **Kitchen** and the **Bathroom** must be identical, in both objects and wall colour". The proportion of configurations that satisfy this is:

$$P(C_{1}) = (1/5)^3 \times 1/4 = 0.002$$

These are both conditions I've seen in some shape or form, and clearly restrict the space very differently.

The chance that condition C_{0} is satisfied given that condition C_{1} is satisfied is simple:

$$P(C_{0}|C_{1}) = (4/5)^{3} = 0.512$$

Therefore, we have that

$$P(C_{0} \cap C_{1}) = P(C_{0}|C_{1}) \times P(C_{1}) = (5/4) \times P(C_{0})P(C_{1})$$
$$= (5/4)^{0}P(C_{0}) \times (5/4)^{1}P(C_{1})$$
$$= \prod_{n=0}^{1}\biggl((5/4)^{n}P(C_{n})\biggr)$$

Now let's extrapolate to all conditions:

$$P(\text{Solution})= \prod_{n=0}^{7}\biggl((5/4)^{n}P(C_{n})\biggr)$$

The geometric mean of $P(C_{0})$ and $P(C_{1})$ is around 0.03. If we were to say that all 8 of our conditions' proportions have a geometric mean of 0.03, then we can say that:

$$P(\text{Solution})= \prod_{n=0}^{7}\biggl((5/4)^{n}(0.03)\biggr) \approx 3.4 \times 10^{-10}$$

This matches quite nicely with the number of total configurations, reducing it down to 1-2 possible solutions. This is perhaps too restrictive, but these calculations were rubbish anyway and just validating my choice of having 0.03 as a starting geometric mean for how much the conditions restrict.
