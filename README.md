# Project description

Finice is a budget tracking appplication with **Voice Recognition** and **Natural Language Processing** feature to increase user convenience and lessen frictions. Users can input daily transactions and track their finances easily through voice input.

# Core features

## Feature 1: Voice input for daily transactions

Users can speak to the application (for example: "Paid Chris 60 dollar for lunch yesterday"), and Finice will use Voice Recognition and Natural Language Processing to parse the details:
- Amount
- Date
- Category
- Short description

And automatically add the transaction to the history log for you.

No more medding with multiple button clicks just to record your finances

## Feature 2: NLP interface for on-demand data analytics

Users can query their transaction using natural language input (for example: "All transactions related to Food greater than $100 in January 2023") and Finance will parse the statement to automatically generate a report for you

## Feature 3: Cross-platform application through Progressive Web App (PWA)

User can enjoy Finice both on the web as well as on mobile because Finice is a PWA

# Technical research and exploration

## Feature 1:

We explore 3 different options to be able to parse the user's input sentence:
- Use GPT API:
    - Opportunities: Initial research shows that GPT is very capable of this task. GPT Function or JSONFormer can be used to force the output to be JSON
    - Challenges: Costly and could be slow
- Fine-tuning Llama:
    - Opportunities: If successful, we will achieve better speed than GPT. The hardest part is categorizing the transaction, which can be done through Machine Learning with a [dataset we have gathered](https://app.surgehq.ai/datasets/financial-transactions-intent-and-expense-category) or a dataset generated from chatGPT
    - Challenges: Time-consuming and we both have limited NLP experience (though we both want to get better at NLP). However, we believe that the input sentence structure is sufficiently simple that we can implement less advanced NLP techniques and still achieve satisfactory results.
- Creating a simple model from scratch

## Feature 2

We recognize this a hard problem. One direction is to use GPT API to generate the appropriate SQL statements after providing it the schema of our database
