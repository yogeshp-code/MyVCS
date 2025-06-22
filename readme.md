---
title: "MyVCS"
description: "A version control system to understand the inner workings of Git."
tags: ["GIT", "VCS"]
image: "/heartbeat-dashboard.png"
---


# MyVCS - A Minimal Git-like Version Control System

## Overview

MyVCS is a minimal version control system implemented in Python to help understand the internal workings of Git. This project was created "the hard way" by implementing core Git concepts from scratch, without relying on existing Git libraries.

## Features

- Basic Git-like commands: `init`, `add`, `commit`, `log`, `diff`, `checkout`, `branch`, `tag`, `status`
- SHA-1 based object storage (blobs, trees, commits)
- Branching and tagging support
- Staging area (index)
- Working directory tracking
- Commit history visualization

## How It Works

MyVCS mimics Git's internal architecture with these key components:

1. **Object Database**:
   - Blobs: Store file contents
   - Trees: Represent directory structures
   - Commits: Snapshots with metadata

2. **References**:
   - Branches (under `refs/heads/`)
   - Tags (under `refs/tags/`)
   - HEAD pointer

3. **Index**:
   - Tracks staged changes before commit

## Installation

1. Clone this repository
2. Ensure you have Python 3 installed
3. Make the script executable:
   ```bash
   chmod +x myvcs.py
   ```

## Usage

Basic command structure:
```bash
./myvcs.py <command> [options]
```

### Available Commands

| Command    | Description                                      | Example Usage                     |
|------------|--------------------------------------------------|-----------------------------------|
| `init`     | Initialize a new repository                     | `./myvcs.py init`                |
| `add`      | Add files to staging area                       | `./myvcs.py add file1 file2`     |
| `commit`   | Commit staged changes                           | `./myvcs.py commit -m "msg"`     |
| `log`      | Show commit history                             | `./myvcs.py log`                 |
| `diff`     | Show changes between commits                    | `./myvcs.py diff sha1 sha2`      |
| `checkout` | Switch branches or restore files                | `./myvcs.py checkout branch`     |
| `branch`   | Create a new branch                             | `./myvcs.py branch new-branch`   |
| `tag`      | Create a new tag                                | `./myvcs.py tag v1.0`            |
| `status`   | Show working tree status                        | `./myvcs.py status`              |

## Implementation Details

### Core Concepts Implemented

1. **Object Storage**:
   - Files are stored as blobs with SHA-1 hashes
   - Directories are represented as tree objects
   - Commits point to tree objects and contain metadata

2. **References**:
   - Branches and tags are lightweight pointers to commits
   - HEAD tracks the current branch or commit

3. **Staging Area**:
   - Tracks changes before they're committed
   - Allows selective commits

### Limitations

This is a learning project with several limitations compared to real Git:

- No network operations (fetch/push/pull)
- Simplified merge conflict handling
- Basic error handling
- Limited performance optimizations

## Learning Resources

This project was inspired by:
- [Git Internals - Git Objects](https://git-scm.com/book/en/v2/Git-Internals-Git-Objects)
- [Building Git](https://shop.jcoglan.com/building-git/)
- [Write yourself a Git!](https://wyag.thb.lt/)

## License

This project is open source and available under the [MIT License](LICENSE).

## Contributing

While this is primarily a learning project, contributions that improve educational value are welcome. Please open issues or pull requests for:

- Bug fixes
- Documentation improvements
- Clearer implementation examples

## Acknowledgments

Special thanks to the Git community for creating such an elegant version control system that inspires projects like this.