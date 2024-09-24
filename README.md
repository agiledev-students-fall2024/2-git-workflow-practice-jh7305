# Git Practice
Link: https://www.freedium.cfd/https://netflixtechblog.com/enhancing-netflix-reliability-with-service-level-prioritized-load-shedding-e735e6ce8f7d

Netflix’s extension of prioritized load shedding to the service level is a smart move to improve system reliability. Initially, they prioritized critical playback requests at the API gateway, but now they've applied the same logic deeper into their services. For example, PlayAPI, which handles requests for streaming, now prioritizes user-initiated requests (like hitting play) over prefetch requests (made while browsing). This ensures users can stream without delay, even during traffic spikes, without needing to split services into separate clusters, saving both time and resources.

In real-world use, this system proved crucial during a major traffic spike after an outage. Thanks to the load-shedding system, Netflix was able to maintain over 99.4% availability for user-initiated requests, while prefetch requests were throttled. This ensured a smooth experience for users. Netflix also introduced similar methods to manage CPU and IO bottlenecks, shedding less important traffic to keep the system running smoothly during high demand.

Interesting, I never read up on how these streaming services handled traffic, so this was really enlightening.
-Arnav