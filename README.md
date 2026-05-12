# Neural-Recall-Multimodal
The Neural Recall plugin but with multimodal model support for "image" memory storage. Made to be slotted into Open WebUI, or, it can be used as a standalone with some mods.
Neural-Recall-Multimodal 🧠🖼️
Neural-Recall-Multimodal is an evolution of the Neural Recall plugin designed for Open WebUI. It extends standard text-based long-term memory by integrating multimodal vision capabilities, allowing the system to "remember" and describe images provided during conversations.
By converting visual input into descriptive text metadata, this plugin enables users to search their long-term memory for specific image attributes, contexts, and visual details using natural language.
✨ Key Features
Visual Memory Encoding: Automatically processes uploaded images through a vision-capable LLM to generate detailed text descriptions.
Attribute Storage: Captures specific details (colors, objects, text within images, setting) and stores them in the vector database.
Multimodal Context Retrieval: When you ask a question, the system retrieves relevant past image descriptions alongside text memories.
Open WebUI Optimized: Built specifically for seamless integration as a Function or Tool within the Open WebUI ecosystem.
Standalone Adaptability: Can be modified for use in custom Python environments or other LLM orchestrators.
🛠️ How It Works
Input Detection: The plugin intercepts image uploads or URL references in the chat context.
Vision Analysis: The image is sent to a multimodal model (e.g., GPT-4o, Claude 3.5 Sonnet, or local models like Llava/Ollama).
Textualization: The model generates a comprehensive description of the image content and attributes.
Vector Storage: This description is injected into the "Neural Recall" memory bank with a [Image Memory] tag for future RAG (Retrieval-Augmented Generation) queries.
🚀 Installation
For Open WebUI
Copy the contents of neural_recall_multimodal.py.
Navigate to your Open WebUI dashboard.
Go to Workspace > Functions > Add Function.
Paste the code and click Save.
Enable the plugin in your specific Model settings.
Standalone Usage
To use this outside of Open WebUI, ensure you have the required dependencies:
pip install openai chromadb  # or your preferred vector store


(Note: Requires modification of the Open WebUI specific wrappers in the main script.)
⚙️ Configuration
Variable
Description
Default
VISION_MODEL
The model used to describe images (e.g., gpt-4o, llava)
gpt-4o
MEMORY_THRESHOLD
Similarity score required for memory retrieval
0.7
MAX_DESC_LENGTH
Character limit for the generated image description
500

🤝 Contributing
Contributions are welcome! If you have ideas for better image-to-text prompting or support for additional vector databases, please open an issue or submit a pull request.
📄 License
This project is licensed under the GNU Affero General Public License v3.0 (AGPL-3.0). See the LICENSE file for more details.
