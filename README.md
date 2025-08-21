# Gensyn_AI
this is my personalized for best gensyn output 

# Use this in rented GPU where we are in Container and dont have sudo command access

# Step 1: System Update and Core Dependencies
First, update your package list and install the essential tools and libraries required for compiling software and managing your system.

# Update package lists and upgrade existing packages
```
apt update && apt upgrade -y
```
# Install essential build tools, utilities, and libraries
```
apt install screen curl iptables build-essential git wget lz4 jq make gcc nano automake autoconf tmux htop nvme-cli libgbm1 pkg-config libssl-dev libleveldb-dev tar clang bsdmainutils ncdu unzip -y
```

# Step 2: Install Python Environment
Next, install Python 3 and the necessary tools for managing Python packages (pip) and creating virtual environments (venv).

# Install Python 3, pip, venv, and development headers
```
apt install python3 python3-pip python3-venv python3-dev -y
```

# Step 3: Install Node.js and Yarn
The application requires Node.js and Yarn. These commands will add the Node.js repository, install it, and then install Yarn.


# Add the NodeSource repository for Node.js v22
```
curl -fsSL https://deb.nodesource.com/setup_22.x | bash -
```
# Install Node.js (which includes npm)
```
apt install -y nodejs
```
# Install Yarn using the official script
```
curl -o- -L https://yarnpkg.com/install.sh | bash
```
# IMPORTANT: Add Yarn to your PATH for the current session.
# You should also add this line to your ~/.bashrc file to make it permanent.
```
export PATH="$HOME/.yarn/bin:$HOME/.config/yarn/global/node_modules/.bin:$PATH"
```
```
source ~/.bashrc
```
# Verify installations (optional)
```
node -v
yarn -v
```

# Step 4: Clone the Gensyn rl-swarm Repository
With all the dependencies installed, you can now download the project code from GitHub.

# Clone the repository into a new folder named 'rl-swarm'
```
git clone https://github.com/gensyn-ai/rl-swarm/
```

# Step 5: Configure and Run the Node
Finally, navigate into the project directory, set up the Python environment, ensure the code is up-to-date, and run the main script. It's recommended to run this inside a tmux session so it continues running if you disconnect.

# Attach to an existing tmux session
```
tmux
```

# Navigate into the project directory
```
cd rl-swarm
```

# Create and activate a local Python virtual environment
```
python3 -m venv .venv
source .venv/bin/activate
```

# Ensure your local code is clean and up-to-date with the main branch
```
git switch main
git reset --hard
git clean -fd
git pull origin main
```

# Execute the run script to start the node
```
./run_rl_swarm.sh
```

# Additional If using vast or Quickpot use command to Get swarm or upload 
# if using CPU use simple smtp method to quick drag and upload
`TXT USE IN AI WITH INFORMATION`
```
scp -O -P xxxPORT "/mnt/c/Users/Admin/Desktop/Gensyn/XXX/swarm.pem" xxxSSH:/workspace/rl-swarm/
```
```
scp -O -P xxxPORT "/mnt/c/Users/Admin/Desktop/Gensyn/XXX/temp-data/userApiKey.json" xxxSSH:/workspace/rl-swarm/modal-login/temp-data/
```
```
scp -O -P xxxPORT "/mnt/c/Users/Admin/Desktop/Gensyn/XXX/temp-data/userData.json.json" xxxSSH:/workspace/rl-swarm/modal-login/temp-data/
```

You may also need this if require
```
chmod 600 /workspace/rl-swarm/swarm.pem
```



