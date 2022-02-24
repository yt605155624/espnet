1. 下载标贝数据集到 
downloads/CSMSC
├── PhoneLabeling
├── ProsodyLabeling
└── Wave
注意 BZNSYP.rar 直接解压缩之后是 BZNSYP, 需要改名为 CSMSC
或者假设你的数据集已经在 ~/datasets/BZNSYP, 可以通过如下方式建立软连接
```bash
mkdir downloads
ln -snf ~/datasets/BZNSYP downloads/CSMSC
```
2. 数据预处理
```bash
./run.sh --stage 1 --stop-stage 1
./run.sh --stage 2 --stop-stage 2
./run.sh --stage 3 --stop-stage 3
./run.sh --stage 4 --stop-stage 4
./run.sh --stage 5 --stop-stage 5
```
or 
```bash
./run.sh --stage 1 --stop-stage 5
```
3. 开始训练
```bash
./run.sh --stage 6 --stop-stage 6
```
4. 查看训练曲线:
```bash
cd exp/tts_train_raw_phn_pypinyin_g2p_phone/tensorboard
tensorboard --logdir=./ --host=0.0.0.0 --port=8123
```
查看训练 log: 
```text
tail -f  exp/tts_train_raw_phn_pypinyin_g2p_phone/train.log
```
训练开始时间：
Wed Feb 16 06:15:40 UTC 2022
