# Provisioning process

### ADRs
- [Provisioning System](../ADRs/06-ProvisioningService.md)

Simplified Flowchart

```mermaid
flowchart TD
    AWX(AWX Process)
    HUB(Central Hub)
    INSA(Detach Instance A from LB)
    INSX(Instance X )
    LB(Load Balancer)
    DPY(Provisioning)
    Attach(Attache to)
    
    HUB --> AWX
    AWX --> LB --> INSA --> DPY --> Attach  --> LB
    LB ----> INSX
```
[![](https://mermaid.ink/img/pako:eNpFkMFqwzAMhl9F6ORC-wI5DJLl0EIoha4sg1w0R2nMYns4ysYoffc5jZcZjOXPH_Jv31D7ljHDbvDfuqcg8FI2DuLIX2sVJ5yC1zyOm4XuL4V6ZieBBthP74kejudclSykezi4Uchphhy64C1Uxb9Uq_W0TrQqVOWphYKGmYeEy9Obijd_mdF4Z9w14VzmO9SygPiE12yw2z3NydcnPEC18Dnlo4jNF3Fpk5y_PHGb7Bq3aDlYMm38otssNCg9W24wi2VL4aPBxt2jR5P484_TmEmYeIvTZ0vCpaFrIItZR8PI91_fBWxM?type=png)](https://mermaid.live/edit#pako:eNpFkMFqwzAMhl9F6ORC-wI5DJLl0EIoha4sg1w0R2nMYns4ysYoffc5jZcZjOXPH_Jv31D7ljHDbvDfuqcg8FI2DuLIX2sVJ5yC1zyOm4XuL4V6ZieBBthP74kejudclSykezi4Uchphhy64C1Uxb9Uq_W0TrQqVOWphYKGmYeEy9Obijd_mdF4Z9w14VzmO9SygPiE12yw2z3NydcnPEC18Dnlo4jNF3Fpk5y_PHGb7Bq3aDlYMm38otssNCg9W24wi2VL4aPBxt2jR5P484_TmEmYeIvTZ0vCpaFrIItZR8PI91_fBWxM)

### Central Hub

Centralized instance which orchestrates processes

### Load Balancer

Edge Gateway Load balancer, manages the connection of the Edge Gateway instances.

### AWX Process

AWX process manager who orchestrates the provisioning process across the instance groups.

When the provisioning is started the AWX process connects to the Edge Gateway and executes the different actions. 


#### Provisioning

AWX process provisions changes to the existing system.


#### Detach Instance A from LB

AWX process initially detaches a instance before provisioning new application state.


#### Attach to

AWX process attaches the instance again to the Load Balancer 