# Building AI/ML Products for Data Scientists
The last decade has been phenomenal in the growth of Data Science as a discipline. Enormous strides have been made in almost all phases of data science that resulted in some of biggest innovations in recent times.
As the exploration phase matures there is increasing focus on moving these data science findings into products and solutions that can be usable in market. These solutions and products needs to be reliable, resilient ,scalable and most important of all , stand test of time.
Software development practices have been around for more than 40 years now , and software delivery models has gone through multiple phases and has stabilized enough that more and more of our day to day activities are software driven.
As AI/ML teams come out of a prototyping/pilot phase to a product development phase, here are a few pointers customized to a data science project, to build a reliable AI/ML based products.
## Understand the difference between prototype and a software product
More often than not many data science projects today start and end as a pilot or prototype never being deployed to larger audience. With a pilot/prototype, the output is needed in a really short time, and the goal is to getting things to work rather than maintainability or reliability.
On the other hand when you build a AI/ML product consumed by millions of users, the model that you build or the software you build around it will be used by the customers for atleast 3–4 years, hence the goal here is not just to get the functionality in place but ensure that its reliable, scalable and maintainable.
A minor additional loop in your inference code might not be a big issue while you are trying to build a prototype for quick use, but it could spiral into a serious memory issue when scaled up and used for a longer time.
Understanding the difference between the two is fundemental to building a resilient AI/ML solution.
## Any module you write should be self testable
Just like any module in a software engineering life cycle, any component built in a ML lifecycle must be self testable and be confident of its working without a dependency on the consumers of the module. For e.g a code that an ML engineer writes to replace missing data with mean of the column should be testable independent of the nature of data or the nature of model selected
## Integrate and deploy as soon and as often as possible
More often than not the data science development is still a fractured process where the model comes out first after multiple iterations and the MLOps part comes later as an after thought.
It is always better to test out the end to end pipeline even with a baseline model, then continue to iterate to better the model . This ensures we can fail fast and fail often.
## Always maintain a single source of truth (SST) for everything
A quite overlooked activity in any data science development project is the need to have a single source of truth(SST). This can pertain to any component in the development.
Have a single set of code versioned and developed from a GitHub repository from where the entire team runs their code, rather than having separate copies in each of the dev machine
Have a single point from where the data set is versioned ,controlled and downloaded for development by the entire team.
This will solve a host of integration issues down the line
## Code defensively (Whatever will go wrong will go wrong)
Model development and feature engineering happens with a assumption that the data would be in a specific format. This would be the basis on which data cleaning happens as well. But more often than not, data and values might not be what you might expect to be. A single bad data could throw your pipeline off gear. Hence it is essential to anticipate this failure and code defensively
## Do code reviews
Machine learning pipelines have greater chances of failures due to cascading data processing issues, that percolate and affect the model performance
Rectifying simple logical mistakes in code can help improve the performance of the model to a great extent.
Doing regular code reviews ensures to keep this in check
## “Fix and prevent” bugs
Everytime you find a bug either in the model code or the data processing code or the inference code, ensure you not only fix it but also put in loggings and other protections in place that it prevents future bugs due to manual errors from cropping up in the area.
## Never hard code
While its convenient to hardcode API keys and data access keys in notebook during the exploration phase, it can be a dangerous practice since while those codes are moved to production a single unencrypted piece of secure information can jeopardize and put the entire application in peril.
## Keep code future friendly
Even while creating the code in a notebook or in a python script, ensure that it is future friendly. With lot of new libraries and innovations coming in , the code changes at a rapid pace. But it is important to capture the design considerations and the original intent of writing a code in a specific way , either can extensive comments or as unit test codes.
## Document all decisions and make available to everyone in the team
Data science teams are more siloed than traditional development teams, hence any decisions that you make, say choosing a specific hyperparameter due to a specific reason or dropping a feature, must be made known to the entire team.
Modern collaboration tools like MS Teams, Slack helps you making this easier. This would be a as well preferred as it is searchable and understandable as opposed to traditional MS Word based documentation
## Use the right tool for the right purpose
People are creatures of habit and would default to tools they are comfortable in for all purposes . In the age of SaaS and fast changing technologies, using the same tool for all purposes and force fitting it to do things that is not meant to be is self defeating and time consuming. say for e.g. AWS Sagemaker is a great tool to develop and deploy models, but if you are more concerned about doing big data processing, sagemaker while can is not the best tool to do that. AWS Glue or Spark might suit you better.
## Do not Repeat Yourself (DRY)
A lot of data scientists in the world are doing the same work over and over again. Activities like stop words removal ,lemmatizing or writing a pytorch boiler plate training code are repetitive and non productive. These must be avoided. Themes like Feature Stores, tools like Pytorch lightning are a good step towards implementing DRY in your data science project
## Maintain the sanctity of production
While making modifications to a live and production systems , for say, adding a new feature or modifying a hyper parameter, directly on the production system might be convinient, it is always a bad idea.Always ensure and respect the sancitity of production and changes should be done after thorough testing in other stacks
## Make it work and then make it great
Data science projects are a never ending iterative process. Though its a noble thought to aim for a close to human level accuracy on any machine learning model, it is important to not to go overboard with it lest the project remains in a development hell and the model never sees the light of the day.