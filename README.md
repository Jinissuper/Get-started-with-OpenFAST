# Get-started-with-OpenFAST

Prerequisites (macOS)
1. Install Homebrew
   Visit https://brew.sh/ or run in Terminal: /bin/bash -c "$(curl -fsSL https://raw.githubusercontent.com/Homebrew/install/HEAD/install.sh)"

2. Install system dependencies
   # Python 3.10+, git, wget
   brew install python git wget

   # Recommended Python packages
   pip install numpy pandas matplotlib ruamel.yaml fastparquet h5py

3. Obtain the OpenFAST executable
   # Install build tools
   brew install cmake gcc

   # By configuring a domestic mirror source, the speed of brew can be improved
   cd "$(brew --repo)" && git remote set-url origin https://mirrors.tuna.tsinghua.edu.cn/git/homebrew/brew.git

   if [ -d "$(brew --repo homebrew/core)" ]; then
     cd "$(brew --repo homebrew/core)" && git remote set-url origin https://mirrors.tuna.tsinghua.edu.cn/git/homebrew/homebrew-core.git
   fi

   if [ -d "$(brew --repo homebrew/cask)" ]; then
     cd "$(brew --repo homebrew/cask)" && git remote set-url origin https://mirrors.tuna.tsinghua.edu.cn/git/homebrew/homebrew-cask.git
   fi
   
   export HOMEBREW_API_DOMAIN="https://mirrors.tuna.tsinghua.edu.cn/homebrew-bottles/api"
   export HOMEBREW_BOTTLE_DOMAIN="https://mirrors.tuna.tsinghua.edu.cn/homebrew-bottles"
   export HOMEBREW_BREW_GIT_REMOTE="https://mirrors.tuna.tsinghua.edu.cn/git/homebrew/brew.git"
   export HOMEBREW_CORE_GIT_REMOTE="https://mirrors.tuna.tsinghua.edu.cn/git/homebrew/homebrew-core.git"

   source ~/.zshrc

   cd "$(brew --repo)" && git remote -v

   Then, use brew install cmake gcc

   brew update
   brew search openfast
   brew install openfast
   which openfast
   openfast -v
 
   # Clone and build OpenFAST
# For macOS using Homebrew, this installs all dependencies
brew install git cmake make openblas gcc

# Clone the repository from GitHub using git
git clone https://github.com/OpenFAST/OpenFAST.git

# Move into the OpenFAST directory
cd OpenFAST

# Create the build directory and move into it
mkdir build
cd build

# Execute CMake with the default options;
# this step creates the Makefiles
cmake ..

# Execute the Make-help command to list all available targets
make help

# Choose a particular target or give no target to compile everything
make hydrodyn_driver
# or
make openfast
# or
make

# Test the compiled binary, for example
./glue-codes/openfast/openfast -v
./modules/hydrodyn/hydrodyn_driver -v

# Move the binaries and other run-time files to the install location
make install

   
