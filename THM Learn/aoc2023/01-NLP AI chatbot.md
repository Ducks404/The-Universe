## Main problem
These AI are trained on datasets and made to predict the next letter of a sequence to make natural language. They can leak data

### Assumption
- Just remove sensitive data from dataset

### Why not
- Sensitive data can change, what is not sensitive now can be sensitive later
- Maintaining a chatbot real time is hard

## Security Measures
### Prompt-assisted
Have an internal prompt that gives the chatbot guidelines

### Ai-assisted
Have an interceptor trained on malicious prompts
