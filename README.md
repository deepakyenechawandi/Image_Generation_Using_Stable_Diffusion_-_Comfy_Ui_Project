
# Image Generation Using Stable Diffusion - Comfy UI Project

This repository contains a project for generating images using the Stable Diffusion model with a user-friendly interface, ComfyUI. The project leverages various machine learning techniques and models to create high-quality images based on textual prompts.

## Table of Contents

- [Installation](#installation)
- [Usage](#usage)
- [File Structure](#file-structure)
- [Configuration](#configuration)
- [Contributing](#contributing)
- [License](#license)

## Installation

To set up the project locally, follow these steps:

1. **Clone the repository**:
   ```bash
   git clone https://github.com/deepakyenechawandi/Image_Generation_Using_Stable_Diffusion_-_Comfy_Ui_Project.git
   cd Image_Generation_Using_Stable_Diffusion_-_Comfy_Ui_Project
   ```

2. **Create a virtual environment**:
   ```bash
   python3 -m venv venv
   source venv/bin/activate   # On Windows, use `venv\Scripts\activate`
   ```

3. **Install the required dependencies**:
   ```bash
   pip install -r requirements.txt
   ```

## Usage

To generate images, follow these steps:

1. **Load the model checkpoint**:
   - Ensure you have the required model checkpoint file (`powerpuffmix_v30.safetensors`) in the project directory.

2. **Run the image generation script**:
   ```bash
   python generate_image.py --config Image_Generation.json
   ```

3. **Check the output**:
   - The generated images will be saved in the specified output directory (default: `ComfyUI`).

## File Structure

```
Image_Generation_Using_Stable_Diffusion_-_Comfy_Ui_Project/
├── Image_Generation.json         # Configuration file for the image generation pipeline
├── generate_image.py             # Script to run the image generation process
├── requirements.txt              # List of dependencies
├── README.md                     # This README file
└── checkpoints/                  # Directory to store model checkpoints
```

## Configuration

The `Image_Generation.json` file contains the configuration for the image generation process. Key components include:

- **Nodes**: Define the steps in the image generation pipeline.
- **Links**: Specify the connections between nodes.
- **Extra**: Additional settings such as scaling and offset values.

### Example Configuration

```json
{
  "last_node_id": 9,
  "last_link_id": 9,
  "nodes": [
    {
      "id": 8,
      "type": "VAEDecode",
      "pos": {
        "0": 914,
        "1": 506
      },
      ...
    },
    ...
  ],
  "links": [
    [1, 4, 0, 3, 0, "MODEL"],
    ...
  ],
  "extra": {
    "ds": {
      "scale": 1,
      "offset": [175.6972201352367, -102.29601803155538]
    }
  },
  "version": 0.4
}
```

## Contributing

Contributions are welcome! Please follow these steps to contribute:

1. **Fork the repository**.
2. **Create a new branch**:
   ```bash
   git checkout -b feature-branch
   ```
3. **Make your changes**.
4. **Commit your changes**:
   ```bash
   git commit -m "Add new feature"
   ```
5. **Push to the branch**:
   ```bash
   git push origin feature-branch
   ```
6. **Create a Pull Request**.

## License

This project is licensed under the Apache License 2.0. See the [LICENSE](LICENSE) file for details.
