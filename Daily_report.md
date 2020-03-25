# 3-24
## Paper Reading
### Unsupervised Generative Attentional Networks with Adaptive Layer-Instance Normalization for Image-to-Image Translation
Junho Kim (NCSOFT), Minjae Kim (NCSOFT), Hyeonwoo Kang (NCSOFT), Kwanghee Lee (Boeing Korea)
[ArXiv](https://arxiv.org/abs/1907.10830) [code](https://github.com/taki0112/UGATI)
* Unsupervised image-to-image translation
* Focus on geometric/shape changes, [selfie2anime dataset](https://drive.google.com/file/d/1xOWj1UVgp6NKMT3HbPhBbtq2A4EDkghF/view?usp=sharing)
* **Adaptive Layer-Instance Normalization**: sum of Adaptive IN and LN with trainable weights.
    * IN: more source semantic details from input in the output
    * LN: more target style in the output 
* Auxiliary classifiers (source/target) in both generator and discriminator 

## Web page
* [Selfie2Anime](https://selfie2anime.com) by [Nathan Glover](https://github.com/t04glovern)
* [Selfie2Waifu](https://waifu.lofiu.com) by [creke](https://github.com/creke)
* [Baidu AI Selfie2Anime](https://ai.baidu.com/tech/imageprocess/selfie_anime)

## Telegram Bot
* [Selfie2AnimeBot](https://t.me/selfie2animebot) by [Alex Spirin](https://github.com/sxela)
#### Code Reading
* Auxiliary classifier have two branch from global_avg_pooling and global_max_pooling
* Auxiliary classifier: x==>Global_avg/max_pooling==>fc*==>logit==>cat(avg, max), NHWC==>NC==>N1==>1==>2
* Attention map: x==>multiply(x, fc\*weight)==>cat(avg, max)==>conv==>reduce_sum, NHWC==>NHW1==>NHW2==>NHWC==>NHW1
* Adaptive Resiual blocks: use same channel so that the gamma/beta sizes are fixed ( NC instead of [NC_1, NC_2...]
* MLP: use a global pooling first to reduce the number of weights
* Kernel sizes of first annn

#### Architecture
<div align="center">
  <img src = '/figures/daily_report/3-24/generator_fix.png' width = '785px' height = '500px'>
</div>

---

<div align="center">
  <img src = '/figures/daily_report/3-24/discriminator_fix.png' width = '785px' height = '450px'>
</div>



