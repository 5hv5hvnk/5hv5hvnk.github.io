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