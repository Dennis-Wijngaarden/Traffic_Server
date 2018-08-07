# Traffic_Server
## Running the traffic server with Valkenburg configuration

./VirtualEntityServer_cli -o output.log Valkenburg_InputFile.ini

# Paparazzi 
## Starting

git checkout dynamic_avoidance

git submodule sync

git submodule update

make clean && make

cd sw/lib/python/pprz_math and make

./start.py and select Conf: "userconf/tudelft/conf.xml" and Controlpanel: "userconf/tudelft/control_panel.xml" as active.

./paparazzi

## Running simulation
A/C = Easystar_Sim
(Flight plan: flight_plans/tudelft/Valkenburg_EZ_avoidance_sim.xml)

Target: nps

Session: Sim_valkenburg_EZ

## Running on disco
A/C = Disco 
(Airframe: airframes/OPENUAS/openuas_parrot_disco.xml)
(Flight plan: flight_plans/tudelft/Valkenburg_disco_avoidance.xml)

Target = ap

Session = DiscoLongRangeXbee

# Avoidance Server

## Change commanded airspeed
/sw/ground_segment/python/no_fly_zones/traffic_server.py line 583 (second input variable in mission.Mission)
 
14. m/s for simulation
 
Find out airspeed for Disco

## Change navigation block in which the avoidance runs
/sw/ground_segment/python/no_fly_zones/mission.py line 331 (for simulation 8, for disco 9)
