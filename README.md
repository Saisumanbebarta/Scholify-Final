# intel-oneAPI

#### Team Name - Vintana
#### Problem Statement - 
The current job market is highly competitive, and it can be difficult for students to stand out from the crowd. Recruiters are often overwhelmed by the number of resumes they receive, and they may not have the time to carefully review each one. As a result, many qualified students are not getting the jobs they deserve.
#### Team Leader Email - bajrangbali2008@gmail.com

## A Brief of the Prototype:
  A software that will revolutionize the education job market. Our software collects all of the data from a student's life(career) and gives the results to the     recruiter & the HR executives about the student's skills. This data includes the student's academic transcript, extracurricular activities, work experience, and   professional skills. Our software can help students get noticed by recruiters and increase their chances of getting a job. It can also help students identify     their strengths and weaknesses, and develop a plan to improve their skills.
  https://github.com/Saisumanbebarta/Scholify-Final/assets/52620952/f20ab6f7-2d64-476b-b8a2-354d2fb39fd6)

  
## Tech Stack: 
   sklearn.tree,
   pandas,
   joblib
## Step-by-Step Code Execution Instructions:
  import pandas as pd
  from sklearn.tree import DecisionTreeClassifier
  import joblib
  #importing the libs
  
  # ds = pd.read_csv("IntelSC.csv")
# X = ds.drop(columns=['Overall','Mindset .1','Creativity','Personality.1','Timing'])
# y = ds['Overall']

# model = DecisionTreeClassifier()
# model.fit(X,y)
  
  
# excel to input data(Converts excel rows to list)
a = pd.read_excel("inputtrial1data.xlsx")
FID = []
NameCol = list(a['Name'])
AcademicsCol = list(a['Academics'])
CreativityCol = list(a['Creativity '])
LeadershipCol = list(a['Leadership '])
MindsetCol = list(a['Mindset '])
TimingCol = list(a['Timing '])
PersonalityCol = list(a['Personality'])
SCHOOLECCol = list(a['SCHOOL EC'])
OUTSIDEECCol = list(a['OUTSIDE EC'])
for x in range(len(NameCol)):
    FID.append(
        [NameCol[x], AcademicsCol[x], CreativityCol[x], LeadershipCol[x], LeadershipCol[x], MindsetCol[x], TimingCol[x],
         PersonalityCol[x], SCHOOLECCol[x], OUTSIDEECCol[x]])
         
model = joblib.load('scholifydata.joblib')#Loading the trained model 

while True:
    s = int(input("Enter values for result output of Overall, Mindset, Creativity, Personality,Timing press 0,1,2,3,4: "))
    if s == 0:
        for z in FID:
            predict = model.predict([[z[1], z[2], z[3], z[4], z[5], z[6], z[7], z[8]]]) #Predicting the output
            pl = list(predict)
            if pl[0] == 'Selected':
                print(f"{z[0]} {pl[0]} in overall") 
    elif s == 1:
        for z1 in FID:
            if z1[1] >= 20:
                print(f"{z1[0]} Selected For Mindset")
    elif s == 2:
        for z2 in FID:
            if z2[2] >= 20:
                print(f"{z2[0]} Selected For Creativity")
    elif s == 3:
        for z3 in FID:
            if z3[7] >= 90:
                print(f"{z3[0]} Selected For Personality")
    elif s == 4:
        for z4 in FID:
            if z4[6] >= 40:
                print(f"{z4[0]} Selected For Timing")

  
## What I Learned:
   We learnt a lot from making this project. 

 Here are some of the most important lessons we learnt:- 

 The importance of planning. :- Before we started working on the project, we took some time to plan out what we wanted to solve. This helped us to stay on track and avoid getting overwhelmed.

 The importance of communication :- We communicated with our team members regularly throughout the project. This helped us to stay on the same page and resolve any issues that arose.
 The importance of iteration :- We didn't expect to get everything right the first time around. We made changes to our code and design as we went along, and this helped us to improve the project over time.

 The importance of perseverance :- There were times when we felt like giving up on the project. But we persevered, and we are glad thag we did it. We are proud of what we are able to accomplish.

We are grateful for the opportunity to have worked on this project. We learnt a lot, and we are excited to apply what we learnt to future projects.
