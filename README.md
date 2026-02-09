
[![Build and deploy](https://github.com/riparuk/riparuk.github.io/actions/workflows/hugo.yaml/badge.svg)](https://github.com/riparuk/riparuk.github.io/actions/workflows/hugo.yaml)


# Installation
Git clone this repository
```bash
git clone https://github.com/riparuk/riparuk.github.io.git
```

# Installation

1. Clone this repository
    ```bash
    git clone https://github.com/riparuk/riparuk.github.io.git
    cd riparuk.github.io
    ```

2. Initialize and update the theme submodule
    ```bash
    git submodule update --init --recursive
    ```

> **Note**: If the theme folder is empty or you face issues, try running `git submodule deinit -f themes/PaperMod` followed by the update command above.

3. Update PaperMod theme (only when needed)
    ```bash
    git submodule update --remote --merge
    ```

# Run
```bash
hugo server -D
```

# Create New Post

```bash
hugo new --kind post content/posts/<name>.md
```