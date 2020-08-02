---
layout: default
---
This page is the demo of 
1. "Quasi-periodic parallel WaveGAN: a non-autoregressive raw waveform generative model with pitch-dependent dilated convolution neural networks" [[paper](https://arxiv.org/abs/2007.12955)] [[code](https://github.com/bigpon/QPPWG)]  
2. "Quasi-periodic parallel WaveGAN vocoder: a non-autoregressive pitch-dependent dilated convolution model for parametric speech generation" [[paper](https://arxiv.org/abs/2005.08654)] 

## **Abstract**  
<p align="justify"> We propose a <b>Quasi-Periodic Parallel WaveGAN (QPPWG)</b> waveform generative model, which applies a quasi-periodic (QP) structure to a parallel WaveGAN (PWG) model using pitch-dependent dilated convolution networks (PDCNNs). PWG is a compact GAN-based raw waveform generative model, whose generation time is much faster than realtime because of its non-autoregressive (non-AR) and non-causal mechanisms. Although PWG achieves a high fidelity speech generation, the generic and simple network architecture lacks pitch-controllability for the unseen auxiliary pitches such as a scaled pitch. To improve the pitch and speech modeling capability, we apply a QP structure with PDCNNs to the generator of PWG, and it introduces pitch information to the network by dynamically changing the network architecture corresponding to the auxiliary pitches. </p>

**Corpus and references:**  
[VCC2018](http://www.vc-challenge.org/)  
[PWG](https://ieeexplore.ieee.org/abstract/document/9053795)  
[PWG_repo](https://github.com/kan-bayashi/ParallelWaveGAN)  
[QPNet](https://bigpon.github.io/QuasiPeriodicWaveNet_demo/)  

## **Architecture of PWG/QPPWG**  
<center><img src="res/figure/PWG.svg" style="display:block;width:370px;height:320px"></center>

## **Generator of QPPWG**  
<center><img src="res/figure/QPPWG_G.svg" style="display:block;width:500px;height:370px"></center>  
    
## **Non-AR PDCNN**  
<center><img src="res/figure/PDCNN.svg" style="display:block;width:500px;height:250px"></center>  
  
## **Demo Sounds**
- Conditioned on **1**&times;*F*<sub>0</sub>

| Vocoder                | Female (SF3)                                                                   | Male (SM3)                                                                     |
|:-----------------------|:------------------------------------------------------------------------------:|:------------------------------------------------------------------------------:|
| **Natural**            | <audio src="res/audio/SF3/Natural/30013.wav" controls preload></audio>         | <audio src="res/audio/SM3/Natural/30017.wav" controls preload></audio>         |
| WORLD<sup> *1</sup>    | <audio src="res/audio/SF3/1_0_F0/WORLD/30013.wav" controls preload></audio>    | <audio src="res/audio/SM3/1_0_F0/WORLD/30017.wav" controls preload></audio>    |
| QPNet<sup> *2</sup>    | <audio src="res/audio/SF3/1_0_F0/QPNet/30013.wav" controls preload></audio>    | <audio src="res/audio/SM3/1_0_F0/QPNet/30017.wav" controls preload></audio>    |
| PWG_30<sup> *3</sup>   | <audio src="res/audio/SF3/1_0_F0/PWG_30/30013.wav" controls preload></audio>   | <audio src="res/audio/SM3/1_0_F0/PWG_30/30017.wav" controls preload></audio>   |
| PWG_20<sup> *4</sup>   | <audio src="res/audio/SF3/1_0_F0/PWG_20/30013.wav" controls preload></audio>   | <audio src="res/audio/SM3/1_0_F0/PWG_20/30017.wav" controls preload></audio>   |
| QPPWG_20<sup> *5</sup> | <audio src="res/audio/SF3/1_0_F0/QPPWG_20/30013.wav" controls preload></audio> | <audio src="res/audio/SM3/1_0_F0/QPPWG_20/30017.wav" controls preload></audio> |
| PWG_16<sup> *6</sup>   | <audio src="res/audio/SF3/1_0_F0/PWG_16/30013.wav" controls preload></audio>   | <audio src="res/audio/SM3/1_0_F0/PWG_16/30017.wav" controls preload></audio>   |
| QPPWG_16<sup> *7</sup> | <audio src="res/audio/SF3/1_0_F0/QPPWG_16/30013.wav" controls preload></audio> | <audio src="res/audio/SM3/1_0_F0/QPPWG_16/30017.wav" controls preload></audio> |

<sup>*1. `WORLD: Baseline I` </sup>  
<sup>*2. `QPNet: Baseline II` </sup>  
<sup>*3. `PWG_30: PWG vocoder with 30 fixed blocks` </sup>   
<sup>*4. `PWG_20: PWG vocoder with 20 fixed blocks` </sup>  
<sup>*5. `QPPWG_20: QPPWG vocoder with 10 adaptive blocks + 10 fixed blocks` </sup>  
<sup>*6. `PWG_16: PWG vocoder with 16 fixed blocks` </sup>  
<sup>*7. `QPPWG_16: QPPWG vocoder with 8 adaptive blocks + 8 fixed blocks` </sup>  
 
<br />  
- Conditioned on **&frac12;**&times;*F*<sub>0</sub>

| Vocoder  | Female (SF3)                                                                   | Male (SM3)                                                                     |
|:---------|:------------------------------------------------------------------------------:|:------------------------------------------------------------------------------:|
| WORLD    | <audio src="res/audio/SF3/0_5_F0/WORLD/30013.wav" controls preload></audio>    | <audio src="res/audio/SM3/0_5_F0/WORLD/30017.wav" controls preload></audio>    |
| QPNet    | <audio src="res/audio/SF3/0_5_F0/QPNet/30013.wav" controls preload></audio>    | <audio src="res/audio/SM3/0_5_F0/QPNet/30017.wav" controls preload></audio>    |
| PWG_30   | <audio src="res/audio/SF3/0_5_F0/PWG_30/30013.wav" controls preload></audio>   | <audio src="res/audio/SM3/0_5_F0/PWG_30/30017.wav" controls preload></audio>   |
| PWG_20   | <audio src="res/audio/SF3/0_5_F0/PWG_20/30013.wav" controls preload></audio>   | <audio src="res/audio/SM3/0_5_F0/PWG_20/30017.wav" controls preload></audio>   |
| QPPWG_20 | <audio src="res/audio/SF3/0_5_F0/QPPWG_20/30013.wav" controls preload></audio> | <audio src="res/audio/SM3/0_5_F0/QPPWG_20/30017.wav" controls preload></audio> |
| PWG_16   | <audio src="res/audio/SF3/0_5_F0/PWG_16/30013.wav" controls preload></audio>   | <audio src="res/audio/SM3/0_5_F0/PWG_16/30017.wav" controls preload></audio>   |
| QPPWG_16 | <audio src="res/audio/SF3/0_5_F0/QPPWG_16/30013.wav" controls preload></audio> | <audio src="res/audio/SM3/0_5_F0/QPPWG_16/30017.wav" controls preload></audio> |
  
<br />  
- Conditioned on **2**&times;*F*<sub>0</sub>

| Vocoder  | Female (SF3)                                                                   | Male (SM3)                                                                     |
|:---------|:------------------------------------------------------------------------------:|:------------------------------------------------------------------------------:|
| WORLD    | <audio src="res/audio/SF3/2_0_F0/WORLD/30013.wav" controls preload></audio>    | <audio src="res/audio/SM3/2_0_F0/WORLD/30017.wav" controls preload></audio>    |
| QPNet    | <audio src="res/audio/SF3/2_0_F0/QPNet/30013.wav" controls preload></audio>    | <audio src="res/audio/SM3/2_0_F0/QPNet/30017.wav" controls preload></audio>    |
| PWG_30   | <audio src="res/audio/SF3/2_0_F0/PWG_30/30013.wav" controls preload></audio>   | <audio src="res/audio/SM3/2_0_F0/PWG_30/30017.wav" controls preload></audio>   |
| PWG_20   | <audio src="res/audio/SF3/2_0_F0/PWG_20/30013.wav" controls preload></audio>   | <audio src="res/audio/SM3/2_0_F0/PWG_20/30017.wav" controls preload></audio>   |
| QPPWG_20 | <audio src="res/audio/SF3/2_0_F0/QPPWG_20/30013.wav" controls preload></audio> | <audio src="res/audio/SM3/2_0_F0/QPPWG_20/30017.wav" controls preload></audio> |
| PWG_16   | <audio src="res/audio/SF3/2_0_F0/PWG_16/30013.wav" controls preload></audio>   | <audio src="res/audio/SM3/2_0_F0/PWG_16/30017.wav" controls preload></audio>   |
| QPPWG_16 | <audio src="res/audio/SF3/2_0_F0/QPPWG_16/30013.wav" controls preload></audio> | <audio src="res/audio/SM3/2_0_F0/QPPWG_16/30017.wav" controls preload></audio> |
  
<br /> 

## **Subjective Results** 
- MOS results of speech quality  
<center><img src="res/figure/MOS.jpg" ></center>  
- XAB results of pitch accuracy  
<center><img src="res/figure/XAB.jpg" style="display:block;width:400px;height:300px"></center>
  
<br /> 

## **Visualized Intermediate Outputs** 
<p align="justify"> Because the waveform outputs of the PWG/QPPWG models are the cumulative results of the skip connections from the residual blocks, the speech modeling behavior of the residual blocks can be explored via the visualized intermediate outputs of partial residual blocks. The following table shows the spectrograms of the intermediate outputs of the cumulative residual blocks. The results of PWG w/ 20 fixed blocks, QPPWG w/ 10 adaptive blocks + 10 fixed blocks (the demo system QPPWG_20), and QPPWG w/ 10 fixed blocks + 10 adaptive blocks are presented.</p> 

<table border="0">
  <tr>
  <td align="center"> <b>PWG</b> </td>
  <td align="center"> <b>QPPWG (adaptive->fixed)</b> </td>
  <td align="center"> <b>QPPWG (fixed->adaptive)</b> </td>
  </tr>
  <tr> <td colspan="3" align="center"> Conditioned on <b>1</b>&times;<i>F</i><sub>0</sub> </td> </tr>
  <tr>
  <td> <img class="preload" src="res/figure/Bf20C2_1f0.gif" style="display:block;width:240px;height:220px"/> </td>
  <td> <img class="preload" src="res/figure/Ba10C2Bf10C1_1f0.gif" style="display:block;width:240px;height:220px"/> </td>
  <td> <img class="preload" src="res/figure/Bf10C1Ba10C2_1f0.gif" style="display:block;width:240px;height:220px"/> </td>
  </tr>
  <tr> <td colspan="3" align="center"> Conditioned on <b>&frac12;</b>&times;<i>F</i><sub>0</sub> </td> </tr>
  <tr>
  <td> <img class="preload" src="res/figure/Bf20C2_0.5f0.gif" style="display:block;width:240px;height:220px"/> </td>
  <td> <img class="preload" src="res/figure/Ba10C2Bf10C1_0.5f0.gif" style="display:block;width:240px;height:220px"/> </td>
  <td> <img class="preload" src="res/figure/Bf10C1Ba10C2_0.5f0.gif" style="display:block;width:240px;height:220px"/> </td>
  </tr>
  <tr> <td colspan="3" align="center"> Conditioned on <b>2</b>&times;<i>F</i><sub>0</sub> </td> </tr>
  <tr>
  <td> <img class="preload" src="res/figure/Bf20C2_2f0.gif" style="display:block;width:240px;height:220px"/> </td>
  <td> <img class="preload" src="res/figure/Ba10C2Bf10C1_2f0.gif" style="display:block;width:240px;height:220px"/> </td>
  <td> <img class="preload" src="res/figure/Bf10C1Ba10C2_2f0.gif" style="display:block;width:240px;height:220px"/> </td>
  </tr>
</table>

According to the results, we can find that
- **PWG**: spectrograms contain more harmonic and non-harmonic details as the number of the cumulative residual blocks increases. 
- **QPPWG (adaptive->fixed)**: the first ten adaptive blocks focus on modeling the harmonic components. 
- **QPPWG (fixed->adaptive)**: the first ten fixed blocks focus on modeling the the non-harmonic components.  

The results confirm our assumption that that the adaptive blocks with the PDCNNs primarily model the pitch-related speech components with the long-term correlations while the fixed blocks with the DCNNs mainly focus on the spectral-related speech components with the short-term correlations.

<br /> 
[Home](https://bigpon.github.io/)

<br />  
<br />  