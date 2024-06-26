# No End Insight

An online social media platform for sharing uplifting insights! Only the front-end (HTML and Bootstrap CSS) was completed for school, and I've since hooked it up with a back-end with live data as a fun side project!

### Installation

```
touch .env
```

Make sure to fill `.env` with correct contents (see [`.env.example`](/.env.example)).

### Usage locally

```
python app.py
```

### Usage with gunicorn (deploy to production)

```
pm2 start pm2.json
```

Behind the scenes this runs `python3 -m gunicorn -w 1 --bind 0.0.0.0:5000 wsgi:app`. This runs the app with gunicorn on the right port, then pm2 manages it, handling automatic restarts. `-w 1` means just use 1 worker process (doing this because I have only 1 CPU on the virtual server). If you try to run gunicorn without pm2 and want it in the background, you'll need to add the `--daemon` flag.

### TODO

- [ ] Put auth behind middleware for better reuse and separation of concerns.
