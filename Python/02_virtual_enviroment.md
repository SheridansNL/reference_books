## Virtual enviroment

Setting up a virtual enviroment:
```bash
$ pip install virtualenv
#or
$ sudo apt-get install python3-venv

# creating directory for venv
$ virtualenv "directoryname"
#or
$ mkdir "directoryname"
$ cd "directoryname"
/dir$ python3 -m venv "enviromentname" #creating virtual enviroment

# activating virtual enviroment
$ source "directoryname"/bin/activate
#deactivating virtual machine
("directoryname")$ deactivate
```

Conda:
```bash
# Conda works across multiple platforms and languages.
# Perfect in the data science space

$ conda create –n new_environment
$ conda activate new_environment
$ conda deactivate
```

---