# WatBot
is an IBM Watson powered ChatBot running on Android and using Conversation Service on IBM Bluemix (an open standards, cloud platform for building, running, and managing apps and services).

## Creation of Conversation Service

Watson Conversation combines a number of cognitive techniques to help you build and train a bot - defining intents and entities and crafting dialog to simulate conversation.

![Watson Conversation Service Overview](https://github.com/VidyasagarMSC/WatBot/blob/initial/Images/Watson_Conversation_Service.png)

### Getting started
<p>Before you can start using the Conversation service, you must log in to IBM® Bluemix® and create a service instance.</p>
<ol>
<li>Log in to Bluemix and navigate to the Conversation service:
<ul>
<li>Don’t have Bluemix account? <a target="_blank" href="https://console.ng.bluemix.net/registration/?target=/catalog/services/conversation/" title="(Opens in a new tab or window)">Sign up</a> to create a free trial account.</li>
<li>Have a Bluemix account? Use <a target="_blank" href="https://console.ng.bluemix.net/catalog/services/conversation" title="(Opens in a new tab or window)">this link</a>.</li>
</ul>
</li>
<li>In the <strong>Service name</strong> field, type a unique name for your new instance of the Conversation service.
Check the “Pricing Plans” for data limits for the Conversation service</li>
<li>Click <strong>Create</strong>. You’ll see details about your new instance in the “Service Details” page.</li>
</ol>

### Creating a Workspace
You use the Conversation tool to create workspaces. You can either create a new workspace from scratch, or you can import a workspace from a JSON file. You can also duplicate an existing workspace within the same service instance.

<ol>
<li>If the Service Details page is not already open, click your Conversation service instance on the Bluemix console. (When you create a service instance, the Service Details page displays.)</li>
<li>On the “Service Details” page, scroll down to <strong>Conversation tooling</strong> and click <strong>Launch tool</strong>.</li>
<li>Click <strong>Create</strong> to create a new workspace.</li>
<li>Specify the details for the new workspace:
<ul>
<li><strong>Name</strong>: A name no more than 64 characters in length. This value is required.</li>
<li><strong>Description</strong>: A description no more than 128 characters in length.</li>
<li><strong>Language</strong>: The language of the user input the workspace will be trained to understand. The service supports Brazilian Portuguese, English, French, Italian, and Spanish.</li>
</ul>
</li>
<li>Click <strong>Create</strong>. The new workspace is created and now appears as a tile on the Workspaces page.</li>
</ol>


<h2 id="creating-an-intent">Creating an intent </h2>
<p>You use the Conversation tool to create intents. The number of intents and examples you can create in a single service instance depends on your Conversation service plan:</p>

<p>Create some intents.</p>
<ol>
<li>
<p>In the Conversation tool, open your workspace and then click the <strong>Intents</strong> tab.</p>
</li>
<li>
<p>Click <strong>Create new</strong>.</p>
</li>
<li>
<p>In the Intent name field, type a descriptive name for the intent. The intent name can contain letters (in Unicode), numbers, underscores, hyphens, and dots. Intent names cannot contain spaces and must not exceed 128 characters. The following are examples of intent names:</p>
<ul>
<li><code>#weather_conditions</code></li>
<li><code>#pay_bill</code></li>
<li><code>#escalate_to_agent</code></li>
</ul>
<p><strong>Tip</strong>: Don’t include the <code>#</code> character in the intent names when you create them in the Conversation tool.</p>
</li>
<li>
<p>In the <strong>User example</strong> field, type the text of a user example for the intent. An example can be any string up to 1024 characters in length. The following might be examples for the <code>#pay_bill</code> intent:</p>
<ul>
<li><code>I need to pay my bill.</code></li>
<li><code>Pay my account balance</code></li>
<li><code>make a payment</code></li>
</ul>
<p><strong>Important</strong>: Intent names and example text can be exposed in URLs when an application interacts with the service. Do not include sensitive or personal information in these artifacts.</p>
<p>Press Enter or click <strong>+</strong> to save the example.</p>
</li>
<li>
<p>Repeat the same process to add more examples. Provide at least 5 examples for each intent. The more examples you provide, the more accurate your application can be.</p>
<p><img src="https://github.com/VidyasagarMSC/WatBot/blob/initial/Images/define_intent.png" alt="Screen capture showing intent definition"></p>
</li>
<li>
<p>When you have finished adding examples, click <strong>Create</strong> to finish creating the intent.</p>
</li>
</ol>
<h3 class="toc-ignore" id="results">Results</h3>
<p>The intent you created is added to the Intents tab, and the system begins to train itself on the new data.</p>
<p>You can click any intent in the list to open it for editing. You can make the following changes:</p>
<ul>
<li>Rename the intent.</li>
<li>Delete the intent.</li>
<li>Add, edit, or delete examples.</li>
<li>Move an example to a different intent.</li>
</ul>
<p>To move an example, select the example by clicking the check box and then click <strong>Move to</strong>.</p>
<p><img src="https://github.com/VidyasagarMSC/WatBot/blob/initial/Images/move_example.png" alt="Screen capture showing how to move an example"></p>

<h2 id="testing-your-intents">Testing your intents </h2>
<p>After you have finished creating new intents, you can test the system to see if it recognizes your intents as you expect.</p>
<ol>
<li>
<p>In the Conversation tool, click the <img src="https://github.com/VidyasagarMSC/WatBot/blob/initial/Images/ask_watson.png" alt="Ask Watson"> icon.</p>
</li>
<li>
<p>In the Try it out panel, enter a question or other text string and press Enter to see which intent is recognized. If the wrong intent is recognized, you can improve your model by adding this text as an example to the correct intent.</p>
<p><strong>Tip</strong>: If you have recently made changes in your workspace, you might see a message indicating that the system is still retraining. If you see this message, wait until training completes before testing:</p>
<p><img src="https://github.com/VidyasagarMSC/WatBot/blob/initial/Images/training.png" alt="Screen capture showing retraining message"></p>
<p>The response indicates which intent was recognized from your input.</p>
<p><img src="https://github.com/VidyasagarMSC/WatBot/blob/initial/Images/test_intents.png" alt="Screen capture of testing intents"></p>
</li>
<li>
<p>If the system did not recognize the correct intent, you can correct it. To correct the recognized intent, click the displayed intent and then select the correct intent from the list. After your correction is submitted, the system automatically retrains itself to incorporate the new data.</p>
<p><img src="https://github.com/VidyasagarMSC/WatBot/blob/initial/Images/correct_intent.png" alt="Screen capture of correcting a recognized intent"></p>
<p>If your intents are not being correctly recognized, consider making the following kinds of changes:</p>
<ul>
<li>Add the unrecognized text as an example to the correct intent.</li>
<li>Move existing examples from one intent to another.</li>
<li>Consider whether your intents are too similar, and redefine them as appropriate.</li>
</ul>
</li>
</ol>

   

 