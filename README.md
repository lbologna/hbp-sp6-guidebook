# hbp-sp6-guidebook

### Building HTML documentation

```bash
virtualenv venv \
    && . venv/bin/activate \
    && pip install -r requirements.txt --upgrade \
    && make html
```

In order to create a .docx file from the source code, the package docxsphinx has to be installed and the 'docxsphinx' extension enabled in the source/conf.py file
