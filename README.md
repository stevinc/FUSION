# Few-Shot Unsupervised Continual Learning through Meta-Examples
This repository contains the PyTorch code for *<a href="https://nips.cc/Conferences/2020/">NeurIPS 2020</a>*, *<a href="https://meta-learn.github.io/2020/">4th Workshop on Meta-Learning</a>* paper:

**<a href="https://arxiv.org/abs/2009.08107">Few-Shot Unsupervised Continual Learning through Meta-Examples</a>**  
*<a href="https://aimagelab.ing.unimore.it/imagelab/person.asp?idpersona=110">Alessia Bertugli</a>,
<a href="https://aimagelab.ing.unimore.it/imagelab/person.asp?idpersona=111">Stefano Vincenzi</a>,
<a href="https://aimagelab.ing.unimore.it/imagelab/person.asp?idpersona=38">Simone Calderara</a>,
<a href="http://disi.unitn.it/~passerini/">Andrea Passerini</a>*  

## Model architecture
![FUSION-ME - overview](/images/model.png)

Scheme of FUSION-ME. The model is composed of 4 phases: embedding learning network phase, unsupervised task construction phase, meta-continual training phase and meta-continual test phase.
## Prerequisites
* Python >= 3.8
* PyTorch >= 1.5
* CUDA 10.0


## Datasets
* *<a href="https://github.com/brendenlake/omniglot">Omniglot</a>*
* *<a href="http://www.image-net.org">Mini-ImageNet</a>*
* *<a href="https://zenodo.org/record/3672132#.X2R9ay2w3pA">SlimageNet64</a>*
* *<a href="https://www.cs.toronto.edu/~kriz/cifar.html">Cifar100</a>*
* *<a href="http://www.vision.caltech.edu/visipedia/CUB-200.html">Cub</a>*

## Embeddings
You can generate embeddings for Mini-ImageNet and SlimageNet64 using the code of *<a href="https://github.com/facebookresearch/deepcluster">DeepCluster</a>*
and for Omniglot the code of *<a href="https://github.com/brain-research/acai">ACAI</a>* or download them from [here](https://drive.google.com/drive/folders/12sXdgg_Cahoki1ldrhI5jXnAOe3RrHhC?usp=sharing).

## Best models
Available soon.

## Usage Example on Omniglot
1. Download the embeddings from the link above, then set the ``data_folder`` variable in the ``get_embeddings`` function contained in the ``dataset/utils.py`` file equal to your dataset path;
1. in the file ``trainers/fusion.py`` set the arg ``--dataset`` equal to the dataset name you want to train on (e.g. Omniglot or Imagenet);
1. set the arg ``--attention`` to exploit the meta-examples and ``--num_clusters`` to the desired number of clusters;
1. run the file ``trainers/fusion.py``.
* Note that the _unsupervised task construction_ is carried out by the function ``cactus_unbalance`` defined in the file ``dataset/dataset_factory`` and executed in the ``trainers/fusion.py`` file.

## Credits
* *<a href="https://github.com/kylehkhsu/cactus-maml">CACTUs-MAML: Clustering to Automatically Generate Tasks for Unsupervised Model-Agnostic Meta-Learning</a>*
* *<a href="https://github.com/khurramjaved96/mrcl">Meta-Learning Representations for Continual Learning</a>*
* *<a href="https://github.com/facebookresearch/deepcluster">Deep Clustering for Unsupervised Learning of Visual Features</a>*


## Cite
If you have any questions,  please contact [alessia.bertugli@unitn.it](mailto:alessia.bertugli@unitn.it)  or [stefano.vincenzi@unimore.it](mailto:alessia.bertugli@unimore.it), or open an issue on this repo. 

If you find this repository useful for your research, please cite the following paper:
```bibtex
@article{Bertugli2020fusion-me,
  title={Few-Shot Unsupervised Continual Learning through Meta-Examples},
  author={Alessia Bertugli and Stefano Vincenzi and Simone Calderara and Andrea Passerini},
  journal={34rd Conference on Neural Information Processing Systems (NeurIPS 2020), 4th Workshop on Meta-Learning},
  year={2020},
  volume={abs/2009.08107}
}
```
