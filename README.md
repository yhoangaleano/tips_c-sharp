# tips

Contraseña Fuerte C#

 

            public override bool IsValid(object value)
            {
            var size = 0;
            var upper = false;
            var number = false;
            var symbol = false;
            var valueReturn = false;
            
            var charArray = value.ToString().ToCharArray();

            foreach (char item in charArray)
            {
                if (Char.IsUpper(item))
                {
                    upper = true;
                }

                if (Char.IsDigit(item))
                {
                    number = true;
                }

                if (Char.IsSymbol(item))
                {
                    symbol = true;
                }
            }

            size = charArray.Length;

            if (upper == true && number == true && symbol == true && size >= 8)
            {
                valueReturn = true;
            }

            return valueReturn;
        }

Valicación de Correo Electrónico

```c#
bool IsValidEmail(string email)
{
    try {
        var addr = new System.Net.Mail.MailAddress(email);
        return addr.Address == email;
    }
    catch {
        return false;
    }
}
```
