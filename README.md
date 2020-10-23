# 快境

## Background

如你所知，我们项目存在Java 、PHP混合开发，在采用了微服务之后，一切变得坑爹起来。

为了开发、测试一个接口，需要跑起来各种服务，环境搭建这事儿就变得amazing起来。当然比较好的方式是运维打包搞定整个环境，但是目前我们的网络各种不通，气死你。。。

这个项目就是为了解决无痛（至少是少痛）开发环境问题的。所以，项目名称叫了“快境”，顾名思义，快速环境。。。当然，十分不建议在生产上使用这个环境，毕竟目前还没有大量的测试验证。开发还是可以的。


## What's include？

- consul 服务注册与发现、配置中心（放了四个节点，假装在集群）
- nacos 服务注册与发现、配置中心（单机模式）
- MySQL 数据库
- Redis 缓存
- Nginx web服务器
- PHP-FPM PHP基础环境
- RabbitMQ 队列
- …… More On Way

## Requirements

用这玩意儿，你需要事先安装

- docker
- docker-compose


## How to use？

本目录下执行

```
docker-compose up
```

如果你只想启动部分服务，只需要带参数即可

```
docker-compose nginx mysql
```

如果你想后台跑，加个 `-d`

```
docker-compose up -d nginx
```

## Configuration

MySQL:

```
username: default
password: secret
# 创库脚本: config/mysql/docker-entrypoint-initdb.d/init.sql
```

Nacos Web UI:

```
url: https://localhost:8848/nacos
username: nacos
password: nacos
```

Nginx Sites:

```
config/nginx/sites
```

## Custom Dockerfile

```
docker-compose build xxx
```

## Thanks to
[Laradock](https://github.com/laradock)


## License
Painless is Open Source software released under the [Apache 2.0 license](https://www.apache.org/licenses/LICENSE-2.0.html).

