# Notes on Software Reliability

1. Chapter 1: Introduction

Everything in this chapter is covered in much more detail later.

Two approaches to hiring people to manage system stability:

- <b>Traditional approach: sysadmins</b>

  - Assemble existing components and deploy to produce a service
  - Respond to events and updates as they occur
  - Grow team to absorb increased work as service grows
  
  
  ###### Pros
    1. Easy to implement because it’s standard
    2. Large talent pool to hire from
    3. Lots of available software
    
  ###### Cons
    1. Manual intervention for change management and event handling causes size of team to scale with load on system
    2. Ops is fundamentally at odds with dev, which can cause pathological resistance to changes, which causes similarly pathological response from devs, which reclassify “launches” as “incremental updates”, “flag flips”, etc.

Resources

1. [ Jamie Brandon’s notes on books he’s read](http://scattered-thoughts.net/)
