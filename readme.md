# AI Summarizer

AI Summarizer is a Python package that uses OpenAI's GPT-3.5 to summarize any given text.
You can input some text describing what kind of information you are interested in. 
When the text is too long it splits it logically into different sections, to make it simpler to summarise

## Installation

You can install AI-Summarizer using pip:

```sh
pip install AI-Summarizer

```

You also need to set up your OpenAI API key, which can be obtained from the OpenAI website. Once you have your API key, create a .env file in the root directory of your project and add the following line:

```py
OPENAI_API_KEY=<your-api-key>
```

Make sure to replace <your-api-key> with your actual API key.

## Usage

Here's a simple example of how to use AI Summarizer. It has been developed to create short summaries that the AI can digest. It should work with any page, but so far it has been only tested with wikipedia pages

```py
from ai_summarizer import summarize_text

text = <insert long wikipedia page text here>

filter = "technological breakthrough"

summary_length = 500

model = "gpt-3.5-turbo"

summary = summarize_text(text, filter=filter, summary_length=summary_length, model=model, max_number_tokens=4096)

print(summary)
```

This example summarizes a text from wikipedia using the summarize_text() function from the AI Summarizer library. The `filter` parameter is used to specify the keywords to include in the summary, the `summary_length` parameter is used to specify the maximum length of the summary, and the `model` parameter is used to specify the GPT-3 model to use.


This will output a summary of (about) the correct length of the given text.

The library includes also a number of other functions that were necessary for it to function,
and could be of great utility for others as well.

```py
def split_text_logically(A: str) --> A_part_1, A_part_2
```

takes some text in markdown format and splits it into two parts. 
The usual way to do this is to split it half way, just keeping some text in common. 
I abhore this practice, as I would abhore reading a book from half a word.
Instead it tries to split it using sections, and if this is not possible sub-sections,
and if this is not possible...

This is useful to analyse the text to summarise easily. But it could be useful for a lot of other reasons too.

```py
def get_number_of_tokens(text,model="gpt-3.5-turbo")
```

this will give you an approximation of how many tokens would this text be, 
if you need to send it to openai. Although if you need this function, you are probably better off just using directly tiktoken and not this which is just a wrap.

```py
def html_to_markdown(html_content,ignore_links=True)
```

This will transform the html text into markdown text. We do this because it is much easier to handle and underastand markdown text for an AI than html which includes a lot of elements unnecessary.


License
AI Summarizer is licensed under the MIT License.

