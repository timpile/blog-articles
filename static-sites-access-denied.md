# How to Fix Access Denied Error for S3 React Static Site

```xml
This XML file does not appear to have any style information associated with it. The document tree is shown below.
<Error>
  <Code>AccessDenied</Code>
  <Message>Access Denied</Message>
  <RequestId>2V1Q6V5R9G4Y7Y3R</RequestId>
  <HostId>coEwimlSDhKFA68EhCV7Fc3fwDzHvMDWqoJoZineHQY6juRu8hLQZXHOUd1eIJujChccsbu9RWg=</HostId>
</Error>
```
The first thing you'll want to do if you haven't already is setup a CloudFront distribution for your S3 static site.

<img src="https://s3.amazonaws.com/blog.timpile.io/images/cloudfront-distribution.png" alt="CloudFront Distribution for Static Site"/>

Then simply add custom error responses to handle `403` and `404` responses by redirecting back to `/index.html`.

<img src="https://s3.amazonaws.com/blog.timpile.io/images/cloudfront-custom-error-response.png" alt="CloudFront Custom Error Response"/>
