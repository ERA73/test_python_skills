# Skill: Python Docstrings

## Objective
Consistent Python module and function docstrings.

## Rules
- Maximum line length is 74.
- Use a short and concise description of the content.
- Do not mix module purpose with function purpose.
- Use the Google Python docstring standard:
```python
"""Short description of the module with max 74 characters
Detailed description of the module with max 74 characters per line
"""

def function(arg1: str, arg2: int) -> bool:
    """Short description of the function with max 74 characters

    Args:
        arg1 (str): Description of arg1 with max 74 characters
        arg2 (int): Description of arg2 with max 74 characters

    Returns:
        bool: Description of the return value with max 74 characters
    """
```

## Definition of Done
- All modules and functions have docstrings following the specified format
- Docstrings are clear, concise, and provide necessary information about the module/function purpose, arguments, and return values.