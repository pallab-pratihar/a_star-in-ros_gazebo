# a_star-in-ros_gazebo
Path planning using A* algorithm and implementation on turtlebot waffle in Gazebo simulation.
## Setup

### Clone the repo
git clone https://github.com/pallab-pratihar/a_star-in-ros_gazebo.git
### Create a workspace
mkdir -p project4_ws/src
### To run the default config of [`astar_sim.py`]
python3 astar_sim.py
### Example with full arguments:

python3 astar_sim.py --rpm1 50.0 --rpm2 100.0 --StartNode 200_200 --GoalNode 5000_1500 --Ori 45 --rr 150
### For different Heuristic function
python3 astar_sim_modified.py --heuristic euclidean

python3 astar_sim_modified.py --heuristic manhattan

python3 astar_sim_modified.py --heuristic diagonal

python3 astar_sim_modified.py --heuristic dijkstra


# Gazebo Simulation
### Source ROS
source install/setup.bash
### Build the workspace
cd project4_ws
colcon build --packages-select turtlebot3_project3
### Launch Environment
ros2 launch turtlebot3_project3 competition_world.launch.py
### To run the ROS node

You can use the `vel_publisher.py` for the following:

ros2 run turtlebot3_project3 vel_publisher.py
### To adjust the goal point

Use the `--GoalNode` flag to set the point. Example:

ros2 run turtlebot3_project3 vel_publisher.py --GoalNode 5750_500
