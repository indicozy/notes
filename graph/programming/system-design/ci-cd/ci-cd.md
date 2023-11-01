![[attachments/Pasted image 20231101152633.png]]

## Software development lifecycle (SDLC) with CI/CD
1. Development
2. Testing
3. Deployment
	1. [[graph/programming/system-design/ci-cd/end-to-end-tests|End-to-end tests]] are made before deployment
4. Maintenance

CI/CD automates and integrates these stages to enable faster and more reliable releases.

## Continuous integration (CI)
Automates:
- build
- test
- merge

## Continuous Delivery (CD)
- deployment
- infrastructure changes

## CI/CD Pipeline
A typical CI/CD pipeline has several connected stages:

- The developer commits code changes to the source control
- CI server detects changes and triggers the build
- Code is compiled, and tested (unit, integration tests)
- Test results reported to the developer
- On success, artifacts are deployed to staging environments
- Further testing may be done on staging before release
- CD system deploys approved changes to production

## Sources
-  https://github.com/ByteByteGoHq/system-design-101
