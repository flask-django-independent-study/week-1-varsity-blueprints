# Week 1 Varsity | Blueprints

### Follow the TODOs in TODO.md to complete this app

If you have questions, you aren't the only one! Check these out:

### FAQ's:

1. Q: Why do I need an `__init__.py` file in each folder?

   A: For Flask to recognize a folder as a package, you need an `__init__.py` file. It's okay if it's blank, this file just tells Flask to look into this folder. Your static folder, for example, doesn't need this, because Flask looks for static for different kinds of files.

2. Q: Why can't I just have a route/ folder with a main.py and party.py? Why do I need seperate folders? Is this just best     
   practice?

   A: You could just have a folder with these blueprints! The reason that we're separating these into separate folders is to get you used to using packages and blueprints. This is helpful in larger projects to sandbox your routes, utility files, and class modules into folders of "like" things. It makes sense to keep the user route file in the same folder as the user utils.py, and the module that you use to define your User class.

3. Q: On a larger project is it bad to have a template folder in each blueprint folder?

   A: This is not a bad idea! This is a super great way to further clarify and categorize your files in your project, to keep yourself and your team sane when handling lots of templates, routes and files! I would just recommend looking into how Flask looks for templates so that you can avoid things getting buggy if you need to move things around:
   https://python-adv-web-apps.readthedocs.io/en/latest/flask3.html#folder-structure-for-a-flask-app
   https://stackoverflow.com/questions/13598363/how-to-dynamically-select-template-directory-to-be-used-in-flask#13598612

4. Q: Is it best practice to use a url prefix for all blueprints or can use one only when I think it's necessary?

   A: This is really up to you, your team, and your project to decide what's best. You can use url_prefix as you see fit when you register your blueprints!

5. Q: Is it best practice to have the app start using __init__.py?

   A: First I want to clarify what you mean by "start". In `__init__.py` we "initialize" the Flask application. This means that we create our app:
   ```python
   app = Flask(__name__)
   ```
   We want to run our app in our app.py folder, which, if you remember, should stay in your project's root folder. Running the app looks like this:
   ```python
   if __name__ == "main":
     app.run()
   ```
   So yes, it is best practice to initialize the application in `__init__.py`. However, it's best practice to run the app from app.py.

6. Q: Is it possible to store `@app.error_handler()` routes inside their own blueprint?

   A: It is totally possible, and not a bad idea! You'll want to make sure that the folder you store these in (if you have them in a separate folder), contains an `__init__.py` file, and that you're registering the blueprint correctly. For clarity, you could call the blueprint something like "error" so that your route would look like: `@error.error_handler()`. This will help you debug and avoid naming issues or confusion.


If you don't see your question here, feel free to contact Starlight or Sid via Slack.

If you find a typo, or other issue with the repository, please add an issue so that we can address it!

Thank you for your feedback!
