# Document Tag Generator

---


# Table of Contents
1. [Introduction](#introduction)
2. [Local Installation](#local-installation )
3. [Links](#links)
4. [System Organization](#architecture)
---

# Introduction
### ✨ Problem
The project website of the Department of Computer Engineering currently has nearly 150 projects. These projects are categorized by only batches and subjectwise. Also, some of the projects have some tags but some of them are not relevant to those projects. Also, some projects do not have any tags. Currently, users can search projects by keywords, but those keywords are derived only from project descriptions.

![Screenshot 2022-03-14 222117](https://user-images.githubusercontent.com/73388013/158224737-a8803bc3-081b-4ecd-8c24-927381c8f04c.png)


* [Project Website](https://projects.ce.pdn.ac.lk/)


### ✨ Our goal
Our goal is to generate relevant tags for each project according to the description of the projects and other valid data available on the project pages. 


### ✨ Solution
Our plan is to build an ML model to generate relevant tags. The data needed to implement the ML model is retrieved from the project pages and the project repositories. To get all details (link to the repositories and project pages + other details) of the project pages and repositories API of the website is used. To get the data from the project pages a scraping tool will be used.
* [API repository](https://github.com/cepdnaclk/projects.ce.pdn.ac.lk)
* [API site](https://api.ce.pdn.ac.lk/)

---

<br/>
<br/>

# Local Installation 

The site is built by Jekyll Builder and hosted on GitHub pages.
* Fork the repository and clone that into your local machine.
* Follow the  build instruction  to install the necessary dependencies to run the Jekyll builder in your local machine
##**Build Instruction**
---
```
gem install just-the-docs
gem install jekyll-sitemap
bundle exec just-the-docs rake search:init jekyll-sitemap
```
---
*Note: - If you face any dependency/version issue follow the instruction in [this](https://github.com/rbenv/rbenv) link to downgrade/upgrade the versions*

**current version is 2.7.1**
```
rbenv install 2.7.1
rbnev global 2.7.1
```
For the API install this additional python packages
```
pip install requests
cd ./python_scripts/
python3 stat_script.py
```

<br/>
<br/>

# Architecture
___

___![image](https://user-images.githubusercontent.com/73387610/158681110-130895f6-e7b0-41f9-a79c-a430109eeb8e.png)

___![architecture](https://user-images.githubusercontent.com/73387610/158680952-006d1fe0-232e-4c90-b506-8bebe55ea301.jpeg)


In department projects website, frontend, and backend are already implemented. According to the current implementation, users can search projects using tags. But the tagging was done using a simple algorithm such that it checks whether the project description contains the searching tag. Our goal is to implement a machine learning model, which can do tagging in a much better way.


In order to train the machine learning model we need a data set that contains the details of the projects. We hope to use project descriptions, project repositories, and project pages to generate the data set. By using this dataset, we have to train a good ML model, which can tag projects in the department website in a better way. 

After implementing the ML model, we have to integrate it with the backend of the department website. Then we need to run the ML model to generate tags and those tags should be stored in a [json file] inside the [backend repository].

Backend of the department project website can be accessed by a [API]. It contains a [end point] to access that json file which contains all the generated tags and their corresponding tags. When a user search a project using tags, by using tags file, relevant projects will be shown to the user.

When new project is added to the department project website, we need to run the ML model again and update the tags file. GitHub actions can be used for that. 

Since project pages and project repositories are update regularly, we hope to run the ML model weekly. 

<br></br>
___
***Project Owner : Mr. Nuwan Jaliyagoda*<br>
*Scrum Master: Mr. Thushara Bandara***
___
<br/>

## ✨Our Team
#### E/17/100 - Gunathilaka R.M.S.M
#### E/17/246 - Perera K.S.D
#### E/17/284 - Rathnayaka R.L.D.A.S




[//]: # 
[API]: <https://api.ce.pdn.ac.lk/docs/projects/>
[end point]: <https://api.ce.pdn.ac.lk/projects/v1/filter/tags/>
[json file]: <https://github.com/SachinthaMadhushanka/api.ce.pdn.ac.lk/blob/main/projects/v1/filter/tags/index.json>
[backend repository]: <https://github.com/SachinthaMadhushanka/api.ce.pdn.ac.lk>


.....

## Links

- [Project Repository](https://github.com/cepdnaclk/e17-co328-Document-Tag-Generator/)
- [Project Page](https://cepdnaclk.github.io/e17-co328-Document-Tag-Generator/)
- [Department of Computer Engineering](http://www.ce.pdn.ac.lk/)
- [University of Peradeniya](https://eng.pdn.ac.lk/)


[//]: # (Please refer this to learn more about Markdown syntax)
[//]: # (https://github.com/adam-p/markdown-here/wiki/Markdown-Cheatsheet)
