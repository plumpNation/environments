Dev environments
============

A collection of development automated environments

## Troubleshooting

If you can't delete an image with 'rmi' try removing all the stopped containers. Thanks to
[kennethklee](https://github.com/kennethklee)

```bash
sudo docker ps -a | grep Exit | awk '{print $1}' | sudo xargs docker rm
```

## Reading materials

* [Cleaning up after docker](http://blog.stefanxo.com/2014/02/clean-up-after-docker/)
