# Get-started-with-OpenFAST

💻 Prerequisites (macOS)
# 1. Install Homebrew
   Visit https://brew.sh/ or run in Terminal: /bin/bash -c "$(curl -fsSL https://raw.githubusercontent.com/Homebrew/install/HEAD/install.sh)"

# 2. Install system dependencies
	brew install python git wget
	
	pip install numpy pandas matplotlib ruamel.yaml fastparquet h5py

# 3. Obtain the OpenFAST executable
	brew install cmake gcc

	🔥 Speed Up
  ⏰ cd "$(brew --repo)" && git remote set-url origin https://mirrors.tuna.tsinghua.edu.cn/git/homebrew/brew.git

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

  cd "$(brew --repo)" && git remote -v ⏰
	 
	brew update
	brew search openfast
	brew install openfast
	which openfast
	openfast -v
	 
	brew install git cmake make openblas gcc
	
	git clone https://github.com/OpenFAST/OpenFAST.git
	cd OpenFAST
	
	mkdir build
	cd build
	cmake ..
	make help
	make
	
	./glue-codes/openfast/openfast -v
	./modules/hydrodyn/hydrodyn_driver -v
	make install

   
