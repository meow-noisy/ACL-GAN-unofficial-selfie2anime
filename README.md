# UNOFFICIAL ACL-GAN repo for selfie2anime (including a pretrained model)
So far(Oct, 25, 2020), it seems official ACL-GAN's trained models are not available.   
I want tried selfie2anime models, so I trained them from scratch.  
Models uploaded at `models/`.


## Model Training Condition
My models weren't trained along original way.  
I used [@xunings's (unofficial) config file](https://github.com/xunings/ACL-GAN/blob/try_20200916/configs/selfie2anime.yaml). thx ;-)

Original paper say, models were trained for 350K iter and batch_size is `3`. However, I reduce batch size parameter as below and trained for `350K * 3` iterations, due to my poor GPU resources. Sorry for a little complicated way.
1. Until 90,000 iter, batch_size is `1` 
2. Until 570,000 iter, batch_size is `2`

Notice I FORGOT changing `step_size`. So the latter part of train may not work.


### Code usage
For test: 

`$ python test.py --config configs/selfie2anime.yaml --input <YOUR IMAGE_FILE PATH>  --output_folder <YOUR OUTPUT_DIR PATH> --checkpoint ./models/test.pth` 

e.g. `$ mkdir results; python test.py --config configs/selfie2anime.yaml --input inputs/test_male.jpg --output_folder results --checkpoint ./models/gen_00570000.pt`   


# link
- [original repo](https://github.com/hyperplane-lab/ACL-GAN)


