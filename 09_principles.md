The following principles come from Saltzer and Schroeder's Secure Design Principles

### 192. Principle of Least Privilege:

> “Every program and every user of the system should operate using the least set of privileges necessary to complete the job”

Ensure that various system actors have the least amount of privilege granted as required by their roles to execute their specified tasks.

Granting excess privilege is prone to misuse/abuse when trusted actors misbehave or their access is hijacked by malicious entities.

### 193. Principle of Separation of Privilege:

> “Where feasible, a protection mechanism that requires two keys to unlock it is more robust and flexible than one that allows access to the presenter of only a single key”

Ensure that critical privileges are separated across multiple actors so that there are no single points of failure/abuse.

A good example of this is to require a multisig address (not EOA) for privileged actors (e.g. owner, admin, governor, deployer) who control key contract functionality such as pause/unpause/shutdown, emergency fund drain, upgradeability, allow/deny list and critical parameters.

The multisig address should be composed of entities that are different and mutually distrusting/verifying.

### 194. Principle of Least Common Mechanism:

> “Minimize the amount of mechanism common to more than one user and depended on by all users”

Ensure that only the least number of security-critical modules/paths as required are shared amongst the different actors/code so that impact from any vulnerability/compromise in shared components is limited and contained to the smallest possible subset.

### 195. Principle of Fail-safe Defaults:

> “Base access decisions on permission rather than exclusion”

Ensure that variables or permissions are initialized to fail-safe default values which can be made more inclusive later instead of opening up the system to everyone including untrusted actors.

### 196. Principle of Complete Mediation:

> `“Every access to every object must be checked for authority.”

Ensure that any required access control is enforced along all access paths to the object or function being protected.

### 197. Principle of Economy of Mechanism:

> “Keep the design as simple and small as possible”

Ensure that contracts and functions are not overly complex or large so as to reduce readability or maintainability.

Complexity typically leads to insecurity.

### 198. Principle of Open Design:

> “The design should not be secret”

Smart contracts are expected to be open-sourced and accessible to everyone.

Security by obscurity of code or underlying algorithms is not an option.

Security should be derived from the strength of the design and implementation under the assumption that (byzantine) attackers will study their details and try to exploit them in arbitrary ways.

### 199. Principle of Psychological Acceptability:

> “It is essential that the human interface be designed for ease of use, so that users routinely and automatically apply the protection mechanisms correctly”

Ensure that security aspects of smart contract interfaces and system designs/flows are user-friendly and intuitive so that users can interact with minimal risk.

### 200. Principle of Work Factor:

> “Compare the cost of circumventing the mechanism with the resources of a potential attacker”

Given the magnitude of value managed by smart contracts, it is safe to assume that byzantine attackers will risk the greatest amounts of intellectual/financial/social capital possible to subvert such systems. Therefore, the mitigation mechanisms must factor in the highest levels of risk.

### 201. Principle of Compromise Recording:

> “Mechanisms that reliably record that a compromise of information has occurred can be used in place of more elaborate mechanisms that completely prevent loss”

Ensure that smart contracts and their accompanying operational infrastructure can be monitored/analyzed at all times (development/deployment/runtime) for minimizing loss from any compromise due to vulnerabilities/exploits.

e.g. critical operations in contracts should necessarily emit events to facilitate monitoring at runtime.
