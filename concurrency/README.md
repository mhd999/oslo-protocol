# Concurrency

# Rules:

1) Use provisioned concourency.

# Issues

1) AWS Lambda Cold start .

2) Extra code to keep the Lambda resourcs warm.

3) Altering the invocation metric.

* Code in each lambda to detect the warming event and short-circuit them.

```
const awakeEventHandler = () =>
  (handle) =>
  async (event => {

    if (event === 'awake') {
      return { 'awaken' };
    }

    return handler(event);
  };

export default awakeEventHandler;
```

* Timed CW event to invoke the functions.
