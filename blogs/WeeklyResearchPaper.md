### Weekly research paper review (in short)
The key motivation is to learn from a research paper every week (whatever I can) and maintain a log of the same.
#### October <br>
**Week 1:** Learning transferable visual models from natural language supervision
- **Authors** : A. Radford, J. W. Kim, et al
- **Journal** : ICML 2021
- **Link** : https://arxiv.org/abs/2103.00020
- **In 1 sentence** <br> Zero shot Image caption generated using image and text encoding.
- **In 10 sentences** <br> Novel approach to image captioning using encodings for image and text related to image. It is inspired by two main models: (a) VirTex: shows image captioning models are really good for tasks like image classification (something like transfer learning)(b) ConVirt : it shows independently training words and images to improve model with less data. The main idea is to maximize the cosine similarity of image and text pairs. Since _WIT_ is large (low risk of overfitting) both encoders are trained from scratch and linear projections (rather than non-linear) used between the representations and the shared embedding space, since no difference was observed during training. ViT-L/14-336px (Trained with FixRes (Touvron et al., 2019)) and a 12 head transformer yielded the best accuracy for the CLIP model.
Zero-shot transfer can be thought of as assessing the task learning ability of a model: A dataset evaluates performance on a task on a specific distribution, the zero-shot transfer focus is inspired by works illustrating task learning in NLP. Evaluate visual representation quality via linear probes: Linear (rather than non-linear) probes are used to avoid the introduction of additional hyperparameters and cost. In zero-shot transfer, using text class labels can present challenges:
Some datasets only provide integer class id labels (these cannot be used). One issue is _polysemy_ - the word sense is ambiguous without context these are resolved by two methods: (i) Prompt Templates and (ii) Customized templates. Prompt Ensembling: Ensembling is performed over the embeddings, rather than predicted probabilities to enable caching so that the cost is amortised over predictions helping to boost the performance by 3.5% .

- **Datasets used** : aYahoo, ImageNet, SUN.
<br>

**Week 2: On Compositions of Transformations in Contrastive Self-Supervised Learning** 
- **Authors** : Mandela Patrick, Yuki M. Asano, et al.
- **Journal** : ICCV 2020
- **Link** : https://arxiv.org/pdf/2003.04298.pdf
- **In 1 sentence** <br> How invariance and distinctiveness to individual transformation can be used to learn meaningfully from video.
- **In 10 sentences** <br> 
Basic idea is to generalize contrastive methods such as CPC, PIRL and etc to learn representations that can be invariant or distinctive to any number of transformations.GDT are Generalized Data Transformation like data augmentation (like cropping or rotating) or extracting a specific image or video from the collection or extracting a specific modality from a video. We wish to generalize this construction to richer data such as videos. Compared to images, videos contain multi- ple modalities and additional dimensions, which allows to consider qualitatively different transformations such as time shift, time reversal, and modality slicing. This generalization is however non-trivial. We leverage the noise contrastive loss (Noise contrastive losses [26, 27] measure the similarity between sample pairs in a representational space and are at the core of several recent works on unsupervised feature learning) as a learning framework to encourage the network to learn desired invariance and distinctiveness to data transformations. We show that GDT’s batch sampling strategy is statistically more efficient than naively-sampled pairs for contrastive learning to do this by showing that GDT’s objective has the same mean but a lower variance than sampling batches, which would either enumerate all possible pairs of transformations (which is prohibitively expensive) or subsample it by sampling transformations independently.
**Datsets:** Kinetics-400,  HT100M <br>