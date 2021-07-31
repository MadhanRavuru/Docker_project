# Dockers

## Bank Note Authentication

Data were extracted from images that were taken from genuine and forged banknote-like specimens. For digitization, an industrial camera usually used for print inspection was used. The final images have 400x 400 pixels. Due to the object lens and distance to the investigated object gray-scale pictures with a resolution of about 660 dpi were gained. Wavelet Transform tool were used to extract features from images. These input features are *variance*, *skewness*, *curtosis* and	*entropy*.
The target classes are 0 0r 1.

### Classifier
Random Forest Classifier is trained to predict the target label. The input data is available in *BankNote_Authentication.csv*. The trained classifier had test accuracy of 99 %. It is saved as pickle file. 

### Frontend API - Flasgger
The trained model is deployed using Frontend API named flasgger.

### Docker
Docker image is built using docker file *dockerfile*.  *docker_example* is image container formed.

Build:

`docker build -f dockerfile -t docker_example .`

Run:

`docker run -p 8000:8000 -ti docker_example`

After entering the docker container,

`cd src`
`source activate ml`
`python flask_api.py`

### To run the Web Application
Go to the [url](http://0.0.0.0:8000/apidocs/) , and test the ouput with get and post methods. For post method, you can supply the *TestFile.csv* file



