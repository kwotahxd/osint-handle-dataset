# Dataset Schema
 
Each file in `dataset/` describes a single transformation type.  
Exception — `combined.json`, which covers examples where multiple transformations are applied simultaneously.
 
---
 
## Transformation file structure
 
```json
{
  "version": "string",
  "type": "string",
  "description": "string",
  
  "substitutions": {
    "<char>": ["<variant1>", "<variant2>"]
  },
 
  "patterns": {
    "<name>": {
      "description": "string",
      "subtypes": [
        {
          "name": "string",
          "description": "string",
          "example": "string"
        }
      ]
    }
  },
 
  "notes": ["string"], 				# any notes will go here
 
  "verified_examples": [
    {
      "base": "string",
      "result": "string",
      "applied": { "<char>": "<replacement>" },
      "pattern": "string",
      "combined": false,
      "source": "string"
    }
  ]
}
```
 
### Top-level fields
 
| Field | Type | Description |
|-------|------|-------------|
| `version` | string | Schema version of the file |
| `type` | string | Transformation type (`leet`, `script_switch`, `suffix`, ... ) |
| `description` | string | Human-readable description of the type |
| `substitutions` | object | Substitution table: character → list of possible replacements |
| `patterns` | object | Application patterns (full, partial, alternating, ... ) |
| `notes` | array | Additional remarks, optional |
| `verified_examples` | array | Verified real-world examples |
 
### verified_examples fields
 
| Field | Type | Description |
|-------|------|-------------|
| `base` | string | Original handle/word |
| `result` | string | Transformation result |
| `applied` | object | Which specific substitutions were applied |
| `pattern` | string | Pattern from `patterns` (`partial`, `full`, `partial/alternating`, ... ) |
| `combined` | bool | Whether combined with other transformations |
| `combined_with` | array | List of transformation types (if `combined: true`) |
| `ref_id` | string | Entry ID in `combined.json` (if `combined: true`) |
| `source` | string | Example source |
 
---
 
## combined.json structure
 
```json
{
  "version": "string",
  "entries": [
    {
      "id": "string",
      "base": "string",
      "result": "string",
      "transformations": [
        {
          "type": "string",
          "applied": { "<char>": "<replacement>" }
        }
      ],
      "source": "string"
    }
  ]
}
```
 
### entries fields
 
| Field | Type | Description |
|-------|------|-------------|
| `id` | string | Unique entry identifier (referenced via `ref_id`) |
| `base` | string | Original handle/word |
| `result` | string | Final result |
| `transformations` | array | List of applied transformations with details |
| `source` | string | Example source |
