# Indus Valley Seals: LLM Analysis  
*A research project evaluating publicly available LLMs' (in this Claude Sonnet 4) ability to interpret ancient Indus Valley seals*  

---

## 📁 Files  
### Dataset  
[`data/seals_dataset.csv`](data/seals_dataset.csv)  
- **Contents**: 25 Indus Valley seals with:  
  - Expert descriptions (ground truth)  
  - LLM-generated descriptions (Claude Sonnet 4)  
  - Accuracy scores (1-5 scale) and justifications  
- **Columns**:  
  `seal_no`, `image_url`, `seal_name`, `expert_description`, `llm_description`, `accuracy_score`, `score_justification`, `has_description`  

### Chat Logs  
[`documentation/chat_logs.txt`](documentation/chat_logs.txt)  
- **Contents**:  
  - Full transcripts of interactions with Claude Sonnet 4  
  - Timestamps, uploaded image links, and prompts  
  - LLM responses for each seal  

---

## 🔗 Data Sources  
All seal images were sourced from:  
> Harappa Archaeological Research Project. (n.d.). *Indus Valley seals* [Photographs]. Harappa.com. https://www.harappa.com  

*(See [chat_logs.txt](documentation/chat_logs.txt) for individual image links.)*  

---

## 🛠️ Usage  
### Load and Analyze Data  
```python
import pandas as pd

# Load dataset
df = pd.read_csv("data/seals_dataset.csv")

# Filter seals with low accuracy (scores ≤ 2)
low_accuracy_seals = df[df["accuracy_score"] <= 2]
print(f"Seals with major inaccuracies: {len(low_accuracy_seals)}")
