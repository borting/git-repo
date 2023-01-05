
# Execution

指令的執行分三階段:
1. system path 中的 `repo` 指令
2. 執行 project (或上層 project) 中 `.repo/repo/main.py`
3. 執行 `.repo/repo/subcmds/xxx.py` sub-command

# Argument Parsing

Argument parsing 分四階段:
1. `repo` parse 出 `--repo-dir` 等資訊傳給 `.repo/repo/main.py`
2. `.repo/repo/main.py` 先 parse 出 `--repo-dir`
3. `.repo/repo/main.py` 再透過 `_Repo` object parse `--trace`, `--trace-python` 等 global config
4. 最後根據執行的 sub-command (`.repo/repo/subcmds/xxx.py`) parse 對應的參數

# Sub-Commands

在 `import subcmds` 時 `subcmds/__init_.py` 會將所有 `subcmds/CMDNAME.py` 中的 `CMDNAME` class import 放入 `all_commands` list.
每一個 subcmds 都繼承 Command class.
