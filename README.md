Programming Fundamentals Final Exam Retake 10.04.2020
Problem 3. Need for Speed III

You have just bought the latest and greatest computer game – Need for Seed III. We know that you can`t wait to start playing. Pick your favorite cars and drive them all you want!
On the first line of the standard input you will receive an integer n – the number of cars that you can obtain. On the next n lines the cars themselves will follow with their mileage and fuel available, separated by "|" in the following format:
{car}|{mileage}|{fuel}
Then, you will be receiving different commands, each on a new line, separated by " : ", until the "Stop" command is given:
Drive : {car} : {distance} : {fuel} 
You need to drive the given distance and you will need the given fuel to do that. If the car doesn`t have enough fuel print:
"Not enough fuel to make that ride"
If the car has the required fuel available in the tank, increase its mileage with the given distance, decrease its fuel with the given fuel and print: 
"{car} driven for {distance} kilometers. {fuel} liters of fuel consumed."
You like driving new cars only, so if the mileage of a car reaches 100 000 km, remove it from the collection(s). Print:
"Time to sell the {car}!"
Refuel : {car} : {fuel}
Refill the tank of your car. 
Each tank can hold a maximum of 75 liters of fuel, so if the given amount of fuel is more than you can fit in the tank, take only what is required to fill it up. 
Print a message in the following format:
"{car} refueled with {fuel} liters"
Revert : {car} : {kilometers}
Decrease the mileage of the given car with the given kilometers and print the kilometers you have decreased it with in the following format:
"{car} mileage decreased by {amount reverted} kilometers"
If the mileage becomes less than 10 000km after it is decreased, just set it to 10 000km and 
DO NOT print anything.
Upon receiving the "Stop" command you need to print all cars in your possession, sorted by their mileage in decscending order, then by their name in ascending order, in the following format:
"{car} -> Mileage: {mileage} kms, Fuel in the tank: {fuel} lt."
Input/Constraints
The mileage and fuel of the cars will be valid, 32-bit integers and will never be negative.
The fuel and distance amounts in the commands will never be negative.
The car names in the commands will always be valid cars in your possession.
Output
All the output messages with the appropriate formats are described in the problem description.
Examples
Input	Output
3
Audi A6|38000|62
Mercedes CLS|11000|35
Volkswagen Passat CC|45678|5
Drive : Audi A6 : 543 : 47
Drive : Mercedes CLS : 94 : 11
Drive : Volkswagen Passat CC : 69 : 8
Refuel : Audi A6 : 50
Revert : Mercedes CLS : 500
Revert : Audi A6 : 30000
Stop	Audi A6 driven for 543 kilometers. 47 liters of fuel consumed.
Mercedes CLS driven for 94 kilometers. 11 liters of fuel consumed.
Not enough fuel to make that ride
Audi A6 refueled with 50 liters
Mercedes CLS mileage decreased by 500 kilometers
Volkswagen Passat CC -> Mileage: 45678 kms, Fuel in the tank: 5 lt.
Mercedes CLS -> Mileage: 10594 kms, Fuel in the tank: 24 lt.
Audi A6 -> Mileage: 10000 kms, Fuel in the tank: 65 lt.
Comments
After we receive the cars with their mileage and fuel, we start driving them. When we get to "Drive : Volkswagen Passat CC : 69 : 8" command, our program calculates that there is not enough fuel and we print the appropriate message. Then we refuel the Audi A6 with 50 l of fuel and Revert the Mercedes with 500 kilometers.
When we receive the "Revert : Audi A6 : 30000", we set its mileage to 10000 km, because if the current mileage of the Audi is 38543 kms and if we subtract 30000 from it, we receive 8543 kms, which is less than 10000 kms.
After all the commands, we print our current collection of cars with their current mileage and current fuel.
