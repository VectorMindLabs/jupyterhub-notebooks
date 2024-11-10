# JupyterHub Notebooks

Highly customized JupyterLab Notebook Docker images tailored for ML engineering at scale.

At **VectorMind Labs**, our team of dedicated machine learning engineers relies on **Kubeflow** to manage and 
orchestrate ML workflows. Kubeflow’s use of JupyterHub as a core component, while powerful, exposes some limitations 
in the default JupyterLab Docker images. As a result, the official Jupyter project images often lack the customizations 
and optimizations needed to meet our performance, productivity, and scalability requirements.

This repository provides a collection of **prebuilt, optimized JupyterLab Docker images** derived from the official 
Jupyter project to help you seamlessly swap out the default images for a more scalable and ML-friendly environment.

---

## Key Features

Our custom JupyterLab images are packed with essential tools and configurations, making them an ideal foundation for ML engineering teams.

### DataScience Notebook

```
 docker pull quay.io/vlpl/datascience-notebook:latest
```

Includes a suite of development tools to streamline workflows and enhance productivity:

- **JupyterLab Language Server** - Real-time code analysis and completion support
- **Python Language Server** - Advanced support for Python programming
- **R Language Server** - Smooth integration for R scripting
- **Jupytext** - Effortlessly convert between Jupyter notebooks and plain-text formats like `.py`, `.R`, or `.md`
- **TexLab** - LaTeX language server for seamless document preparation
- **PyRight** - Fast, static type checker for Python, essential for large codebases and efficient debugging

> **Note:** Enable autocompletion in the JupyterLab WebUI to activate suggestions from the language servers.

---

## License

This project is licensed under the MIT License.

&copy; 2024 VectorMind Labs. All rights reserved.
