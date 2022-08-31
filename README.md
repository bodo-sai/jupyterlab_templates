<img src="https://github.com/jpmorganchase/jupyterlab_templates/raw/main/docs/logo.png" width=400></img>


## Install
```bash
pip install jupyterlab_templates
jupyter labextension install jupyterlab_templates
jupyter serverextension enable --py jupyterlab_templates
```

## Adding templates
install the server extension, and add the following to `jupyter_notebook_config.py`

```python3
c.JupyterLabTemplates.template_dirs = ['list', 'of', 'template', 'directories']
c.JupyterLabTemplates.include_default = True
c.JupyterLabTemplates.include_core_paths = True
```

## Templates for libraries
The extension will search *subdirectories* of each parent directory specified in `template_dirs` for templates.
**Note!** Templates in the parent directories will be ignored. You must put the templates in *subdirectories*, in order to keep everything organized.  

If `include_default = True` the `notebook_templates` directory under the [jupyter data folder](https://jupyter.readthedocs.io/en/latest/use/jupyter-directories.html) is one of the default parent directories. Thus, if you have tutorials or guides you'd like to install for users, simply copy them into your jupyter data folder inside the `notebook_templates` directory, e.g. `/usr/local/share/jupyter/notebook_templates/bqplot` for `bqplot`.


### Flags
- `template_dirs`: a list of absolute directory paths. All `.ipynb` files in any *subdirectories* of these paths will be listed as templates
- `include_default`: include the default Sample template (default True)
- `include_core_paths`: include jupyter core paths (see: jupyter --paths) (default True)


## Development

See [CONTRIBUTING.md](./CONTRIBUTING.md) for guidelines.


## License

This software is licensed under the Apache 2.0 license. See the
[LICENSE](LICENSE) and [AUTHORS](AUTHORS) files for details.
