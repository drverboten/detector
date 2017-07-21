# Detector

## Identify images from Darth Vader and Darth Maul

Create a docker image to run tensorflow:

`docker run --name tensor -it -v ~/workspace/detector/tf_files:/tf_files/star_wars/ -v ~/workspace/detector/testImage.py:/tf_files/star_wars/totest/testImage.py gcr.io/tensorflow/tensorflow:latest-devel`

Navigate to tensorflow folder:

`cd /tensorflow`

Pull the lateste version:

`git pull`

Train using a series of Darth Vader and Darth Maul images:

`python tensorflow/examples/image_retraining/retrain.py \
--bottleneck_dir=/tf_files/bottlenecks \
--how_many_training_steps 500 \
--model_dir=/tf_files/inception \
--output_graph=/tf_files/retrained_graph.pb \
--output_labels=/tf_files/retrained_labels.txt \
--image_dir=/tf_files/star_wars`

Download a random image and check if it is a Darth Vader image or not:

`python /tf_files/star_wars/totest/testImage.py /tf_files/star_wars/totest/Darth_Vader.png`
