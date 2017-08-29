## To build App using Docker - 6
```
OS : macOS Sierra 10.12.5
Docker version : Docker version 17.06.0-ce, build 02c1d87
```

### Unit test using Docker
[UnitTest Python](https://docs.python.org/3/library/unittest.html)

#### 1. Unit test
```
$ docker-compose up -d
$ docker-compose run dockerapp python test.py
```

- User test Into Docker Images
	- Pros:
		- A single iamge is used through development, testing and production, which greatly ensures the reliability of out tests.

	- Cons:
		- It increases the size of the image.




