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
      
  
