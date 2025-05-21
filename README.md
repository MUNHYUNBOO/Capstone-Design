# Capstone-Design

# 🧠 백그라운드 실행 가이드 (Jupyter Notebook & Python Script)

이 프로젝트의 학습/실험 코드는 장시간 실행되므로, 터미널 종료 이후에도 계속 실행되도록 백그라운드 실행이 필요합니다.  
아래 방법을 통해 안정적으로 실행하고 로그를 확인할 수 있습니다.

---

## ✅ 1. Jupyter Notebook을 `.py`로 변환

```bash
jupyter nbconvert --to script 파일명.ipynb
```
## ✅ 2. 백그라운드 실행 (nohup)

```bash
nohup python test.py > log.txt 2>&1 &
```
## 3. 로그 확인 (실시간 출력 보기)
```bash
tail -f log.txt
```
##  Papermill로 .ipynb 백그라운드 실행 (노트북 기록 포함)
```bash
pip install papermill
nohup papermill test.ipynb output.ipynb > log.txt 2>&1 &
```

## 3. 로그 확인 (실시간 출력 보기)
```bash
ps aux | grep papermill  # 실행 중인 test 관련 프로세스 확인
kill -9 <PID>           # 원하는 프로세스 강제 종료
```
