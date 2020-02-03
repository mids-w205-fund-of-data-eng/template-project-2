# Project 2: Tracking User Activity

In this project, you work at an ed tech firm. You've created a service that
delivers assessments, and now lots of different customers (e.g., Pearson) want
to publish their assessments on it. You need to get ready for data scientists
who work for these customers to run queries on the data. 

# Tasks

Prepare the infrastructure to land the data in the form and structure it needs
to be to be queried.  You will need to:

- Publish and consume messages with Kafka
- Use Spark to transform the messages. 
- Use Spark to transform the messages so that you can land them in HDFS

You should include your `docker-compose.yml` used for spinning the pipeline.

Also, include the history of your console by running
```
history > <user-name>-history.txt
```

You can either run Spark through the command line or use a notebook. If you use
the command line, add an annotated mardown file where you present your results,
tools used, and explanations of the commands that you use. 

You should be able to query your data at the end. 

In order to show the data scientists at these other companies the kinds of data
that they will have access to, decide on 1 to 3 basic business questions that
you believe they might need to answer about these data.

## What you turn in
- Your history file (see above)
- A report either as a markdown file or a jupyter notebook
- Any other files needed for the project, e.g., your docker-compose.yml, scripts used, etc
- Make sure you have a good structure in your git repo and explain your repo in the README.

The report should describe your queries and spark SQL to answer business questions that you select. Describe your assumptions, your thinking, what the parts of the pipeline do. What is given? What do you set up yourself? Talk about the data. What issues do you find with the data? Do you find ways to solve it? How? If not describe what the problem is.

## Data

To get the data, run 
```
curl -L -o assessment-attempts-20180128-121051-nested.json https://goo.gl/ME6hjp`
```

Note on the data: This dataset is much more complicated than the one we'll
cover in the live sessions. It is a nested JSON file, where you need to unwrap it
carefully to understand what's really being displayed. There are many fields
that are not that important for your analysis, so don't be afraid of not using
them. The main problem will be the multiple questions field. We recommend for
you to read schema implementation in Spark [Here is the documenation from
Apache](https://spark.apache.org/docs/2.3.0/sql-programming-guide.html)

Here are some example questions that would be useful to know, but you again, you choose your own (1 to 3).These examples are meant to get you started/thinking.

1. How many assesstments are in the dataset?
2. What's the name of your Kafka topic? How did you come up with that name?
3. How many people took *Learning Git*?
4. What are the average grades for each course with its standard deviation?
5. What is the least common course taken? And the most common?
6. Add any query(ies) you think will help the data science team
