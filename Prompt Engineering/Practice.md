### Task : Write a prompt that tells an AI Agent to:

- Compare your branch with main.
- Review only changed Java files.
- Follow Spring Boot best practices.
- Check for security issues.
- Suggest improvements.
- Avoid unnecessary refactoring.

Keep it under 120 words.
``` Text
Our Framework 
- Role
- Context
- Task
- Constraints (Limitation)
- Review criteria
- Output format
```
---
### MY prompt approach vs Better approach 
#### My prompt approach 

Act as an Senior Java/Spring Boot engineer. It is Java Spring Boot Application using java 21 version to complie the code but we are using java 17 version syntax not beyond it.

Compare the current branch with master to find the code changes and review the only changes following the spring boot best practices. Don't make unnecessary the code changes/refactoring. 

For any suggestions, provide the line no, file name and the describe the suggestion. 

Score : 8.5/10


#### Better approach 
Act as a Senior Java/Spring Boot engineer.

Context:

* The application is compiled with Java 21.
* Use only Java 17 language features; do not suggest Java 21-specific features.

Task:

* Compare the current branch with `master` using `git diff master...HEAD`.
* Review only the changed Java files.
* Check for correctness, security issues, exception handling, performance, maintainability, and Spring Boot best practices.

Constraints:

* Do not recommend unrelated changes or unnecessary refactoring.
* Do not suggest changes outside the current diff unless required to fix a finding.

Output:
For each finding, provide:

* Severity: Critical/High/Medium/Low
* File name
* Line number
* Issue
* Recommendation

If no issues are found, state: "No issues found."

Score: 9.5/10

That's a 9.5–10/10 practical prompt.

