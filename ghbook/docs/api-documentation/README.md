---
icon: webhook
---

# API Documentation

[URL: https://exios66.github.io/Literary-Vault/](https://app.gitbook.com/s/uXasb3u6SSZaSP9P5BJw/)

## Response Schema

```yaml
{
  "type": "array",
  "items": {
    "type": "object",
    "properties": {
      "id": {
        "type": "string",
        "description": "Unique identifier for the question"
      },
      "question": {
        "type": "string",
        "description": "The question text"
      },
      "correct_answer": {
        "type": "string",
        "description": "The correct answer"
      },
      "options": {
        "type": "array",
        "items": {
          "type": "string"
        },
        "description": "Multiple choice options if applicable"
      }
    },
    "required": ["id", "question", "correct_answer"]
  }
}
```

***

## Example Response

```json

[
  {
    "id": "ASTRO_001",
    "question": "What is the closest star to Earth besides the Sun?",
    "correct_answer": "Proxima Centauri",
    "options": [
      "Proxima Centauri",
      "Alpha Centauri A",
      "Barnard's Star",
      "Sirius"
    ]
  }
]
```

***

## GET QUESTIONS

```json
{
  "name": "get_questions",
  "description": "Retrieves questions from the repository's structured CSV files",
  "parameters": {
    "type": "object",
    "properties": {
      "category": {
        "type": "string",
        "description": "The category of questions to retrieve (astronomy, literature, or mathematics)",
        "enum": ["astronomy", "literature", "mathematics"]
      },
      "limit": {
        "type": "integer",
        "description": "Maximum number of questions to return",
        "default": 10,
        "minimum": 1,
        "maximum": 50
      },
      "random": {
        "type": "boolean",
        "description": "Whether to return random questions or sequential ones",
        "default": true
      }
    },
    "required": ["category"]
  },
  "returns": {
    "type": "array",
    "items": {
      "type": "object",
      "properties": {
        "id": {
          "type": "string",
          "description": "Unique identifier for the question"
        },
        "question": {
          "type": "string",
          "description": "The question text"
        },
        "options": {
          "type": "array",
          "description": "Multiple choice options if applicable",
          "items": {
            "type": "string"
          }
        },
        "correct_answer": {
          "type": "string",
          "description": "The correct answer to the question"
        }
      },
      "required": ["id", "question", "correct_answer"]
    }
  }
}
```

***

## Randomize JSON

```json
{
  "name": "randomize_questions",
  "description": "Randomly select and order questions from a given category",
  "parameters": {
    "type": "object",
    "properties": {
      "category": {
        "type": "string",
        "description": "The category of questions to randomize (astronomy, literature, or mathematics)",
        "enum": ["astronomy", "literature", "mathematics"]
      },
      "count": {
        "type": "integer",
        "description": "Number of questions to randomly select",
        "default": 5,
        "minimum": 1,
        "maximum": 20
      },
      "seed": {
        "type": "integer",
        "description": "Optional random seed for reproducible randomization",
        "default": null
      }
    },
    "required": ["category"]
  },
  "returns": {
    "type": "array",
    "items": {
      "type": "object", 
      "properties": {
        "id": {
          "type": "string",
          "description": "Unique identifier for the selected question"
        },
        "question": {
          "type": "string",
          "description": "The randomized question text"
        },
        "options": {
          "type": "array",
          "description": "Randomized multiple choice options if applicable",
          "items": {
            "type": "string"
          }
        },
        "correct_answer": {
          "type": "string",
          "description": "The correct answer for the question"
        }
      },
      "required": ["id", "question", "correct_answer"]
    }
  }
}
```

```json
```
