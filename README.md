# Deep Learning Natural Language Processing Workspace

## 환경 재구성
- 아래 단계에 맞춰서 진행
- 또는 `setup_dl_nlp_env.bat` 파일을 저장 한 뒤 Anaconda/Miniforge Prompt 에서 해당 파일의 경로로 이동하여 setup_dl_nlp_env.bat 실행

```
:: 0. 기존 환경 비활성화
conda deactivate

:: 1. 기존 환경 삭제
conda remove -n dl_nlp_env --all -y

:: 2. 새 환경 생성
conda create -n dl_nlp_env python=3.12 -y

:: 3. 환경 활성화
conda activate dl_nlp_env

:: 4. pip / 설치 도구 업그레이드
python -m pip install --upgrade pip setuptools wheel

:: 5. Jupyter / 기본 데이터 처리 패키지 설치
pip install notebook jupyterlab ipykernel ipywidgets
pip install numpy pandas matplotlib seaborn wordcloud

:: 6. NLP 패키지 설치
pip install nltk spacy kss transformers

:: 7. 한국어 형태소 분석 패키지 설치
pip install JPype1 konlpy

:: 8. 딥러닝 패키지 설치
:: CPU 기준
pip install tensorflow
pip install torch torchvision torchaudio

:: 9. spaCy 영어 모델 설치
python -m spacy download en_core_web_sm

:: 10. NLTK 데이터 다운로드
python -c "import nltk; nltk.download('punkt'); nltk.download('punkt_tab'); nltk.download('stopwords'); nltk.download('wordnet'); nltk.download('omw-1.4'); nltk.download('vader_lexicon'); nltk.download('averaged_perceptron_tagger'); nltk.download('averaged_perceptron_tagger_eng')"

:: 11. Jupyter 커널 등록
python -m ipykernel install --user --name dl_nlp_env --display-name "dl_nlp_env"
```