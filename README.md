# Another Awesome Link List
Here are a few awesome links on various topics. I find myself looking for similar things. I have put them all in one place.

## ROS:
1. How to setup a ROS 1 Package with Python
  - [Install Python Modules](http://docs.ros.org/en/melodic/api/catkin/html/howto/format2/installing_python.html#modules)
    - The documentation notes that you don't have to include .py into the CMakeLists.txt file for referencing python nodes, however, I had issues without including it.
  - [MIT: Setup Catkin Package with Python Modules](https://duckietown.mit.edu/media/pdfs/1rpRisFoCYUm0XT78j-nAYidlh-cDtLCdEbIaBCnx9ew.pdf)

  
## Using Git
1. Change Branch
  -[Change Branch Help](https://devconnected.com/how-to-switch-branch-on-git/)
2. Push Branch to Remote Repo
  -[Push Branch to Github](https://www.theserverside.com/blog/Coffee-Talk-Java-News-Stories-and-Opinions/git-push-new-branch-remote-github-gitlab-upstream-example)


## Ros Trees by QUT -> A ROS implementation of PyTrees found [here](https://github.com/qcr/ros_trees)
Various notes:
- The anatomy of a leaf:
    - The load data component simply loads in inputs to your leaf (either from the blackboard, or could just be class variables) and a return from this is the loaded value into the leaf action (i.e., in an Action leaf, this return would be a goal input to that action server)
    - The ticking is then the leaf doing its thing (i.e., in an Action server taking that input and then doing a thing)
    - The attain a result is called once the leaf's function has completed (i.e., Action server returns some result - could be a state, or whatever). This returned value from the leaf's function is what is stored in self.result.
    - The save result leaf then just decides to save it to the blackboard or not (if you specified it)
    - The evaluate the result is some additional complexity you can add to your leaf (i.e., if the Action server failed for some reason, your leaf can do something about it to help in the transition of your tree)

- Although there are various leaf classes, there isn't one for accessing the transforms tree. This doesn't have to be an action server and node, rather it can be run as a separate leaf. What happens during runtime for the leaf on the tree, is, it is attached to a tree that is a node, and subsequently the class methods are able to be accessed with the ROS framework.
