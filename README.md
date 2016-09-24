# Session-9-Pig-Assignment-2
grunt> original_data = foreach noheader generate name,coltaken,dob,$4,grade,state,city;
grunt> score = filter original_data by grade < 5;
grunt> grp = group score by grade;
grunt> out = foreach grp  generate COUNT(score.name);
grunt> outt = group out all;
grunt> out = foreach grp  generate COUNT(score.name) as c;
grunt> outt = group out all;                              
grunt> outtt = foreach outt generate SUM(out.c);          
grunt> dump outtt;
(188)

grunt> original_data = foreach noheader generate name,coltaken,dob,$4,grade,state,city;
grunt> ala = filter original_data by state == 'alaska';                                
grunt> alas = foreach ala generate name;                                               
grunt> alask = group alas all;                                                         
grunt> alaska = foreach alask generate COUNT(alas.name);                               
grunt> dump alaska;                                                                    
(68)


grunt> original_data = foreach noheader generate name,coltaken,dob,$4,grade,state,city;
grunt> ala = filter original_data by state == 'alabama' and coltaken == 'goverenment'; 
grunt> alab = foreach ala  generate coltaken;                                          
grunt> alaba = group alab all;                                                         
grunt> alabama = foreach alaba generate COUNT(alab.coltaken);                          
grunt> dump alabama;                                                                   
(2198)

grunt> original_data = foreach noheader generate name,coltaken,dob,$4,grade,state,city;
grunt> ala = filter original_data by state == 'oregon' and $4 == 'BE'; 
grunt> alab = foreach ala  generate name;                                          
grunt> dump alab;
BLOOM
PATTERSON
WAGGONER
IMMILE
SHOCK
WHITE
JOHN
RICHARD
JACOB
Albright
Buckius
Bowman
Cordes
Danner
Donas
Ehrisman
Frick
Grimler
Heinitsh
Himmelsbach
Hubley
Kitch
Lambert
McNair
Naumann
Royal
Shindle
Wayne
Reformed
P.K.
Charles H
Jacob
Daniel
George
John
Peter
George B
Philip
Dennis
George
Edwin
Frederick

