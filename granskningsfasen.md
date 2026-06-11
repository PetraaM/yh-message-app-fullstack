# Inlämning 3 - Granskningsfasen

To finish this project successfully I applied security principles across the entire SDLC cycle, from planning and threat modelling to implementation, manual review and automated security analysis. The three phases of the project helped me to understand how security should be integrated from the very beginning of the development process and how different review methods compliment each other.

## PHASE 1 - Planning and Threat Modelling

During phase 1. I mostly focused on understanding the applications architecture and identifying potential threats within it with the help of STRIDE model. I defined security requirements related to authentication, password management, authorization, input validation, session handling and dependency management. I think the planning phase went well because many risks that I identified early in the project, later actually appeared during the implementation and review. The security requirements gave me direction and helped me focus on practical improvements. However, looking back to Phase 1. from current perspective, there are a few things I would approach differently. While I did identify certain important risks, i did not consider areas such as rate limiting and CORS configuration. These issues were later identified by CodeQL during automated review phase. If I could start the project again, I would include these controls already during the planning phase. I came to the conclusion that threat modelling is extremely valuable but still does not always identify every possible security weakness.

## PHASE 2 - Manual Review

Phase 2. included identifying issues in the code like broken access control, weak password policy and lack of sufficient input validation. I think that to be able to find these issues you also need to understand how the application works and how users interact with the application and its features. At this point that app architecture sketch from phase 1. came in very handy. In this phase I also tested some other security issues like password hashing with bcrypt, testing against common XSS payloads and dependency testing with npm audit.

## PHASE 3 - Automated Security Analysis

In phase 3. I used automated tools to discover vulnerabilities that I missed in my manual code review. Dependabot discovered vulnerabilities in third party dependencies. CodeQL identified missing rate limiting and permissive CORS configuration. Here it became clear there are other security weaknesses related to app configuration and design that I had not previously considered during my manual review.
At the same time, the automated tools did not identify some of the issues that I found myself during phase 2, such as broken access control, weak password policy and insufficient input validation. This showed me that manual review and automated tools focus on different aspects of security and in that way complement each other.

The most important lesson I learned from this project is that neither approach is sufficient on its own because they have different strengths.
The manual review helped me identify issues related to authorization, input validation, and application logic. Automated tools were more effective at identifying vulnerable dependencies, insecure configurations and patterns that I overlooked in phase 1.

## Conclusion

I think this project demonstrated the value of integrating security throughout the entire SDLC process. Security is not a single activity performed only at the end of development process. It begins with planning and threat modelling, continues through implementation and testing and is strengthened through both manual review and automated analysis. The combination of these approaches provides more complete assessment of the application's security than either of these methods could have provided on its own.
