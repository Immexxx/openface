# OpenFace • [ ![Build Status] [travis-image] ] [travis] [ ![Release] [release-image] ] [releases] [ ![License] [license-image] ] [license] [ ![Gitter] [gitter-image] ] [gitter]

*Free and open source face recognition with
deep neural networks.*


[travis-image]: https://travis-ci.org/cmusatyalab/openface.png?branch=master
[travis]: http://travis-ci.org/cmusatyalab/openface

[release-image]: http://img.shields.io/badge/release-0.2.1-blue.svg?style=flat
[releases]: https://github.com/cmusatyalab/openface/releases

[license-image]: http://img.shields.io/badge/license-Apache--2-blue.svg?style=flat
[license]: LICENSE

[gitter-image]: https://badges.gitter.im/Join%20Chat.svg
[gitter]: https://gitter.im/cmusatyalab/openface

---

+ Website: http://cmusatyalab.github.io/openface/
+ [API Documentation](http://openface-api.readthedocs.org/en/latest/index.html)
+ Join the
  [cmu-openface group](https://groups.google.com/forum/#!forum/cmu-openface)
  or the
  [gitter chat](https://gitter.im/cmusatyalab/openface)
  for discussions and installation issues.
+ Development discussions and bugs reports are on the
  [issue tracker](https://github.com/cmusatyalab/openface/issues).

---

KAR: 

Setup: This Dockerfile has the "setup" 

On OpenFace, the setup instructions point to Dockerhub - which has the contents of this file. 

This Dockerfile uses a prebuilt image with OpenCV, DLib, Torch. On top of that image, it pulls in more things. 

To start with, create a Docker image with this Docker file and see where it takes you! 

#git clone "this repo" (#git clone https://github.com/Immexxx/openface.git) 

(To build the Docker image - use the following command. Tip: looks like this takes a long time) 

#docker build -t openface .

(Alternatively, try - takes about ~ 10-15 mins for the build to complete) 

#docker pull bamos/openface  

($docker images - will show: )

bamos/openface                                                      latest              4a661a4cae83        3 days ago          1.941 GB

Jump into that Docker image: 

$docker run -p 9000:9000 -p 8000:8000 -t -i bamos/openface  /bin/bash

From: https://cmusatyalab.github.io/openface/setup/

$cd /root/openface /n
$./run-tests.sh \n
$./demos/compare.py images/examples/{lennon*,clapton*} /n
$./demos/classifier.py infer models/openface/celeb-classifier.nn4.small2.v1.pkl ./images/examples/carell.jpg \n
$./demos/web/start-servers.sh \n








This research was supported by the National Science Foundation (NSF)
under grant number CNS-1518865.  Additional support
was provided by the Intel Corporation, Google, Vodafone, NVIDIA, and the
Conklin Kistler family fund.  Any opinions, findings, conclusions or
recommendations expressed in this material are those of the authors
and should not be attributed to their employers or funding sources.

# What's in this repository?
+ [batch-represent](https://github.com/cmusatyalab/openface/tree/master/batch-represent): Generate representations from
  a batch of images. [Example directory structure.](https://gist.github.com/bamos/f03037f5df7e05ad0cc8)
+ [demos/web](https://github.com/cmusatyalab/openface/tree/master/demos/web): Real-time web demo.
+ [demos/compare.py](https://github.com/cmusatyalab/openface/tree/master/demos/compare.py): Demo to compare two images.
+ [demos/vis-outputs.lua](https://github.com/cmusatyalab/openface/tree/master/demos/vis-outputs.lua): Demo to
  visualize the network's outputs.
+ [demos/classifier.py](https://github.com/cmusatyalab/openface/tree/master/demos/classifier.py): Demo to train and use classifiers.
+ [demos/classifier_webcam.py](https://github.com/cmusatyalab/openface/blob/master/demos/classifier_webcam.py): Demo to use a trained classifier on a webcam stream.
+ [evaluation](https://github.com/cmusatyalab/openface/blob/master/evaluation): LFW accuracy evaluation scripts.
+ [openface](https://github.com/cmusatyalab/openface/tree/master/openface): Python library code.
+ [models](https://github.com/cmusatyalab/openface/tree/master/models): Model directory for openface and 3rd party libraries.
+ [tests](https://github.com/cmusatyalab/openface/tree/master/tests): Tests for scripts and library code, including neural network training.
+ [training](https://github.com/cmusatyalab/openface/tree/master/training): Scripts to train new OpenFace neural network models.
+ [util](https://github.com/cmusatyalab/openface/tree/master/util): Utility scripts.

# Citations

Please cite OpenFace in your publications if it helps your research.
The following is a [BibTeX](http://www.bibtex.org/) and plaintext reference for our
[OpenFace tech report](http://reports-archive.adm.cs.cmu.edu/anon/anon/2016/CMU-CS-16-118.pdf).

```
@techreport{amos2016openface,
  title={OpenFace: A general-purpose face recognition
    library with mobile applications},
  author={Amos, Brandon and Bartosz Ludwiczuk and Satyanarayanan, Mahadev},
  year={2016},
  institution={CMU-CS-16-118, CMU School of Computer Science},
}

B. Amos, B. Ludwiczuk, M. Satyanarayanan,
"Openface: A general-purpose face recognition library with mobile applications,"
CMU-CS-16-118, CMU School of Computer Science, Tech. Rep., 2016.
```

# Licensing
Unless otherwise stated, the source code and trained Torch and Python
model files are copyright Carnegie Mellon University and licensed
under the [Apache 2.0 License](./LICENSE).
Portions from the following third party sources have
been modified and are included in this repository.
These portions are noted in the source files and are
copyright their respective authors with
the licenses listed.

Project | Modified | License
---|---|---|
[Atcold/torch-TripletEmbedding](https://github.com/Atcold/torch-TripletEmbedding) | No | MIT
[facebook/fbnn](https://github.com/facebook/fbnn) | Yes | BSD
