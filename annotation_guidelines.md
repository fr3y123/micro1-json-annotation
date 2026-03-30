# Annotation Guidelines
## Task: Intent and Entity Annotation

### 1. Overview
This document defines the rules for annotating text data for intent classification and entity extraction tasks. The goal is to produce high-quality, consistent JSON datasets suitable for machine learning model training and evaluation.

---

### 2. Annotation Structure

Each data point must follow this JSON structure:

- `text`: Original user input
- `intents`: List of one or more intents
- `entities`: Extracted structured information from text
- `confidence`: Annotator confidence score (0.0 - 1.0)
- `metadata`: Additional contextual information

---

### 3. Intent Annotation Rules

#### 3.1 General Rules
- Assign **at least one intent** per input.
- Use **multi-intent labeling** if the sentence expresses more than one action.
- Choose intents based on **user goal**, not keywords.

#### 3.2 Examples
| Text | Intent |
|------|------|
| "Cancel my order" | cancel_order |
| "Cancel and refund me" | cancel_order, request_refund |

#### 3.3 Ambiguity Handling
- If unclear, select the **most probable intent**
- Add `"edge_case": true` in metadata

---

### 4. Entity Annotation Rules

#### 4.1 General Rules
- Extract only **relevant entities**
- Do NOT infer values not explicitly present (unless specified)
- Use precise text spans when possible

#### 4.2 Entity Format
Each entity must include:
- `type`: Entity category (e.g., order_id)
- `value`: Extracted value
- `start` (optional): Start index in text
- `end` (optional): End index in text

#### 4.3 Examples
Text:  
"I never received my order 12345"

Entity:
```json
{
  "type": "order_id",
  "value": "12345",
  "start": 30,
  "end": 35
}
