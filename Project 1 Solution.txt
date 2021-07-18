#this program aims to either encrypt or decrypt

#1) asking the user to choose between encryption and decryption:

echo "If you want to encrypt click e, If you want to decrypt click d"
read  var

if [ $var = e ]

then

#a) printing on the screen “Please input the name of the plain text file”:

      echo "Please input the name of the plain text file"
      read file                             #reading the name of the plain file and store it in variable "file"

#b) removing none alphabet characters:

      sed 's/[^a-zA-Z ]//g' $file > temp    #the output of the text with non alphabet charcters removed goes to variable "temp"
      mv temp $file                         #now it is back to variable "file"

#c) convert all characters to lower case:

      sed 's/A/a/g' $file > temp            #the output of the text with "A" replaced with "a" goes to variable "temp"
      mv temp $file                         #then it is back to variable "file"
      sed 's/B/b/g' $file > temp            #and all that is done for the rest of the alphabets
      mv temp $file
      sed 's/C/c/g' $file > temp
      mv temp $file
      sed 's/D/d/g' $file > temp
      mv temp $file
      sed 's/E/e/g' $file > temp
      mv temp $file
      sed 's/F/f/g' $file > temp
      mv temp $file
      sed 's/G/g/g' $file > temp
      mv temp $file
      sed 's/H/h/g' $file > temp
      mv temp $file
      sed 's/I/i/g' $file > temp
      mv temp $file
      sed 's/J/j/g' $file > temp
      mv temp $file
      sed 's/K/k/g' $file > temp
      mv temp $file
      sed 's/L/l/g' $file > temp
      mv temp $file
      sed 's/M/m/g' $file > temp
      mv temp $file
      sed 's/N/n/g' $file > temp
      mv temp $file
      sed 's/O/o/g' $file > temp
      mv temp $file
      sed 's/P/p/g' $file > temp
      mv temp $file
      sed 's/Q/q/g' $file > temp
      mv temp $file
      sed 's/R/r/g' $file > temp
      mv temp $file
      sed 's/S/s/g' $file > temp
      mv temp $file
      sed 's/T/t/g' $file > temp
      mv temp $file
      sed 's/U/u/g' $file > temp
      mv temp $file
      sed 's/V/v/g' $file > temp
      mv temp $file
      sed 's/W/w/g' $file > temp
      mv temp $file
      sed 's/X/x/g' $file > temp
      mv temp $file
      sed 's/Y/y/g' $file > temp
      mv temp $file
      sed 's/Z/z/g' $file > temp
      mv temp $file

#d) printing the sum of word characters frequencies:

      #count the frequency for each letter
      #each letter has it's frequency stored in a variable

      freqa=$(cat $file | tr -cd "a" | wc -c)
      freqb=$(cat $file | tr -cd "b" | wc -c)
      freqc=$(cat $file | tr -cd "c" | wc -c)
      freqd=$(cat $file | tr -cd "d" | wc -c)
      freqe=$(cat $file | tr -cd "e" | wc -c)
      freqf=$(cat $file | tr -cd "f" | wc -c)
      freqg=$(cat $file | tr -cd "g" | wc -c)
      freqh=$(cat $file | tr -cd "h" | wc -c)
      freqi=$(cat $file | tr -cd "i" | wc -c)
      freqj=$(cat $file | tr -cd "j" | wc -c)
      freqk=$(cat $file | tr -cd "k" | wc -c)
      freql=$(cat $file | tr -cd "l" | wc -c)
      freqm=$(cat $file | tr -cd "m" | wc -c)
      freqn=$(cat $file | tr -cd "n" | wc -c)
      freqo=$(cat $file | tr -cd "o" | wc -c)
      freqp=$(cat $file | tr -cd "p" | wc -c)
      freqq=$(cat $file | tr -cd "q" | wc -c)
      freqr=$(cat $file | tr -cd "r" | wc -c)
      freqs=$(cat $file | tr -cd "s" | wc -c)
      freqt=$(cat $file | tr -cd "t" | wc -c)
      frequ=$(cat $file | tr -cd "u" | wc -c)
      freqv=$(cat $file | tr -cd "v" | wc -c)
      freqw=$(cat $file | tr -cd "w" | wc -c)
      freqx=$(cat $file | tr -cd "x" | wc -c)
      freqy=$(cat $file | tr -cd "y" | wc -c)
      freqz=$(cat $file | tr -cd "z" | wc -c)

      #count the sum of word character frequencies

      value=$(<"$file")
      array=($value)          #creating "array" variable that holds the content of the plain file
      Maxfreq=0               #defining a variable that will have the max frequency of the words

      for i in ${array[@]}    #looping through all the words
      do

        j=0                           #used for the second loop
        CharPosition=1                #variable that holds the position of a letter in a word
        Sumoffrequencies=0            #variable that holds the sum of frequencies of each word
        numofchars=$(echo $i | wc -c)         #variable that holds the number of chars in each word

        while [ "$j" -lt  "$numofchars" ]        #looping throught every character in a word
        do

           char=$(echo $i | cut -c$CharPosition-$CharPosition)       #variable that hold the present char

           case "$char"                                              #checking what alphabet is the char
             in
             a) Sumoffrequencies=$(($Sumoffrequencies + $freqa));;   #adding the frequency of the char to the sum of frequencies of the word based on what alphabet it is
             b) Sumoffrequencies=$(($Sumoffrequencies + $freqb));;
             c) Sumoffrequencies=$(($Sumoffrequencies + $freqc));;
             d) Sumoffrequencies=$(($Sumoffrequencies + $freqd));;
             e) Sumoffrequencies=$(($Sumoffrequencies + $freqe));;
             f) Sumoffrequencies=$(($Sumoffrequencies + $freqf));;
             g) Sumoffrequencies=$(($Sumoffrequencies + $freqg));;
             h) Sumoffrequencies=$(($Sumoffrequencies + $freqh));;
             i) Sumoffrequencies=$(($Sumoffrequencies + $freqi));;
             j) Sumoffrequencies=$(($Sumoffrequencies + $freqj));;
             k) Sumoffrequencies=$(($Sumoffrequencies + $freqk));;
             l) Sumoffrequencies=$(($Sumoffrequencies + $freql));;
             m) Sumoffrequencies=$(($Sumoffrequencies + $freqm));;
             n) Sumoffrequencies=$(($Sumoffrequencies + $freqn));;
             o) Sumoffrequencies=$(($Sumoffrequencies + $freqo));;
             p) Sumoffrequencies=$(($Sumoffrequencies + $freqp));;
             q) Sumoffrequencies=$(($Sumoffrequencies + $freqq));;
             r) Sumoffrequencies=$(($Sumoffrequencies + $freqr));;
             s) Sumoffrequencies=$(($Sumoffrequencies + $freqs));;
             t) Sumoffrequencies=$(($Sumoffrequencies + $freqt));;
             u) Sumoffrequencies=$(($Sumoffrequencies + $frequ));;
             v) Sumoffrequencies=$(($Sumoffrequencies + $freqv));;
             w) Sumoffrequencies=$(($Sumoffrequencies + $freqw));;
             x) Sumoffrequencies=$(($Sumoffrequencies + $freqx));;
             y) Sumoffrequencies=$(($Sumoffrequencies + $freqy));;
             z) Sumoffrequencies=$(($Sumoffrequencies + $freqz));;
           esac

           if [ "$Sumoffrequencies" -gt "$Maxfreq" ]           #comparing the sum of frequencies of the word is greater that the max sum of frequencies
           then
             Maxfreq=$Sumoffrequencies                         #if it is greater then it becomes the new max
           fi

           CharPosition=$(expr $CharPosition + 1)              #moving to the next position
           j=$(expr $j + 1)

        done

        printf "The sum of frequencies of %s = %d\n" $i $Sumoffrequencies          #printing the sum of frequencies of each word

      done

      printf "Max sum of frequencies = %d\n" $Maxfreq                      #printing the max sum of frequencies

#e) printing the shift value:

      shift=$(expr $Maxfreq % 26)
      printf "shift value = %d\n" $shift            #calculating and printing the shift value

#f) asking the user to enter the name of the cipher file

      dual=abcdefghijklmnopqrstuvwxyz
      rot=$shift
      echo "Please input the name of the cipher text file"
      read file1

#g)  writing the generated cipher text on the cipher file

      sed "y/${dual}/${dual:$rot}${dual::$rot}/" <<< $value >> $file1



elif [ $var = d ]

then

#a) printing on the screen “Please input the name of the cipher text file”:

     echo "Please input the name of the cipher text file"
     read file2                            #reading the name of the cipher file and store it in variable "file2"

#b) removing none alphabet characters:

     sed 's/[^a-zA-Z ]//g' $file2 > temp    #the output of the text with non alphabet charcters removed goes to variable "temp"
     mv temp $file2                         #now it is back to variable "file2"

#c) convert all characters to lower case:

     sed 's/A/a/g' $file2 > temp            #the output of the text with "A" replaced with "a" goes to variable "temp"
     mv temp $file2                         #then it is back to variable "file2"
     sed 's/B/b/g' $file2 > temp            #and all that is done for the rest of the alphabets
     mv temp $file2
     sed 's/C/c/g' $file2 > temp
     mv temp $file2
     sed 's/D/d/g' $file2 > temp
     mv temp $file2
     sed 's/E/e/g' $file2 > temp
     mv temp $file2
     sed 's/F/f/g' $file2 > temp
     mv temp $file2
     sed 's/G/g/g' $file2 > temp
     mv temp $file2
     sed 's/H/h/g' $file2 > temp
     mv temp $file2
     sed 's/I/i/g' $file2 > temp
     mv temp $file2
     sed 's/J/j/g' $file2 > temp
     mv temp $file2
     sed 's/K/k/g' $file2 > temp
     mv temp $file2
     sed 's/L/l/g' $file2 > temp
     mv temp $file2
     sed 's/M/m/g' $file2 > temp
     mv temp $file2
     sed 's/N/n/g' $file2 > temp
     mv temp $file2
     sed 's/O/o/g' $file2 > temp
     mv temp $file2
     sed 's/P/p/g' $file2 > temp
     mv temp $file2
     sed 's/Q/q/g' $file2 > temp
     mv temp $file2
     sed 's/R/r/g' $file2 > temp
     mv temp $file2
     sed 's/S/s/g' $file2 > temp
     mv temp $file2
     sed 's/T/t/g' $file2 > temp
     mv temp $file2
     sed 's/U/u/g' $file2 > temp
     mv temp $file2
     sed 's/V/v/g' $file2 > temp
     mv temp $file2
     sed 's/W/w/g' $file2 > temp
     mv temp $file2
     sed 's/X/x/g' $file2 > temp
     mv temp $file2
     sed 's/Y/y/g' $file2 > temp
     mv temp $file2
     sed 's/Z/z/g' $file2 > temp
     mv temp $file2

#d) printing the sum of word characters frequencies:

      #count the frequency for each letter
      #each letter has it's frequency stored in a variable

      freqa=$(cat $file2 | tr -cd "a" | wc -c)
      freqb=$(cat $file2 | tr -cd "b" | wc -c)
      freqc=$(cat $file2 | tr -cd "c" | wc -c)
      freqd=$(cat $file2 | tr -cd "d" | wc -c)
      freqe=$(cat $file2 | tr -cd "e" | wc -c)
      freqf=$(cat $file2 | tr -cd "f" | wc -c)
      freqg=$(cat $file2 | tr -cd "g" | wc -c)
      freqh=$(cat $file2 | tr -cd "h" | wc -c)
      freqi=$(cat $file2 | tr -cd "i" | wc -c)
      freqj=$(cat $file2 | tr -cd "j" | wc -c)
      freqk=$(cat $file2 | tr -cd "k" | wc -c)
      freql=$(cat $file2 | tr -cd "l" | wc -c)
      freqm=$(cat $file2 | tr -cd "m" | wc -c)
      freqn=$(cat $file2 | tr -cd "n" | wc -c)
      freqo=$(cat $file2 | tr -cd "o" | wc -c)
      freqp=$(cat $file2 | tr -cd "p" | wc -c)
      freqq=$(cat $file2 | tr -cd "q" | wc -c)
      freqr=$(cat $file2 | tr -cd "r" | wc -c)
      freqs=$(cat $file2 | tr -cd "s" | wc -c)
      freqt=$(cat $file2 | tr -cd "t" | wc -c)
      frequ=$(cat $file2 | tr -cd "u" | wc -c)
      freqv=$(cat $file2 | tr -cd "v" | wc -c)
      freqw=$(cat $file2 | tr -cd "w" | wc -c)
      freqx=$(cat $file2 | tr -cd "x" | wc -c)
      freqy=$(cat $file2 | tr -cd "y" | wc -c)
      freqz=$(cat $file2 | tr -cd "z" | wc -c)

      #count the sum of word character frequencies

      value=$(<"$file2")
      array=($value)          #creating "array" variable that holds the content of the cipher file
      Maxfreq=0               #defining a variable that will have the max frequency of the words

      for i in ${array[@]}    #looping through all the words
      do

        j=0                           #used for the second loop
        CharPosition=1                #variable that holds the position of a letter in a word
        Sumoffrequencies=0            #variable that holds the sum of frequencies of each word
        numofchars=$(echo $i | wc -c)         #variable that holds the number of chars in each word

        while [ "$j" -lt  "$numofchars" ]        #looping throught every character in a word
        do

           char=$(echo $i | cut -c$CharPosition-$CharPosition)       #variable that hold the present char

           case "$char"                                              #checking what alphabet is the char
             in
             a) Sumoffrequencies=$(($Sumoffrequencies + $freqa));;   #adding the frequency of the char to the sum of frequencies of the word based on what alphabet it is
             b) Sumoffrequencies=$(($Sumoffrequencies + $freqb));;
             c) Sumoffrequencies=$(($Sumoffrequencies + $freqc));;
             d) Sumoffrequencies=$(($Sumoffrequencies + $freqd));;
             e) Sumoffrequencies=$(($Sumoffrequencies + $freqe));;
             f) Sumoffrequencies=$(($Sumoffrequencies + $freqf));;
             g) Sumoffrequencies=$(($Sumoffrequencies + $freqg));;
             h) Sumoffrequencies=$(($Sumoffrequencies + $freqh));;
             i) Sumoffrequencies=$(($Sumoffrequencies + $freqi));;
             j) Sumoffrequencies=$(($Sumoffrequencies + $freqj));;
             k) Sumoffrequencies=$(($Sumoffrequencies + $freqk));;
             l) Sumoffrequencies=$(($Sumoffrequencies + $freql));;
             m) Sumoffrequencies=$(($Sumoffrequencies + $freqm));;
             n) Sumoffrequencies=$(($Sumoffrequencies + $freqn));;
             o) Sumoffrequencies=$(($Sumoffrequencies + $freqo));;
             p) Sumoffrequencies=$(($Sumoffrequencies + $freqp));;
             q) Sumoffrequencies=$(($Sumoffrequencies + $freqq));;
             r) Sumoffrequencies=$(($Sumoffrequencies + $freqr));;
             s) Sumoffrequencies=$(($Sumoffrequencies + $freqs));;
             t) Sumoffrequencies=$(($Sumoffrequencies + $freqt));;
             u) Sumoffrequencies=$(($Sumoffrequencies + $frequ));;
             v) Sumoffrequencies=$(($Sumoffrequencies + $freqv));;
             w) Sumoffrequencies=$(($Sumoffrequencies + $freqw));;
             x) Sumoffrequencies=$(($Sumoffrequencies + $freqx));;
             y) Sumoffrequencies=$(($Sumoffrequencies + $freqy));;
             z) Sumoffrequencies=$(($Sumoffrequencies + $freqz));;
           esac

           if [ "$Sumoffrequencies" -gt "$Maxfreq" ]           #comparing the sum of frequencies of the word is greater that the max sum of frequencies
           then
             Maxfreq=$Sumoffrequencies                         #if it is greater then it becomes the new max
           fi

           CharPosition=$(expr $CharPosition + 1)              #moving to the next position
           j=$(expr $j + 1)

        done

        printf "The sum of frequencies of %s = %d\n" $i $Sumoffrequencies          #printing the sum of frequencies of each word

      done

      printf "Max sum of frequencies = %d\n" $Maxfreq                      #printing the max sum of frequencies

#e) printing the shift value:

      shift=$(expr $Maxfreq % 26)
      printf "shift value = %d\n" $shift            #calculating and printing the shift value

#f) asking the user to enter the name of the plain file

      dual=abcdefghijklmnopqrstuvwxyz
      rot=$(expr $shift \* -1)
      echo "Please input the name of the plain text file"
      read file3

#g)  writing the generated plain text on the plain file

      sed "y/${dual}/${dual:$rot}${dual::$rot}/" <<< $value >> $file3




#printing error message to the user if he/she enters a wrong choice
else
      echo "ERROR"
fi

