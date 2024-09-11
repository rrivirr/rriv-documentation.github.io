# Quick Start

There are two kinds of roles available when using the RRIV platform.  
One is contributing as a developer, this means writing code and uploading this
code to the RRIV board to make new functionality.
The other is operating the board to develop new sensors or deploy them into the field. 
This role is called being an operator.

This quick start guide is divided into setup paths for either developer or operator roles.  
A developer probably wants to do both setups, while an operator only needs to set up for the 
operator role.

Choose the right setup path for your use case below and get started!

## Operator Setup

To get set up to operate and deploy the RRIV board, you will need to install the rrivctl command line
tool and set up your computer for USB communication with the RRIV board.   You will communicate
with the RRIV board using the rrivctl command line tool.

The instructions below are for linux.  If you are using MacOS or Windows some of the installation steps
will be different.

1. Download and install the rrivctl command line tool
   1. Navigate to https://github.com/rrivirr/rriv-ctl
   2. Clone this repository onto your computer using git
   3. Using the command line, navigate to the rriv-ctl folder
   4. Install nodejs dependencies on your computer
      1. sudo apt-get install nodejs
      2. sudo apt-get install npm
      3. sudo npm i typescript -g
   5. Follow the setup instructions in rriv-ctl/README.md
      1. npm install # installs the nodejs packages required by rriv-ctl
      2. npm run build # builds the rriv-ctl tool
      3. source ./create-alias.sh # makes the command rrivctl available on the command line
      4. You can now test this installation by typing `rrivctl` on the command line, you should see the help message.
3. Update your computer to allow USB communication with the rriv board
4. Connect to the board and load configuration, or log data


## Developer Setup
