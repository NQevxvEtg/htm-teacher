# HTM-Teacher

**HTM-Teacher** is an educational tool designed to demonstrate the fundamental workings of Hierarchical Temporal Memory (HTM) using minimalistic and easy-to-understand Python code. This project aims to help learners grasp the core concepts of HTM models, including Sparse Distributed Representations (SDRs), Spatial Pooling, and Temporal Memory, through visualization and animation.

![htm-teacher](https://github.com/NQevxvEtg/htm-teacher/blob/main/output.gif)


## Table of Contents

- [Introduction](#introduction)
- [Features](#features)
- [Installation](#installation)
- [Usage](#usage)
  - [Running the Simulation](#running-the-simulation)
  - [Understanding the Output](#understanding-the-output)
- [Dependencies](#dependencies)
- [Project Structure](#project-structure)
- [Contributing](#contributing)
- [License](#license)

## Introduction

Hierarchical Temporal Memory is a biologically inspired machine learning model that mimics the structure and function of the neocortex. It is capable of learning time-based patterns and making predictions. **HTM-Teacher** provides a simplified implementation of an HTM model from scratch, focusing on educational clarity rather than performance or scalability.

The project includes:

- A **Random Distributed Scalar Encoder (RDSE)** for converting scalar inputs into Sparse Distributed Representations.
- A **Spatial Pooler (SP)** that learns to recognize spatial patterns in the input data.
- A **Temporal Memory (TM)** that learns sequences of patterns over time.

## Features

- **Minimalistic Code**: The code is written to be as concise and readable as possible, making it accessible to beginners.
- **Visualization**: Uses `matplotlib` to visualize SDRs, input values, active columns, and prediction accuracy.
- **Animation**: Animates the entire HTM processing pipeline, showing how the model learns and predicts over time.
- **Educational Comments**: Thoroughly commented code explains the purpose and functionality of each component and step.
- **No External Dependencies**: Apart from common libraries (`numpy`, `matplotlib`), the code does not rely on any external HTM frameworks.

## Installation

1. **Clone the Repository**

   ```bash
   git clone https://github.com/yourusername/htm-teacher.git
   cd htm-teacher
   ```

2. **Create a Virtual Environment (Optional)**

   ```bash
   python -m venv venv
   source venv/bin/activate  # On Windows, use venv\Scripts\activate
   ```

3. **Install Dependencies**

   ```bash
   pip install -r requirements.txt
   ```

   The `requirements.txt` file should contain:

   ```
   numpy
   matplotlib
   ```

## Usage

### Running the Simulation

To run the HTM simulation and view the animation:

```bash
python htm_teacher.py
```

**Note:** Ensure that you have `ffmpeg` or `imagemagick` installed if you want to save the animation as a video or GIF file.

### Understanding the Output

The program will display an animated visualization with four subplots:

1. **Input Value Over Time**: Shows the input scalar values being fed into the model.
2. **Prediction Accuracy Over Time**: Displays how the model's prediction accuracy evolves.
3. **Encoded Input SDR**: Visualizes the Sparse Distributed Representation of the current input.
4. **Active Columns Over Time**: Illustrates which columns in the Spatial Pooler are active at each time step.

The animation is divided into training and testing phases, mimicking typical machine learning workflows.

## Dependencies

- **Python 3.6 or higher**
- **NumPy**
- **Matplotlib**

To install the dependencies, run:

```bash
pip install numpy matplotlib
```

## Project Structure

- **htm_teacher.py**: The main Python script containing the HTM implementation and animation code.
- **requirements.txt**: A list of required Python packages.
- **README.md**: Project description and usage instructions.
- **LICENSE**: The project's license.

## Contributing

Contributions are welcome! If you have ideas for improvements or new features, feel free to open an issue or submit a pull request.

1. Fork the project.
2. Create your feature branch (`git checkout -b feature/YourFeature`).
3. Commit your changes (`git commit -m 'Add your feature'`).
4. Push to the branch (`git push origin feature/YourFeature`).
5. Open a Pull Request.

## License

This project is licensed under the AGPL 3.0 License - see the [LICENSE](LICENSE) file for details.

---

**Disclaimer:** This project is intended for educational purposes to illustrate the basic workings of HTM models. It is not optimized for performance and may not represent the most efficient or scalable implementation of HTM.

**Acknowledgments:** This project was inspired by the desire to make complex machine learning concepts more accessible through minimalistic and well-commented code.

# Additional Information

## Understanding HTM Components

### Random Distributed Scalar Encoder (RDSE)

The RDSE converts scalar input values into high-dimensional, sparse binary vectors (SDRs). It ensures that similar input values produce SDRs with overlapping active bits, capturing the similarity in the input space.

### Spatial Pooler (SP)

The Spatial Pooler processes the SDRs from the encoder and produces a new set of SDRs representing the spatial patterns in the input data. It uses inhibition to maintain sparsity and learns to recognize frequently occurring patterns by adjusting synapse permanences.

### Temporal Memory (TM)

The Temporal Memory models sequences by connecting cells that become active in order. It learns temporal patterns and makes predictions by activating cells that anticipate future inputs based on learned sequences.

## Visualization and Animation

The animation provides a dynamic view of how the HTM model processes data over time, making it easier to understand the temporal aspects of learning and prediction.

- **Interactive Exploration**: Pause, rewind, or step through the animation to examine specific time steps.
- **Customization**: Modify parameters like the number of iterations, number of columns, or input sequences to observe different behaviors.

## Troubleshooting

- **Animation Not Displaying**: Ensure that you're running the script in an environment that supports GUI operations. If using SSH or a headless server, you may need to configure X11 forwarding or use a virtual display.
- **FFmpeg Not Found**: If you encounter issues saving the animation, make sure FFmpeg is installed and accessible. You can specify the path to FFmpeg in the script if necessary.

  ```python
  import matplotlib as mpl
  mpl.rcParams['animation.ffmpeg_path'] = r'/path/to/ffmpeg'
  ```

- **Performance Issues**: If the animation is slow or unresponsive, consider reducing `NUM_ITERATIONS` or the complexity of the model parameters.

## Extending the Project

- **Add More Encoders**: Implement additional encoders (e.g., categorical, multi-dimensional) to explore how different data types are processed.
- **Enhance Visualization**: Include more detailed plots or 3D visualizations to delve deeper into the model's internal states.
- **Integrate Real Data**: Use real-world datasets to test the model's ability to learn and predict complex patterns.

---

Thank you for your interest in **HTM-Teacher**! We hope this tool enhances your understanding of Hierarchical Temporal Memory models. If you have any questions or feedback, please don't hesitate to reach out.
