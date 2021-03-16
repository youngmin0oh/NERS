Neural Experience Replay Sampler (NERS) under Rainbow
=======
This is a source code for Neural Experience Replay Sampler (NERS) which accepted in International Conference in Learning Representation 2021 (https://openreview.net/forum?id=gJYlaqL8i8).

Although NERS can be used in various algorithms, this repository applys Rainbow implemented in https://github.com/Kaixhin/Rainbow/blob/master/README.md

Run the following command to test NERS: 

```
sh run.sh
```
The shell file will test NERS under data-effieicnt Rainbow (Prioritized Experience Replay (PER) is also used by "--replay-type PER"): 
```
CUDA_VISIBLE_DEVICES=0 python main.py --target-update 2000 \
               --T-max 100000 \
               --learn-start 1600 \
               --memory-capacity 100000 \
               --replay-frequency 1 \
               --multi-step 20 \
               --architecture data-efficient \
               --hidden-size 256 \
               --learning-rate 0.0001 \
               --evaluation-interval 1000 \
               --replay-type NERS \
               --game ms_pacman \
               --enable-cudnn
```

To install all dependencies, run the following command:

```
pip install -r requirements.txt
```