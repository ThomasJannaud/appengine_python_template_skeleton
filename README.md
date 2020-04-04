# Google AppEngine: Minimal skeleton of a Python server
A minimal Flask server serving static HTML pages that deploys seamlessly to Google AppEngine, no troubleshooting needed.

As of April 2020, GAE runs your server for free as long as you are under a million visits a day or so. You only need to purchase a domain name, and that's optional if you can be content with PROJECTNAME.appspot.com.

# Instructions

Run your server locally. When you are happy with the result, deploy to Google AppEngine (you will need to setup that account) and your website will be on internet.

## Run locally

Most of this skeleton consists in a minimal Flask server for you to customize.  
Edit the webpages ([Jinja|https://jinja.palletsprojects.com/] templates) in the `Templates/` folder and style them in the `static/` folder.  
Change the logic in `page_handler.py` to serve more urls.  

```
git clone https://github.com/ThomasJannaud/appengine_python_skeleton.git
python -m venv env
source env/bin/activate
pip install  -r requirements.txt
python main.py
```

The server is now running on localhost:8080. Just navigate to either one of:
- localhost:8080
- localhost:8080?name=Thomas
- localhost:8080/contact

On the next runs, you only need `python main.py`. The nice thing about Flask is that you can update your HTML templates or your Python code and Flask should take the changes into account without restarting the server.



## Deploy

You need to have a [GAE account|https://cloud.google.com/appengine] and create a project there.
Your website will be hosted on https://PROJECTNAME.appspot.com but if you own a domain you can point it to this host.

Follow the instructions as you install gcloud to validate your credentials. Then run

`gcloud app deploy --project PROJECTNAME`

to deploy. The setup might take time but once it is ready one command line is enough.