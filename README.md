1、setup.py安装依赖包

2、两种训练方式

1）直接输入视频，对嘴唇进行预测，然后训练

2）先对嘴唇进行预测，并将嘴唇分割成图片，然后对图片数据集进行训练

3）方法1）暂时没跑通，先用2），数据集在http://spandh.dcs.shef.ac.uk/gridcorpus/

3、流程

1）下载数据，下载任意一个talker的video(normal)和wordalignments

2）将video转换为嘴唇图片，执行scripts目录下的extract_mouth_batch.py，用法写在脚本里，人脸特征需要的模型是common/predictors/shape_predictor_68_face_landmarks.dat

3）训练场景有5个，都在training目录下，暂选overlapped_speakers，在该文件夹下建立datasets，结构为

datasets/align/*.align

datasets/train/s{i}/{id}/*.png

datasets/val/s{i}/{id}/*.png

i为talker的index

4）执行根目录下的train，用法写在脚本里
