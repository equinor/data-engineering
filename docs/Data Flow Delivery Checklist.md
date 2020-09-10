# Data flow delivery checklist

This document should be updated whenever changes are made to a data flow.  

Standard git history can be used to track changes to both this document and the related solution.

## Usage Guidelines

Update each review question as below. Where appropriate add comments, either inline with the questions or at the end

- [ ] Blank not reviewed
- [x] Accepted
- [ ] ~~Not relevant~~  
*Add a comment to indicate reasoning*
- [x] :heavy_exclamation_mark: [question]  
*Should be corrected, but will be accepted. Add a comment to indicate reasoning*
- [ ] :x: [question]  
*Needs correcting to pass approval. Add a comment to indicate reasoning*

## Design Review

Done by a peer before starting development of a new solution or major changes

- [ ] Data flow name. When available, application name should be part of the name.
- [ ] Solution design and technology used
- [ ] Access and secret management solution
- [ ] Security risk of IT components approved
- [ ] A copy of the [Background Information & Decision Log.md](https://github.com/equinor/data-engineering/blob/master/docs/Background%20Information%20%26%20Decision%20Log.md) has been completed for consumers
- [ ] A copy of the [Consumer Requirements.md](https://github.com/equinor/data-engineering/blob/master/docs/Consumer%20Requirements.md) has been completed


## Development Review

Done by a peer developer before deployment to test environment

- [ ] No basic flaws or problems
- [ ] Component naming according to standard
- [ ] Shared OMNIA components used when appropriate
- [ ] All functions documented in source code
- [ ] No passwords nor service principal keys in code
- [ ] No dead code (limit cruft, no dead code without justifying comment)
- [ ] Project is split reasonably (ref. Curly’s law: Do one thing)
- [ ] Config in DevOps release pipeline ARM templates with override parameters
- [ ] No passwords nor service principal keys in config files
- [ ] All artifacts (e.g. scripts for stored procedures and table definitions) in GitHub
- [ ] No development in master branch
- [ ] Runbook created
- [ ] All config described and as either override parameters in CI/CD or defined in Runbooks
- [ ] External dependencies documented in runbook
- [ ] readme.md on GitHub, including installation instructions
- [ ] System diagram updated to reflect solution
- [ ] All components included in deployment scripts
- [ ] Any deployment work outside DevOps pipelines is documented
- [ ] Managed identify used wherever possible
- [ ] Proper testing done in development environment
- [ ] Test cases scripted and passed

## Production review 

Done by a peer developer before deployment to production environment

- [ ] Pipeline running successful for 2 days in test environment
- [ ] Documentation updated 
- [ ] Data flow diagram included in runbook
- [ ] Known errors documented in runbook
- [ ] Contact information for customers available in runbook
- [ ] Data catalog updated
- [ ] Data cleaned up and database scaled down to necessary level in dev and test
- [ ] Data flows paused in development and test environments
- [ ] All components follow minimum security requirements 
- [ ] Production database scaled to proper level
- [ ] Relevant user names/passwords/keys stored in a Key Vault
- [ ] Passwords meet complexity requirements

## Other Comments
