# secure
Secure coding practices

## User Management
- [ ] Any user should be able to view only their resources. (OWASP: Insecure Direct Object References)
- [ ] Don't use GUID's for password reset codes. (Ex: Instead use python secrets module.)
- [ ] All token's should have a default expiry time.
- [ ] Once a password reset code has been used, it has to be invalidated/deleted. The same code shouldn't work.
- [ ] After password change, invalidate the existing access tokens and prompt the user to login again.
- [ ] Any invites should also expire after some time.

## API's
- [ ] API rate limiting.

## Spam
- [ ] Verify mobile number as well. For more security, mobile number can be made unique to an user.
