#!/bin/bash
#To-Do List script

if [ -f ~/.config/q/to-do_list_file ]
then
    echo A To-Do List already existed
else
    mkdir ~/.config/q
    touch ~/.config/q/to-do_list_file
    echo New to-do list created
fi

add()
{
    item=$1
    if [ $# == 2 ]
    then
       basicDate=$2
       realDate=$(date -d $basicDate -I)
    else
       realDate=
    fi
    echo $realDate $item >> ~/.config/q/to-do_list_file
    sort ~/.config/q/to-do_list_file -o ~/.config/q/to-do_list_file
}

pop()
{
    if [ $# == 1 ]
    then
        line=$1
        delete=${line}d
    else
        delete=1d
    fi
    sed -i $delete ~/.config/q/to-do_list_file
}

list()
{
    cat ~/.config/q/to-do_list_file
}

if [ $1 == "add" ]
then
    add "$2" $3
    echo Added "$3 "$2"" to the to the to-do list
elif [ $1 == "pop" ]
then
    pop $2
    echo Removed line "$2" of the to-do-list
elif [ $1 == "list" ]
then
    list
fi
