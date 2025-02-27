Peppers er en meget kort random str af characters appended to the end of a password. They are **random** and **different for each password**

hjemmesiden tjekker alle peppers til et password ved login. 
- **eksempel**:
	![[Pasted image 20240212205554.png]]

Dette er modsat [[Passwords Salt]] som gemmes direkte i databasen til godkendelse af passwords. Peppers **gemmes ikke!** ingen ved hvad pepperen til et password er. Derfor går hjemmesiden igennem alle de mulige peppers ved et login.
- **eksempel**
	![[Pasted image 20240212205814.png]]
s