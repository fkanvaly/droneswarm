# CHALLENGE ESSAIM DE DRONE

# Environnement de simulation

## Requirements (ROS Melodic [vient avec gazebo]) #

L'environnement de simulation a été fait avec Gazebo + ROS Melodic (Ubuntu 18.04 LTS).
Par defaut la version complete de ROS vient avec Gazebo. Il faut donc d'installer la version complète: **ros-melodic-desktop-full**. Vous trouverez les instructions sur le site de ros : [lien installation](http://wiki.ros.org/melodic/Installation/Ubuntu)

## Compiler notre environnement et lancer la simulation


<table>
    <thead>
        <tr>
            <th align="center">level 1</th>
            <th align="center">level 2</th>
        </tr>
    </thead>
    <tbody>
        <tr>
            <td><img src="img/level1.jpg"></td>
            <td align="center"><img src="img/level2.jpg"></td>
        </tr>
    </tbody>
</table>

Une fois ROS installé, il suffira juste d'aller dans le dossier **simulation_ws** et compiler l'environnement.

```
cd simulation_ws
catkin build
```

Après la compilation de nouveaux dossiers se créeront et le dossier simulation_ws devrait être organisé comme suit

```
simulation_ws
    +-- build
    +-- devel
    +-- logs
    +-- src
```


Toujours dans le dossier **simulation_ws** entrer la commande:
`source devel/setup.bash`

Maintenant toutes les variables du système devraient être installées pour lancer la simulation il vous reste juste à entrer:
```
roslaunch sjtu_drone level1.launch
```
ou
```
roslaunch sjtu_drone level2.launch
```
# Package python

installation des packages python:
```
pip3 install -r requirements.txt
```


## Piloter les drones depuis Python

Le dossier **py_control** contient une interface Python permettant d'intéragir avec l'environnement de simulation dans lequel les drones évoluent. Deux classes sont fournies : ``Drone`` et ``DroneSwarm``, la seconde étant devant suffire pour se familiariser avec l'environnement.

Le fichier **exemple.py** fournit un exemple basique démontrant comment piloter un essaim de drones. Lancez Gazebo avec ``roslaunch sjtu_drone level1.launch``, mettez en marche la simulation en cliquant sur le bouton play en bas de la fenêtre qui s'ouvre, puis exécutez ``python3 exemple.py``. Notez bien dans **exemple.py** l'utilisation nécessaire de ``turn_on`` et ``turn_off`` avant et après l'envoi de toute commande. Pour plus de détails sur l'interface des classes, se référer aux fichiers **drone.py** et **drone_swarm.py**.

