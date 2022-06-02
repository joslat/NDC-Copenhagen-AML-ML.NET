# NDC-Copenhagen-AML-ML.NET
Code, Slides and links on my NDC Copenhagen presentation "Azure Machine Learning &amp; ML.NET: Better Together" 

<b>The ONNX is generated on by following this walkthrough: </b>    
https://docs.microsoft.com/en-us/azure/machine-learning/tutorial-auto-train-models   

<b>And performing the changes stated on my presentation, which are the following: </b>


1. Add support for ONNX on the AutoML Configuration, AutoMLConfig with the following:
   1. `enable_onnx_compatible_models=True,`
2. Once the model is built, to export it as ONNX doing the following:
   1. First, retrieve the model with:     
          1.`best_run, onnx_mdl = local_run.get_output(return_onnx_model=True)`
   2. Second, convert and save it with:
      1. `from azureml.automl.runtime.onnx_convert import OnnxConverter
onnx_fl_path = "./best_model.onnx"`
      1. `OnnxConverter.save_onnx_model(onnx_mdl, onnx_fl_path)`

Once this is executed the model should be generated.

Then you can download and use it in .NET with ML.NET from your favourite IDE.
<b>The ONNX is used as stated on this walkthrough: </b>    
https://docs.microsoft.com/en-us/azure/machine-learning/how-to-use-automl-onnx-model-dotnet 
- or just follow me along in my talk :)

The completed, fulfilled, Notebook is on this repository, as well as the generated ONNX model, but i recommend you give it a try to it on your own and use it as a last resort.

Also, in short I will be putting up some videos and blog posts on Azure Machine Learning and ML.NET in my blog, [AzureSamurai.blog](https://azuresamurai.blog/) and in [my Azure Samurai video channel](https://www.youtube.com/channel/UCyIlMjwlhR2iokca6btIZng).
Those will cover the topics in a bit more detail but still concise. My goal there is to enable to be followed along while you are coding and/or working with Azure Machine Learning and ML.NET.

Have fun!   
José