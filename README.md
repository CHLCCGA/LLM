# LLM



## Acknowledgment

The notes in this repository are based on  [LLM Quick Start - DjangoPeng](https://github.com/DjangoPeng/LLM-quickstart/blob/main/README-en.md).

thanks to the open-source spirit of sharing and collaboration, which has made this learning journey possible.

## Setting Up the Development Environment

- Python v3.10+
- Python Environment Management: [Miniconda](https://docs.conda.io/projects/miniconda/en/latest/)
- Interactive Python Development Environment: [Jupyter Lab](https://jupyterlab.readthedocs.io/en/stable/getting_started/installation.html)
- [Hugging Face Transformers](https://huggingface.co/docs/transformers/installation#install-with-conda)
- [Audio processing toolkit ffmpeg](https://phoenixnap.com/kb/install-ffmpeg-ubuntu)

### Dependencies

### Configuring Jupyter Lab for Background Startup

After installing the development environment as mentioned above, it's recommended to start Jupyter Lab as a background service. Here's how to configure it (using the root user as an example):

```shell
# Generate a Jupyter Lab configuration file
$ jupyter lab --generate-config
Writing default config to: /root/.jupyter/jupyter_lab_config.py
```

Open the configuration file and make the following changes:

```python
# Allowing Jupyter Lab to start as a non-root user (no need to modify if starting as root)
c.ServerApp.allow_root = True
c.ServerApp.ip = '*'
```

Use `nohup` to start Jupyter Lab in the background:

```shell
$ nohup jupyter lab --port=8000 --NotebookApp.token='replace_with_your_password' --notebook-dir=./ &
```

Jupyter Lab's output log will be saved in the `nohup.out` file (which is already filtered in the `.gitignore` file).