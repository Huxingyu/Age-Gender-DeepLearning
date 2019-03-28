**1，guees.py**

//是主操作程序

//年龄检测，性别检测，人脸检测

**2，preproc.py**

//预处理数据（preprocess the data using preproc.py）

```
python preproc.py --fold_dir /home/dpressel/dev/work/AgeGenderDeepLearning/Folds/train_val_txt_files_per_fold/test_fold_is_0 --train_list age_train.txt --valid_list age_val.txt --data_dir /data/xdata/age-gender/aligned --output_dir /home/dpressel/dev/work/AgeGenderDeepLearning/Folds/tf/age_test_fold_is_0

The preproc.py program generates 'shards' for each of the datasets, each containing JPEG encoded RGB images of size 256x256
```

**3,train.py**

//训练模型(train the model)

//Now that we have generated the training and validation shards, we can start training the program. 

```
python train.py --train_dir /home/dpressel/dev/work/AgeGenderDeepLearning/Folds/tf/age_test_fold_is_0
```
[gender]
```python train.py --train_dir /home/dpressel/dev/work/AgeGenderDeepLearning/Folds/tf/gen_test_fold_is_0 --max_steps 30000 --eta 0.001
```

//Train the model (fine-tuned Inception)

  //```
  python train.py --train_dir /home/dpressel/dev/work/AgeGenderDeepLearning/Folds/tf/age_test_fold_is_0 --max_steps 15000 --model_type inception --batch_size 32 --eta 0.001 --dropout 0.5 --pre_model /data/pre-trained/inception_v3.ckpt```

**4,eval.py**

//评估模型
```
//python eval.py  --run_id 15918 --train_dir /home/dpressel/dev/work/AgeGenderDeepLearning/Folds/tf/gen_test_fold_is_0/ --eval_dir /home/dpressel/dev/work/AgeGenderDeepLearning/Folds/tf/eval_gen_test_fold_is_0
```
**5，data.py**

//提供一些数据处理函数

**6，detect.py**

//利用CV2对图像进行处理，提供出一些函数

**7，dlibdetect.py**

//换作dlib处理图像，而不是opencv，本质没有区别

**8，export.py**

//[?]尝试对图片进行操作输出

**9，fliter_by_face.py**

//单个脚本文件，人脸检测（类似MNIST）

**10,model.py**

//模型处理文件，提供模型处理函数，与data.py相同作用方式

**11,utils.py**

//工具函数集合

**12,yolodetect.py**

//利用yolo处理图像，与opencv,dlib作用相同


plus:

**1,监督训练（对应正文3-train.py）**

```
tensorboard --logdir /home/dpressel/dev/work/AgeGenderDeepLearning/Folds/tf/gen_test_fold_is_0/run-31376
```
