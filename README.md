# with

## What?
Use the CLI all the time but tired of repeating the prefix of commands again and again?.

For eg:
```
git status
git add README.md
git commit -m "add readme"
git status
```

Of course, you end up alisasing some of those commands at the top level. Like `gs` and `ga`. Also helps that `git` is a
single 3 letter command.

What about this?
```
kubectl get ns
kubectl -n kube-system get deployments
kubectl -n kube-system get pods
kubectl -n kube-system describe pod <pod name>
kubectl -n kube-system logs <pod name>
```

Now what? Introducing `with`.

## With - variant 1

Variant 1 of `with` is a single bash function in the file `with1`. It is to be used as follows:
```
$ with kubectl -n kube-system
kubectl -n kube-system> 
kubectl -n kube-system> get pods
kubectl -n kube-system> logs <pod name>
kubectl -n kube-system> exit
$ 
```

It has one problem, the prompt is a sham and not actually a shell. Means, 
1. No shell features like command completion.
2. No Up/Down arrow functionality.
3. No history.
