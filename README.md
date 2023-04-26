# OpenAI - Common Use Cases

## Common Use Cases

- Recommendation system
- Language transation
- Personalization and content generation
- Prompting and complition from your own content
- Image generation
- Image recognition

### Recommendation System

OpenAI can be used to develop recommendation systems that can suggest products, services, or content to users based on their preferences and behavior.

```mermaid
flowchart LR
  A((start))-->B{From curated<br/>content}  
  B--No-->C[Do not<br/>add context]
  B--Yes-->D[Add curated<br/>content as context]
  C-->E[Prompt<br/>OpenAI API]
  D-->E
```

Examples:

- Without context
```python
prompt = "List the best restaurants in downtown London."
```

- With context
```python
list = get_restaurants("London").join("\n")
prompt = "List the best restaurants in downtown London. The answer should come from the following list:\n{list}"
```

### Language Translation

OpenAI can be used to develop language translation models that can translate text from one language to another.

```mermaid
flowchart LR
  A((start))-->B[Add text<br/>to be translated]
  B-->O[Prompt<br/>OpenAI API]
```

Examples:

```python
source_lang = "English" 
target_lang = "Japanes"
text = load_text()
prompt = "Translate the following text from {source_lang} to {target_lang}:\n{text}"
```


### Personalization & Content Generation

OpenAI can be used to develop personalized content and experiences for users based on their interests and behavior.

```mermaid
flowchart LR
  A((start))-->B[Get structured<br/>properties]
  B-->D[Build a simple description<br/>from the properties]
  D-->O[Prompt<br/>OpenAI API]
```

Examples:

```python
item = {"make","Ford","model":"Explorer","year":2020,"Color":"red","condition":"excellent"}
item_description = get_item_description(item)
prompt = "Get a full sales description for the following used vehicle:\n" + item_description
```

### Search Your Own Content

