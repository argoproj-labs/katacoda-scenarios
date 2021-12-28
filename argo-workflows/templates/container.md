A container template is the most common type of template, let's look at a complete example:

```
apiVersion: argoproj.io/v1alpha1
kind: Workflow                 
metadata:
  generateName: container-   
spec:
  entrypoint: main         
  templates:
  - name: main             
    container:
      image: docker/whalesay
      command: [cowsay]         
      args: ["hello world"]
```

Let's run the workflow:

`argo submit --watch container-workflow.yaml`{{execute}}

Open the Argo Server tab and navigate to the workflow, you should see a single container running.

## Exercise

Edit the workflow to make it echo "howdy world".
