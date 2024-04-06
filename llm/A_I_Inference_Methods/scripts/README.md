### Start the Flask App

#### Open a new session using tmux

```sh
tmux new -s flask
conda activate pytorch
python flask_api.py

```

#### Detach from the session terminal

- Press Cntl + B to enter into tmux command mode
- Press D to detach

Command to check running sessions::

```sh
tmux ls
```

> **NOTE**\
> The flask app is running on localhost\
>\
> WARNING: This is a development server. Do not use it in a production deployment. Use a production WSGI server instead.
> * Running on all addresses (0.0.0.0)
> * Running on http://127.0.0.1:7861
> * Running on http://10.0.0.123:7861

#### Test if the app is responding

##### One shot response

```sh
curl -iX POST -H "Content-Type: application/json" -d '{"prompt":"What was the capital of India before 1911?", "parameters": {"max_new_tokens": 100}}' "10.0.0.123:7861/generate"

```

##### Streaming response response

```sh
curl -iX POST -H "Content-Type: application/json" -d '{"prompt":"What was the capital of India before 1911?", "parameters": {"max_new_tokens": 100}}' "10.0.0.123:7861/generate/stream"
```
