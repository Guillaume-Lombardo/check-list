# API Security Best Practices Checklist

## 1. Authentication

1. [ ] Avoid **Basic Authentication**, use standard (e.g. JWT). ([example](examples/01-jwt-fastapi.md))
2. [ ] Do not reinvent the wheel in authentication mechanisms. ([example](examples/02-do-not-reinvent-the-wheel.md))
3. [ ] Use **Max Retry** and fail safeties in login. ([example](examples/03-max-retries-and-jail.md))
4. [ ] Use encryption on all sensitive data. ([example](examples/04-use-encryption-on-sensitive-data.md))

## 2. JWT (JSON Web Token)

1. [ ] Use a good **JWT Secret** to make brute force attacks difficult.
2. [ ] Do not extract the algorithm from the header, use backend.
3. [ ] Make token expiration (TTL, RTTL) as short as possible.
4. [ ] Avoid storing sensitive data in JWT payload.
5. [ ] Keep the payload small to reduce the size of the JWT.

## 3. Access Control

1. [ ] Limit requests (throttling) to avoid DDoS / brute force.
2. [ ] Use HTTPS on server-side and secure clients.
3. [ ] Use HSTS header with SSL to avoid SSL Strip attacks.
4. [ ] Turn off directory listings.
5. [ ] Private APIs to only be accessible from safe listed IPs.

## 4. Auth

1. [ ] Always validate **redirect_uri** on server-side.
2. [ ] Avoid **response_type=token** and try to exchange for code.
3. [ ] Use **state** parameter to prevent CSRF attacks.
4. [ ] Define default scope, and validate scope for each application.

## 5. Input

1. [ ] Use proper HTTP methods for the operation.
2. [ ] Validate **content-type** on request header.
3. [ ] Validate user input to avoid common vulnerabilities.
4. [ ] Use standard **Authorization** header for sensitive data.
5. [ ] Use only server-side encryption.
6. [ ] Use an API Gateway for caching, rate limit policies, etc.

## 6. Output

1. [ ] Send **X-Content-Type-Options: nosniff** header.
2. [ ] Send **X-Frame-Options: deny** header.
3. [ ] Send **Content-Security-Policy: default-src 'none'** header.
4. [ ] Remove fingerprinting headers (i.e. X-Powered-By, etc.).
5. [ ] Force **content-type** for your response.
6. [ ] Avoid returning sensitive data (credentials, etc.) in responses.
7. [ ] Return proper response codes as per the operation.

## 7. Processing

1. [ ] Check if all endpoints are protected behind authentication to avoid broken authentication process.
2. [ ] Avoid user's personal ID in the resource URL (e.g., `/users/242/orders`).
3. [ ] Prefer using UUID over auto-increment IDs.
4. [ ] Disable entity parsing if you are parsing XML to avoid XXE attacks.
5. [ ] Disable entity expansion if using XML, YAML, or any other language.
6. [ ] Use CDN for file uploads.
7. [ ] Avoid HTTP blocking if you are using huge amounts of data.
8. [ ] Make sure to turn the debug mode off in production.
9. [ ] Use non-executable stack when available.

## 8. CI & CD

1. [ ] Audit your design and implementation with unit/integration tests.
2. [ ] Use a code review process and disregard self-approval.
3. [ ] Continuously run security analysis on your code.
4. [ ] Check your dependencies for known vulnerabilities.
5. [ ] Design a rollback solution for deployments.

## 9. Monitoring

1. [ ] Use centralized logins for all services and components.
2. [ ] Use agents to monitor all requests, responses, and errors.
3. [ ] Use alerts for SMS, Slack, Email, Kibana, Cloudwatch, etc.
4. [ ] Ensure that you aren't logging any sensitive data.
5. [ ] Use an IDS and/or IPS system to monitor everything.
