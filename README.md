### To create the driver
```
make	
```

### Remove module if exist
```
sudo rmmod mastermind
```

### Major number, max guess number and secret number can be given as module parameters
```
sudo insmod mastermind.ko major_number=142 mmind_max_guesses=10 mmind_number=4283	
```

### To see mastermind in the list of loaded modules
```
lsmod
```

### Remove device node if exist
```
sudo rm /dev/mastermind
```

### Create device node
```
sudo mknod -m 666 /dev/mastermind c 142 0
```

### Write to device (example)
```
echo "1234" > /dev/mastermind
```

### Read from device
```
cat /dev/mastermind
```

### Compile test code
```
gcc -o game game.c
```

### Execute test code
```
./game
```


## When program is executed the process given below will be performed

<pre>
Enter secret:                               <b>--->type 4 digit secret number</b>				           
Staring new game secret= < secret number >  <b>--->Your secret number will be showing here</b>
Commands:                                   <b>--->Possible commands that user can select</b>
(New Game) new < secret >                   <b>--->To start new game, type "new" and your secret number</b> 
(Exit Game) end 0                           <b>--->To end game, type "end" and 0</b>
(Guess) gus < guess >                       <b>--->To do guess, type "gus" and your guess number</b>
</pre>
