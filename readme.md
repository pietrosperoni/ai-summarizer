# AI Summarizer

AI Summarizer is a Python package that uses OpenAI's GPT-3.5 to summarize any given text. 

## Installation

You can install AI Summarizer using pip:

```sh
pip install AI-Summarizer

You also need to set up your OpenAI API key, which can be obtained from the OpenAI website. Once you have your API key, create a .env file in the root directory of your project and add the following line:

OPENAI_API_KEY=<your-api-key>

Make sure to replace <your-api-key> with your actual API key.

Usage
Here's a simple example of how to use AI Summarizer. It has been developed to create short summaries that the AI can digest. It should work with any page, but so far it has been only tested with wikipedia pages


from AI-Summarizer import summarize_text

text = <insert long wikipedia page text here>

filter = "technological breakthrough"

summary_length = 500

model = "gpt-3.5-turbo"

summary = summarize_text(text, filter=filter, summary_length=summary_length, model=model)

print(summary)




This example summarizes a text about the COVID-19 pandemic using the summarize_text() function from the AI Summarizer library. The filter parameter is used to specify the keywords to include in the summary, the summary_length parameter is used to specify the maximum length of the summary, and the model parameter is used to specify the GPT-3 model to use.



This will output a summary of the given text.

License
AI Summarizer is licensed under the MIT License.

