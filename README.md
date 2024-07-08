# Players
databasecreate database Players;
use Players;

create table TIMU(
Country_code char(2) not null ,
Country varchar(15) not null,
continent varchar(15) not null check (continent = 'Africa'),

primary key (Country_code)
);

create table WACHEZAJI(
P_code char(4) not null ,
P_name varchar(30) not null,
Prof_club varchar(30) not null,
Goals int  null,
Country_code varchar(2),

primary key(P_code),

CONSTRAINT FOREIGN KEY(Country_code)
references TIMU (Country_code)
ON DELETE CASCADE ON UPDATE CASCADE
);

INSERT INTO WACHEZAJI VALUES("G001","Junior Agogo", "Birminham",3, "G1");
INSERT INTO WACHEZAJI VALUES("E039","Mohammed Zidane", "Bayern Munich",2, "E2");
insert into WACHEZAJI values("G002","Micheal Essein","Chelsea",4,"G1");
insert into WACHEZAJI values("N021","John Obi Mikel","Chelsea",1,"N1");
insert into WACHEZAJI values("C087","Samuel E'too","Barcelona",5,"C9");
insert into WACHEZAJI values("G004","Stephen Appiah","Fernerbeche",2,"G1");
insert into WACHEZAJI values("E009","Hassan Osam","Al Ajli",'0',"E2");
insert into WACHEZAJI values("N032","JJ Okocha","Chelsea NULL",6,"N1");

INSERT INTO TIMU VALUES ("G1","Ghana", "Africa");
INSERT INTO TIMU VALUES ("E2","Egypt", "Africa");
INSERT INTO TIMU VALUES ("N1","Nigeria", "Africa");
INSERT INTO TIMU VALUES ("C9","Cameroon", "Africa");
INSERT INTO TIMU VALUES ("K1","Kenya", "Africa");

select * from WACHEZAJI;
SELECT * FROM TIMU;

select WACHEZAJI.P_name,TIMU.Country,WACHEZAJI.Prof_club FROM WACHEZAJI,TIMU;
