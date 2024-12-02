# Physics-based-OCTA-Image-Correction-for-Shadow-Compensation
## Intruduction
Optical coherence tomography (OCT) is being widely applied in clinical studies to investigate insight into the
 retina under the retinal pigment epithelium. Optical coherence
 tomography angiography (OCTA) is one of the functional
 extensions of OCT, for visualizing retinal circulation. Due
 to obstruction of light propagation, such as vitreous floaters
 or pupil boundaries, OCTA remains challenged by shadow
 artifacts that can disrupt volumetric data. Detecting and
 removing these shadow artifacts are crucial when quantifying
 indicators of retinal disease progression. We simplified an
 optical attenuation model of shadow formation in OCTA to a
 linear illumination transformation. And learn its parameters
 using an adversarial neural network. Our framework also
 consists of a sub-network for shadows automatic detection.
 We experimented our method on 28 OCTA images of normal
 eyes and compared the non-perfusion area (NPA), an index to
 measure retinal vascularity. The results showed that the NPA
 adjusted to a reasonable range after image processing using our
 method. Furthermore, we tested 150 OCTA images of synthesis
 artifacts, and the mean absolute error(MAE) values reached
 0.83 after shadow removal.<br>
This method was developed by Kang Wang from TGU-UOW laboratory based on SpA and SID.<br>
Office Website：[TGU-UOW](http://tgu-uow.gitee.io/)
## Usage
SPA-MASK<br>
·pytorch 1.8.1<br>
·python 3.8<br>
SID<br>
·follow requirements.txt<br>
### Train
#### SPA-MASK
Modify the config.yml to set your parameters and run:<br>
```
python train.py
``` 
#### SID
To generate "train_params": please run the ipython notebook included in "data_processing".

Please refer to the training script in the "scripts" folder.
### Test
#### SPA-MASK
Although the image size we trained is 256*256, the predicted image can be any size, you just need to modify the length and width in config.yml. <br>
```
python predict.py --config <path_to_config.yml_in_the_out_dir> --test_dir <path_to_a_directory_stored_test_data> --out_dir <path_to_an_output_directory> --pretrained <path_to_a_pretrained_model> --cuda
```
#### SID
1.Download the pretrained-model above and but them into ./checkpoint_path/model_name/..pth<br>
2.Set the path to the shadow-mask of the test set<br>
3.
```
python infer.py --model SIDPAMIwinp --name model_name --epoch best
```

### Pretrained model
Download the pretrained model shadow artifact-removal [Baidu Drive](https://pan.baidu.com/s/1Vh4FiW_cUK_0mXauz1mZsA) extract code：epzo  <br>
If you can't extract it,please contact us.


## Contact Us
For additional questions or discussions, Please contact email:  
wangkang9951@163.com  
liguangxu@tiangong.edu.cn
## Copyright
Do not use for commercial purposes without permission.
Copyright (c) [TGU-UOW](http://tgu-uow.gitee.io/)
## Acknowledgment
The code is based on https://github.com/zhangbaijin/SpA-Former-shadow-removal and https://github.com/cvlab-stonybrook/SID
