# Using Document Intelligence and OpenAI to acquire information from a pdf file. 
In this Tutorial, we will demonstrate how Azure cognitive service Document Intelligence and OpenAI can be used to extract information from a phd file, such as a scientific publication. 

## Part 1 Document Intelligence 
Azure AI Document Intelligence, formerly known as Form Recognizer, is a cloud-based service offered by Microsoft Azure. It leverages advanced machine learning technologies to automatically extract text, key-value pairs, tables, and structures from various documents. This service simplifies the process of converting unstructured documents into usable data, enabling businesses to focus more on utilizing information rather than compiling it. Document Intelligence supports both pre-built models for common document types and custom models that can be tailored to unique document structures. This service can be applied in numerous scenarios including cloud-based or edge deployments, making it versatile for different IT architectures and business needs​ (Microsoft Azure)​​ (MS Learn)​.

Begin by navigating to the Azure portal ([https://portal.azure.com]) and logging in with your Azure account credentials. Once logged in, you can access various Azure services, including Document Intelligence. 

<img src="./images/DocumentIntellegente_1.png" style="height: 90%; width: 90%;"/>

click ```Create```

Fill out the options as shown in the image below 

 <img src="./images/DocumentIntellegente_2.png" style="height: 90%; width: 90%;"/>

Keep other options as default, and click ```create```

To use this service, you will need end point and key of the API you created, here is how to find it: Navigate to your resources group main page, and in the list of the resource you created, find the Document Intelligence service you just created, click it, and find the API and Key information in Resource Management/keys and Endpoint

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

Begin by navigating to the Azure portal ([https://portal.azure.com]) and logging in with your Azure account credentials. Once logged in, you can access various Azure services, including OpenAI resources.

### Step 2.2:Create OpenAI Resource 

In the Azure portal, search for "OpenAI" in the service catalog to explore available OpenAI resources. You'll find services such as the OpenAI API, which provides access to AI models like GPT-3 and CLIP, as well as other related services.

 
In your resource group, click Create: <img src="./images/CreateAPI_1.png" style="height: 90%; width: 90%;"/>

Next in the marketplace, search for OpenAI and select Azure OpenAI 
<img src="./images/CreateAPI_2.png" style="height: 90%; width: 90%;"/>


<img src="./images/CreateAPI_3.png" style="height: 90%; width: 90%;"/>


<img src="./images/CreateAPI_4.png" style="height: 90%; width: 90%;"/>
Here, if you haven't already had access to Azure OpenAI, you will have this error message, which you should click the link to fill out a request access form. 

<img src="./images/ReqestForm_1.png" style="height: 90%; width: 90%;"/>
In the form, you will need to fill out your subscription ID, to prove you have enough credits to access this service, 

<img src="./images/ReqestForm_2.png" style="height: 90%; width: 90%;"/>

you will also be asked to fill out what kind of services you will do with OpenAI, ChatGPT4.0, GPT Turbo. Dall-E, or others. Some of these questions are very specific, 
<img src="./images/ReqestForm_3.png" style="height: 90%; width: 90%;"/>

If your request is approved, you will get an email from Cognitive Service of Azure to welcome you to the Azure OpenAI service. Now, you are ready to create the OpenAI resources, 

When your subscription has Azure OpenAI access, use when you click create Azure OpenAI in the marketplace, you will see 
<img src="./images/CreateAPI_5.png" style="height: 90%; width: 90%;"/>

Use your own UW NetID to name your Azure OpenAI resource, and choose the standard price tier, and keep all the other options in the Network, Tags as default option, and click create in the ```Review+Submit```


if your resource is created successfully, you will see this page:
 <img src="./images/CreateAPI_6.png" style="height: 90%; width: 90%;"/>

### Step 2.3: Create Azure OpenAI Deployment 

To use OpenAI, you also need to prompt the model you created through Azure OpenAI Deployment. Azure OpenAI Deployment is a service offered by Microsoft Azure that facilitates the integration and deployment of OpenAI models within Azure's cloud infrastructure. This service enables developers to easily deploy, scale, and manage OpenAI models for various applications such as natural language processing, image recognition, and more. With Azure OpenAI Deployment, users can leverage the power of OpenAI while benefiting from Azure's robust platform for seamless integration, scalability, and reliability. It simplifies the process of deploying AI models, allowing developers to focus on building innovative solutions without worrying about infrastructure management.

Go to Azure OpenAI Studio [https://oai.azure.come/portal] and click ```Create new deployment```


 <img src="./images/CreateDepolyment_1.png" style="height: 90%; width: 90%;"/>

Remember the name of the Azure OpenAI deployment. 


