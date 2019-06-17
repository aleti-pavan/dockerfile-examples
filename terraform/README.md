Build:
-----

```
$ docker image build -t `image-name` .
```

Run:
---

```
$ docker container run -v ~/.aws:/root/.aws:ro `name` -it deployawscli bash
```
