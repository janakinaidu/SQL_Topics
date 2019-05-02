# SQL_Topics

Desc:
----
 SQL Queires for creating two tables student,department tables where deptid is primary key in department table and act as foreign key 
 in student table;

        CREATE TABLE `department` (
        `id` int(11) NOT NULL AUTO_INCREMENT,
        `dept_name` varchar(128) DEFAULT NULL,
        `location` varchar(45) DEFAULT NULL,
        PRIMARY KEY (`id`)
      ) ENGINE=InnoDB AUTO_INCREMENT=1 DEFAULT CHARSET=latin1;

      CREATE TABLE `student` (
        `sid` int(11) NOT NULL AUTO_INCREMENT,
        `name` varchar(45) DEFAULT NULL,
        `age` int(45) DEFAULT NULL,
        `email` varchar(45) DEFAULT NULL,
        `deptid` int(11) DEFAULT NULL,
        PRIMARY KEY (`sid`),
        KEY `FK_DETAIL_idx` (`deptid`),
        CONSTRAINT `FK_DETAIL` FOREIGN KEY (`deptid`) REFERENCES `department` (`id`) ON DELETE NO ACTION ON UPDATE NO ACTION
      ) ENGINE=InnoDB AUTO_INCREMENT=1 DEFAULT CHARSET=latin1;
      
      
      
      if you want to ouput as :
      ECE 3
      CSE 2
      
    ->insert some data after creating tables:
    
    insert into department values(101,'ECE','hyderabad'); 
    insert into department values(102,'CSE','hyderabad'); 
    
    insert into  student values(5,'hari',24,'hari@gmail.com',102);
    ............
    
    QUery:
    ======
    select d.dept_name,count(s.sid) from department d left join student s on d.id = s.deptid
    group by d.dept_name order by count(s.sid) desc,d.dept_name ASC
    
    
