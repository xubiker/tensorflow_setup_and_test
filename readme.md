## Tensorflow 2.11 with Python 3.10 (серверы ММОИ)
```
conda create --name tf python=3.10
conda activate tf
conda install -c conda-forge cudatoolkit=11.2.2 cudnn=8.1.0
export LD_LIBRARY_PATH=$LD_LIBRARY_PATH:$CONDA_PREFIX/lib/
python3 -m pip install tensorflow[and-cuda]==2.11.0
```

Для проверки корректности установки и распознавания GPU запустить:

```
python3 -c "import tensorflow as tf; print(tf.config.list_physical_devices('GPU'))"
```

Игрушечный проект с выбором GPU:
```
python train.py 0 # place the index of wanted GPU instead of "0"
```

P.S. Совместимость версий tensorflow, python, cudnn и cuda можно проверять по [табличке](https://www.tensorflow.org/install/source#gpu).


## Tensorflow 2.9 with Python 3.10 for M1 mac

```
conda create --name tf29 python=3.10
conda activate tf29
python -m pip install tensorflow-macos==2.9
python -m pip install tensorflow-metal==0.5.0
```