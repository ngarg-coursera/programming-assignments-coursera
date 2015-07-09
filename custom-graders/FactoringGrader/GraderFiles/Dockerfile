# Fetch ubuntu docker image supporting java.
# TODO: Use 'FROM ubuntu:latest' and install java on top.
FROM java:8

# Make a directory where your files will be stored
RUN mkdir /grader

# Below commands copy the files that you need to put in your docker image

COPY executeGrader.sh /grader/executeGrader.sh
COPY testCases.txt /grader/testCases.txt
COPY solution.txt /grader/solution.txt
COPY Grader.java /grader/Grader.java

# Important: Docker images are run without root access on our platforms. Its important to setup permissions accordingly.
# Executable permissions: Required to execute executeGrader.sh
# Read permissions: Required to read testCases.txt, solution.txt, Grader.java
# Write permissions: Required to store the compiled java files
RUN chmod a+rwx -R /grader/

# Setup the command that will be invoked when your docker image is run.
ENTRYPOINT ["./grader/executeGrader.sh"]