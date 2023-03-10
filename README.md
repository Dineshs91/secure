# secure
Secure coding practices

## User Management
- [ ] Any user should be able to view only their resources. (OWASP: Insecure Direct Object References)
- [ ] Don't use GUID's for password reset codes. (Ex: Instead use python secrets module.)
- [ ] All token's should have a default expiry time.
- [ ] Once a password reset code has been used, it has to be invalidated/deleted. The same code shouldn't work.
- [ ] After password change, invalidate the existing access tokens and prompt the user to login again.
- [ ] Any invites should also expire after some time.
- [ ] JWT access token should have a short life, whereas refresh token have a longer expiry time.

## Anti Patterns
- [ ] [Lack of Data Recognition](https://learn.secdim.com/course/defensive-programming-1st-core-principle/principle-1-anti-patterns): Commonly referred as data validation, Data recognition is the process of looking at a given input and trying to make sense out of it. We check if the given input has the expected data properties. The absence of this can cause confidentiality, integrity or availability issues.
- [ ] [Insufficient Data Recognition](https://learn.secdim.com/course/defensive-programming-1st-core-principle/principle-1-anti-patterns): This happens when input is checked against a few expected data properties, however the checks are incomplete.
- [ ] [Overlooking untrusted entry point](https://learn.secdim.com/course/defensive-programming-1st-core-principle/principle-1-anti-patterns): This happens when a program trust an entry point and use it. For example, a REST response from a third-party SaaS provider is an example of entry point that is commonly overlooked. We may not realise the input to our program is far more than user entries that comes from outside world. The more we breakdown a process in multiple services, the more exposure and possibility of new entry points that is left with no data recognition.
- [ ] [Interpreter or Parser Differential](https://learn.secdim.com/course/defensive-programming-1st-core-principle/principle-1-anti-patterns): This happens when our program interpret the input differently from what it was validated. Regardless of completeness of security checks, our program may use a wrong input.
- [ ] [Parse Data Principle](https://learn.secdim.com/course/defensive-programming-1st-core-principle/principle-1-principle): Parsing is simply a process of converting a less structured input to a more structured output. For example, a program receives a string and parses it into an integer value. Any parser uses a set of rules, known as grammar, to recognise the input data and produces its output. Naturally, some input does not satisfy the parser’s grammar and any parser should handle failed cases. Parsing untrusted data enforces thinking about a process that input must go through and return a result. It inherently makes us to use the output of a parser and not the original input.
- [ ] [Unsafe Data Models](https://learn.secdim.com/course/defensive-programming-2nd-core-principle/principle-2-anti-patterns): Primitive (int, long) or composite (string) types have many possible values and default behaviours. The concept we try to model is a subset of these generic types. However, not all the possible values and behaviours are applicable to our use case. Some of which can result in security vulnerabilities. I.e A persons age is likely not going to be stored as 2000000001 
but an int allows for that! We then need to confine generic types into what we want. Here, we are going to have another problem: what are all those checks, have we cover all edge cases? and where to place the checks?
- [ ] [Shotgun parser](https://learn.secdim.com/course/defensive-programming-2nd-core-principle/principle-2-anti-patterns): This anti-pattern happens when validation checks are scattered and tangled up with the code logic. We hope the checks are sufficient and unsafe input will not make it through. It also means that there is no single place to look for to understand the concepts our program tries to model. The data model definition spans across the whole code base.

There are secure programming games at [SecDim](https://secdim.com) that apply these teachings in the form of a game, a good place to practice these.


## API's
- [ ] API rate limiting.

## Spam
- [ ] Verify mobile number as well. For more security, mobile number can be made unique to an user.
