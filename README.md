:exclamation: This project is just a curated list of resources to help with the implementation of MLKit's [TensorFlow Lite](https://www.tensorflow.org/mobile/tflite/) for the [nativescript-plugin-firebase](https://github.com/EddyVerbruggen/nativescript-plugin-firebase), more precisely for the missig `custom inference` part.



# Expected behavior

TFLite should infer models based upon a `.lite` model file. In this example, it should accept the model:

**Custom Model:** `tf_files/optimized_graph.lite`

combined with this input:

**Input:** `tf_files/flower_photos/daisy/3475870145_685a19116d.jpg`

and be able to print:

**Expected output:**
```
daisy 0.7361
dandelion 0.242222
tulips 0.0185161
roses 0.0031544
sunflowers 8.00981e-06
```

**Note:** here we use a picture for simplicity, but it should obviously infer right from live video too by pointing the camera to a flower...


# Resources

* The goal of this repo is to help for the Nativescript implementation of MLKit's on-device custom inference, which docs can be found [here](https://firebase.google.com/docs/ml-kit/use-custom-models). 
* [/tf_files](https://github.com/Jonarod/ns-mlkit-tflite-curated/tree/master/tf_files) directory contains the converted `optimized_graph.lite` equivalent of `retrained_graph.pb` which is a reinforcement model of the classic [MobileNet](https://research.googleblog.com/2017/06/mobilenets-open-source-models-for.html) with 224psx224px images as input. The retraining aims at recognizing flowers like the one in the same directory: [/tf_files/flower_photos/daisy/3475870145_685a19116d.jpg](https://github.com/Jonarod/ns-mlkit-tflite-curated/tree/master/tf_files/flower_photos/daisy/).
* In addition to that, this repo contains 2 sample native apps for [/android](https://github.com/Jonarod/ns-mlkit-tflite-curated/tree/master/android/tflite) & [/iOS](https://github.com/Jonarod/ns-mlkit-tflite-curated/tree/master/ios/tflite) using a [converted .lite model](tree/master/tf_files/optimized_graph.lite), which are nothing more than a combined version of the awesome Google's codelab on TFLite: [here for Android](https://codelabs.developers.google.com/codelabs/tensorflow-for-poets-2-tflite) and [here for iOS](https://codelabs.developers.google.com/codelabs/tensorflow-for-poets-2-ios/index.html)
* This React Native standalone implementation of TFLite for Android & iOS [react-native-tensorflow-lite](https://github.com/jazzystring1/react-native-tensorflow-lite) seems to be good resource to check.
* Another React Native implemenation [react-native-camera-tflite](https://github.com/ppsreejith/react-native-camera-tflite) with its [Medium blog post](https://medium.com/@namar/high-performance-image-classification-with-react-native-336db0a96cd) seems to give pretty good results too. 
