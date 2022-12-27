# Deep Attention-guided Graph Clustering with Dual Self-supervision

[python-img]: https://img.shields.io/github/languages/top/ZhihaoPENG-CityU/DAGC?color=lightgrey
[stars-img]: https://img.shields.io/github/stars/ZhihaoPENG-CityU/DAGC?color=yellow
[stars-url]: https://github.com/ZhihaoPENG-CityU/DAGC/stargazers
[fork-img]: https://img.shields.io/github/forks/ZhihaoPENG-CityU/DAGC?color=lightblue&label=fork
[fork-url]: https://github.com/ZhihaoPENG-CityU/DAGC/network/members
[visitors-img]: https://visitor-badge.glitch.me/badge?page_id=ZhihaoPENG-CityU.DAGC
[agcn-url]: https://github.com/ZhihaoPENG-CityU/DAGC

[![Made with Python][python-img]][agcn-url]
[![GitHub stars][stars-img]][stars-url]
[![GitHub forks][fork-img]][fork-url]
[![visitors][visitors-img]][agcn-url]

DOI: 

URL: http://arxiv.org/abs/2111.05548

We have added comments in the code, the specific details can correspond to the explanation in the paper.

We appreciate it if you use this code and cite our paper, which can be cited as follows,
> @article{peng2021deep, <br>
>   title={Deep Attention-guided Graph Clustering with Dual Self-supervision}, <br>
>   author={Peng, Zhihao and Liu, Hui and Jia, Yuheng and Hou, Junhui},  <br>
>   journal={arXiv preprint arXiv:2111.05548},  <br>
>   year={2022}
> } <br>

# Environment
+ Python[3.6.12]
+ Pytorch[1.9.0+cu102]
+ GPU (GeForce RTX 2080 Ti) & (NVIDIA GeForce RTX 3090) & (Quadro RTX 8000)

# To run code
+ Step 1: choose the data, i.e., [data_name]=acm/cite/dblp/hhar/reut/usps/amap/pubmed/aids
+ Step 2: python DAGC.py --name [data_name]
* For examle, if u would like to run AGCN on the ACM dataset, u need to
* run the command "python DAGC.py --name acm"

# Evaluation
+ evaluation.py
👉
The commonly used clustering metrics, such as acc, nmi, ari, and f1, etc.
+ get_net_par_num.py
👉
Get the network parameters by `print(num_net_parameter(model))', where model is the designed network.

# Data
Due to the limitation of GitHub, we share the data in [<a href="https://drive.google.com/drive/folders/1D_kH2loUTH6fHfdwnVElUHVw1kHfflVV?usp=sharing">here</a>].

# Q&A
* Q1: What we use the cosine similarity measure as a distance measure to construct graph data for non-graph datasets?
* A1: KNN graph construction with the Euclidean distance measure fails to exploit the geometric structure information and hence cannot provide an effective KNN graph. Instead, we use the cosine similarity measure as a distance measure to conduct the KNN-k graph construction, since two samples owing to the same cluster tend to have larger absolute cosine values than those lying in different clusters.
* Q2: What device was the experiment run on?
* A2: The experiments are run on the Pytorch platform using an Intel(R) Core(TM) i7-8700K CPU @ 3.70GHz, 32.0GB RAM, and a NVIDIA GeForce RTX 2080-Ti 27.0GB GPU. Particularly, for the large-scale dataset, the experiments are run on a dedicated server in the laboratory, which has an Intel(R) Xeon(R) Gold 6226R CPU @ 2.90GHz, a Quadro RTX 8000 49152 MB GPU. 
