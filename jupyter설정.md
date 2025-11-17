
# Jupyter 노트북 사용 순서

1. **가상환경 + 종속성 동기화**
   ```bash
   uv sync
   ```
   > `.venv`가 없으면 새로 만들고, `pyproject.toml`에 적힌 의존성을 모두 설치합니다.

2. **(필요 시) 터미널에서 가상환경 활성화**
   ```bash
   source .venv/bin/activate
   ```
   > `uv run <command>`를 쓰면 활성화 없이도 실행 가능합니다.

3. **ipykernel 등록**
   ```bash
   uv run python -m ipykernel install --user --name llm-study --display-name "Python (llm-study)"
   ```
   > 한 번만 실행하면, 주피터/VS Code에서 `Python (llm-study)` 커널을 선택할 수 있습니다.

4. **IDE/노트북에서 커널 선택**
   - VS Code/Cursor에서 커널 목록을 열어 `Python (llm-study)` 선택
   - 목록에 없으면 새로고침(↻)이나 창 리로드 후 다시 선택

5. **필요한 패키지 추가**
   ```bash
   uv add tokenizers sentencepiece ipykernel
   ```
   > 나중에 패키지를 더 설치하면 `pyproject.toml`과 `.venv`가 동시에 업데이트됩니다.

마지막으로 노트북 셀을 실행하며 테스트하면 됩니다.