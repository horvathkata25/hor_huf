Ez a projekt egy egyszerű ROS 2 csomagot tartalmaz, amely egy autonóm jármű állapotát szimulálja.  
A csomag két node-ból áll:  

- Publisher Node (publisher_node.cpp): Egy üzenetet küld a vehicle_status topic-ra, amely jelzi, hogy a jármű mozog-e.  
- Subscriber Node (subscriber_node.cpp): Feliratkozik a vehicle_status topic-ra, fogadja az üzeneteket és kiírja őket a konzolra.  

## 1. Telepítés és build  
A projekt build-eléséhez kövesd az alábbi lépéseket:  

```bash
# ROS 2 környezet betöltése
source /opt/ros/humble/setup.bash

# Csomag lefordítása
colcon build --packages-select my_autonomous_package

# Fordítás után forrásold a workspace-t
source install/setup.bash
