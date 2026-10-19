# Module 10 data — Fashion-MNIST (small sample)

`fashion_mnist_small.npz` is a stratified sample of **Fashion-MNIST** (Zalando Research, 2017): 28 × 28 grayscale pictures of ten kinds of clothing.

| Array | Shape | Type | Contents |
|---|---|---|---|
| `X_train` | 12,000 × 28 × 28 | `uint8` | training pictures (pixel values 0 to 255) |
| `y_train` | 12,000 | `int64` | their class numbers, 0 to 9 (1,200 of each) |
| `X_test` | 2,000 × 28 × 28 | `uint8` | test pictures |
| `y_test` | 2,000 | `int64` | their class numbers (200 of each) |
| `class_names` | 10 | text | T-shirt/top, Trouser, Pullover, Dress, Coat, Sandal, Shirt, Sneaker, Bag, Ankle boot |

- **Source:** `torchvision.datasets.FashionMNIST` (torchvision 0.26.0), which downloads Zalando Research's Fashion-MNIST.
- **Licence:** MIT (Zalando Research). <https://github.com/zalandoresearch/fashion-mnist>
- **Sampling:** `numpy.random.default_rng(6930)`, drawing the same number of pictures from each class, without replacement, from the 60,000 training and the 10,000 test pictures.

Load it by URL:

```python
import io, urllib.request, numpy as np
url = "https://raw.githubusercontent.com/prof-tcsmith/6930Fall26-DATA/main/data/module10/fashion_mnist_small.npz"
data = np.load(io.BytesIO(urllib.request.urlopen(url).read()))
X_train, y_train, X_test, y_test = data["X_train"], data["y_train"], data["X_test"], data["y_test"]
class_names = data["class_names"]
```
