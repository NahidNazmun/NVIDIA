# NVIDIA
This repository has been created for NVIDIA JETSON NANO certification. The goal of this project is to creat a gesture recognition system which we will be able to integrate in small robots to perform Human Robot Interaction smoothly.
# Motivation
Body language and gestures, in particular, say a lot about you. A gesture is whenever you move your hand or head to express or emphasize an idea. And this is an important part of your overall body language. By doing a survey on different case studies we out 4 main reasons gestures are important:​

1.Gestures can help you describe what you’re talking about, both literally (e.g., when you talk about drawing a circle, you can motion a circle with your hand) and metaphorically (e.g., you could motion a circle with your hand to say “everybody”)

2.Gestures can help you point to people and things in your surroundings (e.g., pointing at an object while you say “look at that”)​

3.Gestures can help you add emphasis and structure when you talk (e.g., showing numbers when you count, “1, 2, 3…”)​

4.Gestures give clues about your emotional state. These gestures are not always connected to what you’re saying (e.g., are you confident?, are you lying?, are you anxious?)

A study led by neuroscientist Spencer Kelly found that, "Gestures – more than actions – appear to make people pay attention to the acoustics of speech. When we see a gesture, our auditory system expects to also hear speech." There are  more researches to back it up. Gestures can increase the amount of information you can get across by as much as 60%.
# Aims of this project
1.Human computer interaction

2.Make it easier for robot to understand human more

3.Computational cost

4.Complexity reduction

5.Modular Flexibility
# Why Transfer Learning?
Andrew Ng, chief scientist at Baidu and professor at Stanford, said during his widely popular NIPS 2016 tutorial that transfer learning will be -- after supervised learning -- the next driver of ML commercial success. In order to motivate the most common way of transfer learning is currently applied, we must understand what accounts for the outstanding success of large convolutional neural networks on ImageNet.

While many details of how these models work still remain a mystery, we are by now aware that lower convolutional layers capture low-level image features, while higher convolutional layers capture more and more complex details, such as body parts, faces, and other compositional features. General informations of how an image is composed and what combinations of edges and shapes it contains are contained in one of the final convolutional layers or early fully-connected layers in large convolutional neural networks trained on ImageNet. For a new task, we can thus simply use the off-the-shelf features of a state-of-the-art CNN pre-trained on ImageNet and train a new model on these extracted features. In practice, we either keep the pre-trained parameters fixed or tune them with a small learning rate in order to ensure that we do not unlearn the previously acquired knowledge. A model trained on ImageNet seems to capture details about the way hands are structured and composed that is generally relevant when dealing with images. 

# Things to consider while setting up JETSON Nano
* For some cases while setting up the webcam you might need to use this code instead of the code provided in the certification course:

echo "sudo docker run --runtime nvidia -it --rm --network host \
    --volume ~/nvdli-data:/nvdli-nano/data \
    --device /dev/video0 \
    nvcr.io/nvidia/dli/dli-nano-ai:v2.0.1-r32.4.4" > docker_dli_run.sh
chmod +x docker_dli_run.sh
./docker_dli_run.sh

The reason behind this is that JETSON Nano can not always initialize the webcam due to compatibility. Also, you need to do some device compatibility check after running it to check if the device is showing or not.

* Sometimes the JETSON Nano date is not up to date even if you put the date during the setup. Make sure to check that otherwise when you set up the docker the configuration will not mach.

# Our System 
In our project we tested all available pretrained networks. Finally we kept Mobilenet V2, Resnet 18 and Resnet 34 based on the performance. With Resnet 18 no lagging can be seen while doing the realtime testing but the accuracy is comparatively lower than other two models. Whereas both Resnet 34 and Mobilenet V2 showed lagging once in a while when the movements are very fast but based on accuracy Mobilenet V2 was slightly better than Resnet 34. So we chose Mobilenet V2 for the final demo video. In the Gesture folder we have put a part of our demo data. The video of our work can be seen in this link:




