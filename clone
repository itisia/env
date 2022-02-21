# color
# Foreground colors
  black=$(tput setaf 0)        #000000
  maroon=$(tput setaf 1)       #800000
  green=$(tput setaf 2)        #008000
  olive=$(tput setaf 3)        #808000
  navy=$(tput setaf 4)         #000080
  purple=$(tput setaf 5)       #800080
  teal=$(tput setaf 6)         #008080
  silver=$(tput setaf 7)       #c0c0c0
  gray=$(tput setaf 8)         #808080
  red=$(tput setaf 9)          #ff0000
  lime=$(tput setaf 10)        #00ff00
  yellow=$(tput setaf 11)      #ffff00
  blue=$(tput setaf 12)        #0000ff
  magenta=$(tput setaf 13)     #ff00ff
  aqua=$(tput setaf 14)        #00ffffo
  white=$(tput setaf 15)       #ffffff
  red=`tput setaf 1`
  green=`tput setaf 2`
  reset=`tput sgr0`

# echo "${red}red text ${green}green text${reset}"
function fileExist(){
	if [ -f  "$1" ]; then 
		echo 1
	else
		echo 0
	fi
}

function dirExist(){
	if [ -d "$1" ]; then
		echo 1
	else
		echo 0
	fi
}

function varHasVal(){
	if [ -z $1 ] ; then
		echo 0
	else
		echo 1
	fi
}




if [ $( fileExist "./token" ) == "1" ]; then
		# When token file exist
		token=$( cat "./token" )
		if [ $( varHasVal $token ) == "1" ]; then
			if [ $( varHasVal $1 ) == "1" ]; then
	# IF the repository name is provided
			echo ${reset}"Cloning $1 🚀🚀🚀"
			git clone https://$token@github.com/itisia/$1.git
				if [ $( dirExist "./$1" ) == "1" ]; then
					echo "Repository $1 Cloned Successful ✅"
				else
					echo ${red}"Error "${reset}": Something Went Wrong"${reset}
				fi
				exit;
			fi
			# Token exist
			echo -n ${reset}"Repository : "${aqua};
			read repository;echo -n ${reset};
			echo ${reset}"Cloning $repository 🚀🚀🚀"
			git clone https://$token@github.com/itisia/$repository.git
			if [ $( dirExist "./$repository" ) == "1" ]; then
				echo "Repository $repository Cloned Successful ✅"
			else
				echo ${red}"Error "${reset}": Something Went Wrong"${reset}
			fi
		else
			# token not exist
			echo ${red}"Error"${reset}" : Token Not Exist In ./token"
		fi
	else
		# When Token File not exist
		echo ${red}"Error"${reset}" : ./token Not Exist"
	fi
