```csharp
using System;
using System.Linq;

public static class Bob
{
    public static string Response(string statement)
    {
        string trimmed = statement.Trim();

        if (string.IsNullOrEmpty(trimmed))
            return "Fine. Be that way!";

        bool isQuestion = trimmed.EndsWith('?');
        bool hasLetters = trimmed.Any(char.IsLetter);
        bool isYelling = hasLetters && trimmed.Where(char.IsLetter).All(char.IsUpper);

        if (isYelling && isQuestion)
            return "Calm down, I know what I'm doing!";

        if (isYelling)
            return "Whoa, chill out!";

        if (isQuestion)
            return "Sure.";

        return "Whatever.";
    }
}
```
