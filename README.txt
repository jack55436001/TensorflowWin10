how to install tensorflow on win10
https://rreadmorebooks.blogspot.tw/2017/04/win10tensorflowgpu.html

how to open tensorboard(on anaconda env)
go to  C:\Users\USER\Anaconda3\Lib\site-packages\tensorflow\tensorboard
and type following
python tensorboard.py --logdir=where your logdir
ip which I try is 127.0.0.1:6006

how to make sure tensorflow use GPU
using following code
	import tensorflow as tf
	# Creates a graph.
	a = tf.constant([1.0, 2.0, 3.0, 4.0, 5.0, 6.0], shape=[2, 3], name='a')
	b = tf.constant([1.0, 2.0, 3.0, 4.0, 5.0, 6.0], shape=[3, 2], name='b')
	c = tf.matmul(a, b)
	# Creates a session with log_device_placement set to True.
	sess = tf.Session(config=tf.ConfigProto(log_device_placement=True))
	# Runs the op.
	print(sess.run(c))
if you look maxmul use GPU0(default) than you are right

how to look more log
tf.logging.set_verbosity(tf.logging.INFO)

how to visulize tensorboard(https://www.tensorflow.org/get_started/summaries_and_tensorboard)
using tf.summary.scalar -> tf.summary.merge_all -> tf.summary.FileWriter

With tf.name_scope("") share variable
