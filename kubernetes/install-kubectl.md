# Install kubectl

## Install kubectl

* [https://kubernetes.io/docs/tasks/tools/](https://kubernetes.io/docs/tasks/tools/)



kubectl은 kubernetes 클러스터를 제어하기 위한 CLI이다.

config는 기본적으로 `.kube/config`에   저장하고 있다.

만약 별도로 config 파일을 두고 싶다면 kubectl 명령어에서 --kubeconfig 플래그를 이용해 직접 config파일을 지정할 수 있다.



### Auto Completion

kubectl 명령어를 사용하면서 tab키를 활용한 자동완성 기능을 사용할 수 있다. 공식 docs에서 제공한다.

```
echo 'source <(kubectl completion bash)' >>~/.bashrc
```

