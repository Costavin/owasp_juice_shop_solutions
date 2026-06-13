# Multiple Likes

Here it is asked to put at least 3 likes on the same product review. However, json tampering doesn't lead anywhere. Once a comment gets liked, its state is very hard to change. However, it can be exploited the small time frame where the update record is created, and not committed yet. In that small time frame, we need to deliver additional payloads that will still be counted until committment. That's known as race conditions, where it is exploited a small window time frame of ambiguos state to trigger an error, or misbehaviour.

## Remediation

A possible way to prevent this kind of condition is actually to put semaphores, or locks, on resources that are getting modified. In this way, once a resource is getting modified by a request, it won't be available to other requests until committment.
