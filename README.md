# Py-denseflow


This is a modified python port of denseflow, which extract the videos' frames and **optical flow images** with **TVL1 algorithm** as default.
We added here flow_quantity argument to allow users to select the number of contiguous RGB frames from which optical flow is extracted.

Here step is fixed to 1. In a future version :
- The step argument will be used to determine the space between each couple of contiguous frames. We must beware here to avoid exceeding each clip index.
- The flow_quantity argument will still determine how many flow frames to extract from each video clip.

---

### Requirements:
- numpy
- cv2
- PIL.Image
- multiprocess
- scikit-video

## Installation
#### Install the requirements:
```
pip install -r requirements.txt

```

---

## Usage
The denseflow.py contains two modes including '**run**' and '**debug**'.


Hre 'debug' is built for debugging the video paths and video-read methods. ([IPython.embed](http://ipython.org/ipython-doc/dev/interactive/reference.html#embedding) suggested)

Just simply run the following code:

```
python denseflow.py --new_dir=flow --num_workers=1 --flow_quantity=20 --bound=20 --mode=debug

```
While in 'run' mode, here we provide multi-process as well as multi-server

for example:  server 0 need to process 3000 videos with 4 processes parallelly working:

```
python denseflow.py --new_dir=flow --num_workers=4 --step=1 --bound=20 --mode=run
```

---

Just feel free to let me know if any bugs exist.

