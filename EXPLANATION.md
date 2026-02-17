 **What was the bug?**
 The bug was wrong condition checking and binary operator usage
- **Why did it happen?**
The first issue was the truthiness logic behind the prototypical inheritance and instance checking whereby instead of checking if the oauth2Token object wasn't prototype child of the OAuth2Token class , we were checking it was . 
The second issue was the OR operator between the instance checking and the expiry where the AND was being used which checks if both conditions are met instead of one either one 
- **Why does your fix solve it?**
My solution fixes the issue by  checking if the oauth2Token object is not a prototype child of the OAuth2Token class and also correctly using the OR operator to check if either condition is met for the token to be  expired.
- **One realistic case / edge case your tests still don’t cover**
If the  oauth2Token object is not a prototype child of the OAuth2Token but also its expiry date is past already . 