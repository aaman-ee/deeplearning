# Prerequisites

All the examples and training are done in Ubuntu 14.04.5 LTS Desktop (64-bit) which you can download [here](http://www.ubuntu.com/download/alternative-downloads). The installation is very easy and I would recommend to make a fresh install without partitions. 
If you are not familiar with Linux, this is great place to start [flashing the Ubuntu ISO from Windows](http://www.ubuntu.com/download/desktop/create-a-usb-stick-on-windows) in a USB Stick. 

Your desktop pc can serve also as a Deep Learning Server, in terms that labelling training data and even the CNN training process can be done remotely using the web interfaces that we will introduce later. This means that members of your team can work at the same time in training a network and labelling at the same time your future training data. A strong GPU is necessary for the training, and if multiple GPUs are present, multiple networks can be trained at the same time. 

For the current workshop, an Intel i7 with 32GB RAM is used, with an [NVidia TitanX (12GB) GPU](http://www.evga.com/articles/00935/EVGA-GeForce-GTX-TITAN-X-HYBRID/), [1KW Power Supply](http://www.evga.com/Products/Product.aspx?pn=120-G2-1000-XR) and 512GB SSD. 

In our tutorial, the training data preparation and the network training will be processed on the DL Server, while the deployment/inference of your trained network will be realized in low-power [TX1 NVIDIA developer Kit](http://www.nvidia.com/object/jetson-tk1-embedded-dev-kit.html). Don't worry If you don't have the current board since inference can be done also in your DL Server using a connected camera.

So, in terms of H/W we have:
  ⋅*Deep Learning Server (Intel i7, 32GB RAM, NVidia TitanX, 512 SSD)
