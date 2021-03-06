littlemathematics is a simple module that includes functions douing some small mathematical stuff. 
The practical usefulness is limited, as there are certainly modules out there that achieve the same reuslts more efficiently.
Nonetheless, it may be amusing to see what is going on inside the black box.

So far, littlemathematics includes four functions:
littlemathematics.eratosthenes()
littlemathematics.pimaker()
littlemathematics.montecarlopi()
littlemathematics.taxicab()

--------------------------------------------------------------------------------------------

littlemathematics.eratosthenes()


The syntax of this function is:
littlemathematics.eratosthenes(limit)

whereby limit is an integer representing the number up to which (and including) prime numbers are to be searched.
The function uses the ancient "sieve of Eratosthenes" to find prime numbers: 
It starts with a raw list up to (and including) the given limit and then removes, subsequently, all numbers that are multiples of smaller integers.
The resulting list (which constitutes the output of the function) includes all primes up to and including the given limit.

--------------------------------------------------------------------------------------------

littlemathematics.pimaker()


The syntax of this function is:
littlemathematics.pimaker(i)

where i is the number of iterations of the algorithm you wish to perform.

The function uses the Bailey-Borwein-Plouffe (BPP) formula to iteratively compute approximations of pi. The output is a tuple with two floating point numbers; 
the first is the approximation of pi as calculated by the algorithm, the second is the absolute of the difference between that approximation and the value of pi 
as stored in the math module of Python. You will see that this difference becomes very small even after few iterations.

--------------------------------------------------------------------------------------------

littlemathematics.montecarlopi()


The syntax of this function is:
littlemathematics.montecarlopi(i)

where i is the number of iterations of the algorithm you wish to perform.

The function uses a simple Monte Carlo algorithm to iteratively compute approximations of pi. It generates a random "droplet", i.e. a point that lies randomly on a 1-1 cartesian coordinate system. 
It then uses the Pythagorean theorem to calculate the distance of the droplet from the origin of the coordinate system. If that distance is less than or equal to 1,
the point lies on or within a circle of radius 1 around the origin. We know that the segment of this circle in our quadrant of the coordinate system is pi/4, 
so we would assume that on average n*pi/4 (n being the number of iterations) of the droplets lie on or within the circle. 
The algorithm therefore uses the percentage of droplets which actually did fall on or within the circle to compute an estimate of pi.

The output is a tuple with two floating point numbers; the first is the approximation of pi as calculated by the algorithm, the second is the absolute of the difference between that approximation and the value of pi as stored in the math module of Python. 
Bear in mind that a Monte Carlo algorithm can only produce approximations, never exact figures; even though the approximations should get more precise 
(and hence the absolute of the difference smaller) the more iterations you run, you cannot expect that you will get the same result twice 
if you run the algorithm twice with the same number of iterations.

--------------------------------------------------------------------------------------------

littlemathematics.taxicab()

This function takes no arguments, it is simply called. It performs a brute-force search for the Ramanujan-Hardy number, also known as taxicab number: The smallest
natural number that can be expressed as the sum of two cubes in two different ways (for the anecdote behind it, see https://en.wikipedia.org/wiki/Taxicab_number). 
To perform the search, the algorithm starts with the smallest cube of a natural number, 1^3 = 3, and sums it with all the cubes it has previously looked at. 
It then checks if it has come across the same sum before. If yes, it ends the search and outputs that hit; if no, it proceeds to do the same for the cube of the next natural number. 
Depending on your hardware, the algorithm should identify (and print) the correct result quite quickly (within seconds): 1729, together with the two ways to
express it as the sum of two cubes (1000 + 729 and 1728 + 1).

--------------------------------------------------------------------------------------------
Version 2.8, May 2021
