# AUC<sub>&mu;</sub>

AUC<sub>&mu;</sub> is a performance measure for multi-class classification models and it is an extension of the standard two-class area under the receiver operating characteristic curve (AUC-ROC).

## Getting Started

These instructions will get you a copy of the project up and running on your local machine for development and testing purposes.

### Prerequisites

Dependencies for this Python script include: Python, scikit-learn, and the scipy stack.

### Installing

Simply place auc_mu.py in any directory that is in your Python import path.

### Usage

Example Usage:
```
import auc_mu
import numpy as np
from sklearn.datasets import load_iris
from sklearn.ensemble import RandomForestClassifier as RFC
from sklearn.model_selection import train_test_split as tts

data = load_iris()
X = data.data
y = data.target

np.random.seed(0)
X_train, X_test, y_train, y_test = tts(X, y, test_size=.3)
clf = RFC(n_estimators=100)
clf.fit(X_train, y_train)
y_score = clf.predict_proba(X_test)

auc_mu.auc_mu(y_test, y_score)
>>> 0.99326599
```

Additional information regarding use of an alternative partition matrix or weight matrix is contained in the auc_mu.auc_mu Docstring.

## Authors

* **Ross Kleiman**

## License

This project is licensed under the MIT License - see the [LICENSE.md](LICENSE.md) file for details
