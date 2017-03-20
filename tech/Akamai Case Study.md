# Akamai Case Study
> Tue, 14 Mar 2017 at 12:02:03 MYT

1. internet traffic has increased over 500% since 2010 and predicted to nearly triple over the next five years
- Experts call services like YouTube, Netflix & HD streaming video "net bombs" because they threaten the effective operation of the internet
- growth: exponential
- analyst differ on how fast internet traffic is growing
- *Akamai is one of the web's major helper*
- Akamai serves more than 25 terabits of web traffic per second
- Akamai founded by Tom Leighton, MIT professor of applied math, and Daniel Lewin, MIT grad student
- Akamai officially launched in August 1998
- Akamai Intelligent Platform, a cloud platform made up of over 200.000 servers in 110 countries within over 1400 networks around the world. and all within a single network hop of 85% of all internet users
- Akamai's software determines which server is optimium for the user and transmits the *Akamaized* content locally
- Akamaized web content can be delivered up from 4-10 times faster than non-akamaized content

---
> *Why does Akamai need to geographically disperse its servers to deliver its customers' web content?*

Akamai does so because they map the location of user's request with the nearest Akamai's server. This way, Akamai can make sure that each traffic is served from the closest server relative to that traffice which make the delivery speed faster, and more bandwidth efficient.


> *If you wanted to deliver software content over the internet, would you sign up for Akamai's service? Why or why not?*

It depends on the need, because for CDN, we have other options beside Akamai, eg. AWS Cloudfront, Cloudflare, etc.

Cloudflare has good performance and offer free plan. However, when the content we want to provide is a massive content with very diverse geographical network, Akamai might be better choice because Akamai offers more robust solution.

Other than that, Akamai has way more edge locations especially internationally, where CloudFront suffers.

CloudFront is targeting customers who don't need Akamai and don't have the traffic to justify it. Amount and location of the traffic are common keys to determine which CDN we want to use. Or even, no CDN at all.

For instance, if we know that the content we provide is only accessible from small geographical location, using Akamai will not be a good choice. However, when the traffic is from around the world, Akamai will be a big help for the system. The system owners does not need to create their own insfrastructure to make sure that the content is delivered as fast as possible, because they can simply use Akamai's service.

