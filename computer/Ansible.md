## Ideas from <https://redhat-cop.github.io/automation-good-practices/>
- When there are multiple implementations of the same functionality, we call them “providers”. A role supporting multiple providers should have an input variable called $ROLENAME_provider. If this variable is not defined, the role should detect the currently running provider on the system, and respect it.

We don't need this yet but putting this here for if we do need it.

### Why it is good
Ansible won against things like [[Chef]] and so on as they use an declarative model that doesn't match real world performance. Not because they are directly slow, but because the upstream tends to choose a imperative model for their tools as it is faster.

Imperative reflects what people actually want, they don't want to rebuild the system for each update, too slow. Updating your [[NixOS]] config file and rebooting each time you make a tiny change on your computer.