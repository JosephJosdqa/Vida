## 3D Face Visualization

We use `pytorch3d` to visualize the 3D faces from a single image.

The requirements for 3D visualization are difficult to install, so here's a tutorial:

```bash
git clone https://github.com/JosephJosdqa/VIDAI
cd VIDAI 
conda create -n VIDAI3d python=3.8
source activate VIDAI3d

conda install ffmpeg
conda install -c fvcore -c iopath -c conda-forge fvcore iopath
conda install libgcc gmp

pip install torch==1.11.0+cu113 torchvision==0.12.0+cu113 torchaudio==0.11.0 --extra-index-url https://download.pytorch.org/whl/cu113

# insintall pytorch3d
pip install --no-index --no-cache-dir pytorch3d -f https://dl.fbaipublicfiles.com/pytorch3d/packaging/wheels/py38_cu113_pyt1110/download.html

pip install -r requirements3d.txt

### install gpfgan for enhancer
pip install git+https://github.com/TencentARC/GFPGAN


### when occurs gcc version problem `from pytorch import _C` from pytorch3d, add the anaconda path to LD_LIBRARY_PATH
export LD_LIBRARY_PATH=$LD_LIBRARY_PATH:/$YOUR_ANACONDA_PATH/lib/

``` 

Then, generate the result via:

```bash


python inference.py --driven_audio <audio.wav> \
                    --source_image <video.mp4 or picture.png> \
                    --result_dir <a file to store results> \
                    --face3dvis

```

The results will appear, named `face3d.mp4`.

More applications about 3D face rendering will be released soon.
