## Project Title
A brief description of the project, including its purpose and any relevant background information.

## Getting Started
Instructions on how to set up the project on a local machine for development and testing purposes. This should include information on how to install any dependencies and any necessary setup steps.
```
# Install the dependencies
pip install -r requirements.txt

# Set up the database
python scripts/setup_db.py

# Run the development server
python app.py

```

or example from: ``` https://github.com/lucidrains/PaLM-rlhf-pytorch```
```python
import torch
from palm_rlhf_pytorch import PaLM

palm = PaLM(
    num_tokens = 20000,
    dim = 512,
    depth = 12
).cuda()

seq = torch.randint(0, 20000, (1, 2048)).cuda()

loss = palm(seq, return_loss = True)
loss.backward()

# after much training, you can now generate sequences

generated = palm.generate(2048) # (1, 2048)
```

## Prerequisites
A list of any dependencies or requirements that must be installed before the project can be run. This could include things like Python packages, system libraries, or external tools.

## Installing
Detailed instructions on how to install the project and any necessary dependencies. This should include information on how to clone the repository, how to install dependencies, and any other necessary setup steps.
```
# Clone the repository
git clone https://github.com/username/project.git

# Change into the project directory
cd project

# Install the dependencies
pip install -r requirements.txt

```

## Running
### Tests
Instructions on how to run the automated tests for this project. This should include information on how to run the tests and what they cover.
```
# Run the test suite
python -m unittest discover
```
### Running the code
```
# Run the main script
python main.py
```
## Deployment
Instructions on how to deploy the project on a live system. This should include information on any necessary configuration or setup steps, as well as any necessary instructions for the user.

## Todo
Example from this repo: ``` https://github.com/lucidrains/PaLM-rlhf-pytorch```
- [x] clone base transformer with separate lora for critic
- [x] also allow for non-LoRA based finetuning
- [x] redo normalize to be able to have a masked version, not sure if anyone will ever use per token rewards / values, but good practice to implement

- [ ] add Hugging Face accelerate and test out wandb instrumentation
- [ ] search literature to figure out what is the latest SOTA for PPO, assuming RL field is still making progress.


## Contributing
Guidelines for contributing to the project, including information on how to submit pull requests and any necessary coding standards or conventions.
```
# Example contribution guidelines

## Pull Requests

1. Fork the repository
2. Create a new branch for your changes
3. Make the necessary changes
4. Commit your changes and push to the new branch
5. Submit a pull request

## Coding Standards

- Follow the [PEP 8](https://www.python.org/dev/peps/pep-0008/) style guide for Python code
- Use [yapf](https://github.com/google/yapf) to automatically format your code
- Write thorough and descriptive commit messages

```
## Versioning
Information on how the project is versioned, including any relevant version numbering schemes or conventions.
```
# Use Semantic Versioning for version numbering
__version__ = "1.0.0"

```
## Authors
A list of the people who contributed to the project, along with their roles and responsibilities.

## Acknowledgments
Any credits or acknowledgments that should be included in the documentation, such as any third-party libraries or tools that were used in the project.#