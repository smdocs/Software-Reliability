# Notes on Software Reliability

#### 1. Chapter 1: Introduction

Everything in this chapter is covered in much more detail later.

Two approaches to hiring people to manage system stability:

- <b>Traditional approach: sysadmins</b>

  - Assemble existing components and deploy to produce a service
  - Respond to events and updates as they occur
  - Grow team to absorb increased work as service grows
  
  
  ###### Pros
    1. Easy to implement because it’s the norm
    2. Large talent pool to hire from since there are no specific job requirements.
    
  ###### Cons
    1. Manual intervention for change management and event handling causes size of team to scale with load on system
    2. Ops is fundamentally at odds with dev, which can cause pathological resistance to changes, which causes similarly pathological response from devs, which reclassify “launches” as “incremental updates”, “flag flips”, etc.
    

- <b> Software Reliability Engineering Approach </b>
  - Find ways to improve the design and operation of systems 
  - Have software engineers do operations in order to continually improve production environments and systems.
  - Candidates should be able to pass or nearly pass normal dev hiring bar, and may have some additional skills that are rare among devs (e.g., L1 - L3 networking or Linux system internals or Database internals).
  - Career progress comparable to dev career track

  ###### Results
  - SREs would be bored by doing tasks by hand
  - Have the skillset necessary to automate tasks
  - Do the same work as an operations team, but with automation instead of manual labor. To avoid manual labor trap that causes team size to scale with service load, place a 50% cap on the amount of “ops” work for SREs

  Upper bound. Actual amount of ops work is expected to be much lower

##### Resposibilitiesof SRE

> SRE team is responsible for latency, performance, efficiency, change management, monitoring, emergency response, and capacity planning

- <b> Ensuring a durable focus on engineering</b>
  - 50% ops cap means that extra ops work is redirected to product teams on overflow
  - Provides feedback mechanism to product teams as well as keeps load down
  - Target max 2 events per 8-12 hour on-call shift
  - Postmortems for all serious incidents, even if they didn’t trigger a page
  - Blameless postmortems

- <b> Move fast without breaking SLO</b>
  - Error budget. 100% is the wrong reliability target for basically everything
  - Going from 5 9s to 100% reliability isn’t noticeable to most users and requires tremendous effort
  - Set a goal that acknowledges the trade-off and leaves an error budget
  - Error budget can be spent on anything: launching features, etc.
  - Error budget allows for discussion about how phased rollouts and 1% experiments can maintain tolerable levels of errors
  - Goal of SRE team isn’t “zero outages” – SRE and product devs are incentive aligned to spend the error budget to get maximum feature velocity

- <b>Monitoring</b>
  - Monitoring should never require a human to interpret any part of the alerting domain. Three valid kinds of monitoring output
      - Alerts: human needs to take action immediately
      - Tickets: human needs to take action eventually
      - Logging: no action needed. Note that, for example, graphs are a type of log

- <b>Emergency Response</b>
  - Reliability is a function of MTTF (mean-time-to-failure) and MTTR (mean-time-to-recovery)
  - For evaluating responses, we care about MTTR
  - Humans add latency
  - Systems that don’t require humans to respond will have higher availability due to lower MTTR
  - Having a “playbook” produces 3x lower MTTR
  - Having hero generalists who can respond to everything works, but having playbooks works better
  
- <b>Change management</b>
  - 70% of outages due to changes in a live system. Mitigation:
      - Implement progressive rollouts
      - Monitoring
      - Rollback
  - Remove humans from the loop, avoid standard human problems on repetitive tasks
  - Demand forecasting and capacity planning. Straightforward, but a surprising number of teams/services don’t do it




#### Resources

1. [ Jamie Brandon’s notes on books he’s read](http://scattered-thoughts.net/)
