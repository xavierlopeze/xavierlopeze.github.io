---
layout: post
title: Style Transfer
subtitle: Styling with Neural Networks
gh-repo: lengstrom/fast-style-transfer
gh-badge: [star, fork, follow]
tags: [test]
comments: false
---

The power and capability of Neural Networks goes beyond classification or prediction, a particularly beautyful application of NN is style transfer.


**Style transfer** allows you to recreate your own images adding the style of famous paintings.


The network **learns the underlying techniques of the paintings** and figures out how to apply them on new images (or videos) on its own.


A great repository I found is [fast style transfer](https://github.com/lengstrom/fast-style-transfer) which contains an implementation of style tranfer on images and even [videos](https://www.youtube.com/watch?v=xVJwwWQlQ1o&ab_channel=LoganEngstrom)!


I have applied it on a picture of myself and applied it the style of [Udnie](https://en.wikipedia.org/wiki/File:Francis_Picabia,_1913,_Udnie_(Young_American_Girl,_The_Dance),_oil_on_canvas,_290_x_300_cm,_Mus%C3%A9e_National_d%E2%80%99Art_Moderne,_Centre_Georges_Pompidou,_Paris..jpg).
Moreover the authors have trained with [other styles](https://github.com/lengstrom/fast-style-transfer/tree/master/examples/style) and uploaded the trained [weights](https://drive.google.com/drive/folders/0B9jhaT37ydSyRk9UX0wwX3BpMzQ) ready to be used!

![Udnie](https://i.ibb.co/JrXpGgN/rcboat-st-udnie.jpg | width=100){: .mx-auto.d-block :}

<img src="https://i.ibb.co/JrXpGgN/rcboat-st-udnie.jpg" alt="drawing" width="200"/>

# Try it yourself

Start by setting up your enviornment:
~~~
conda create -n style-transfer python=3
conda activate style-transfer
conda install tensorflow scipy pillow
pip install moviepy
python -c "import imageio; imageio.plugins.ffmpeg.download()"
~~~

Then:

1. Clone the repository [fast style transfer](https://github.com/lengstrom/fast-style-transfer).
2. Download the Rain Princess checkpoint from [here](https://drive.google.com/drive/folders/0B9jhaT37ydSyRk9UX0wwX3BpMzQ). Put it in the fast-style-transfer folder. A checkpoint file is a model that already has tuned parameters. By using this checkpoint file, we won't need to train the model and can get straight to applying it.
3. Copy the image you want to style into the fast-style-transfer folder.
4. Enter the Conda environment you created above, if you aren't still in it.


Finally, in your terminal, navigate to the fast-style-transfer folder and enter:
 
 
 ~~~
python evaluate.py --checkpoint ./rain-princess.ckpt --in-path <path_to_input_file> --out-path ./output_image.jpg
~~~

{: .box-note}
**Note:** Be careful with the size of the input image. The style transfer can take quite a while to run on larger images.


<a href="" alt="rcboat-st-udnie" border="0"></a>
