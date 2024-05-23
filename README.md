<img src="./images/OpenAI-ChatGPT-Enterprise-A-Tall-Order.png" style="height: 50%; width: 80%;"/>

Author: Luna Yue Huang, Ph.D. Acknowledgement: Henry Stirrat, Yueyao Fan 

# Using Document Intelligence and OpenAI to acquire information from a pdf file. 
In this Tutorial, we will demonstrate how Azure cognitive service Document Intelligence and OpenAI can be used to extract information from a pdf file, such as a scientific manuscript.  

## Part 1 Document Intelligence 
Azure AI Document Intelligence, formerly known as Form Recognizer, is a cloud-based service offered by Microsoft Azure. It leverages advanced machine learning technologies to automatically extract text, key-value pairs, tables, and structures from various documents. This service simplifies the process of converting unstructured documents into usable data, enabling businesses to focus more on utilizing information rather than compiling it. Document Intelligence supports both pre-built models for common document types and custom models that can be tailored to unique document structures. This service can be applied in numerous scenarios including cloud-based or edge deployments, making it versatile for different IT architectures and business needs​​.

Begin by navigating to the Azure portal (https://portal.azure.com) and logging in with your Azure account credentials. Once logged in, you can access various Azure services, including Document Intelligence. 

<img src="./images/DocumentIntellegente_1.png" style="height: 90%; width: 90%;"/>

click ```Create```

Fill out the options as shown in the image below (note: the "Free F0" may not be available; if so, please choose the Standard S0 pricing tier)

 <img src="./images/DocumentIntellegente_2.png" style="height: 90%; width: 90%;"/>

Keep other options as default, and click ```create```

To use this service, you will need the endpoint and key of the resource you created; here is how to find it: Navigate to your resource group main page, and in the list of the resource you created, find the Document Intelligence service you just created; select it, and find the API and Key information in Resource Management/keys and Endpoint

<img src="./images/DocumentIntellegente_3.png" style="height: 90%; width: 90%;"/>

you can copy the key directly using the icon on the right. 

<img src="./images/DocumentIntellegente_4.png" style="height: 90%; width: 90%;"/>


## Part 2 OpenAI API introduction
The OpenAI API is a powerful tool that provides access to state-of-the-art artificial intelligence models developed by OpenAI. It allows developers to integrate cutting-edge AI capabilities into their applications with ease. Some key capabilities of the OpenAI API include:

1. Natural Language Understanding and Generation: The API can understand and generate human-like text, making it useful for tasks such as text completion, translation, summarization, and question answering.
2. Text Classification: It can classify text into predefined categories or labels, enabling applications to automatically categorize and organize large volumes of text data.
3. Image Recognition: With models like CLIP (Contrastive Language-Image Pre-training), the API can understand the content of images and provide textual descriptions or classify images into categories.
4. Customization and Fine-Tuning: Developers can fine-tune the pre-trained models provided by OpenAI to adapt them to specific tasks or domains, allowing for more tailored and accurate AI solutions.
5. Scalability and Performance: The API is designed to handle large-scale requests efficiently, making it suitable for applications with high throughput and demanding computational requirements.

##  Using OpenAI with Azure
OpenAI's powerful artificial intelligence capabilities are now available through Microsoft Azure. If you already have an Azure subscription, integrating OpenAI into your applications is straightforward. This introduction will guide you through the process of getting started with OpenAI on Azure.

### Step 2.1: Accessing OpenAI Resources on Azure

Begin by navigating to the Azure portal (https://portal.azure.com) and logging in with your Azure account credentials. Once logged in, you can access various Azure services, including OpenAI resources.

### Step 2.2:Create OpenAI Resource 

In the Azure portal, search for "OpenAI" in the service catalog to explore available OpenAI resources. You'll find services such as the OpenAI API, which provides access to AI models like GPT-3 and CLIP, as well as other related services.

 
In your resource group, click Create: <img src="./images/CreateAPI_1.png" style="height: 90%; width: 90%;"/>

Next in the marketplace, search for OpenAI and select Azure OpenAI 

<img src="./images/CreateAPI_2.png" style="height: 50%; width: 50%;"/>


<img src="./images/CreateAPI_3.png" style="height: 50%; width: 50%;"/>

Here, if you haven't already had access to Azure OpenAI, you will have this error message, which you should click the link to fill out a request access form. The next few steps are only applicable if you hit this error. 

<img src="./images/CreateAPI_4.png" style="height: 70%; width: 70%;"/>


<img src="./images/ReqestForm_1.png" style="height: 90%; width: 90%;"/>

In the form, you will need to fill out your subscription ID.

<img src="./images/ReqestForm_2.png" style="height: 70%; width: 70%;"/>

You will also be asked to fill out what kind of use cases you will leverage the OpenAI service for, and which models you will use (GPT4.0, GPT Turbo. Dall-E, or others). Some of these questions are very specific.
<img src="./images/ReqestForm_3.png" style="height: 90%; width: 90%;"/>

Once your request is approved, you will get an email from Cognitive Service of Azure to welcome you to the Azure OpenAI service. Now, you are ready to create the OpenAI resources.

Once your subscription has Azure OpenAI access,  when you click "create Azure OpenAI" in the marketplace, you will see the following:
<img src="./images/CreateAPI_5.png" style="height: 90%; width: 90%;"/>

Use your own UW NetID to name your Azure OpenAI resource, and choose the standard price tier, and keep all the other options in the Network, Tags as default option, and click create in the ```Review+Submit```.


If your resource is created successfully, you will see this page:
 <img src="./images/CreateAPI_6.png" style="height: 90%; width: 90%;"/>

### Step 2.3: Create Azure OpenAI Deployment 

To use OpenAI, you also need to select the ML model you want to use on the Azure OpenAI portal, in what is called a "Deployment". Azure OpenAI Deployment is a service offered by Microsoft Azure that facilitates the integration and deployment of OpenAI models within Azure's cloud infrastructure. This service enables developers to easily deploy, scale, and manage OpenAI models for various applications such as natural language processing, image recognition, and more.

Go to Azure OpenAI Studio (https://oai.azure.com/portal). The first time you log in, you will be asked to log in with your UW microsoft account and choose the subscription of this class and the OpenAI resource you just created. Navigate to ```Deployments``` in the left bar and click ```Create new deployment```.

 <img src="./images/CreateDepolyment_1.png" style="height: 70%; width: 70%;"/>

Remember the name of the Azure OpenAI deployment, which will be used when accessing the resource. 

Now, you have all your need to try out the Document Intelligence and Azure Open AI! Clone the https://github.com/lunayuehuang/OpenAI repository, or simply download the Jupyter notebook for the demonstration here: https://github.com/lunayuehuang/OpenAI/blob/main/PdfExtractionTutorial_Demo.ipynb
and the 2 pdf files that you will use for this demo here: https://github.com/lunayuehuang/OpenAI/blob/main/PapersToAnalyze/15.pdf and https://github.com/lunayuehuang/OpenAI/blob/main/UnridableBicycle.pdf. 
Put the python notebook in a directory, with the pdf files in a subdirectory called "PapersToAnalyze". Create a new python environment for this tutorial and open the PdfExtractionTutorial_Demo.ipynb notebook. Modify the PdfExtractionTutorial_Demo.ipynb with the information of the resources you created, and try this demo which will give you relevance ranking of the 2 pdf files to the topic you are interested in.  

Now, go ahead and try changing the prompt, so that you can use this notebook to get information from a research publication that you are familiar with, and design a test to analyze if you can use OpenAI to get the information you are interested in from a publication, and write a short report to analyze the results. 


