# hello-world this is my coding that i learnt so far from the R and other courses
starting to use github for the first time
here i could copy paste and keep
help()
help(package = “ggplot2”)

browseVignettes().   #PROVIDES WITH REQUIRED CODE FORMAT FOR SPECIFIC PACKAGE (extended help files) how to use functions 
browseVignettes(“ggplot2”)

Go to history and revert the changes you made through version control. 

Github-a repository
Similar to dropbox, editing, file changes are kept,  anybody can see files or can be kept pvt,  commit is snapshot of your files to keep track of changes. push is to update and to make changes to the code. pushing is to send changes. pulling is to update the updated version of codes you had. then you make changes and push it so others can pull it. conflict is when so many people have made changes to the same file. cloning is when you make a copy. fork is when you use someone’s copy which is being edited? making purposeful commit is important. make one change per commit. add notes related to commit so people know what changes you made. push and pull very often. frequently check you are up to date. also don’t hold your files. push them. On GitHub, saved changes are called commits.

Anything that you need to apply, you can find using str()
Example: how to apply str?
>str(str)
it gives you: function (object, ...)
or 
> str(lm)
function (formula, data, subset, weights, na.action, 
    method = "qr", model = TRUE, x = FALSE, 
    y = FALSE, qr = TRUE, singular.ok = TRUE, 
    contrasts = NULL, offset, ...)  
or
> str(rnorm)
function (n, mean = 0, sd = 1)  

Install packages on R
functions>packages>library>repository (github, Bioconductor, CRAN)

install.packages(”ggplot2”)
install.packages(c(“ggplot2”, “devtools”, “lme4”). 
May use R interface to see which one you need to download
old.packages()
update.packages()
or simply tools> packages> load or un load from here and as many as you want 
detach()
detach(“package:ggplot2”, unload=TRUE)

sometimes you need to know which version of R you are running for a package to run 

version
sessionInfo()

Bioconductor uses its own way to download a package 
source(https://bioconductor.org/biocilite.R)
biociLite()
biociLite(“GenomicFeatures”)

Github
First find the package on website and author name 
install.packages(“devtools”)
library(devtools)
install_github(“author/package”)

library function is to load the package which you always have to do before you start any related work
you don’t need to install something again and again 

R Projects is built-In R which keeps all your files together
Project makes a folder designated for all the files that are related to that project to organize





Basic Building Blocks
$ sign is to retrieve a specific collection which was inserted previously in data.frame. 
== equals to
<= less than and equals
>= greater and equals
!= not equals to
!<= opposite of less than and equals
!>= opposite of greater and equals
Workspace and Files
Getwd()     		  #to see which directory, you are in 
dir().            		 # to see files in your directory
list.files().  	  	# to see files in your directory
?list.files()  		 # provides you help to see files in your directory
args()                     	 #to see what arguments are there in a specific function eg: args(list.files)
old.dir<- getwd()           #Assign value of current working directory to a variable called "old.dir"
dir.create(“testdir”)     #Use dir.create() to create a directory in the current working directory called "testdir"
set(“testdir”)		 #set testdir as your new current directory, don’t forget inverted commas
file.create(“mytestR”)  #Create a file in your working directory called "mytest.R" using the file.create() function
file.exists(“mytest.R”)   #To see if "mytest.R" exists in the working directory using the file.exists() function
file.info(“mytest.R”)     #Access information about the file "mytest.R" by using file.info()
file.rename("mytest.R","mytest2.R")  #Change the name of the file "mytest.R" to "mytest2.R" by using file.rename()
file.remove("mytest2.R")      #delete the file you created created
file.copy("mytest2.R", "mytest3.R")  # Make a copy of "mytest2.R" called "mytest3.R" using file.copy()
file.path(“mytest3.R”).                          #Provide the relative path to the file "mytest3.R" by using file.path()
file.path("folder1", "folder2").       #Pass 'folder1' and 'folder2' as arguments to file.path to make a platform-independent pathname
?dir.create.                      #Take a look at the documentation for dir.create by entering ?dir.create
File path 		Eg: Mutations<- read.table("~/Downloads/mutation_file.vcf", header=T)
(In order to create nested directories, 'recursive' must be set to TRUE)
dir.create(file.path(“testdir2”, “testdier3”), recursive=True)  # Create a directory in the current working directory called "testdir2" and a subdirectory for it called "testdir3", all in one command by using dir.create() and file.path()
setwd(old.dir)                 # Go back to your original working directory using setwd()
remove(testdir)              #now delete the 'testdir' directory
plot(cars, xlim=c(20,2)
boxplot(mpg$hwy, main="Highway mpg vs drv", col="yellow", ylab="speed", xlab="distance", ylim=c(0,50))
Sequences of Numbers
1:20                   # to get range of number from 1 to 20
pi:10		#pi is already set so it will give you a range from pi to 10
15:1 		#gives a backward counting-based increment. Also, in the case of an operator like the colon used above, you must enclose the symbol in backticks like this: ?`:`
?`:` 		# Pull up the documentation for `:` now
seq(1,20)	# The most basic use of seq() does exactly the same thing as the `:` operator however use comma in it with numbers. 
seq(from=0, to=10, by=0.5) # vector of numbers ranging from 0 to 10, incremented by 0.5
my_seq<- seq(5,10, length=30) # store the result in a new variable called my_seq, like this: my_seq <- seq(5, 10, length=30) 
length(my_seq)   #determine length of my_seq
1:length(my_seq) #we want a new vector (1, 2, 3, ...) that is the same length as my_seq where you don’t know the length of my_seq (pretend)
seq(along.with=my_seq)   #Another option for above command is to use seq(along.with = my_seq)
seq_along(my_seq)   #Also, R has a separate built-in function for this purpose called seq_along()
rep(0, times=40)   #rep means replicate 0 as in 40 times so that we don’t have to press 0 for 40 times
rep(c(0,1,2), times=10) # If instead we want our vector to contain 10 repetitions of the vector (0, 1, 2), we can do rep(c(0,1, 2), times = 10)
rep(c(0,1,2), each=10)   # we want our vector to contain 10 zeros, then 10 ones, then 10 twos. We can do this with the `each` argument.

Vectors (Atomic vectors and lists) 
numeric vectors, which are one type of atomic vector. Other types of atomic vectors include logical, character, integer, and complex
num_vect<- c(0.5,55,-10,6) # create a numeric vector num_vect that contains the values 0.5, 55, -10, and 6
tf<- num_vect<1 	          #create a variable called tf that gets the result of num_vect < 1
tf 			           #simply writing this will print off the values of tf. The statement num_vect < 1 is a condition and tf tells us whether each corresponding element of our numeric vector num_vect satisfies this condition.
num_vect >= 6 # we are asking whether each individual element of num_vect is greater than OR equal to 6
The `<` and `>=` symbols in these examples are called 'logical operators' Other logical operators include `>`, `<=`, `==` for exact equality, and `!=` for inequality.
(3 > 5) & (4 == 4) #this is false
If we have two logical expressions, A and B, we can ask whether at least one is TRUE with A | B (logical 'or' a.k.a. 'union') or whether they are both TRUE with A & B (logical 'and' a.k.a. 'intersection'). Lastly, !A is the negation of A and is TRUE when A is FALSE and vice versa.
(TRUE == TRUE) | (TRUE == FALSE) #this is true because one of this is true and both of them are separated by a line. 
The `|` in the middle states that AT LEAST ONE of the pieces is TRUE. Your job is to figure out if that is an accurate statement. If so, the entire condition is TRUE. If not, it's FALSE.
((111 >= 111) | !(TRUE)) & ((4 + 1) == 5) # this is true 

Character vectors are also very common in R. Double quotes are used to distinguish character objects, as in the following example.
my_char<- c("My", "name", "is") # Create a character vector that contains the following words: "My", "name", "is". Remember to enclose each word in its own set of double quotes, so that R knows they are character strings.
paste(my_char, collapse=" ")               # Use paste(my_char, collapse = " ") to collapse the words in the vector so they almost form a sentence. There should be a single space between the double quotes in the `collapse` argument so that there are single spaces separating the words. 
my_name<- c(my_char, "yasha")        # Tack your name on to the end of the my_char vector using the c() function
my_name 				#prints the contents in it
paste(my_name, collapse = " ")          #makes a complete sentence with spaces between words to join the elements of multiple character vectors. 
paste("Hello", "world!", sep = " ") 	# join two character vectors that are each of length 1
paste(1:3, c("X", "Y", "Z"), sep="")      # Use paste(1:3, c("X", "Y", "Z"), sep = "") to see what happens when we join two vectors of equal length using paste(). make sure to keep the sep outside inner bracket of concatenation.
paste(LETTERS, 1:4, sep = "-")              #Vector recycling! paste(LETTERS, 1:4, sep = "-"), where LETTERS is a predefined variable in R containing a character vector of all 26 letters in the English alphabet. Note that LETTERS is defined by R as alphabets from A to Z. R recycles number 1 to 4 each time until Z.

Missing Values (defined by NA in R)
x<- c(44, NA, 5, NA)    		#create a vector c(44, NA, 5, NA) and assign it to a variable x
x*3     				#multiplying x with 3
y<- rnorm(1000)		#create a vector containing 1000 draws from a standard normal distribution with y <- rnorm(1000).
z<- rep(NA, 1000)		# create a vector containing 1000 NAs with z <- rep(NA, 1000)
my_data<- sample(c(y,z), 100) #select 100 elements at random from these 2000 values (combining y and z) such that we don't know how many NAs we'll wind up with or what positions they'll occupy in our final vector -- my_data <- sample(c(y, z), 100).
where are NAs located in data? 
my_na<- is.na(my_data)	#Call is.na() on my_data and assign the result to my_na
my_na				#print my_na. (true will be NA and false will not be an NA) here in background, R has assigned all Ts as 1 and all Fs as 0
`==` operator as a method of testing for equality between two objects.
my_data == NA. 		#Does the expression my_data == NA yields the same results as is.na(). Ans: no
sum(my_na)			# Call the sum() function on my_na to count the total number of TRUEs in my_na
my_data			# Print my_data to the console.
A second type of missing value -- NaN, which stands for 'not a number'. To generate NaN, try dividing (using a forward slash) 0 by 0 now
0/0				#zero divided by 0 will give you NaN rather NA because NaN means: not a number

Subsetting vectors (extract elements from a vector based on some conditions that we specify)
The way you tell R that you want to select some particular elements (i.e. a 'subset') from a vector is by placing an 'index vector' in square brackets immediately following the name of the vector.
x				#if x is a set of your data that comprises of NAs and numbers 
x[1:10]				#to print first ten elements of x; here you are selecting the subset of a vector x
x[is.na(x)] 			#will give you all the NAs
Recall that `!` gives us the negation of a logical expression, so !is.na(x) can be read as 'is not NA'. Therefore, if we want to create a vector called y that contains all of the non-NA values from x, we can use y <- x[!is.na(x)]
y<- x[!is.na(x)]			#all non-NA values 
y				#print y (congrats you isolated the non NA values from NA values) 
y[y>0]				#to view only positive elements of y (you wouldn’t be able to get this answer with x[x>0] because it also had NAs
x[!is.na(x)& x>0]		#Combine knowledge of logical operators with new knowledge of subsetting
'zero-based indexing', which means that the first element of a vector is considered element 0. R uses 'one-based indexing', which (you guessed it!) means the first element of a vector is considered element 1.
x[c(3,5,7)]			#subset the 3rd, 5th, and 7th elements of x
x[0]				# find zeroth element of x
x[3000]			# find 3000th element of x
x[c(-2, -10)] 			# the command x[c(-2, -10)] gives us all elements of x EXCEPT for the 2nd and 10 elements
x[-c(2,10)]			#Another way to get same elements of x EXCEPT for the 2nd and 10 elements
vect<- c(foo=11, bar=2, norf=NA) #Create a numeric vector with three named elements
vect 				#print vect
names(vect)			#We can also get the names of vect by passing vect as an argument to the names() function
vect2<- c(11,2,NA) 		#create an unnamed vector vect2 with c(11, 2, NA)
names(vect2)<- c("foo", "bar", "norf") #dd the `names` attribute to vect2 after the fact 
identical(vect, vect2)		#let's check that vect and vect2 are the same by passing them as arguments to the identical() function.
vect["bar"]			#element named "bar" (i.e. the second element of vect)
vect[c("foo", "bar")]		#specify a vector of names with vect[c("foo", "bar")]

Matrices and Dataframes
matrices are rectangular data types i.e. tabular form data with rows and columns. matrices can only contain a single class of data, while data frames can consist of many different classes of data. 
my_vector<- 1:20		#create a vector that has number 1 to 20
my_vector			#print 
dim(my_vector)		#dimensions of vector
length(my_vector)		#length of vector
dim(my_vector)<-c(4,5)	#give dimensions to your already existing vector
dim(my_vector)		#print
attributes(my_vector)		#to check or print the dimensions you created using dim
my_vector			#print it and you will be surprised to see vector changed to matrix after we gave such dimensions 
class(my_vector)		#use class to see or print matrix
my_matrix<- my_vector 	#change the name from vector to matrix
?matrix			#pull up all details of matrix
my_matrix2<-matrix(1:20, nrow = 4, ncol = 5) #Call the matrix() function with three arguments -- 1:20, the number of rows, and the number of columns. Be sure to specify arguments by their proper names and store the result in my_matrix2 (not in my_matrix).
identical(my_matrix, my_matrix2)  #to see if both the matrices are identical or not (answer: they are)
patients<-c("Bill", "Gina", "Kelly", "Sean")  #creating a character vector containing the names to be added to the already available matrix data
cbind(patients, my_matrix) 	#cbind is used to combine the two vectors either one of the vector contains numbers or characters
my_data<-data.frame(patients,my_matrix)	# combining names of our patients in the table without destroying the integrity of our numeric data 
data.frame() function allowed us to store our character vector of names right alongside our matrix of numbers
my_data			#print the data
class(my_data)		#confirm this by calling the class() function on our newly created data frame
cnames<- c("patient", "age", "weight", "bp", "rating", "test") #assigning names to the columns of our data frame so that we know what type of measurement each column represents
colnames(my_data) <- cnames #use the colnames() function to set the `colnames` attribute for our data frame
my_data			#print my_data

Logic
There are two logical values in R, also called boolean values. They are TRUE and FALSE. In R you can construct logical expressions which will evaluate to either TRUE or FALSE.
TRUE == TRUE		#is true equal to true? (Ans: true)
(FALSE==TRUE)==FALSE # is this expression false? Ans: true/yes it is false
The equality operator can also be used to compare numbers. Use `==` to see if 6 is equal to 7.
6==7 			#is 6 equal to 7? Ans: false
6<7			#is 6 less than 7? Ans: true
10<=10		#is 10 less than or equal to 10? Ans: true yes
9 >= 10			#9 is greater or equal to 10? Ans: false/no
-6 > -7			#true b/c -6 is greater than -7
The next operator we will discuss is the 'not equals' operator represented by `!=`. Not equals tests whether two values are unequal, so TRUE != FALSE evaluates to TRUE. Like the equality operator, `!=` can also be used with numbers. Try writing an expression to see if 5 is not equal to 7.
!=			# this is the sign for not equals
5!=7			#5 is not equal to 7? Ans: true
In order to negate boolean expressions you can use the NOT operator. An exclamation point `!` will cause !TRUE (say: not true) to evaluate to FALSE and !FALSE (say: not false) to evaluate to TRUE. Try using the NOT operator and the equals operator to find the opposite of whether 5 is equal to 7.
!5==7			#gives you opposite results of what you would expect without ! here exclamation mark is NOT Boolean
(TRUE != FALSE) == !(6 == 7)	#gives you answer TRUE
how the AND operator works. There are two AND operators in R, `&` and `&&`. Both operators work similarly, if the right and left operands of AND are both TRUE the entire expression is TRUE, otherwise it is FALSE. For example, TRUE & TRUE evaluates to TRUE. Try typing FALSE & FALSE to how it is evaluated.
FALSE & FALSE		#gives false
TRUE & c(TRUE, FALSE, FALSE)	#to see how & operator works with concatenate
TRUE && c(TRUE, FALSE, FALSE)	#with double && the left operand is only evaluated with the first member of the right operand (vector). remaining elements aren’t evaluated at all in this expression. 
The OR operator follows a similar set of rules. The `|` version of OR evaluates OR across an entire vector, while the `||` version of OR only evaluates the first member of a vector. Even if one of the either sides is true, overall expression will be true. If both are. false then only it will be false. 
TRUE | c(TRUE,FALSE,FALSE)	#gives three trues
TRUE || c(TRUE,FALSE,FALSE)	#gives one true only
5 > 8 || 6 != 8 && 4 > 3.9		#gives true because one of it is true for sure
TRUE && FALSE || 9 >= 4 && 3 < 6	#gives true
FALSE && 6 >= 6 || 7 >= 8 || 50 <= 49.5 #gives false
The function isTRUE() takes one argument. If that argument evaluates to TRUE, the function will return TRUE. Otherwise, the function will return FALSE. Try using this function by typing: isTRUE(6 > 4)
isTRUE(6>4)				#gives true
!isTRUE(4 < 3)				#is false actually
identical("twins", "twins")		#true
identical(5 > 4, 3 < 3.1)		#true
xor(5==6, !FALSE)			#gives true You should also be aware of the xor() function, which takes two arguments. The xor() function stands for exclusive OR. If one argument evaluates to TRUE and one argument evaluates to FALSE, then this function will return TRUE, otherwise it will return FALSE.
xor(4 >= 9, 8 != 8.0)			#false
ints<- sample(10)			#create integers vector 
ints					#print ints (will show you number 1 to 10)
ints>5					#If we type ints > 5, we will get a logical vector corresponding to whether each element of ints is greater than 5
which(ints>7)				#to see which of the elements in ints is greater than 7
which(ints <= 2)			#which ints are less than or greater to 2
any(ints<0)				#any elements of ints less than zero
all(ints>0)				#to see if all of the elements of ints are greater than zero
…					#it is called ellipses and it is for 
Functions

mydata<- rnorm(100)
sd(mydata)
sd(x=mydata)
sd(x=mydata, na.rm=FALSE)
sd(na.rm=FALSE, x=mydata)
sd(na.rm=FALSE, mydata)
all these above represent the same answer. 

f<- function(a, b=1, c=2, d=NULL) {			#here b, c, d have default values and NULL means there’s nothing there. 

}

f<- function(a,b) {					#f function doesn’t use b value because there isn’t anything for b
	a^2
}
f(2) 		#calling f
##[1] 4		#answer

f<- function(a,b) {
print(a)
print(b)
}
f(45)

this gives error because you need to give something for b as well. 

“…” arguments
these three dots are used to extend the function so that you don’t have to copy everything. Arguments need not to be written again. 
myplot<- (function(x,y,type=”l”,…) {
plot{x,y,type=type, …)
}

… argument is also used when number of arguments passed to function can’t be known in advance. concatenates strings or vectors of strings. 
>args(paste)
function(…, sep=””, collapse=NULL)
#this pastes together the things you listed in brackets
OR 
>args(cat)
function(…, file= “”, sep=””, fill= FALSE,
	labels=NULL, append= FALSE)
everything after … must be named explicitly. this is the rule. 


Sys.Date() gives you today’s date
write the following in the script area:
add2 <- function(x,y) {
		x+y
}
Now hit ‘run’ on the right corner of script window, it automatically sends this command set to the console. 

now when you write add2(2,3) in the console you get 5

this code will take the vector set and return the subset of vector numbers that are greater than 10.
above 10<- function(x) {
use <- x>10
x[use]	
}
OR

above<- function(x,n=10) {
use<- x>n
x[use]
}

Now hit ‘run’ on the right corner of script window, it automatically sends this command set to the console. 
write this in console: 

x<- 1:20

above(x)
this returns values above 12 till 20. 

columnmean<- function(y) {

nc<- ncol(y). 			#counts number of columns of this data y
means<- numeric(nc)
for (I in 1:nc) {
means [i] <- mean (y[,i], na.rm=removeNA)
}
means
}
now source this into R console and run this forloop using air quality dats set
on the console type:
columnmean(airquality)
you see two columns of NAs missing values. it calculates means of observed values. you can remove NAs this is why you add na.rm=removeNA. 
always fsave the file after writing codes because if R crashes THEN THE FILE IS GONE.

mean(c(2,4,5)) gives you the mean of numbers here mean is the function and 2,4,5 are arguments. 
if else: for testing logical conditions. Example: 
> r<-19
> if (r<=19) (
r<-c(1,2,3,4)
) else ( 
r<-20
For: execute a loop a fixed number of times. (i is iteration in this command)
for (i in 1:10)(
print(i)
)
Example 2: nested:
x<- matrix(1:6, 2,3)
While: executes a loop while a condition is true. 
Repeat: execute an infinite loop. 
Example:
xo<-1
tol<- 1e-8

repeat {
	x1<- computeEstimate()
	if(abs(x1-xo)<tol	{
		break
}else{
xo<- x1}
}
loop may run forever, so it is better to use for loop because if there is a problem it will come to hard limit and stop
in repeat it will keep running and won’t come to stop. Break is the way to exit a loop if something doesn’t work

Break: allows you to break out of any type of loop.
next: skips an interaction of a loop  
return: allows you to exit a function. 
Example:
for (i in 1:100) {
	if (i <= 20){
		## skip the first 20 iterations
		next
		}
		## Do something here
}
return signals that a function should exit and return a given value. 

Sum(c(1,2,3)    	#this function of sum will give you answer 5
Length(c(1,2,3)      	#this function of length will give you length of the numbers which is 3
Mean 			#this function is not written as mean() but once you assign vector data to it then you can calculate mean
my_mean<- function(my_vector){
  sum(my_vector)/length(my_vector)
}
Function		#name a function yourself by assigning argument to it and then print the argument in next line by returning value. Example: 
boring_function <- function(x) {
  x
}
Evaluate		 
evaluate<- function(func,dat){
  func(dat)
}
some_function <- function(func){
func(2, 4)
}
multiply_two_numbers <- function(num1, num2){
num1 * num2
}
add_two_numbers <- function(num1, num2){
num1 + num2
}
call this function by writing:
evaluate(c(1,2,3,4,5,20.3) or 
evaluate(sd,c(1.4,3.6,7.9,8.8)) #The function for standard deviation is called sd(). Make sure that when you pass a function as an argument you pass the name
evaluate(function(x){x[length(x)]}, c(8,4,0))
Ellipses		            #this argument of a function is represented as … which means anything in a data or a collection of data you aren’t sure what it has
# The ellipses can be used to pass on arguments to other functions that are used within the function you're writing. Usually a function that has the ellipses as an argument has the ellipses as the last argument. The usage of such a function would look like:

ellipses_func(arg1, arg2 = TRUE, ...)

#In the above example arg1 has no default value, so a value must be provided for arg1. arg2 has a default value, and other arguments can come after arg2 depending on how they're defined in the ellipses_func() documentation. Interestingly the usage for the paste function is as follows:

paste (..., sep = " ", collapse = NULL)

Notice that the ellipses is the first argument, and all other arguments after the ellipses have default values. This is a strict rule in R programming: all arguments after an ellipses must have default values. Take a look at the simon_says function below:

simon_says <- function(...){
paste("Simon says:", ...)
}
#another way to use this is:

telegram <- function(...){
  paste("START", ..., "STOP")
}
call this as:
telegram("Good", "morning")	#this will give you the calculated answer

#Another usage is as follows: here you break … using args, then you assign something to args, then you paste it along with something you want to be default printed. If you write helicopter in [[noun]] then in sentence it will be printed/pasted as such. 
mad_libs <- function(...){
args <- list(...)
place <- args[["place"]]
adjective  <- args[["adjective"]]
noun <- args[["noun"]]
paste("News from", place, "today where", adjective, "students took to the streets in protest of the new", noun, "being installed on campus.")
}
Binary Operators
The syntax for creating new binary operators in R is unlike anything else in R, but it allows you to define a new syntax for your function. I would only recommend making your own binary operator if you plan on using it often!
User-defined binary operators have the following syntax:
%[whatever]% 
where [whatever] represents any valid variable name.

#Let's say I wanted to define a binary operator that multiplied two numbers and then added one to the product. An implementation of that operator is below:

"%mult_add_one%" <- function(left, right){ # Notice the quotation marks!
left * right + 1
}

Write your own binary operator below from absolute scratch! Your binary operator must be called %p% so that the expression:

       "Good" %p% "job!"

will evaluate to: "Good job!"

"%p%" <- function(left, middle, right, mostright){ # Remember to add arguments!
  paste(left, middle, right, mostright)

Remainder function # it takes two arguments	 num and divisor and returns the remainder. 
remainder<- function(num=7, divisor=2){
num%%divisor
}
Call the above function by: remainder(7,4)
This means it is 7 %% 4 and it would evaluate to 3 where %% is modulus operator. 
Increment function: 
increment <- function(number, by = 1){
number + by
 }
call function by: increment(2,3)  	#It will give 5 because 2+3=5

lapply and sapply

			#lapply and sapply are two members of apply family of functions also known as loop functions
			#these functions along with their close relatives vapply(), and tapply() offer convenient way of Split-apply-combine strategy for data analysis
			# Each of the *apply functions will SPLIT up some data into smaller pieces. APPLY a function to each piece, then COMBINE the results. Throughout this lesson, we'll use the Flags dataset from the UCI Machine Learning Repository. This dataset contains details of various nations and their flags. http://archive.ics.uci.edu/ml/datasets/Flags
head(flags)		#dataset in variable called flags is already stored so open it to preview first 6 lines (head)
dim(flags)		#dimensions of flags files where answer 194 30 means rows and columns 
viewinfo()		#gives the following information of dataset in separate text file 		"/Library/Frameworks/R.framework/Versions/3.5/Resources/library/swirl/Courses/R_Programming/lapply_and_sapply/flag.names.txt"
class(flags)		#tells format of variables stored, as in class of each variable. Eg: class is data.frame (overall class of entire dataset) but if we need to know it for each column we will have to do it individually otherwise use loop using lapply() which applies function to each element of the list. 
as.list(flags)		# to see list of vectors in the data frame of flags. 
cls_list<- lapply(flags,class)#class() function is applied to each column of the data. 
			#the letter l in lapply stands for list. 
class(cls_list)		#we got a list of length 30. One element for each variable/column. Output is more compact if we represent it as a vector instead of a list. 
			#lists are helpful to store multiple classes of data. 
as.character(cls_list)#to see the character vector
sapply()		#automates process by calling lapply behind the scenes. s means simplify. 
cls_vect<- sapply(flags, class)#storing data in cls_vect
# Columns 11 through 17 of our dataset are indicator variables,each represents different color, If it represents color of flag then 1 otherwise 0
sum(flags$orange)	# Therefore, if we want to know the total number of countries (in our dataset) with, for example, the color orange on their flag, we can just add up all of the 1s and 0s in the 'orange' column.
flag_colors<- flags[,11:17]# extract columns containing color data and store in new data frame called flag_colors. We use comma because we want columns 11 to 17. 
head(flag_colors)	# look at the first 6 lines of flag_colors.

lapply(flag_colors, sum)	#To get a list containing the sum of each column of flag_colors, call the lapply() function with two arguments. The first argument is the object over which we are looping (i.e. flag_colors) and the second argument is the name of the function we wish to apply to each column (i.e. sum). Remember that the second argument is just the name of the function with no parentheses,etc. result is a list, since lapply() always returns a list
sapply(flag_colors, sum)         # result can be simplified to a vector by calling sapply() instead of lapply()
sapply(flag_colors, mean) # Use sapply() to apply the mean() function to each column of flag_colors. sapply simplifies the result to vector. 
flag_shapes <- flags[, 19:23] # let's extract columns 19 through 23 from the flags dataset and store the result in a new data frame called flag_shapes.
range()				# The range() function returns the minimum and maximum of its first argument, which should be a numeric vector. Use lapply() to apply the range function to each column of flag_shapes. Don't worry about storing the result in a new variable. By now, we know that lapply() always returns a list.
lapply(flag_shapes, range)	
shape_mat<- sapply(flag_shapes, range)	# will apply the range() function to each column of flag_shapes and store the result in shape_mat.
shape_mat. 	#to view the contents of shape_mat
class(shape_mat)	#determine the class of shape_mat it gives you the type is “matrix”
unique(c(3,4,5,5,5,6,6)) #when you use this function you get only the unique vectors displayed in the answer. Answer it gives is: 3 4 5 6
unique_vals<- lapply(flags, unique)# We want to know the unique values for each variable in the flags dataset. To accomplish this, use lapply() to apply the unique() function to each column in the flags dataset, storing the result in a variable called unique_vals.
unique_vals 		#print
sapply(unique_vals, length)	#determine length of each element of unique_vials by simplifying results. The fact that the elements of the unique_vals list are all vectors of *different* length poses a problem for sapply(), since there's no obvious way of simplifying the result.
sapply(flags, unique). # applies the unique function to each column of the flags dataset 
lapply(unique_vals, function(elem) elem[2]).  #gives the list containing second item from each element of unique_vals list. Note that our function takes one argument elem wheich is just a dummy argument which takes each value of unique_vals. 
vapply()# what if you forget that what unique numbers will be returned when you write sapply(flags, unique). Normally you get answers rightaway but when writing a code yourself you can make a mistake and that is where vapply comes. 
vapply(flags, unique, numeric(1)) #gives error like it should. To get out of error type ok()
sapply(flags, class). #this is what you did earlier in sapply. If we wish to be explicit about the format of the result we expect, we can use vapply(flags, class, character(1)). The 'character(1)' argument tells R that we expect the class function to return a character vector of length 1 when applied to EACH column of the flags dataset. So the result is identical to the sapply() result -- a character vector of column classes. 

tapply() 		#As a data analyst, you'll often wish to split your data up into groups based on the value of some variable, then apply a function to the members of each group. The next function we'll look at, tapply(), does exactly that.
table(flags$landmass) # make a table of landmass in flags. How many countries fall into the group of 1 to 6. it shows.
table(flags$animate) #see how many flags have animate image. here 1 is yes and 0 is no. 
tapply(flags$animate, flags$landmass, mean)	# take the arithmetic mean of a bunch of 0s and 1s, you get the proportion of 1s
tapply(flags$population, flags$red, summary) # summary of population with red flags
tapply(flags$population, flags$landmass, summary)# summary of population values for each of the six landmasses.

Looking at the Data:
# Whenever you're working with a new dataset, the first thing you should do is look at it! What is the format of the data? What are the dimensions? What are the variable names? How are the variables stored? Are there missing data? Are there any flaws in the data?
ls() #lists the folders in your current directory. there is a folder named plants in this directory.
class(plants)#determine the class of plants file. Answer: it is a dataframe. Since the dataset is stored in a data frame, we know it is rectangular or it has two dimensions (rows and columns) and fits neatly into a table or spreadsheet
dim(plants) #see how many rows and columns it has. The first number you see (5166) is the number of rows (observations) and the second number (10) is the number of columns (variables).
nrow(plants) #if you only want to see the rows and not both rows and columns.
ncol(plants)		 # if you only want to see the columns and not both rows and columns.
object.size(plants) #tells you the size of the file in bytes. 
size(plants) 		# Now that we have a sense of the shape and size of the dataset, let's get a feel for what's inside. names(plants) will return a character vector of column (i.e. variable) names. Give it a shot. We've applied fairly descriptive variable names to this dataset, but that won't always be the case. A logical next step is to peek at the actual data. However, our dataset contains over 5000 observations (rows), so it's impractical to view the whole thing all at once.
head(plants) 		# By default, head() shows you the first six rows of the data. You can alter this behavior by passing as a second argument the number of rows you'd like to view. Use head() to preview the first 10 rows of plants.
head(plants, 10). 	 #head along with the first 10 rows of data.
tail(plants, 15).  	#shows the last part of the data with 15 rows
summary(plants)	#since there are NAs in the data therefore you need to see the summary to see how many NAs missing values there are. 
categorical FACTORS# For categorical variables (called 'factor' variables in R), summary() displays the number of times each value (or 'level') occurs in the data. For example, each value of Scientific_Name only appears once, since it is unique to a specific plant. In contrast, the summary for Duration (also a factor variable) tells us that our dataset contains 3031 Perennial plants,682 Annual plants, etc. some data is truncated in summary. 
table(plants$Active_Growth_Period) #make the table of one category in R 
str()			#most important concise function of datasets. The beauty of str() is that it combines many of the features of the other functions you've already seen, all in a concise and readable format. At the very top, it tells us that the class of plants is 'data.frame' and that it has 5166 observations and 10 variables. It then gives us the name and class of each variable, as well as a preview of its contents.

Simulation:

sample()		#The first function we'll use to generate random numbers is sample(). TO RANDOMLY GIVE NUMBERS LIKE A DICE DOES.
sample(1:6, 4, replace=TRUE)# simulate rolling four six-sided dice. Answer: 2 6 3 1 (instructs R to randomly select four numbers between 1 and 6). Sampling with replacement simply means that each number is "replaced" after it is selected, so that the same number can show up more than once. This is what we want here, since what you roll on one die shouldn't affect what you roll on any of the others.
#Now repeat the command to see how your result differs. (The probability of rolling the exact same result is (1/6)^4 = 0.00077, which is pretty small!)
sample(1:20, 10)	# sample 10 numbers between 1 and 20, without replacement. Since the last command sampled without replacement, no number appears more than once in the output. 
LETTERS		#LETTERS is a predefined variable in R containing a vector of all 26 letters of the English
sample(LETTERS)	#gives random alphabets 26 times
flips<- sample(c(0,1), 100, replace = TRUE, prob=c(0.3,0.7))# simulate 100 flips of an unfair two-sided coin. this specific coin has a 0.3 probability of landing 'tails' and a 0.7 probability of landing 'heads'. let the tails be 0 and heads be 1. Use sample() to draw a sample of size 100 from the vector c(0,1), with replacement. Since the coin is unfair, we must attach specific probabilities to the values 0 (tails) and 1 (heads) with a fourth argument prob = c(0.3, 0.7). Assign the result to a new variable called flips.
flips #view or print flips. Since we set the probability of landing heads on any given flip to be 0.7, we'd expect approximately 70 of our coin flips to have the value 1. Count the actual number of 1s contained in flips using the sum() function.
sum(flips)		# sum(flips) will add up all the 1s and 0s, giving you the total number of 1s in flips.
?rbinom		# A coin flip is a binary outcome (0 or 1) and we are performing 100 independent trials (coin flips),use rbinom() to simulate a binomial random variable. 
rbinom(1, size=100, prob = 0.7)#A binomial random variable represents the number of 'successes' (heads) in a given number of independent 'trials' (coin flips). Therefore, we can generate a single random variable that represents the number of heads in 100 flips of our unfair coin using rbinom(1, size = 100, prob = 0.7). Note that you only specify the probability of 'success' (heads) and NOT the probability of 'failure' (tails).
flips2 <- rbinom(100, size = 1, prob = 0.7)# 100 observations, each of size 1 and prob 0.7
sum(flips2)#check how many 1s are there 
rnorm() #simulate random numbers from many other probability distributions.
?rnorm#.  documentation for rnorm. | The standard normal distribution has mean 0 and standard deviation 1. As you can see under the 'Usage' section in the documentation, the default values for the 'mean' and 'sd' arguments to rnorm() are 0 and 1, respectively. 
rnorm(10)# Thus, rnorm(10) will generate 10 random numbers from a standard normal distribution.
rnorm(10, mean=100, sd=25). # Now do the same, except with a mean of 100 and a standard deviation of 25.
rpois(5, 10)# Generate 5 random values from a Poisson distribution with mean 10
my_pois<-replicate(100, rpois(5,10))# replicate() created a matrix, each column of which contains 5 random numbers generated from a Poisson distribution with mean 10. 
cm<-colMeans(my_pois)#  Now we can find the mean of each column in my_pois using the colMeans() function. Store the result in a variable called cm.
hist(cm)# distribution of our column means by plotting a histogram with hist(cm).
All of the standard probability distributions are built into R, including exponential (rexp()), chi-squared (rchisq()), gamma (rgamma()), .... Well, you see the pattern.
Simulation is practically a field of its own and we've only skimmed the surface of what's possible. I encourage you to explore these and other functions further on your own.
rnorm #generate randome normal variates with given mean and sd
dnorm #evaluate normal probability density at a point
pnorm # evaluate cumulative distribution function for normal distribution
rpois #generate random poisson variates with given rate

r= random number generation
q= quantile function
d= density
p= cumulative distributiuon

qnorm(p, mean=0, sd=1, lower.tail=TRUE, liog.p=FALSE) #evaluating on the log 
rnorm(n, mean=0, sd=1)
pnorm(q, mean=0, sd=1, lower.tail=TRUE, log.p=FALSE)
dnorm(x, mean=0, sd=1, log=FALSE)

Dates and Times:

Based on data that shows something changes over time (i.e. time-series data) or if your data contain some other temporal information, like dates of
birth. Dates are represented by the 'Date' class and times are represented by the 'POSIXct' and 'POSIXlt' classes. Internally, dates are stored as the number of days since 1970-01-01 and times are stored as either the number of seconds since 1970-01-01 (for 'POSIXct') or a list of seconds, minutes, hours, etc. (for 'POSIXlt').
d1<- Sys.Date()  #get the current date and store it in the variable d1.
class(d1)	# class() function to confirm d1 is a Date object
unclass(d1)	# see what d1 looks like internally. That's the exact number of days since 1970-01-01!
d1		#format of dates will be YEAR-MONTH-DAY
d2<- as.Date("1969-01-01") 	# we need to reference a date prior to 1970-01-01 by creating a variable d2 using as.Date()
unclass(d2)			#d2 internally gives negative number. As you may have anticipated, you get a negative number. In this case, it's -365, since
1969-01-01 is exactly one calendar year (i.e. 365 days) BEFORE 1970-01-01.
Now, let's take a look at how R stores times. You can access the current date and time using the Sys.time() function with no arguments. Do this and store the result in a variable called t1.
t1<- Sys.time()	# You can access the current date and time using the Sys.time() function with no arguments.
t1		#see the contents of t1
class(t1)	#gives "POSIXct" "POSIXt" 
As mentioned earlier, POSIXct is just one of two ways that R represents time information. (You can ignore the second value above, POSIXt, which just functions as a common language between POSIXct and POSIXlt.) 
unclass(t1)	# unclass() to see what t1 looks like internally -- the (large) number of seconds since the beginning of 1970.
t2<-as.POSIXlt(Sys.time())	# By default, Sys.time() returns an object of class POSIXct, but we can coerce the result to POSIXlt with as.POSIXlt(Sys.time()).
t2				#show the contents of t2 as 2020-04-26 22:29:33 EDT"
class(t2)			#gives the class of t2
unclass(t2)			# is just a list of values that make up the date and time
str(unclass(t2))			#gives a more compact view
#we want just the minutes from the time stored in t2, we can access them with t2$min. Now that we have explored all three types of date and time objects, let's look at a few functions that extract useful information from any of these objects -- weekdays(), months(), and quarters().
t2$min				#finding minutes in t2 data
weekdays(d1)			# The weekdays() function will return the day of week from any date or time object.
months(t1)			#what is the month in t1?
quarters(t2)			#what is the quarter of t2?
Strptime() 			# Often, the dates and times in a dataset will be in a format that R does not recognize. The strptime() function can be helpful in this situation. strptime() converts character vectors to POSIXlt. In that sense, it is similar to as.POSIXlt(), except that the input doesn't have to be in a particular format (YYYY-MM-DD).
t3<- "October 17, 1986 08:24"#  store the following character string in a variable called t3: "October 17, 1986 08:24" (with the quotes).
t4<- strptime(t3, "%B %d, %Y %H:%M")  # will convert our date/time object to a format that R understands.
t4				#print t4
class(t4)			#check the class of t4. Answer is "POSIXlt" "POSIXt"
Finally, there are a number of operations that you can perform on dates and times, including arithmetic operations (+ and -) and comparisons (<, ==, etc.)
Sys.time>t1			#since you created t1 long time ago and present time would be more than that right? to confirm check it if it is true. 
Sys.time() -  t1			#but how much time has passed since then? this will show. 
The same line of thinking applies to addition and the other comparison operators. If you want more control over the units when finding the above difference in times, you can use difftime(), which allows you to specify a 'units' parameter.
difftime(Sys.time(), t1, units= 'days')	#this shows difference in days time. to work with dates and time you may want to check out check out the lubridate package by Hadley Wickham.

Base Graphics
One of the greatest strengths of R, relative to other programming languages, is the ease with which we can create publication-quality graphics.
More advanced ones include: lattice, ggplot2 and ggvis.
data(cars)			#get the data of cars
?cars				#find information for cars data
head(cars)			#head of the data. you can also use dim(), names(), head(), tail() and summary() onto cars. 
plot(cars)			#plots the graph for cars which is dist vs speed. As always, R tries very hard to give you something sensible given the information that you have provided to it. First, R notes that the data frame you have given it has just two columns, so it assumes that you want to plot one column versus the other.
?plot				#help page for plot
The help page for plot() highlights the different arguments that the function can take. The two most important are x and y, the variables that will be plotted. For the next set of questions, include the argument names in your answers. That is, do not type plot(cars$speed, cars$dist), although that will work. Instead, use plot(x = cars$speed, y = cars$dist). 
plot(x=cars$speed, y=cars$dist)#Plot() can take x and y arguments with any labels columns using equals sign. this result is different from the plot(cars) because R wasn’t sure what we wanted to use as labels etc. There are other ways as well to plot the same graph. such as : plot(dist ~ speed, cars)
plot(x=cars$dist, y=cars$speed)	#opposite of what we did earlier
plot(x=cars$speed, y=cars$dist, xlab="Speed")	#on the same graph label x axis as “Speed”
plot(x=cars$speed, y=cars$dist, ylab= "Stopping Distance")#on the same graph label y axis as “Stopping Distance”
plot(x=cars$speed, y=cars$dist, xlab="Speed", ylab= "Stopping Distance") #recreating graph with both labels
plot(cars, main = "My Plot")		#main heading of plot be My plot.
plot(cars, sub= "My Plot Subtitle")	#Give subtitle as My plot subtitle. You can do some research on ?par
plot(cars, col=2)			#plot cars and the color would be red
Plot cars while limiting the x-axis to 10 through 15.
plot(cars, xlim=c(10,15))		#the xaxis must be starting from 10 to 15. 
plot(cars, pch=2)			#change the shape of points to any number type
data(mtcars)				#load data of mtcars
?boxplot				#help page boxplot. Instead of adding data columns directly as input arguments, as we did with plot(), it is often handy to pass in the entire data frame. 
This is what the "data" argument in boxplot() allows. boxplot(), like many R functions, also takes a "formula" argument, generally an expression with a tilde ("~") which indicates the relationship between the input variables. This allows you to enter something like mpg ~ cyl to plot the relationship between cyl (number of cylinders) on the x-axis and mpg (miles per gallon) on the y-axis.
boxplot(mpg~cyl, data=mtcars)# boxplot() with formula = mpg ~ cyl and data = mtcars to create a box plot
hist(mtcars$mpg)		#hist() with the vector mtcars$mpg to create a histogram
