# checkout the code

```
git clone https://github.com/logstash-plugins/logstash-output-elasticsearch
```

# build the docker images

```console
docker build -t logstash-output-aws-elasticsearch .
```

# Get on to the docker container

```console
docker run -it --entrypoint /bin/bash --volume ~/projects/logstash-output-elasticsearch:/usr/src/app logstash-output-aws-elasticsearch
```

# Now build the project

```console
bundle install
bundle exec rake vendor
bundle exec rspec spec
```

# Create the gem file
```console
gem build logstash-output-elasticsearch.gemspec
```

# install this newly built gem to logstash

```console
bin/logstash install /path/to/new/gem
```
