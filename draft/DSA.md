# DSA - Section 5
> Thu, 16 Mar 2017 at 10:26:27 MYT

- use stack to show step-by-step evaluation of the post-fix expression given below:
`5.2 2.0 1.5 * + 4.0 2.0 2.0 ^ * -`
> if it's operand, push. if it's operator, pop 2 times

    - see number: push
    - see asterisk: pop 2 times
- stack: LIFO (last in first out)
- queue: FIFO (first in first out)

Q1. Why does Akamai need to geographically disperse its servers to deliver its customers' web content?
Akamai does so because they map the location of user's request with the nearest Akamai's server. This way, Akamai make sure that each traffic is served from the closest server relative to the traffic which make the delivery speed faster, and more bandwidth efficient.
