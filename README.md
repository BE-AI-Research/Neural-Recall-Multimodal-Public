# **Neural-Recall-Multimodal 🧠🖼️**

**Neural-Recall-Multimodal** is an evolution of the Neural Recall plugin designed for [Open WebUI](https://github.com/open-webui/open-webui). It extends standard text-based long-term memory by integrating multimodal vision capabilities, allowing the system to "remember" and describe images provided during conversations.

By converting visual input into descriptive text metadata, this plugin enables users to search their long-term memory for specific image attributes, contexts, and visual details using natural language.

## **✨ Key Features**

* **Visual Memory Encoding:** Automatically processes uploaded images through a vision-capable LLM to generate detailed text descriptions.  
* **Attribute Storage:** Captures specific details (colors, objects, text within images, setting) and stores them in the vector database.  
* **Multimodal Context Retrieval:** When you ask a question, the system retrieves relevant past image descriptions alongside text memories.  
* **Open WebUI Optimized:** Built specifically for seamless integration as a Function or Tool within the Open WebUI ecosystem.  
* **Standalone Adaptability:** Can be modified for use in custom Python environments or other LLM orchestrators.

## **🛠️ How It Works**

1. **Input Detection:** The plugin intercepts image uploads or URL references in the chat context.  
2. **Vision Analysis:** The image is sent to a multimodal model (e.g., GPT-4o, Claude 3.5 Sonnet, or local models like Llava/Ollama).  
3. **Textualization:** The model generates a comprehensive description of the image content and attributes.  
4. **Vector Storage:** This description is injected into the "Neural Recall" memory bank with a \[Image Memory\] tag for future RAG (Retrieval-Augmented Generation) queries.

## **🚀 Installation**

### **For Open WebUI**

1. Copy the contents of neural\_recall\_multimodal.py.  
2. Navigate to your Open WebUI dashboard.  
3. Go to **Workspace** \> **Functions** \> **Add Function**.  
4. Paste the code and click **Save**.  
5. Enable the plugin in your specific Model settings.

### **Standalone Usage**

To use this outside of Open WebUI, ensure you have the required dependencies:

pip install openai chromadb  \# or your preferred vector store

*(Note: Requires modification of the Open WebUI specific wrappers in the main script.)*

## **⚙️ Configuration**

| Variable | Description | Default |
| :---- | :---- | :---- |
| VISION\_MODEL | The model used to describe images (e.g., gpt-4o, llava) | gemma3:4b |
| MEMORY\_THRESHOLD | Similarity score required for memory retrieval | 0.64 |
| MAX\_DESC\_LENGTH | Character limit for the generated image description | 500-1024 |

## **🤝 Contributing**

Contributions are welcome\! If you have ideas for better image-to-text prompting or support for additional vector databases, please open an issue or submit a pull request.

## **📄 License**

This project is licensed under the **GNU Affero General Public License v3.0 (AGPL-3.0)**. See the [LICENSE](http://docs.google.com/LICENSE) file for more details.
