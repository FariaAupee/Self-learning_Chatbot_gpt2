# Self-learning_Chatbot_gpt2

This repository contains code for an interactive chatbot about Bangladesh. The chatbot is designed to answer various questions about Bangladesh based on a conversational dataset.
The dataset is a JSON file containing 2000 lines of information about various topics related to Bangladesh. 
It consists of conversations between two participants discussing different aspects of Bangladesh.

Approach
The chatbot is built using the GPT-2 language model, trained on a conversational dataset. It uses the torch library for training and inference. 
The dataset is loaded using the 'ChatData' class.
The model is trained using Adam optimizer. After training, the model is saved and can be loaded for chatbot interaction.
During interaction, the chatbot takes user input and generates a response using the trained model. 
It also provides an option for users to provide feedback on the response, allowing the chatbot to learn and improve its answers over time. 
The feedback is collected and stored in a dictionary.

Design Choices
GPT-2 Model: The GPT-2 model is chosen for its ability to generate coherent and contextually relevant responses. It has been pretrained on a large corpus of text and fine-tuned on the conversational dataset specific to Bangladesh.
Tokenizer: The GPT-2 tokenizer is used to preprocess the input data and encode it into tokens suitable for input to the model. Special tokens such as <startofstring>, <endofstring>, and <bot>: are added to indicate the start and end of the input string and to differentiate the bot's responses.
Training Loop: The training loop iterates over the dataset in batches, feeding the input to the model and calculating the loss using the model's output. The Adam optimizer is used to update the model parameters based on the loss.
You can visit [Chatbot](https://drive.google.com/drive/folders/1PD-JrZVVOXWMxh7UsLiwgUzBQTETlHAi?usp=drive_link)
for accessing required weights.
User Feedback: The chatbot allows users to provide feedback on the generated responses. Users can indicate whether the response was helpful, not helpful, or choose to skip providing feedback. This feedback is used to improve the chatbot's answers over time.

Challenges Faced
Dataset Creation: A conversational dataset between two participants about Bangladesh was created to extract the relevant text for training the model. Some of the topics of the conversation include foods,famous places, culture, climate, traditions, national history, arts and crafts about Bangladesh.  
Additionally, the conversations in the dataset were structured in a specific format, requiring careful extraction of the conversational turns.
Training Time: Training a large language model like GPT-2 can be computationally expensive and time-consuming. Training was performed on a GPU if available, or on a CPU if not. It required multiple epochs to achieve reasonable performance.
User Feedback Handling: Collecting and processing user feedback adds complexity to the chatbot system. Handling different types of feedback and updating the knowledge dictionary required careful implementation.

Instructions to Run and Interact with the Chatbot
1. Clone the repository to your local machine.
2. Install the required dependencies mentioned in the code (torch, json, tqdm, transformers).
3. Download the GPT-2 medium model and tokenizer files.
4. Place the conversational dataset JSON file (newdata.json) in the specified location (/content/drive/MyDrive/Chatbot/).
5. Set up a CUDA-enabled GPU environment if available. Alternatively, the code will run on a CPU, but with reduced performance.
6. Open the terminal/command prompt and navigate to the cloned repository directory.
7. Run the code using the Python interpreter: python chatbot.py.
8. The chatbot will start interacting by displaying User: prompt. Enter your query about Bangladesh and press Enter.
9. The chatbot will generate a response based on the trained model and display it as Bot: response.
10. After each response, the chatbot will prompt for feedback: Was the response helpful? (yes/no/skip):.
11. Provide feedback on the response by entering yes, no, or skip and press Enter.
12. If you choose yes, the chatbot will proceed to the next query.
13. If you choose no, the chatbot will prompt: Please provide the correct answer:. Enter the correct answer and press Enter.
14. If you choose skip, the chatbot will not learn from your feedback and proceed to the next query.
15. To exit the chatbot, enter exit as your query.
Note: The knowledge learned by the chatbot will be stored in a dictionary file (knowledge.json) located in /content/drive/MyDrive/Chatbot/. This file contains the improved responses based on user feedback.

Feel free to interact with the chatbot and explore different aspects of Bangladesh!
