# Character-Image-Classifier
Classifying images into four classes (Minion, Mickey Mouse, Simson, Poo)

After saving a trained model,

use google cloud platfor - app engine to deploy and launch the app in the browser.

( way to deploy : https://course.fast.ai/deployment_google_app_engine.html )




# [ SOLVE THE ERRORS WHEN RUNNING THE LINE 
#    'gcloud app deploy' ]
1. Go into file 'app.yaml' and add the below code
resources:
    memory_gb: 4 
2. Uploade the model(.pth) in dropbox and create a link
3. https://www.dropbox.com/s/yw21apbp3yzvwwl/stage-2.pth?dl=0 
   when you get this kind of link ->  change =0 to =1
4. Go into 'server.py'
   Change the value of the  model_file_url variable into the link that has been changed in 3.
5. Leave the  value of model_file_name as 'model'
6. Change the value in classes as the classes the user made to train the model (classes = ["Poo","Mickey","Simson","Minion"])
7. Never touch the other codes in 'server.py'
8. Go to models directory (Use 'cd models') --> Delete all the files except 'models.md'
9. Download the model the user is going to use. ( Use "wget (changed link(same as the linnk changed in 3.)" )
10. Chnage the downloaded model name into 'model.pth' (Use 'cp stage-1.pth?dl=2 model.pth')
11. Go to the '~/gitrepo(name)/' directory and run 'gcloud app deploy'
