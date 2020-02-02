
# Tensorflow Object-Detection API 사용하여 사물인식 학습하기

####  환경설정

1. python 3.6.5 버전으로 가상환경을 만들어준다.
  1. python 3.6.5 버전을 install
     - https://www.python.org/downloads/release/python-365/ 링크에서 macOS version을 install하고, 
install과정에서 (Add Python 3.6 to PATH) 체크박스를 선택함으로써 Python 3.6.5버젼을 환경변수로 세팅한다. (전에 Python3를 install 했더라면, python3를 downgrade 시켜줘야 한다...)
  1. virtualenv를 다운받는다.
     - $sudo pip install virtualenv
>   >  $virtualenv --python==python3 (가상환경디렉토리 이름)  명령어를 통해 가상환경을 만들어준다.
>   >  가상환경으로 작업하기 위해 가상환경이 저장되있는 디렉토리로 가서  $source (가상환경디렉토리 이름)/bin/actviate 명령을 실행한다.




학습을 시키기 위해 필요한 라이브러리는
1. pip install tensorflow==1.8
2. pip install Cython
3. pip install pillow
4. pip install lxml
5. pip install jupyter
6. pip install matplotlib
