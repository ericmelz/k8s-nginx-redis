```
eksctl --profile emelz-admin --cluster eric-eks get nodegroups
eksctl --profile emelz-admin create nodegroup --config-file=dev-cluster2.yaml
eksctl --profile emelz-admin --cluster eric-eks delete nodegroup --name=ng-1-workers
eksctl --profile emelz-admin --cluster eric-eks delete nodegroup --name=ng-2-routers
```
