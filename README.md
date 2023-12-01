# Yaml_Web_Editor
A tool for editing YAML files, with a web interface

## Table of Contents
- [Overview](#overview)
- [Usage](#usage)
  * [1. TODO with the previous project](#todo_previous_prj)
  * [2. Test my project](#todo_my_prj)

## Overview
This project is based on a previous project. It is an upgraded version that runs on the Python3 environment.
- Previous project: https://github.com/gsilos/YamlWebEditor
- In terms of previous projects, the author used to build the app in Python2, which is now obsolete. As a result, I have revised the necessary formats to ensure that the program runs well on Python3. Furthermore, the author utilized Docker to containerize the program, however there were still some errors when it launched because Python2 now is no longer supported. So, based on the author's prior file, I rewrite the Dockerfile, which is located in the directory: Dockerfile_for_Python2.7_original_project

## Usage
#### 1. TODO with the previous project
If you want to test the previous project, I'll give you a step-by-step instruction: 
- First, clone the previous project and my project, by:
    * git clone https://github.com/gsilos/YamlWebEditor
    * git clone https://github.com/loihoang1411/Yaml_Web_Editor
- Second, replace Dockerfile in the previous project by Dockerfile_for_Python2.7 in my project, which is located in the directory: Dockerfile_for_Python2.7_original_project
- Third, run the command:
  ```
  docker build -f Dockerfile_for_Python2.7 -t ywe .
  docker run -i -p 8421:8421 -t ywe
  ```
- Last but not least, open your browser: http://your_ip_address:8421
#### 2. Test my project
- All operations were performed on Ubuntu 22.04:
  ```
  sudo apt install python3-pip -y
  pip install flask netaddr paramiko
  git clone https://github.com/loihoang1411/Yaml_Web_Editor
  cd Yaml_Web_Editor/
  python3 web.py
  ```
- You can create a custom YAML file
  ```
  cd Yaml_Web_Editor/
  cd basket/
  vi demo.yml
  
  # Sample YAML File
  person:
    name: John Doe
    age: 30
    occupation: Developer
  address:
    city: Anytown
    street: 123 Main Street
    zip_code: "12345"
  ```

- Open your browser: http://your_ip_address:8421
  ![image](https://github.com/loihoang1411/Yaml_Web_Editor/assets/126635820/e6b291cc-dac6-4959-8229-037dc591d005)
- Now you can edit the file we just created by entering the file name in the box: ("demo" for example)
  * Enter "Retrieve YML":
  ![image](https://github.com/loihoang1411/Yaml_Web_Editor/assets/126635820/d85969e0-113d-4589-abad-16df64691647)
  * Edit the information:
    * city: Anytown -> NewYork
    * street: 123 Main Street -> 666 Global Street
    * zip_code: 12345 -> 88888
  ![image](https://github.com/loihoang1411/Yaml_Web_Editor/assets/126635820/b5ff5cb6-b27a-45f5-9f1f-09453ba0269d)
  * Enter "Save". And the file was saved successfully:
  ![image](https://github.com/loihoang1411/Yaml_Web_Editor/assets/126635820/d93a86fc-9123-4fdd-8331-fe5aaee146d3)
  * You can check "demo" file:
  ```
  root@abcxyz:~/Yaml_Web_Editor/basket# cat demo
  address:
    city: NewYork
    street: 666 Global Street
    zip_code: '88888'
  person:
    age: 30
    name: John Doe
    occupation: Developer
  ```

Done !!!

