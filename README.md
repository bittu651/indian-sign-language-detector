# project-exbhition-2
# Indian Sign language Detector
# ABSTRACT
The only way the speech and hearing impaired (i.e dumb and 
deaf) people can communicate is by sign language. The main 
problem of this way of communication is normal people who 
cannot understand sign language can’t communicate with these 
people or vice versa. Our project aims to bridge the gap between 
the speech and hearing-impaired people and the normal people. 
The basic idea of this project is to make a system using which 
dumb people can significantly communicate with all other 
people using their normal gestures. The system does not require 
the background to be perfectly black. It works on any 
background. The project uses image processing system to 
identify, especially Indian sign language used by the deaf people 
to communicate and converts them into text so that normal 
people can understand.
# Motive
Communication is one of the basic requirement for survival in society. Deaf and dumb people communicate among themselves using sign language but normal people find it difficult to understand their language. So for that purpose we have developed a software which can interpret the trained signs and depicts with the respective message.

Target audience: Any one who wishes to communicate.
# Methodology
Our Project required basic knowledge of object detection. We used tensorflow object detection API which is SSD mobilenet V2 FPNlite 320*320.The SSD (Single Shot Detector) object detection was very useful to get the required data.From the results of performance of various object detection models on the MSCOCO dataset, it can be deduced that SSD models are faster when compared to the Faster R-CNN.SSD is faster compared to other object detection models but has difficulty in detecting small objects. Our project is one of the applications that can be done using tensorflow object detection

We prepared a dataset(According to ISL)and labeled it with the help of LabelImg Tool as shown here

![167244398-b3e8d91e-eb84-412e-851b-32d0370f85b4](https://user-images.githubusercontent.com/69419280/171203261-4fd73898-a6ba-4f95-855c-d8ec8349ad4b.png)

A particular region for model to look for and also labelled it according to the sign and it will be saved in an XML format containing the original dimensions of image and annotations that is height ,length ,depth up to which we wanted to detect by our model.In this way we labeled our images and divide it into Training and Testing dataset.
Then we did leverage the already existing model into customization according to our environment and updating the pipeline configurations so that we can use that pre-trained model in our environment& according to our terms. All this comes under Transfer learning
# Training phase
Then Training the model on our dataset, this took a few hours but at last our model is trained, while training this it shown few things like For every 100 steps there will be a update given with message that says time taken and loss and for every 10 of those updates a checkpoint will be formed. This loss rate will be high at the first checkpoint time i.e, 1.628 but gradually after 5000 steps we get loss as 0.3 this is a good thing cause loss percentage should be reduced gradually if not we can say our model is not accurate. Updates for every 100steps 

![167246331-1b866c3f-4198-47b3-8159-b12e66895b31](https://user-images.githubusercontent.com/69419280/171203665-a6d9b9bc-77e5-42c2-a1e6-b7936df1aad8.png)

# Results
According to the training it received it will detect the signs irrespective of background and gives output as the box bounded within the signs saying the label which we gave and with the confidence score. Like shown

<img width="345" alt="167245696-97857727-792e-4945-a1c5-5e5d827e2a0d" src="https://user-images.githubusercontent.com/69419280/171203827-206d4c34-92de-4260-842d-ca2a1cf659e4.png">   
<img width="271" alt="167245777-2fb6ac6e-0791-4ff9-88b1-06e8078028e3" src="https://user-images.githubusercontent.com/69419280/171203878-9ad9c9f2-0352-4d3e-aba7-97fd32b1d48b.png">

# Analysis
For every 10 of those epoch updates a checkpoint and for every checkpoint you can see the graph formed so there are 5 checkpoints and we can see 5 graphs converged together in one graph for ever evaluation metrics and loss metrics. As we can see in the tensorboard metrics the graph is gradually decreasing saying that loss is minimised at the end of Training.
# Limitation and Conclusion
The Limitation like the model can detect only words/ Image dataset, but we are not giving video dataset, if we give video dataset then we can get output for all possible signs. And moreover our model only say the meaning of the signs but not form full sentences which would be great if we did manage to do the them

![167246050-6e418a30-fa0a-4108-866d-8740c8b5635c](https://user-images.githubusercontent.com/69419280/171204221-ffa76b93-d304-4fbc-8af8-16d8aac90f46.png)

That can be Enhanced into detecting the signs according to pose detection(for covering wide range of signs)and also with neural network for forming a meaningful sentences.We can also enhance the system by adding speech recognition so that blind people can benefit as well.
