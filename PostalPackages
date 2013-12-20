/* 
Name: Renato Recio
Program Status: Complete
Program Function: Postal Packages
				Program processes different
				packages and determines the 
                cost (based on weight) and
                also determines whether or 
                not they are able to be 
                shipped based on dimensions
				
*/


////////////////////////////////////////////////////////////////////
//Include                                                         /
///////////////////////////////////////////////////////////////////	
#include <iomanip>
#include <iostream>
#include <cmath>
#include <string>

using namespace std;

////////////////////////////////////////////////////////////////////
//Declare methods                                                //
///////////////////////////////////////////////////////////////////	
int process_transactions(); 
int calculate_girth(int, int, int);


////////////////////////////////////////////////////////////////////
//Main                                                             /
///////////////////////////////////////////////////////////////////	
int main(){

cout << "For each transaction, enter package weight and 3 dimensions.";
cout << "\nEnter -1 to quit.";
process_transactions(); // Call the process_transactions to begin processing
   
return 0;
}

////////////////////////////////////////////////////////////////////
//This method processes all the transactions for the packages     //
///////////////////////////////////////////////////////////////////	
int process_transactions(){
int accepted_count = 0; //track accepted
int rejected_count = 0; //track rejected
int transaction_number = 1; //Stores the current transaction being processed
int weight, length, width, height; //Package properties
int valid_size = 1; //If the package is a valid size, this will stay at 1
int valid_weight = 1; //If the package is a valid size, this will stay at 1
int accept_status = 1; //If the status is accepted, put 1, else, put 0
int w; //W for weight
float cost = 0; //Store cost;
int weight_table[15] = {1,2,3,5,7,10,13,16,20,25,30,35,40,45,50}; //initialize integer weight table
float cost_table[15] = {1.50, 2.10, 4.00, 6.75, 9.90, 14.95, 19.40, 24.20, 27.30, 31.90, 38.50, 43.50, 44.80, 47.40, 55.20}; //initialize FP cost table
int exit_status = 0; //if exit status changes to -1, we are finished
   
while (exit_status != -1){ //as long as the -1 flag (exit) is not set, we continue processing

//Reset values
accept_status = 1; 
valid_weight = 1;
valid_size = 1;

cout << "\n\nEnter package weight and 3 dimensions: "; 
cin >> weight ; //Receive input for package information

if (weight == -1){
exit_status = -1; //We have an exit signal
continue;
}
cin >> length >> width >> height;

if (weight < 1)
valid_weight = -1; //We have an invalid weight
else if (length <= 0 || width <= 0 || height <= 0) //If any of these fall below the minimum (1), invalidate
valid_size = -1;

if (valid_size != 1 || valid_weight != 1){
               cout << "\nError - package weight and dimensions must be larger than 0";
               cout <<"\nPlease re-enter transaction\n";
               continue;
               }


//Check the conditions
if (!calculate_girth(length, width, height) || length > 36 || width > 36 || height > 36 || weight > 50)
accept_status = 0; //set 0 if rejected
else{
for (w = 1; w < 15; w++){ //Calculate cost by traversing weight table
    if (weight == weight_table[w]){
    cost = cost_table[w]; //set cost using cost table of weight table index
    break;
    }
    if (weight < weight_table[w] && weight > weight_table[w-1])
    cost = cost_table[w]; //set cost using cost table of weight table index
    if (weight == weight_table[w-1])
    cost = cost_table[w-1];
}
}

//////////////////////
//Begin printing data
cout <<"\nTransaction:"  << setw(10) << right << transaction_number; 

cout <<"\nStatus     :";
if (accept_status == 1)    
cout   << setw(10) << right << "Accepted";
else 
cout   << setw(10) << right << "Rejected";

cout <<"\nWeight     :" << setw(10) << right << weight;

cout <<"\nCost       :";
if (accept_status == 1)
cout   << setw(10) << right << setprecision(2) << fixed << cost;
else
cout   << setw(10) << right << "-";
//End printing data
/////////////////////
    
transaction_number++; //increment transaction_number for next transaction

if (accept_status == 1)
accepted_count++;
else
rejected_count++;   
 
   
}

//Once while loop exits, we can print the results
cout << "\nNumber of accepted packages: " << accepted_count;
cout << "\nNumber of rejected packages: " << rejected_count;

return -1; 
    
}

////////////////////////////////////////////////////////////////////
//This method determines if the size is acceptable for the package//
///////////////////////////////////////////////////////////////////	
int calculate_girth(int length, int width, int height){
int valid_girth = 1; //we will use 1 to indicate a valid girth
int girth, largest; //girth calculation requires info for largest 

/////////////////////////////
//Find the largest of the 3 
if (length > width)
largest = length;
else
largest = width;
if (height > largest)
largest = height;
/////////////////////////////

girth = 2 * (length + width + height - largest); //Calculate girth

if (girth > 60) //If girth is too large, invalidate
valid_girth = 0;

return valid_girth;
}
