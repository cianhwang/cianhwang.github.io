# Rebuttal Material: Multispectral Image Intrinsic Decomposition via Low Rank Constraint

[Inital Estimation (#R1)](#init)

[PCA vs. 'Best' Bands (#R2)](#lr)

[Experiments (#R3)](#mit)
* [on MIT intrinsic benchmark](#mit)
* [on MIID, our newly-captured dataset](#miid)
* [on SIID dataset](#siid)

[Contributions (#R3)](#contri)

## <span id="init">Initial Estimation (#R1)</span>
![Image](https://farm5.staticflickr.com/4721/26045732858_1133701b2c_b.jpg)
> Fig. 1: the bias distribution on MIT intrinsic dataset and our MIID dataset.

From Fig. 1, we can see that the biases between the reflectance image and the input image follow a heavy-tailed distribution with zero mean, which validate our assumption that the reflectance image has small deviation from the input image.

## <span id="lr">PCA vs. 'Best' 8 bands (#R2)</span>
![Image](https://farm5.staticflickr.com/4701/26047528898_29a16acf4f_h.jpg)
> Fig. 2 the comparison between PCA and selected 8 bands on our MIID dataset. LMSE is applied to evaluate the performance. 

In Fig. 2, our algorithm outperforms 8-best-band method by 38% on average. We think this is because in the linear case, the PCA-based selection can also be regarded as the ’best’ bands selection theoretically, which is a coincidence of the reviewer’s suggestion.

## <span id="mit">Experiments (#R3)</span>

### <span id="mit">On MIT Intrinsic benchmark</span>
![Image](https://farm5.staticflickr.com/4664/39926442791_cd9d6e8964_k.jpg)
> Fig. 3: comparison of visual results on MIT intrinsic benchmark (first row: reflectance; second row: shading), where GT denotes Ground Truth and CR denotes Color Retinex. Our shadings are more uniform and reflectances are more 'flat' visually.

![Image](https://farm5.staticflickr.com/4714/25049103807_9b4d41bcf9_h.jpg)
> Fig. 4: the quantitative performance of our method. 

To better illustrate our algorithm, we test our algorithm on MIT intrinsic benchmark. In Fig. 3, we display some results on MIT dataset. Compared with CR, our algorihtm on RGB cases would also achieve great visual results. In Fig. 4, we evaluate our algorithm quantitatively. Since we directly operate on image domain and use iteration to better the results, the performance would elevate from 0.030 to 0.028 on average.

### <span id="miid">On MIID Dataset</span>
![Image](https://farm5.staticflickr.com/4704/39918684321_42faa1c719_k.jpg)
![Image](https://farm5.staticflickr.com/4761/39019998775_fa2a84c34a_k.jpg)
> Fig. 5: the first subfigure is 12 groups of MIID dataset that we provided in the paper. The second one is newly-captured 10 groups which aim to validate the performance of our algorithm.

Apart from 12 groups of our MIID dataset provided in the paper, we add 10 groups in order to demonstrate the contribution of our algorithm. We mainly compare our algorithm with SIID*, the state-of-the-art algorithm on the MIID problem.

> *Chen et al. _Intrinsic decomposition from a single spectral image._ Applied optics 56.20 (2017): 5676-5684.

#### Objective evaluation
![img](https://farm5.staticflickr.com/4743/39022043025_103a809018_b.jpg)
> Fig. 6: LMSE performance on our newly-captured dataset. Our algorithm achieve better results on every group of 10.

In Fig. 6, we show LSME performance of our algorithm. Our algorithm outperform SIID on each group of 10, the results of which validate the effectiveness of our algorithm.

#### Subjective evaluation
![img](https://farm5.staticflickr.com/4623/39041994725_0d6ea3b36c_k.jpg)
> Fig. 7: some visual results of our algorithm and SIID on newly captured dataset (first row: reflectance; second row: shading). Captured by two different spectral imagers, images are slightly different in color because of different white balance settings.

SIID introduced super-pixel based method to handle MIID problem in order to reduce the complexity of multispectral information. Their results would cause the mosaic effect, in other words, the loss of details. In Fig. 7, we demonstrate that our algorithm can better maintain the detailed information. And our shadings tend to be uniform and reflectances are more 'flat'.

Noted that in the group 'cap' our results appear to be worse, but our algorithm maintains high frequency information on shading image.

### <span id="siid">On SIID dataset</span>
![Image](https://farm5.staticflickr.com/4740/39043645675_2937afc880_b.jpg)
> Fig. 8: the performance of our algorithm on SIID dataset, where SR denotes Spectra Retinex.

> *SIID dataset, 'spectral retinex' and 'error metric score' are proposed by Chen et al., _Intrinsic decomposition from a single spectral image._, Applied optics 56.20 (2017): 5676-5684.

Also, we do another experiment on SIID dataset and display our result in Fig. 8. We achieve better results than SIID and SR.

## <span id='contri'>Contributions (#R3)</span>
In sum, our LRIID algorithm outperforms state-of-the-art algorithms on various kinds of databases. And the MIID dataset with the ground truth that we provide would play an important role in following MIID researches.
