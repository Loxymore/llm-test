## A test project for running LLMs in Java

The loader used by the project is llama.cpp so the LLMs have to be in the .gguf file format.

### Usage guide :
1. Clone the repo
2. Download a model in the .gguf format and place it in [app/models](app/models).\
   Example model : (https://huggingface.co/bartowski/Llama-3.2-3B-Instruct-GGUF)
3. Run the app with gradle run and add the model name as an argument
   ```shell
   ./gradlew run -PappArgs="model_filename.gguf"
    ```
   Example command with the model from step 2 :
   ```shell
   ./gradlew run -PappArgs="Llama-3.2-3B-Instruct-Q6_K_L.gguf"
    ```
4. If you want to compile the app into a jar run :
    ```shell
   ./gradlew shadowJar
    ```
    *app_all.jar* will be created in app/build/libs

### Using the jar :
1. To use the compiled jar just place it in a directory with this structure : 
```
some-directory
│   app_all.jar   
│
└───models
│   │   your_model1.gguf
│   │   your_model2.gguf
```
2. Now when you run the jar you just need to give it the model name as an argument :
```shell
java -jar app_all.jar your_model1.gguf
```
   
