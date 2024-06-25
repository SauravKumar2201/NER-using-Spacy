# Named Entity Recognition using spaCy

## Overview
This project demonstrates the use of spaCy for Named Entity Recognition (NER). The Jupyter notebook walks through the process of loading the spaCy model, processing a sample sentence, and extracting named entities.

## Features
- Import and load the spaCy model (`en_core_web_sm`).
- Process a test sentence to identify named entities.
- Extract and print entities by type (organizations, persons, locations).

## Installation
To run this project, you need to have Python installed along with the spaCy library and the `en_core_web_sm` model.

1. Install spaCy:
    ```sh
    pip install spacy
    ```
2. Download the model:
    ```sh
    python -m spacy download en_core_web_sm
    ```

## Usage
1. Load the required libraries and model:
    ```python
    import spacy
    import en_core_web_sm
    nlp = en_core_web_sm.load()
    ```
2. Define and process a test sentence:
    ```python
    sentence = "satyam is the CEO of Apple and he lives in USA"
    doc = nlp(sentence)
    ```
3. Extract named entities:
    ```python
    entities = [(X.text, X.label_) for X in doc.ents]
    ```
4. Print entities by type:
    ```python
    def entity_name(name):
        for entity in entities:
            if entity[1] == name:
                print(entity[0])

    print("\nOrganization(s):")
    entity_name("ORG")
    print("\nPerson(s):")
    entity_name("PERSON")
    print("\nLocation(s):")
    entity_name("GPE")
    ```

## Output
The script will output the entities found in the test sentence:
