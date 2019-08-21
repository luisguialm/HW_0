# HW 0
## Short Bio **Luis Andres Guillen**
1. Personal Info:

   **Born in Sweden, grew up in Venezuela, married to an Italian, now in the USA**.
   
2. Education:
   
   **Forestry Engineering (VE), MS Forest Management (SWE), (currently) PhD Forest Hydrology (USA)**.   
3. Interests: 

  **Travel, languages, nature, ~~soccer~~ futbol, politics, enjoying the fruits of biodiversity and human innovaiton (wine, beer and food) but most importantly spending time with my family, friends and Grappa (my dog).**    

4. Why do I take a Data Science Course?

  As most people do, I have a love/hate relationship with coding. Coding makes you think, but can also be frustrating.  
  I've noticed that the more I practice the better I get at it. Moreover, nowadays I can find a lot of help online,  
  which helps people like me, who can't remember syntax and need to google even the easiets commands, as e.g. `rm=list(ls())` 
  
  After 3 years of PhD I finally have a lot of data. I avoid using excel as much as I can. I'm even reading my files directly into R and combining them into larger dataframes: _
 ```r
dataFiles <- lapply(Sys.glob("19*.csv"), read.csv,header=FALSE) #Reads the names of the files
for (i in 1:length(dataFiles)){ #loop to read the files and get them into a variable
    data<-as.data.frame(dataFiles[i]) # reads each of the files 
  if (i==1){# condition to bind the data of each file
    vari<-data #creates variable for first file
  }else{ #condition for several files 
    pos=0 #initial counter 
    for(j in 1:nrow(data)){ # loop to compare the values in the two files
      if(pos==0){  # Conditionto run the second loop
      a<-vari[nrow(vari),2] # a is the last value of row in the big vector vari
      b<-data[j,2] # b is the value of each row in the new data set until it is equal to a
        if(a == b){ #condition that to know from what point append the new data to the vector vari
          vari<-rbind(vari,data[(j+1):nrow(data),]) # appending the new data to the vector vari.
        pos=1 # this changes the counter and stops the second loop. 
        }
      } 
    }
  }
}
```
Although, such line of code saved me from opening each file and coping and pasting them into a master file, I am still running the code for each of my data groups. I know it could be done more quickly and efficiently. 


I also know that improving my Data Science skills will help me in other aspects of my work, such as collaborating with other scientists, having better research methods, and maybe using some of the tools in future teaching endevours. 

5. Current Research:

  I work for Dr. Nicolas Zegre at the [Mountain Hydrology Lab](https://www.mountainhydrologylab.com/).  
  My research looks at Forest-Water dynamics in the Appalachian region. One of my research projects is to study transpiration rates of Maples and Oaks when they are stressed by water scarcity. Here is a picture from the field.

![alt text](https://github.com/luisguialm/data_science_course/blob/master/HW_0/20170420_124050.jpg)
 
_**Looking forward to meeting y'all**_
