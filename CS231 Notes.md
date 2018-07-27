# **CS231 Notes**

## ** Lesson1-2**

交叉检验通常用于小数据集，深度学习数据集过大较少使用。

建立数据集时，一般随机选择数据作为训练集和测试集，这样能够减少数据采集误差带来的问题。

线性分类对学好神经网络很重要。

CIFAR10 dataset， 50000 training images, 10000 test images, 32 × 32 × 3, 10 class

![矩阵维度说明](C:\project\blog\assets\1530284399929.png)

![示例](C:\project\blog\assets\1530284421434.png)

load the image:

```python
Xtr, Ytr, Xte, Yte = load_CIFAR10('data/cifar10/') # a magic function we provide
# flatten out all images to be one-dimensional
Xtr_rows = Xtr.reshape(Xtr.shape[0], 32 * 32 * 3) # Xtr_rows becomes 50000 x 3072
Xte_rows = Xte.reshape(Xte.shape[0], 32 * 32 * 3) # Xte_rows becomes 10000 x 3072
```

procedures for train and evaluate a classifier:

```python
nn = NearestNeighbor() # create a Nearest Neighbor classifier class
nn.train(Xtr_rows, Ytr) # train the classifier on the training images and labels
Yte_predict = nn.predict(Xte_rows) # predict labels on the test images
# and now print the classification accuracy, which is the average number
# of examples that are correctly predicted (i.e. label matches)
print 'accuracy: %f' % ( np.mean(Yte_predict == Yte) )
```

take validation set:

```python
# assume we have Xtr_rows, Ytr, Xte_rows, Yte as before
# recall Xtr_rows is 50,000 x 3072 matrix
Xval_rows = Xtr_rows[:1000, :] # take first 1000 for validation
Yval = Ytr[:1000]
Xtr_rows = Xtr_rows[1000:, :] # keep last 49,000 for train
Ytr = Ytr[1000:]

# find hyperparameters that work best on the validation set
validation_accuracies = []
for k in [1, 3, 5, 10, 20, 50, 100]:
  
  # use a particular value of k and evaluation on validation data
  nn = NearestNeighbor()
  nn.train(Xtr_rows, Ytr)
  # here we assume a modified NearestNeighbor class that can take a k as input
  Yval_predict = nn.predict(Xval_rows, k = k)
  acc = np.mean(Yval_predict == Yval)
  print 'accuracy: %f' % (acc,)

  # keep track of what works on the validation set
  validation_accuracies.append((k, acc))
```

数据集较小时可考虑使用交叉检验，数据集较大时较少采用，因为计算开销大。



t-SNE（T分布随机近邻嵌入算法）是一种数据可视化算法。属于流行学习。

参考书：

[A Few Useful Things to Know about Machine Learning](./assets/A Few Useful Things to Know about Machine Learning.pdf)



## **Lecture 3**

