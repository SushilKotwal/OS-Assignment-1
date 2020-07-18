
echo "Enter directory name :"
read dname
cd $dname

i=1
while[ $i = 1 ]
    do

	echo "1. Create File"
    echo "2. Create a new directory"
	echo "3. Search File"
	echo "4. Delete File"
	echo "5. Rename File"
	echo "6. view Dictionary"
    echo "7. Show contents of directory"
	echo "8. Go back to main directory and enter into another directory."
	echo "9. Enter into a sub directory"
	echo "10. exit"
	echo "Enter the choice"
	read choice

case $choice in
	1)
		echo "Enter File Name :"
		read fname
		if[-f $fname]
		then
			echo "File already exists"
		else
			touch $fname
			echo "File Succcessfully created"
		fi;;
    
     2)
	    echo "Enter new directory name : "
	    read newdirec
	    if [ -d $newdirec ]
       	then
	       echo "Directory already exists!"
	    else 
	       mkdir $newdirec
	       echo "Directory created successfully."
   	    fi;;
	3) 
		echo "Enter File name :"
		read sname
		if[-f $sname]
		then
			echo "File exists"
		else
			echo "No such File exists"
		fi;;
	4)
		echo "Enter the file name to delete :"
		read dename
		if[-f $dename]
		then
			rm $dename
			echo "File Successfully deleted"
		else
			echo "No such file exists"
		fi;;
	5) 
		echo "Enter the file name to be renamed :"
		read oldname
		echo "Enter the new name :"
		read newname
		mv $oldname $newname;;
	6) 
		echo "Files in Directory S" $dname
		ls;;
	7)
	    ls;;

	8) 
	    cd ..
	    echo "You have come back to main directory"
	    echo "Enter name of the directory - "
	    read dname
	    if [ -d $dname ]
       	then 
	       cd $dname
   	       echo "Switched to $dname"
	    else 
     	   echo "Directory doesn't exist."
	fi;;
    
	9) 
	    echo "Enter name of the directory - "
	    read dnam
	    if [ -d $dnam ]
       	then 
	       cd $dnam
   	       echo "Switched to $dnam"
	    else 
     	   echo "Directory doesn't exist."
	fi;;

	10) 
	    echo "YOU HAVE SUCCESSFULLY LEFT THE FM SYSTEM. "
	    i=0
	;;
    esac
    done
    
