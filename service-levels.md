#Service level objectives

#####What do you and your users care about?
- Too many indicators: hard to pay attention
- Too few indicators: might ignore important behavior
- Different classes of services should have different indicators
    - User-facing: availability, latency, throughput
    - Storage: latency, availability, durability
    - Big data: throughput, end-to-end latency
- All systems care about correctness

#####Collecting indicators
Can often do naturally from server, but client-side metrics sometimes needed.

#####Aggregation
- Use distributions and not averages
- User studies show that people usually prefer slower average with better tail latency
- Standardize on common defs, e.g., average over 1 minute, average over tasks in cluster, etc.
- Can have exceptions, but having reasonable defaults makes things easier

#####Choosing targets
- Don’t pick target based on current performance 
- Current performance may require heroic effort
  - Keep it simple
  - Avoid absolutes
  - Unreasonable to talk about “infinite” scale or “always” available
  - Minimize number of SLOs
  - Perfection can wait
        Can always redefine SLOs over time
    SLOs set expectations
        Keep a safety margin (internal SLOs can be defined more loosely than external SLOs)
    Don’t overachieve
        See Chubby example, above
        Another example is making sure that the system isn’t too fast under light loads

