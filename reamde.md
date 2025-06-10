Here's the `README.md` file for your "People You May Know" recommendation system:

```markdown
# People You May Know - Pure Python Recommendation System

## Overview
This is a friendship recommendation system implemented in pure Python without external dependencies. It suggests potential connections based on mutual friends, similar to social media platforms' "People You May Know" features.

## How It Works

### Data Structure
The system expects a JSON file (`massive_data.json`) with this structure:
```json
{
    "users": [
        {
            "id": 1,
            "friends": [2, 3, 4]
        },
        ...
    ]
}
```

### Recommendation Algorithm
The system follows these steps:

1. **Data Preparation**:
   - Creates a dictionary mapping user IDs to their friend sets
   - Verifies the target user exists in the dataset

2. **Friend Analysis**:
   - Identifies the target user's direct friends (1st-degree connections)
   - Examines friends-of-friends (2nd-degree connections)

3. **Suggestion Scoring**:
   - For each potential connection (friend-of-friend):
     - Excludes existing friends and the user themselves
     - Scores by number of mutual friends

4. **Ranking**:
   - Sorts suggestions by mutual friend count (descending)
   - Returns a list of user IDs in recommendation order

## Key Features
- Zero-dependency Python implementation
- Uses set operations for efficient friend lookups
- Implements classic social network "triadic closure" principle
- Returns recommendations ordered by connection strength

## Example Output
```python
[45, 12, 83]  # User IDs sorted by mutual friend count
```
