1. Preparation:     
    -environment: >= pyhton 3.8    
    -torch and CUDA: 1.7.1+cu110; (install here : https://pytorch.org/)                  
    -Other packages: Simply run the requirements in the built-in requirements.txt file of the code, and install whatever is missing     


2. Creating dataset:       
    -Creating a dataset is a tedious and tedious process that requires the use of the LabelImg tool.     
    -The specific steps will not be elaborated, but it is important to be careful when labeling specific categories, as this will determine your prediction results.     
    -Also, the more images you use to train the model, the more accurate it will be.     


4. Creating files:    
    -under the directory "data", you will need to create another 3 new directories: "images", "labels", "Annotations".    
        under the directory "images", you will need to have all the fire images you want to use to train the model.    
        under the directory "Annotations", you will need to have all the .xml file converted from images in directory "images" using labeling software such as "labelImg".    
        keep "labels" empty for now    
    -under the directory "yolov5_master", create another directory "weights", you will need to have the weight file you want to use there (I used yolov5m.pt, you can also use other models and weights: such as yolov5s, yolov5l, yolov5x).     
    (download here:https://github.com/ultralytics/yolov5/releases)


5. Convert xml files to txt files:     
    -run 1make_text.py    
    -run 1voc_label.py    
    -run xml_txt.py    


6. train the model    
    -run "train.py", you can customise the arguments (such as epochs)    
    -results will be under runs/train    


8. detect     
    -under the runs/train, you will find several exp file, go to the most recent one you will find a file called "best.pt", that's the weight you want to use to detect fire.    
    -go to "detect.py", change the argument "weights" to the path of your "best.pt"     
    -the argument "source" determines the images you want to detect, you can add more images or videos under directory data/test    
    -run "detect.py" or run the command : python detect.py --save-txt    
    -the result will be under runs/detect     

