# secure
Secure coding practices

## User Management
- [ ] Any user should be able to view only their resources. (OWASP: Insecure Direct Object References)
- [ ] Don't use GUID's for password reset codes. Instead use python secrets module.
- [ ] All token's should have a default expiry time.
- [ ] Once a password reset code has been used, it has to be invalidated/deleted. The same code shouldn't work.

## API's
- [ ] API rate limiting.
