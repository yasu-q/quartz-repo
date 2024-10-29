### can use:
- arraylists
- strings
- math
- wrappers
nothing else, no hash maps

- accounts must have unique ids but names can be multiples

### account class:
- field for name associated w/ account
- field for account number
- field for balance
- list of transactions associated w/ account
### transactions
- only relevant information w/ transactions are day / month / year
- either overcomplicate it and make an arraylist containing a 'transaction class' which stores these 3 integers
it's going to be overcomplicate it solution because there can be multiple transactions on the same date so either we make a distinct id for each transaction or just store them in diff obejects which will by definition be distinct.

### transaction class:
- a int[3] w/ dates thats it lil bto
- transactions are created at deposit and at withdraw

## design
nboc manager accnts
accts manage transactions
ez pz

### Questions
- does larry care abt javadoc documentation
- are my method descriptions detailed enough
- is my formatting good
- is it ok if I make this method static
- do i need to comment getters??
- do i need to comment very obvious fields??
- why there no space between var=


practice safe code 