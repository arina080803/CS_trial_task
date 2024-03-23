# CS_trial_task

Project Task: Text Improvement Engine (English only)

Objective:
Develop a tool that analyses a given text and suggests improvements based on the similarity to a list of "standardised" phrases. These standardised phrases represent the ideal way certain concepts should be articulated, and the tool should recommend changes to align the input text closer to these standards.
_____________________________________________________________________________________________

**SpaCy** is an open-source software library for advanced natural language processing, written in the programming languages Python and Cython.

SpaCy is designed specifically for production use and helps to create applications that process and "understand" large amounts of text. It can be used to build information extraction or natural language understanding systems, or to pre-process text for deep learning.

In this case we have small text, however using this library I test how it works on small amounts of data, checking the accuracy of query execution and selecting the optimal threshold value of the parameter.

Some conclusions can be drawn after applying the proposed list:

*   The specified threshold plays a key role. When this value is reduced even by a small degree, the result of the function changes significantly: the library makes mistakes, mistaking articles for words with a large semantic load and replaces them with suggested phrases that have a completely different meaning and are not suitable in this particular situation. Also, the library makes a big mistake and replaces words with a parameter less than 0.65 that have completely different meanings;
*   **Cosine similarity** does not solve the problem of natural language in text data, i.e. synonyms and polysemy. This has a big impact on the accuracy of the search. At first glance, this method gives the same answer as the basic spacy library, but the result of accuracy (the confidence of the model in the result) may differ for the better by a very small fraction of one

Ideas for improvement:

*   we can train a special model that will also work with the space library or any other natural language processing library. In such a model, it is possible to implement the division of text into semantic phrases according to the vocabulary of the language in order to exclude the occurrence of article substitutions. The model will also be able to learn from hundreds of similar phrases in order to learn how to see the context and eliminate lexical, grammatical and semantic errors.
*   in case we avoid writing our own model, we could additionally use text preprocessing libraries that work not only with punctuation marks, spaces and an array of words, but also take into account the totality of words during processing. Thus, the synthesis library would allow for high-quality lexical replacement of words in any text that the user suggests, for any text size.
