# AWS Docker
This container will be all things amazon. It contains or will contain(* denotes not yet) the following:
- awscli -> http://docs.aws.amazon.com/cli/latest/userguide/
- aws-shell -> https://github.com/awslabs/aws-shell
- *aws CodeDeploy Service -> https://aws.amazon.com/documentation/codedeploy/

#Usage
Usage is incredibly simple. Below are the steps:

1. Configure(one time deal)
  1. `docker run -ti --rm -v $HOME:/root/ kcmerrill/aws`
2. Create an alias for aws-shell
  2. `alias aws-shell='docker run -ti --rm -v $HOME:/root/ --entrypoint="aws-shell" kcmerrill/aws'`
3. Create an alias for aws cli
  3. `alias aws="docker run -ti --rm -v $HOME:/root/ kcmerrill/aws"`

# Todo
 - Add auto installer hotsauce
