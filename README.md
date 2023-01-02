# BPG

**Setup**
1. install docker (including docker-compose)
2. navigate to NLP/webapp
3. run "docker-compose up" or "docker-compose up --build"
    - If there are any problems, try "docker-compose down --volumes" or "docker kill $(docker ps -q)"
    - the build process may take a while
4. Once done you can navigate to "localhost:5000" in your browser

**Using the webapp**
1. upload your document (.docx)
    - be sure that your document follows the needed structure
    - you can also use our example (example-computational-linguistics.docx in the Documentation-Folder)
    - the question generation can take 1-3min depending on your hardware
2. now you can use the learning and exercise pages as much as you want!

** **
**If you want to take a closer look at the database...** 
#### ...you can use the tool adminer that we have implented in the container
1. navigate to "localhost:1234" in your browser
2. choose "PostgreSQL"
3. log in withe following data:
    - User: "postgres"
    - Password: "securepwd"

**Documentation**
- Within the documents "upload-prozess.png" and "exercise-prozess.png", you can see a flowchart for the upload- and exercise-process
- The document "Präsentation" is corresponding to the presentation held on 18.01.2022
- There is an example-document to check the upload-process, named example-computational-linguistics.docx: 


**Answer-Checker**
- In this part the user input is compared and evaluated with the actual solutions (with the help of TF-IDF)
- The evaluation is then used to decide whether the answer is correct or incorrect (If the score is >= 50% then the answer is right, otherwise the answer is wrong)
- Libraries used in the process: Pandas, Numpy and Sklearn

- Process stages:
1. Get the answer from the User and the actual answer
2. The TfidfVectorizer gets created (it is important that the stop words are rated lower, as they are not meaningful for the calculation of the score)
3. The model is applied to the two texts
4. The similarity of the texts are then calculated
5. Based on the score, it is then decided whether the answer is wrong or right 

