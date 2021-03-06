---
layout: post
title: Style Transfer
subtitle: Styling with Neural Networks
gh-repo: lengstrom/fast-style-transfer
gh-badge: [star, fork, follow]
tags: [Neural Style Transfer, Neural Networks, Deep Learning]
comments: false
---

The power and capability of Neural Networks goes beyond classification or prediction, a particularly beautyful application of NN is style transfer.


**Style transfer** allows you to recreate your own images adding the style of famous paintings.


The network **learns the underlying techniques of the paintings** and figures out how to apply them on new images (or videos) on its own.


A great repository I found is [fast style transfer](https://github.com/lengstrom/fast-style-transfer) which contains an implementation of style tranfer on images and even [videos](https://www.youtube.com/watch?v=xVJwwWQlQ1o&ab_channel=LoganEngstrom)!


I have applied it on a picture of myself and applied it the style of [Udnie](https://en.wikipedia.org/wiki/File:Francis_Picabia,_1913,_Udnie_(Young_American_Girl,_The_Dance),_oil_on_canvas,_290_x_300_cm,_Mus%C3%A9e_National_d%E2%80%99Art_Moderne,_Centre_Georges_Pompidou,_Paris..jpg).
Moreover the authors have trained with [other styles](https://github.com/lengstrom/fast-style-transfer/tree/master/examples/style) and uploaded the trained [weights](https://drive.google.com/drive/folders/0B9jhaT37ydSyRk9UX0wwX3BpMzQ) ready to be used!


<p float="center">
<img src="https://i.ibb.co/NKMTrWR/udnie.jpg" alt="drawing" width="200"/>
<img src="https://i.ibb.co/m69TG7K/rcboat.jpg" alt="drawing" width="250"/>
<img src="https://i.ibb.co/JrXpGgN/rcboat-st-udnie.jpg" alt="drawing" width="250"/>
</p>

#### Check the other styles:

[Rain Princess](https://afremov.com/)
<p float="center">
<img src="https://i.ibb.co/G3jC6fK/rain-princess.jpg" alt="drawing" width="200"/>
<img src="https://i.ibb.co/m69TG7K/rcboat.jpg" alt="drawing" width="250"/>
<img src="https://i.ibb.co/KNW2zJL/rcboat-st.jpg" alt="drawing" width="250"/>
</p>

[The Scream](https://en.wikipedia.org/wiki/The_Scream)
<p float="center">
<img src="https://i.ibb.co/9t2MBfD/the-scream.jpg" alt="drawing" width="200"/>
<img src="https://i.ibb.co/m69TG7K/rcboat.jpg" alt="drawing" width="250"/>
<img src="https://i.ibb.co/zXhgFmm/rcboat-st-scream.jpg" alt="drawing" width="250"/>
</p>

[La Muse](https://www.pablo-ruiz-picasso.net/work-1906.php)
<p float="center">
<img src="https://i.ibb.co/JvbvdJV/la-muse.jpg" alt="drawing" width="200"/>
<img src="https://i.ibb.co/m69TG7K/rcboat.jpg" alt="drawing" width="250"/>
<img src="https://i.ibb.co/Fsfvp7S/rcboat-st-lamuse.jpg" alt="drawing" width="250"/>
</p>

[The Great Wave of Kanagawa](https://en.wikipedia.org/wiki/The_Great_Wave_off_Kanagawa)
<p float="center">
<img src="https://i.ibb.co/BttKY1t/wave.jpg" alt="drawing" width="200"/>
<img src="https://i.ibb.co/m69TG7K/rcboat.jpg" alt="drawing" width="250"/>
<img src="https://i.ibb.co/rx9Cxxq/rcboat-st-wave.jpg" alt="drawing" width="250"/>
</p>


[The shipwreck of the minotaur](https://en.wikipedia.org/wiki/HMS_Minotaur_(1793))
<p float="center">
<img src="https://i.ibb.co/y4YgcJh/the-shipwreck-of-the-minotaur.jpg" alt="drawing" width="200"/>
<img src="https://i.ibb.co/m69TG7K/rcboat.jpg" alt="drawing" width="250"/>
<img src="https://i.ibb.co/Px5ny2K/rcboat-st-wreck.jpg" alt="drawing" width="250"/>
</p>






#### Try it yourself!

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


#### Interesting Papers to read
- [A Neural Algorithm of Artistic Style](https://arxiv.org/abs/1508.06576)
- [Perceptual Losses for Real-Time Style Transfer
and Super-Resolution](https://cs.stanford.edu/people/jcjohns/eccv16/)
- [Instance Normalization: The Missing Ingredient for Fast Stylization](https://arxiv.org/abs/1607.08022)
-[A Neural Algorithm of Artistic Style](https://arxiv.org/abs/1508.06576)
- [Texture Synthesis Using Convolutional Neural Networks](https://arxiv.org/abs/1505.07376)




