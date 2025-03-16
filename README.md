Ez a projekt egy egyszerű ROS 2 csomagot tartalmaz, amely egy autonóm jármű állapotát szimulálja.  
A csomag két node-ból áll:  

- Publisher Node (publisher_node.cpp): Egy üzenetet küld a vehicle_status topic-ra, amely jelzi, hogy a jármű mozog-e.  
- Subscriber Node (subscriber_node.cpp): Feliratkozik a vehicle_status topic-ra, fogadja az üzeneteket és kiírja őket a konzolra.  

## 1. Telepítés és build  
### Lépések:  

```bash
# ROS 2 környezet betöltése
source /opt/ros/humble/setup.bash

# Csomag lefordítása
colcon build --packages-select my_autonomous_package

# Fordítás után forrásold a workspace-t
source install/setup.bash
```

## 2. Gráf

``` mermaid
graph LR;

pub([ /publisher_node]):::red --> topic1
sub([ /subscriber_node]):::red --> topic1

topic1[ /vehicle_status<br/>std_msgs/String]:::light 

classDef light fill:#34aec5,stroke:#152742,stroke-width:2px,color:#152742  
classDef dark fill:#152742,stroke:#34aec5,stroke-width:2px,color:#34aec5
classDef white fill:#ffffff,stroke:#152742,stroke-width:2px,color:#152742
classDef red fill:#ef4638,stroke:#152742,stroke-width:2px,color:#fff
