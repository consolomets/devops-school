from ubuntu:18.04
run apt update
run apt install -y 
RUN DEBIAN_FRONTEND=noninteractive apt-get install -y -q python-all python-pip
run pip install -q Flask Jinja2 Werkzeug distribute wsgiref
mkdir -p /opt/webapp
workdir /opt/webapp
run echo "import os"                                                     >> /opt/webapp/app.py
run echo                                                                 >> /opt/webapp/app.py
run echo "from flask import Flask"                                       >> /opt/webapp/app.py
run echo "app = Flask(__name__)"                                         >> /opt/webapp/app.py
run echo                                                                 >> /opt/webapp/app.py
run echo "@app.route('/')"                                               >> /opt/webapp/app.py
run echo "def hello():"                                                  >> /opt/webapp/app.py
run echo "    return 'Hello world!'"                                     >> /opt/webapp/app.py
run echo                                                                 >> /opt/webapp/app.py
run echo "if __name__ == '__main__':"                                    >> /opt/webapp/app.py
run echo "    # Bind to PORT if defined, otherwise default to 5000."     >> /opt/webapp/app.py
run echo "    port = int(os.environ.get('PORT', 5000))"                  >> /opt/webapp/app.py
run echo "    app.run(host='0.0.0.0', port=port)"                        >> /opt/webapp/app.py
run chmod +x /opt/webapp/app.py
expose 5000
cmd ["python", "run"]