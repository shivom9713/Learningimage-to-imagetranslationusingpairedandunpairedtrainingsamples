# Learningimage-to-imagetranslationusingpairedandunpairedtrainingsamples
This is the implementation for the  "Learning image-to-image translation using paired and unpaired training samples" (https://arxiv.org/pdf/1805.03189.pdf)). This paper is accepted in ACCV 2018. 
 
 **Training**
 1. Downlaod cityscapes datasets as in pix2pix and cyclegan as sugggested in [here](https://github.com/junyanz/pytorch-CycleGAN-and-pix2pix) 
 2. Create a folder name *datasets* with the subfolder structures as given in this repo.
 3. Keep the paired data in *train*-subfolder and unpaired data in *trainA* and *trainB* subfolders.
 4. Then run: *python train.py --dataroot ./datasets --model cycle_gan --dataset_mode unaligned --which_model_netG resnet_9blocks --which_direction AtoB --super_epoch 50 --super_epoch_start 0 --super_mode aligned --super_start 1 --name mygan_70 --no_dropout*
**Testing**
 1. Downlaod cityscapes test data as in cyclegan as sugggested in [here](https://github.com/junyanz/pytorch-CycleGAN-and-pix2pix) 
 2. Keep the test data in *testA* and *testB* subfolders within *datasets* folder.
 3. Then run: *python test.py --dataroot ./datasets --model cycle_gan --dataset_mode unaligned --which_model_netG resnet_9blocks --which_direction AtoB --name mygan_70 --how_many 100*
 
 *Training Tips:*
 1. With less paired data, increase the --super_epoch value for better results. 
 2. With No paired data, set --super_start 0. 
 3. For no unpaired data, set --super_epoch and --niter to same value. 
 
 *Note*: If you are using this implementation for your research work then please cite us as: 
 
@article{tripathy+kannala+rahtu,
  title={Learning image-to-image translation using paired and unpaired training samples},
  author={Tripathy, Soumya and Kannala, Juho and Rahtu, Esa},
  journal={arXiv preprint arXiv:1805.03189},
  year={2018}
}
