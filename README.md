# Autonomous Exploration of Mobile Robots via Deep Reinforcement Learning Based on Spatiotemporal Information on Graph
This repository contains code for robot exploration under uncertainty that uses graph convolutional network (GCN), temporal convolutional network (TCN), gated recurrent unit (GRU), in conjunction with deep reinforcement learning (DRL), enabling decision-making over graphs containing exploration information to predict a robot’s optimal sensing action in belief space.

<p align='center'>
    <img src="/doc/train-test.png" alt="drawing" width="500" />
</p>

<p align="center">
  <img src="/doc/Graph-TSNN.png" alt="drawing" width="1000" />
</p>

<p align='center'>
    <img src="/doc/20.jpg" alt="drawing" width="1000" />
</p>

<p align="center">
  <img src="/doc/40.jpg" alt="drawing" width="1000" />
</p>
<p align='center'>
    <img src="/doc/stage-1.jpg" alt="drawing" width="400" />
    <img src="/doc/stage-2.jpg" alt="drawing" width="400" />
</p>


## Dependency
- Python 3
- [PyTorch](https://pytorch.org/)
- [PyTorch Geometric](https://pytorch-geometric.readthedocs.io/en/latest/#)
- Tebsorflow
- tensorboardX
- [gtsam](https://gtsam.org/) (Georgia Tech Smoothing and Mapping library)
  ```
  git clone -b emex --single-branch https://bitbucket.com/jinkunw/gtsam
  cd gtsam
  mkdir build && cd build
  cmake ..
  sudo make install
  ```
- [pybind11](https://github.com/pybind/pybind11) (pybind11 — Seamless operability between C++11 and Python)
  ```
  git clone https://github.com/pybind/pybind11.git
  cd pybind11
  mkdir build && cd build
  cmake ..
  sudo make install
  ```
 
## Compile
You can use the following commands to download and compile the package.
```
git clone https://github.com/zhangzw-nudt/Graph-STNN_Exploration.git
cd Graph-STNN_Exploration
mkdir build && cd build
cmake ..
make
```


## How to Run?
- To run the saved policy:
    ```
    cd DRL_graph_exploration/scripts
    python3 test_entropy.py
    ```
- To show the average reward and loss during the training:
    ```
    cd DRL_graph_exploration/scripts
    tensorboard --logdir=log
    ```
- To train your own policy:
    ```
    cd DRL_graph_exploration/scripts
    python3 train.py
    ```


## Attention
- please visit [this web page](https://gitee.com/zhangzhiwen_nudt/Graph-STNN_Exploration.git) for our code for the reason of our network problem.
- We have abandoned this platform，and will not maintain this code.
- We are building a simulation environment closer to the real robot based on the Stage.
- Our work is mainly based on [this article](https://arxiv.org/pdf/2007.12640.pdf), please site it if you use any of this code.
```
@inproceedings{ExplorGraphDRL2020,
  title={Autonomous Exploration Under Uncertainty via Deep Reinforcement Learning on Graphs},
  author={Chen, Fanfei and Martin, John D. and Huang, Yewei and Wang, Jinkun and Englot, Brendan},
  booktitle={IEEE/RSJ International Conference on Intelligent Robots and Systems (IROS)},
  year={2020},
}
```


## Cite
- Please cite [our paper](https://www.mdpi.com/2076-3417/11/18/8299/pdf) if you use any of this code.
```
@article{Graph-STNN2021,
  title={Autonomous Exploration of Mobile Robots via Deep Reinforcement Learning Based on Spatiotemporal Information on Graph},
  author={Zhiwen Zhang, Chenghao Shi, Pengming Zhu, Zhiwen Zeng and Hui Zhang},
  journal={Applied Sciences},
  year={2021},
  volume = {11},
  number = {18},
  article-number = {8299},
  url = {https://www.mdpi.com/2076-3417/11/18/8299},
  issn = {2076-3417},
  abstract = {In this paper, we address the problem of autonomous exploration in unknown environments for ground mobile robots with deep reinforcement learning (DRL). To effectively explore unknown environments, we construct an exploration graph considering historical trajectories, frontier waypoints, landmarks, and obstacles. Meanwhile, to take full advantage of the spatiotemporal feature and historical information in the autonomous exploration task, we propose a novel network called Spatiotemporal Neural Network on Graph (Graph-STNN). Specifically, the proposed Graph-STNN extracts the spatial feature using graph convolutional network (GCN) and the temporal feature using temporal convolutional network (TCN). Then, gated recurrent unit (GRU) is performed to synthesize the spatial feature, the temporal feature, and the historical state information into the current state feature. Combined with DRL, our Graph-STNN helps estimation of the optimal target point through extracted hybrid features. The simulation experiment shows that our approach is more effective than the GCN-based approach and the information entropy-based approach. Moreover, Graph-STNN also performs better generalization ability than GCN-based, information entropy-based, and random methods. Finally, we validate our approach on the simulation platform Stage with the actual robot model.},
  doi = {10.3390/app11188299}
}
```


## Reference
- [em_exploration](https://github.com/RobustFieldAutonomyLab/em_exploration)
- [DRL_graph_exploration](https://github.com/RobustFieldAutonomyLab/DRL_graph_exploration)
# Graph-STNN_Exploration
