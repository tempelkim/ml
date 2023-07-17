# Technical Requirements/Questions

## Data Model

Could be anything from simple 'question + answer + question_embedding' to a very elaborated model containing documents, document references, keywords, validity periods, scopes, target groups, language, ownership etc. alongside administrative informations like creation, modification, usage, ...

What is the minimal information unit aka data record? One q & a? One document/regulation/article? If different types of documents get stored, how do they relate to each other?

The more complicated the model gets the more thoughts have to be spent on how to keep it reusable and flexible to adapt for further changes and extensions.

## Database

What database can/should be used?

Dedicated vector databases are

- [Chroma](https://www.trychroma.com/)
- [Pinecone](https://www.pinecone.io/)
- [Weaviate](https://weaviate.io/)
- [Milvus](https://milvus.io/)
- [Faiss](https://faiss.ai/)

Alternative: Postgres + extension ([pgvector](https://github.com/pgvector/pgvector))? 

## Data Collection

How do we collect data? Raw data needs to be prepared for import into the database. This preparation highly depends on the model structure. It involves things like classifications, adding keywords, providing references, splitting documents.

A workflow must be established to add the prepared data into the database.

## Data Maintenance

We need a way to take care of this knowledge base. Records must be revised regularly. Entries must be changed, added or deleted. Most likely this will require a dedicated application that -again depending on the complexity of the data model- might be far more complex than the user facing side.
