# Contributors

Thank you to everyone who has contributed to **vqe-bench**! 🙏

## Maintainer

| Name | GitHub | Role |
|---|---|---|
| Nidhal Zitouni | [@ZitouniNidhal](https://github.com/ZitouniNidhal) | Creator, lead maintainer |

## Contributors

<!-- Add contributors below, in chronological order of first contribution.
     Example row:
     | Jane Doe | [@janedoe](https://github.com/janedoe) | VQE driver, tests |
-->

| Name | GitHub | Contributions |
|---|---|---|
| _Be the first contributor!_ | — | See [How to contribute](#how-to-contribute) below |

## How to contribute

We welcome contributions of all kinds — bug reports, feature requests, documentation, new benchmarks, and code.

### Getting started

1. **Fork** the repository on GitHub.
2. **Clone** your fork:

   ```bash
   git clone https://github.com/<your-username>/vqe-bench.git
   cd vqe-bench
   ```

3. **Create a branch** from `main`:

   ```bash
   git checkout -b feat/my-improvement
   ```

4. **Install** the package with dev and chemistry extras:

   ```bash
   pip install -e ".[dev,chemistry]"
   ```

5. **Run the checks** — all must pass before any pull request:

   ```bash
   ruff check src tests
   mypy src
   pytest
   ```

6. **Commit** using [Conventional Commits](https://www.conventionalcommits.org/):

   ```bash
   git commit -m "feat(diagnostics): add local-cost gradient variance test"
   ```

7. **Push** and open a **Pull Request** against `main`:

   ```bash
   git push origin feat/my-improvement
   ```

### Contribution guidelines

- Write **type-hinted** code with **Google-style docstrings**.
- Add **unit tests** for every new feature (place them in `tests/`, following the existing naming: `test_<module>.py`).
- Keep experiments **reproducible**: fixed seeds, no hard-coded absolute paths.
- One YAML config = one experiment; validate new config fields with pydantic.
- No placeholder code, no `TODO` stubs, no invented APIs — use only documented Qiskit / Qiskit Nature functions, and state explicitly if you are unsure about an API version.
- Follow the existing code style (`ruff` is enforced in CI).

### Adding a new benchmark

1. Implement the Hamiltonian / ansatz / diagnostic in the appropriate `src/vqe_bench/` submodule.
2. Add a YAML config in `configs/` and document it in `docs/config_reference.md`.
3. Add unit tests in `tests/` and, if relevant, a row in the README "Expected results" table.

### Reporting issues

Open an issue at https://github.com/ZitouniNidhal/vqe-bench/issues including:

- Your OS and Python version (`python --version`).
- Output of `pip list | grep -E "qiskit|vqe"` (Windows PowerShell: `pip list | Select-String -Pattern "qiskit|vqe"`).
- A **minimal YAML config** (or Python snippet) that reproduces the problem.
- The full error traceback, if any.

### Suggesting features

Open an issue with the `enhancement` label and describe:

- The benchmark question you want to answer (e.g. "compare k-UpCCGSD against UCCSD on LiH").
- The proposed config fields and their defaults.
- The expected output / metrics.

## Recognition

Contributions of any kind — code, documentation, bug reports, benchmark data, reviews — are recognised in this file and in release notes. This project follows the [all-contributors](https://allcontributors.org/) specification: ideas and documentation count as much as code.

## Code of Conduct

Be kind, be constructive, be respectful. By participating, you agree to abide by the
[Contributor Covenant, version 2.1](https://www.contributor-covenant.org/version/2/1/code_of_conduct/).
Instances of unacceptable behaviour may be reported to the maintainer via GitHub.

## License

By contributing to vqe-bench, you agree that your contributions will be licensed under the
[MIT License](./LICENSE).
