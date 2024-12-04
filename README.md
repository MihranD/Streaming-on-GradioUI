# Company Sales Brochure Generator with Gradio UI
***
We created user interfaces using the simple Gradio framework.

Please note: your Gradio screens may appear in `dark mode` or `light mode` depending on your computer settings.

![Brochure](https://github.com/MihranD/Streaming-on-GradioUI/blob/main/images/brochure.png)

## Project Organization
----------------------------------------------------------------------------------------------
    ├── .gitignore          <- Includes files and folders that we don't want to control
    |
    ├── images              <- Images for use in this project
    │   ├── brochure.png    <- Brochure image
    │   └── result.png      <- Result image
    |
    ├── main.ipynb          <- Main jupyter file that needs to be run
    |
    ├── requirements.txt    <- The required libraries to deploy this project. 
    |                       Generated with `pip freeze > requirements.txt`
    └── README.md           <- The top-level README for developers using this project.

## Project Introduction

### Business Problem

Creating tailored marketing brochures for companies is a complex and manual process, requiring extensive effort to gather, analyze, and organize relevant information from their websites. This project provides an automated solution to streamline the process using GPT-4o-mini and cutting-edge techniques for link evaluation and content generation.

### Problem Definition

Generating professional, company-specific sales brochures involves time-consuming tasks like identifying relevant content, assembling marketing details, and designing layouts. This project automates the process by:

1. Using GPT-4o-mini or GPT-4o to analyze company websites and extract only the most relevant links and content.
2. Automating the design and creation of sales brochures based on the extracted information.
3. Enhancing user experience with real-time streaming output for smoother content generation.
4. Displaying the streaming results interactively using `Gradio UI` for a more intuitive and engaging experience.

### Model Output Example

`system_prompt = "You are an assistant that analyzes the contents of a company website landing page and creates a short brochure about the company for prospective customers, investors and recruits. Respond in markdown."`

```
view = gr.Interface(
    fn=stream_brochure,
    inputs=[
        gr.Textbox(label="Company name:"),
        gr.Textbox(label="Landing page URL including http:// or https://"),
        gr.Dropdown(["GPT-4o-mini", "GPT-4o"], label="Select model")],
    outputs=[gr.Markdown(label="Brochure:")],
    flagging_mode="never"
)
view.launch(share=True)
```

![Result](https://github.com/MihranD/Streaming-on-GradioUI/blob/main/images/result.png)

## Conclusion

Using `Gradio UI`, we successfully enhanced our content generation project by providing an interactive and user-friendly way to visualize results, making the process more accessible and engaging.

## How to run the app

Follow these steps to set up and run the application:

1. **Create a `.env` file**  
   Add your OpenAI API key to the `.env` file in the following format:  
   ```plaintext
   OPENAI_API_KEY=sk-proj-blabla
   ```
   
2. **Setup virtual envirenment**  
   Run the following command to setup virtual envirenment:  
   ```bash
   python3 -m venv venv  # Create a virtual environment named 'venv'
   source venv/bin/activate  # Activate the virtual environment (Linux/Mac)'
   .\venv\Scripts\activate   # Activate the virtual environment (Windows)'
   ```

3. **Install Dependencies**  
   Run the following command to install all required dependencies:  
   ```bash
   pip install -r requirements.txt
   ```

4. **Open and Run the Notebook**  
   Open the `main.ipynb` file in Jupyter Notebook and execute the cells to run the application.

