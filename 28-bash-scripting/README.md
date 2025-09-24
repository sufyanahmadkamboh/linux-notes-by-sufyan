# Bash Scripting Basics

Create hello.sh:

bash
Copy code
#!/usr/bin/env bash
set -euo pipefail
name="${1:-world}"
echo "Hello, $name"
Run:

bash
Copy code
chmod +x hello.sh
./hello.sh Linux
