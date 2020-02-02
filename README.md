
# Tensorflow Object-Detection API 사용하여 사물인식 학습하기

##  환경설정  
  
  
  
  
### 1. python 3.6.5 버전으로 가상환경을 만들어준다.  



1. python 3.6.5 버전을 설치한다.
    - https://www.python.org/downloads/release/python-365/ 링크에서 macOS version을 install하고, 
    install과정에서 (Add Python 3.6 to PATH) 체크박스를 선택함으로써 Python 3.6.5버젼을 환경변수로 세팅한다. (전에 Python3를 install 했더라면, python3를 downgrade 시켜줘야 한다...)

1. virtualenv를 다운받는다.
    - $sudo pip install virtualenv   
        
1. 가상환경을 만들어 준다.    
    - $virtualenv --python==python3 (가상환경디렉토리 이름)
        
1. 가상환경으로 작업하려면 가상환경디렉토리가 있는 디렉토리에서 아래의 명령어 실행
    - $source (가상환경디렉토리 이름)/bin/actviate
  
  
  
### 2. 가상환경에 tensorflow object detection api를 사용하기위한 라이브러리들을 설치 한다.

    - $pip install tensorflow==1.8
    - $pip install Cython
    - $pip install contextlib2
    - $pip install pillow
    - $pip install lxml
    - $pip install jupyter
    - $pip install matplotlib


### 3. Clone this [Repository](https://github.com/tensorflow/models)
    - $git clone https://github.com/tensorflow/models

### 4. Protobuf 설치 후 protobuf를 이용하여 models/research/object_detection/protos 디렉토리에 pb2.py 파일들 만들기
- $brew install protobuf
- models/research 디렉토리로 이동
- $protoc object_detection/protos/*.proto --python_out=.
- 위 명령어 실행시 protos 디렉토리에 이름이 '_pb2.py'라고 끝나는 파일들이 많이 생성되 있을 것이다. 

### 5. 환경변수 등록
- $export PYTHONPATH=$PYTHONPATH:/PATH-TO/models/research:/PATH-TO/models/research/slim
- 위의 명령으로 임시로 환경변수를 등록할 수 있다. (/PATH-TO 대신 models를 저장한 디렉토리 경로를 작성해 주면 된다.)
- 위의 방법으로 하면 터미널을 끄고 킬 때마다 저 명령어를 실행 해줘야 한다. 
- 터미널을 껏다가 켜도 계속 환경변수가 유지 되게 하고 싶으면
$open ~/.bash_profile 명령어를 통해 .bash_profile 을 열어 맨 밑줄에 PYTHONPATH=$PYTHONPATH:/PATH-TO/models/research:/PATH-TO/models/research/slim 을 추가 해주면 된다.

### 6. 환경설정이 제대로 되었는지 확인하기
- models/research 디렉토리로 이동한 뒤, 밑에 명령어를 실행하자
- $python object_detection/builders/model_builder_test.py
- 잘 동작하면 제대로 환경설정이 된 것이고, 위의 라이브러리를 잘 설치 했는데 에러가 난다면, tensorflow 버젼(tensorflow 1.8 버젼 추천)이나 터미널을 껏다 켰는데 환경변수 등록하는 것을 잊은 건 아닌지 한번 확인해보자.

  
  ***

##  이미지 라벨링하기 
1. 
