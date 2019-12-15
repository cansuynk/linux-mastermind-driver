<h4>###########To create the driver##############</h4>

make	
<h4>remove module if exist </h4>
sudo rmmod mastermind      

<h4>major number, max guess number and secret number can be given as module parameters</h4>
sudo insmod mastermind.ko major_number=142 mmind_max_guesses=10 mmind_number=4283	

<h4>to see mastermind in the list of loaded modules</h4>
lsmod 							

<h4>remove device node if exist</h4>
sudo rm /dev/mastermind							

<h4>create device node</h4>
sudo mknod -m 666 /dev/mastermind c 142 0

<h4>write to device (example)</h4>
echo "1234" > /dev/mastermind

<h4>read from device</h4>
cat /dev/mastermind	

<h4>compile test code</h4>
gcc -o game game.c

<h4>execute test code</h4>
./game		


<h4>######### When program is executed the process given below will be performed ##########</h4>

<h4>Enter secret: 				                     --->type 4 digit secret number</h4>				           
<h4>Staring new game secret= <secret number>	 --->Your secret number will be showing here</h4>
<h4>Commands:									                 --->Possible commands that user can select</h4>
<h4>(New Game) new <secret>						         --->To start new game, type "new" and your secret number</h4>
<h4>(Exit Game) end 0							             --->To end game, type "end" and 0</h4>
<h4>(Guess) gus <guess>							           --->To do guess, type "gus" and your guess number</h4>
