# Run the local check

You’ll need Git and Python 3.12 on macOS or Linux. The check runs on CPU and requires no model credentials.

For a new checkout, clone the project along with the pinned Beyond Owls fork.

```sh
git clone --recurse-submodules https://github.com/wongm6216/subliminal-objectives.git
cd subliminal-objectives
```

If you already cloned the project, open its root directory and run `git submodule update --init --recursive` to initialize the pinned fork.

Create the Python environment and run the check from the project root.

```sh
python3.12 -m venv .venv
.venv/bin/python -m pip install -r third_party/beyond_owls/experiments/chess_hacking/local/requirements.txt
.venv/bin/python third_party/beyond_owls/experiments/chess_hacking/local/smoke.py
```

Expected final line

```text
PASS: 8 prompts, 4 scripted responses rejected, 3 train, 1 holdout
```

The check verifies the released steering vector’s shape and norm, generates eight prompts with a fixed seed, and passes hand-written responses through the reference filter. The training and holdout counts describe rows written to files. To inspect the rows and rejection reasons, add `--keep` to the last command and open the output directory it prints.

The submodule preserves the authors’ code and license alongside the team’s smoke test. [Pinned fork](https://github.com/wongm6216/beyond_owls/tree/bbc9fcfdd711bf31e2e8d8952612a2d1a00b790e) · [License](https://github.com/wongm6216/beyond_owls/blob/bbc9fcfdd711bf31e2e8d8952612a2d1a00b790e/LICENSE)
