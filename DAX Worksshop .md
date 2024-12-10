# STEP BY STEP GUILD ON HOW I understand simplify and categories MY DATA  

## Calculated columns

1) I used calculated column in dax to create a new column joining first name and last name to create a new column
 using the function (and = which add two or more columns together) the formula is 
 : 'cutomer' [First name]&" "&'cutomer[last name]

![Image of the 1 solution](https://github.com/Smd419/DAX-PROJECT-/blob/main/Image/DAX1.png)
 
 
 2) After creating our full name column in our customer table, i used the if statement to classifiy the age from
  the age column into groups of age (IF = function as a away of puting condition to a specific command) the Formula
   is : IF ('cutomer'[Age] >=55,"55+",
              IF ('Cutomer'[Age] >=45,"45-54",
              IF ('Cutomer'[Age] >=35,"35-44",
                                      "18-34))) 

![Image of the 2 solution](https://github.com/Smd419/DAX-PROJECT-/blob/main/Image/DAX2.png)


3) Then i created a new column called Month Year using the function Format to turn data value into sting month
 and year (Fomat = it functin is used to format a value, such as a number,date,time into a string) the Formular
  is : FORMAT('Data'[Data],"MM-YYY")
 
 ![Image of the 3 solution](https://github.com/Smd419/DAX-PROJECT-/blob/main/Image/DAX3.png)


4) A last purchase data column was created in our customer table, by using MAXX to add it all and RELATEDTABLE
 to be able to extract my information from internet sales (MAXX = Function returns the maximum value of an 
 expression evaluated for each row in a table) (RELATEDTABEL = makes a relationship between two tabel so you 
 can extract a data from one table to another table) Formular is :MAXX(RELATEDTABLE('Internetsales'),'Internet Sale'[OrderDate])

![Image of the 4 solution](https://github.com/Smd419/DAX-PROJECT-/blob/main/Image/DAX6.png)


## Calculated Measure
  
1) I created my First new measure  called Total Transaction using the countrow function to count the Transaction 
sales in Internetsales and RELATEDTABLE to make a relationship to be able to extract my information from Internetsales
( countrow = It returns the number of rows in a table ) formula : countrow(RELATEDTABEL('Internetsales'))

![Image of the 5 solution](https://github.com/Smd419/DAX-PROJECT-/blob/main/Image/DAX7.png)


2) Then made a column called region volums using switch function to add condition to some information grouping it
(switch = function is used to evaluate an expression and return a value from a list of possible values based on that
expression. it's like an IF statement, but with multipel condition and return value)
                      switch(TRUE(),
                      ISBLANK('sales Territory[Total Transaction]),"N/A"
                      'sales Territory'[Total Transaction]>=7000,"high volums"
                      'sales Territory'[Total Transaction]>=4000,"miedium volums"
                      'sales Territory'[Total Transaction]>=1,"low volums","N/A")

![Image of the 6 solution](https://github.com/Smd419/DAX-PROJECT-/blob/main/Image/DAX8.png)


3) After making the region volums measure i created a new Measure called profit magin using DIVID function to 
Divid my Totalsales profit (DIVID = It is use to Divid a particulary set of numbers  ) formula :DIVID([PROFIT],[TOTALSALES])

![Image of the 7 solution](https://github.com/Smd419/DAX-PROJECT-/blob/main/Image/DAX10.png)