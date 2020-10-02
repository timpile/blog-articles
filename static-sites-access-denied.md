# How to Fix Access Denied Error for S3 React Static Site

So you've got your statically hosted S3 site up and running with React.js and React Router - exciting!
You click around to your sexy new site admiring your brilliant work. Everything looks great, as expected.
Until you refresh the page and get this...

```xml
This XML file does not appear to have any style information associated with it. The document tree is shown below.
<Error>
  <Code>AccessDenied</Code>
  <Message>Access Denied</Message>
  <RequestId>2V1Q6V5R9G4Y7Y3R</RequestId>
  <HostId>coEwimlSDhKFA68EhCV7Fc3fwDzHvMDWqoJoZineHQY6juRu8hLQZXHOUd1eIJujChccsbu9RWg=</HostId>
</Error>
```
Not a very helpful error message, but the solution is actually rather simple.
The first thing you'll want to do, if you haven't already, is setup a CloudFront distribution for your S3 static site.

<img src="https://s3.amazonaws.com/blog.timpile.io/images/cloudfront-distribution.png" alt="CloudFront Distribution for Static Site"/>

Then simply add custom error responses to handle `403` and `404` responses by redirecting back to `/index.html`.

<img src="https://s3.amazonaws.com/blog.timpile.io/images/cloudfront-custom-error-response.png" alt="CloudFront Custom Error Response"/>
