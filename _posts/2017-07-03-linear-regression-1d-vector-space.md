---
layout: post
category : Geek
tags : [tensorflow, python, quickstart]
title: Linear regression in a >1D vector space
---
{% include JB/setup %}

This is a simple example of running a linear regression on a vector space with
more than one dimension.

The main take away on my end is that the `*` operator is overwritten with the
product between tensors, not matrices - if you think about how training is done
with batches, it totally make sense though.. Hopefully if you did study a lot of
linear algebra but not so much tensors, you won't have to waste time trying to
figure out why your regression converge to such weird values.

```py
import tensorflow as tf
import random

def generate_test_case(sess, input_size, output_size):
  new_input = []
  for j in range(input_size):
    new_input.append(random.randrange(-50, 50))

  # Define the model we are interested to discover.
  # This assums input_size=2 and output_size=3
  W = tf.constant([1, 2, 3, 4, 5, 6], shape=[2, 3])
  b = tf.constant([10, 13, 22], shape=[1, 3])

  x = tf.constant(new_input, shape=[1, 2])
  test = tf.matmul(x, W) + b
  new_output = sess.run(test)[0]

  return new_input, new_output

def main(input_size, output_size):
  # Generate the linear model we want to build.
  x = tf.placeholder(tf.float32, [None, input_size], name='x')
  W = tf.Variable(tf.zeros([input_size, output_size]))
  b = tf.Variable(tf.zeros([output_size]))
  model = tf.matmul(x, W) + b

  # Build the loss function.
  sess = tf.Session()
  y = tf.placeholder(tf.float32, [None, output_size], name='y')
  squared_deltas = tf.square(model - y)
  loss = tf.reduce_mean(squared_deltas)

  # Define how we'll optimize W.
  init = tf.global_variables_initializer()
  optimizer = tf.train.GradientDescentOptimizer(0.001)
  train = optimizer.minimize(loss)
  sess.run(init)

  num_training_cases = 100 # Number of training cases
  train_input = []
  train_output = []
  for i in range(num_training_cases):
    new_input, new_output = generate_test_case(sess, input_size, output_size)
    train_input.append(new_input)
    train_output.append(new_output)

  print('Initial loss %d' % sess.run(loss, feed_dict={x:train_input, y:train_output}))
  print()

  for i in range(10000):
    sess.run(train, {x:train_input, y:train_output})

  print('---------------------')
  print('W\n %s' % sess.run(W))
  print('b\n %s'% sess.run(b))
  print('Loss %d' % sess.run(loss, feed_dict={x:train_input, y:train_output}))
  print()

  print('---------------------')
  print('Evaluating with a single case')
  eval_input, eval_output = generate_test_case(sess, input_size, output_size)
  print(eval_input)
  print(eval_output)
  print(sess.run(model, {x:[eval_input]}))
  print('Loss %d' % sess.run(loss, feed_dict={x:[eval_input], y:[eval_output]}))

if __name__ == "__main__":
  main(2, 3)
```
