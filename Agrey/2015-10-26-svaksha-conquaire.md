+ [OBJECTIVES](#objectives)
+ [TECHNOLOGY](#technology)
   + [Continuous Integration](#continuous-integration)        
        + [Configuration Management](#configuration-management)
        + [TDD](#tdd)
   + [Computational Reproducibility - Docker](#computational-reproducibility-docker)
   + [Computational Reproducibility - Reprozip](#computational-reproducibility-reprozip)
   + [Database](#database)
   + [DVCS - Git GitLab](#dvcs-git-gitlab)
   + [Framework - Data Quality Assesment](#framework-data-quality-assesment)
        + [Bubbles](#bubbles)
   + [Framework - Web](#framework-web)
   + [Messaging Lib](#messaging-lib)
   + [Visualization](#visualization)
   + [Communication - Internal](#communication-internal)
   
====

# OBJECTIVES
+ Infrastructure to support continuous research data quality monitoring.
+ Infrastructure to host data and implement corresponding workflows.
+ OpenData - Make the data publicly available to allow reproduction of the computational analysis.
+ Ensure research data quality and reproducibility along the whole research lifecycle. 

### Guidelines
Other useful projects to remember: 
+ https://github.com/swcarpentry/good-enough-practices-in-scientific-computing/blob/gh-pages/index.md is an ongoing paper being written about best practices in scientific computing with many useful tips like normalizing data, automation, writing small funtions, etc.. 
+ The standardization of research methodologies and processes will help the data quality monitoring process, create reusable datasets and reproducable research.

General development tips for choosing a FOSS stack :
+ Choose the stack whose programming language is popular across domains (web-dev, TDD and scientific development) as they have good library support for all the different domains. Besides, these will most likely be well-maintained due to their popularity.
+ Mixing programming languages is inevitable for certain tasks but more than 2 or 3 will become a maintenance nightmare over time - Dependency hell and future maintenance issues, if any.
+ Must be easy to learn - in terms of future development and maintenance issues.
+ Existing cross-lang API wrappers must be maintained in future too.
+ Good community support - very essential for bugs or help wanted situations. 
   + For external project libs: They must have a mailing list, irc-channel and bug tracker with some core-devs interacting with the general public otherwise its hard to get help.
+ Good documentation :: Locally, where ever possible provide links to documentation and other helpful links in a wiki or a git-based system that can be easily updated (via markdown document files), say, the public github wiki system based on git. Alternatively, a self-hosted [private wiki](https://github.com/kahun/awesome-sysadmin#wikis) can also be used but it creates additional overheads of regular maintenence and data backups, hence, the public git-based system is more suitable.

====

# TECHNOLOGY

The Hardware infrastructure & servers for the below mentioned FOSS stack will run on self-hosted server farms. The idea is to leverage existing free software stack for the similarity in features and other specifications and their reuse potential as per the Licenses they are released under. 

Here is a quick outline for the web frameworks, CI, messaging libs, and other backend stack options that are currently available and/or popular:

## [Continuous Integration](https://en.wikipedia.org/wiki/Continuous_integration)

+ [GitLab Continuous Integration](https://about.gitlab.com/gitlab-ci/): Integrated CI to test, build and deploy your code on GitLab. [Volkswagen](https://github.com/auchenberg/volkswagen) detects when your tests are being run in a CI server, and makes them pass. Gitlab CI is supported.
+ [BuildBot](https://en.wikipedia.org/wiki/Buildbot), is written in Python on top of the Twisted libraries.
+ [Dockunit.io](https://dockunit.io/) is a GPL licensed, cross-platform experiment in Docker based integration tests [CI platform](https://github.com/dockunit/platform) that integrates with github.
+ https://github.com/kahun/awesome-sysadmin#continuous-integration--continuous-deployment
+ [Tox](http://tox.readthedocs.org/en/latest/), an automation tool providing packaging, testing and deployment of Python software.
+ [Rake](https://en.wikipedia.org/wiki/Rake_%28software%29), a Ruby tool for software task management and build automation.
+ [Capistrano](https://en.wikipedia.org/wiki/Capistrano_%28software%29), an open source Ruby tool for running scripts on multiple servers to deploy web applications.
+ _NON-FOSS_:
   + [Travis-CI](https://travis-ci.org/), free only for open source projects - integrates with github, gitlab status is not known.


### Configuration Management
+ Ansible (.py)
  + + [julia-ansible-scripts](https://github.com/staticfloat/julia-ansible-scripts) :: Various julia ansible scripts for provisioning servers, buildbots etc... 
+ Saltstack (.py)
+ Puppet (.rb)
+ Chef (.rb) : https://github.com/obazoud/awesome-chef

### TDD
+ Julia: https://github.com/svaksha/Julia.jl/blob/master/QA.md
+ Python: https://github.com/svaksha/pythonidae/blob/master/QA.md
+ Ruby: 
   * https://github.com/sdogruyol/awesome-ruby#testing
   * https://github.com/markets/awesome-ruby#testing


## Database
Depending on the researcher's data types, support which of the following DB's(?):

#### RDBMS
+ [Relational DBMS](https://github.com/kahun/awesome-sysadmin#rdbms) : Postgres, MariaDB, ..

#### NoSQL
+ NoSQL : Is it document/ graph/ array based?
   - MongoDB
   - [Redis](http://redis.io/), is an open source (BSD licensed), in-memory data structure store, used as database, cache and message broker.
+ Array-based DB (SciDB).
+ https://github.com/kahun/awesome-sysadmin#nosql

#### Distributed File Systems
+ HDF5
+ https://github.com/kahun/awesome-sysadmin#distributed-filesystems


## DVCS - Git GitLab
+ Git is the DVCS running the backend system to store data running a web-application to upload scripts, etc..
+ GIT-based Free and open source DVCS hosting service:
   + https://notabug.org
   + https://gitlab.com
+ For advanced features of git, non-CS researchers would need to be provided with help and documentation to enable them to use the tools smoothly. 


## Computational Reproducibility - [Docker](https://docker.com)
VM's are memory-intensive and harder to setup besides varying across distros. Hence, docker containers are a safer method to ensure easy reproducability without massive system or data changes.
+ Containerize the research data that is syntactically well-formed, has __meta tags__, is __cleaned up__ and __ready for reuse__ or for __testing and revalidating__ already published research. 
+ By creating __docker instances__ for the pockets of research that a scientist wishes to share, one can easily __reproduce the same environment instance in which the original computation was carried out__.
+ Write simple scripts to simplify the deployment of local code which will ease the worktable. (see, https://github.com/svaksha/yaksha)
+ From 2015November, docker will upgrade the autobuilds functionality and infrastructure to offer dynamic matching of git branches and tags as well as faster builds. This means, the Docker Hub build system can be configured to dynamically trigger builds when the team creates new git branches and tags. For example, if you you create a new git feature branch named `new-feature`, the build system will automatically build a docker image tagged as `new-feature`. This allows Docker Hub autobuilds to fit seamlessly into your development and deployment workflow and it is configurable to support full dynamic matches, regex filters, or simple static matches.

###### Resources
+ Collection of [docker images](https://github.com/hwuethrich/docker-images) and an [index](https://hub.docker.com/u/hwuethrich/).


## Computational Reproducibility - [Reprozip](https://vida-nyu.github.io/reprozip/)
+ Computational reproducibility is hard to achieve due to the tedious scientific paper reviewing process which requires authors to generate a compendium that encapsulates all the inputs needed to correctly reproduce their experiments: the data, a complete specification of the experiment and its steps, and information about the originating computational environment (OS, hardware architecture, and library dependencies). 
+ Various OS introduce a dependency hell making it an impossible task to get the same computational environment across all distros even if they use similar tools.
+ Reprozip is almost like a virtual machine, but maybe smaller than a VM and most importantly it uses vagrant and docker and runs on anaconda (2.x).
+ Gives the user an isolated sandbox to test their research while allowing others to use the tools used by the scientist to reproduce the analytic procedures (e.g. scripts, spreadsheets, etc.) that were used to process or analyse the research data. 
+ There was a package conflict bug for Python-3.x within anaconda, now fixed : https://github.com/ViDA-NYU/reprozip/issues/157

   
## Framework - Data Quality Assesment
+ Quality checks on data for range and errors.
+ Domain-independent tests check syntactic wellformedness.
+ Validate data according to schemas. _Task_: Integrate validation scripts into platform.
+ Provision of metadata and consistent use of vocabulary.
+ Open availability of scripts for automation tasks.
+ Domain-specific quality checks will be implemented and integrated into the framework as services in a plug-in framework. 

The Foss tools available are : 

### [Bubbles](http://bubbles.databrewery.org/index.html)
+ A Python framework for data processing and data quality measurement.
+ Implements basic concepts like abstract data objects, operations and dynamic operation dispatch. 
+ Repo: https://github.com/Stiivi/bubbles
+ License: MIT.

###### NOTES
+ _Pros_:
   * A Python framework reduces the dependency hell between various scientific libs when researchers also use Python for their analyical work, thereby reducing devops infrastructure maintenance.
   * The scientific library ecosystem has excellent support for [Astronomy & GIS](https://github.com/svaksha/pythonidae/blob/master/Earth-Science.md), [Biology](https://github.com/svaksha/pythonidae/blob/master/Biology.md), [Chemistry](https://github.com/svaksha/pythonidae/blob/master/Chemistry.md), [Physics](https://github.com/svaksha/pythonidae/blob/master/Physics.md), [Math](https://github.com/svaksha/pythonidae/blob/master/Mathematics.md), [Statistics](https://github.com/svaksha/pythonidae/blob/master/Statistics.md), and other scientific disciplines.
+ _Cons_:
   * The packaging ecosystem can be hard for a newbie to navigate. Hence, the service adoption can be increased by automating simple tasks and providing this information to all the researchers.



## Framework - Web
The most popular web frameworks to consider are:

+ Django (.py) : [List of Django libs](https://github.com/rosarior/awesome-django).
   - Django is better suited to CMS-like tasks.
   - Strong and popular with many django-libs.
   - Good community support, project wont vanish or cease development.
   - More explicit than Ruby/RoR.
+ RoR (.rb)
   - Rails is more general-purpose.
   - Good community support and a popular web tool.
   - Fast prototyping and easy to get webapps up and running in a very quick time BUT has too much inbuilt magic.
   - Many high quality gems (libs) out there that would serve many common requirements for web development.
+ [Volt](http://voltframework.com/) (.rb), https://github.com/voltrb/volt
   - New ruby framework.
   - Not sure about the level of community support, libs and documentation.


## Messaging Lib
+ RabbitMQ
+ ZeroMQ
+ https://github.com/kahun/awesome-sysadmin#queuing

## Visualization 
Toolkits for visualization are available in the following languages:
+ JS: [D3.js](https://github.com/wbkd/awesome-d3) is a list of D3 libraries, plugins and utilities.
+ Julia: [Visualization](https://github.com/svaksha/Julia.jl/blob/master/Computer-Graphics.md#infographics) libs.
+ Python: [Bokeh, Matplotlib, etc..](https://github.com/svaksha/pythonidae/blob/master/Computer-Graphics.md#infographics).


## Communication - Internal 
Options for internal communication/ help channel:
+ Discourse.org :: A mailing list integrated with a Forum-like UI with useful features like topic tags, etc..
   * From: https://groups.google.com/forum/#!topic/mozilla.moss/f8dmpPE4W2M, they plan to add features for "complete mailing list parity". Discourse already has a lot of overlap with mailing lists and supports creating and responding to topics by e-mail in the "mailing list mode" that e-mails every new topic to opt-in subscribers, and there's upcoming support for "email profiles", letting users join a discussion by e-mail without having to sign up for a regular Discourse account. Complete ML parity will allow users to participate in discussions on a Discourse forum in exactly the same way as they would on a mailing list. That way, an organisation's disparate mailing lists can all be run on a single (or just a few, for larger organisations) Discourse instance, keeping all longform communication (i.e. not chat) in one central place, whilst allowing users to choose between a mailing list or forum interface to participate.

----

