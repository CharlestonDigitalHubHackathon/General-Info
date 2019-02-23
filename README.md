![](https://raw.githubusercontent.com/Hackathon2019/General-Info/master/Hackathon2019_Logo.png)

## Contents
* [General Info](#general-info)
	* [Schedule](#schedule)
	* [Map](#map)
	* [Wifi Network](#wifi-network)
* [Project Info](#project-info)
	* [Project Judging (First Round)](#project-judging-first-round)
	* [Best in Show Judging (Second Round)](#best-in-show-judging-second-round)
	* [Additional Repositories](#additional-repositories)
	* [Database Backups](#database-backups)
		* [Restoring a Database using recommended database tool](#restoring-a-database-using-recommended-database-tool)
		* [Restoring a Database using command line](#restoring-a-database-using-command-line)
* [Questions](#questions)

# [General Info](#general-info)
This repository contains general information about the 2019 Charleston Digital Hub Hackathon, such as the schedule, map, and WiFi instructions. Each sustainable development goal will have an additional repository containing resources specific to it, such as the provided datasets, a description of the goal, and helpful website resources to aid in solution implementation.

## [Schedule](#schedule)

Saturday, February 23rd   
Charleston Digital Hub - 2387 Clements Ferry Road, Charleston, SC 29492

| Time              | Details                                                              |
| :---------------- | -------------------------------------------------------------------- |
| 8:00 AM – 9:00 AM | Registration / breakfast                                             |
| 9:00 AM - 9:15 AM | Introductions                                                        |
| 9:15 AM           | Development begins                                                   |
| 12:00 PM          | Lunch begins                                                         |
| 4:00 PM           | Warning to make sure teams are watching the time                     |
| 4:40 PM           | Warning to make sure teams have all code checked in                  |
| 5:00 PM           | Development ends and dinner begins                                   |
| 5:15 PM           | Project judging begins                                               |
| ~6:45 PM          | Project judging ends (tentative)                                     |
| ~7:00 PM          | Announce the winners in each project track                           |
| ~7:15 PM          | Final presentations begin                                            |
| ~8:00 PM          | Best in show winners announced                                       |

## [Map](#map)
![](https://raw.githubusercontent.com/Hackathon2019/General-Info/master/Hackathon2019_Map.png)
  
## [Wifi Network](#wifi-network)
SSID: `hackathon2019` 
Password: `BoozAllenHT2019`

# [Project Info](#project-info)

## [Project Judging (First Round)](#project-judging-first-round)
Your project will be judged across the following categories with the corresponding weight:

|  Category      | Weight |
| :------------- | :----: |
| Implementation | 15     |
| Creativity     | 10     |
| Data           | 10     |
| Impact         | 10     |
| X-Factor       | 5      |

[Complete Rubric](https://github.com/CharlestonDigitalHubHackathon/General-Info/blob/master/Rubric.pdf)

Four rooms will be assigned for judging (see map to find rooms):

| Room          | Goal                             |
| :-----------: | :------------------------------: |
| Peanut Butter | Quality Education                |
| Dev/Null      | Affordable & Clean Energy        |
| Situation     | Climate Action                   |
| Eggs          | Sustainable Cities & Communities |

Outside of each room will be a schedule of when each team is assigned for judging. Generally, the number postfixed to your team name represents where your slot is in the schedule. 

Teams will have 3 minutes to demo working code, followed by a 2 minute Q&A session with the judges. 

## [Best in Show Judging (Second Round)](#best-in-show-judging-second-round)
If your project wins the first round, your project will move onto the second round to determine best in show. This round will pit the winning project across the four categories against eachother in front of a panel of judges with a variety of experiences and backgrounds.

While the final round judges will have seen the rubric, we are asking them to consider each project using their backgrounds and insights to determine the one that best solves the issue at heart for the Sustainable Development Goal.

## [Additional Repositories](#additional-repositories)

The following repositories contain information specific to each sustainable development goal. Please visit the one assigned to your team to download a copy of the challenge datasets, see more information about the goal, etc. 

+ [Quality Education](https://github.com/charlestondigitalhubhackathon/Quality-Education)
+ [Affordable & Clean Energy](https://github.com/charlestondigitalhubhackathon/Affordable-and-Clean-Energy)
+ [Climate Action](https://github.com/charlestondigitalhubhackathon/Climate-Action)
+ [Sustainable Cities & Communities](https://github.com/charlestondigitalhubhackathon/Sustainable-Cities-and-Communities)

## [Database Backups](#database-backups)

### [Restoring a Database using recommended database tool](#restoring-a-database-using-recommended-database-tool)

Download [DBeaver Community](https://dbeaver.io/download/) (supported on Mac, Windows, multi SQL variants). 

If you have already connected to your SQL instance and have your database(s) created already, you can restore a database via: right clicking the target database navigating to `Tools > Restore database`, and choosing the database backup file corresponding to the target database.

 If you haven't connected to your SQL instance and have not created your database(s) already, follow the steps below.

### [Restoring a Database using command line](#restoring-a-database-using-command-line)
 
> __NOTE__: This assumes you have not configured your machine locally with your SQL of choice or any database backups

#### MySQL
This procedure explains how to install and configure [MySQL](https://www.mysql.com) locally for database backups using [Homebrew](http://brew.sh) on macOS 

##### 1. Install Homebrew
Installing Homebrew via opening Terminal and entering :  
 `$  /usr/bin/ruby -e "$(curl -fsSL https://raw.githubusercontent.com/Homebrew/install/master/install)"`
 
##### 2. Install MySQL
At this time of writing, Homebrew has MySQL version **8.0.15** as default formulae in its main repository :

Enter the following command : `$ brew info mysql`  
> Expected output: **mysql: stable 8.0.15 (bottled)**

To install MySQL enter : `$ brew install mysql`

##### 3. Start MySQL

Start your local MySQL instance via: `mysql.server start`
> Expected output: 
>```
>Starting MySQL
> SUCCESS!
> ```
##### 4. Login to MySQL
Login as a root user to MySQL via: `mysql -uroot`
> Expected output:
> ```
> Welcome to the MySQL monitor.  Commands end with ; or \g.
>Your MySQL connection id is 9
>Server version: 8.0.15 Homebrew
>
>Copyright (c) 2000, 2019, Oracle and/or its affiliates. All rights reserved.
>
>Oracle is a registered trademark of Oracle Corporation and/or its
>affiliates. Other names may be trademarks of their respective
>owners.
>
>Type 'help;' or '\h' for help. Type '\c' to clear the current input >statement.
>
>mysql>
>```

##### 5. Restore a MySQL database

1. Within the mysql prompt, to restore a MySQL database, first create the target database in the backup file via:

	`create database <NAME-OF-DATABASE-IN-BACKUP-FILE>;`
	> For example, if the name of the database in the backup file was `international_energy_statistics`,  the mysql prompt would look like so:
	> 
	> ```mysql> create database international_energy_statistics;```
3.  Exit the prompt via `command` + `D`, then execute the following to restore the database: 

	`mysql -uroot <NAME-OF-DATABASE-IN-BACKUP-FILE> <NAME-OF-BACKUP-FILE>.sql`
	> For example, if the name of the database in the backup file was `international_energy_statistics` and the name of the backup is `international_energy_statistics_mysql.sql`,  the correct command would be: 
	`mysql -uroot international_energy_statistics < international_energy_statistics_mysql.sql`


## Questions?

Ask your question in the [#helpline](https://hackathon2019.slack.com/messages/CF4TJ01NU) channel on the Hackathon 2019 Slack. 
