# REST APIs

## Types of REST Interfaces

With hopefully no loss of generality, we're going to say that every request produces a **job**, some unit of work that the service is going to do
which will generate a **result**. The result might be an answer to some kind of question, or it might just be the status of the job, such as whether
it was successful or not.

Based on this, we can summarize four common classes of REST interfaces:

1. Fire and forget - Make a request, don't care about the result.
2. Synchronous - Make a request, get the result in the response.
3. Job polling (async) - Make a request, get a job ID, check back for status and result.
4. Job notification (async) - Make a request and tell the server how to contact you with the results (e.g., webhook).


