# RLHF (Reinforcement Learning from Human Feedback) DeepSeek Tuning

A reinforcement learning-based implementation for fine-tuning DeepSeek LLM locally using human feedback, reward model training, and experimental policy optimization features.

This framework provides a foundation for improving the locally-hosted DeepSeek model's performance through interactive training sessions where the AI responses are rated. A reward model is trained from this feedback, with experimental policy optimization features for exploring reinforcement learning from human feedback.

## Features

- Interactive Training: Two modes for collecting human feedback
  - User-prompted conversations with manual feedback
  - Auto-generated prompts with response evaluation
- DeepSeek Integration: Supports both local Ollama and Hugging Face model backends
- Reward Model: Neural network-based reward prediction using LSTM and attention mechanisms
- Experimental PPO Integration: Proximal Policy Optimization for policy updates
- Progress Tracking: Comprehensive statistics and visualization of training progress
- Session Persistence: Save and load training checkpoints

## How to Run

### Prerequisites

- Python 3.8+
- Ollama (for Local LLM inference)

### Usage

1. Clone this repository on your local machine.
2. Install dependencies:
```bash
pip install torch transformers requests matplotlib numpy
```
3. Install and setup Ollama, and run the LLM:
```bash
# Install Ollama (visit https://ollama.ai)
# Pull the required model
ollama run deepseek-r1:14b
```
4. Open and run the `Feedback LLM.ipynb` Jupyter Notebook.

### Main Menu Options

1. User-Prompt Feedback: Enter your own prompts and rate the LLM's responses.
2. Automated-Prompt Feedback: The system generates prompts automatically, you rate responses.
3. Exit: Save progress and view training statistics.

### Interactive Commands

During conversations, you can use:
- `back` - Return to main menu
- `train` - Force immediate model training
- `stats` - Display current statistics

### Rating System

Rate responses on a 1-5 scale:
- 1: Very Poor (-1.0 reward)
- 2: Poor (-0.5 reward)
- 3: Average (0.0 reward)
- 4: Good (+0.5 reward)
- 5: Excellent (+1.0 reward)

## Structure

### Project Flow

```
DeepSeek Chat Bot → Feedback Collector → Reward Model → Reward Model Trainer → Policy Framework   
```

### Project Structure (after running the Jupyter Notebook)

```
├── Feedback LLM.ipynb    # Main end-to-end system 
├── feedback_data.json    # Persistent feedback storage
├── rlhf_checkpoint.pkl   # Model training checkpoints
├── README.md             # This file
└── LICENSE               # MIT License
```

## Contributing

Contributions are welcome!

## License

Distributed under the MIT License.  
