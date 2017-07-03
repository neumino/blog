---
layout: post
category : Geek
tags : [tensorflow, python, quickstart]
title: Quick start with tensorflow
---
{% include JB/setup %}

These are quick notes about playing with Tensorflow. They are similar to the
main tutorial but much more concise. They assume you have a bit of background
in machine learning.

Install on Arch linux:

```bash
sudo pacman -Sy tensorflow
pip install tensorflow --user
```

Quick start:

```py
import tensorflow as tf

# Create constant nodes that always output the same value.
node1 = tf.constant(3.0)
node2 = tf.constant(4.0)
print(node1, node2)

# Start a session and print their output.
sess = tf.Session()
print(sess.run([node1, node2]))

# Sum two nodes, `+` is overwritten with `tf.add`.
a = tf.placeholder(tf.float32)
b = tf.placeholder(tf.float32)
adder_node = a + b
print(sess.run(adder_node, {a: 3, b:4.5}))
print(sess.run(adder_node, {a: [1,3], b: [2, 4]}))

# Multiply a node by 3.
add_and_triple = adder_node * 3.
print(sess.run(add_and_triple, {a: 3, b:4.5}))

# Create a small linear model
W = tf.Variable([.3], dtype=tf.float32)
b = tf.Variable([-.3], dtype=tf.float32)
x = tf.placeholder(tf.float32)
linear_model = W * x + b
init = tf.global_variables_initializer()
sess.run(init)
print(sess.run(linear_model, {x:[1,2,3,4]}))

# Define a loss function.
y = tf.placeholder(tf.float32)
squared_deltas = tf.square(linear_model - y)
loss = tf.reduce_sum(squared_deltas)
print(sess.run(loss, {x:[1,2,3,4], y:[0,-1,-2,-3]}))

# Optimize W and b with a gradient descent.
optimizer = tf.train.GradientDescentOptimizer(0.01)
train = optimizer.minimize(loss)
sess.run(init) # reset values to incorrect defaults.
for i in range(1000):
  sess.run(train, {x:[1,2,3,4], y:[0,-1,-2,-3]})
print(sess.run([W, b]))
```

A few notes about warnings I saw.

```bash
2017-07-02 13:49:56.753464: W tensorflow/core/platform/cpu_feature_guard.cc:45] The TensorFlow library wasn't compiled to use SSE4.1 instructions, but these are available on your machine and could speed up CPU computations.
```

You can silence it by setting `TF_CPP_MIN_LOG_LEVEL` to `2` (or properly compile the TensorFlow library yourself).

```bash
export TF_CPP_MIN_LOG_LEVEL=2
```

You may also see this warning:

```bash
WARNING:tensorflow:From /home/michel/.local/lib/python3.6/site-packages/tensorflow/contrib/learn/python/learn/estimators/head.py:625: scalar_summary (from tensorflow.python.ops.logging_ops) is deprecated and will be removed after 2016-11-30.
Instructions for updating:
Please switch to tf.summary.scalar. Note that tf.summary.scalar uses the node name instead of the tag. This means that TensorFlow will automatically de-duplicate summary names based on the scope they are created in. Also, passing a tensor or list of tags to a scalar summary op is no longer supported.
```

You can prevent all these warnings by setting the verbosity in your python code.

```py
tf.logging.set_verbosity(tf.logging.ERROR)
```
