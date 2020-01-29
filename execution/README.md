# execution


## Rules 

*  Make everything idempoten.
*  Return success instead of not-found error when retrying to re-create or re-delete something already deleted or created not-found.
*  Set proper timeout.

## Issue

* Lambda executed multiple times for a single event.

## Reason

* invocation error:

1)  Client timeouts.
2)   Throttling errors (429).
3)   Other errors not caused by a bad request (500 series).


* function error:

1) Function – Your function's code throws an exception or returns an error object.
2) Runtime – The runtime terminated your function because it ran out of time, detected a syntax error, or failed to marshal the response object into JSON. The function exited with an error code.

