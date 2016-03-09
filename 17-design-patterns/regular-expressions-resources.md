# REGULAR EXPRESSIONS

### MSDN Regex Quick Reference
* https://msdn.microsoft.com/en-us/library/az24scfc(v=vs.11).aspx

### Regex Cheatsheet
* http://www.mikesdotnetting.com/article/46/c-regular-expressions-cheat-sheet

### Regex Testers
* https://visualstudiogallery.msdn.microsoft.com/16b9d664-d88c-460e-84a5-700ab40ba452
* http://www.regexplanet.com/advanced/dotnet/index.html
* http://regexr.com/
* http://regexone.com/

### 90 Minute Regex Tutorial
* http://www.codeproject.com/Articles/9099/The-Minute-Regex-Tutorial

### from Sonda's Notes
####  Split using REGEX:
* normally you don’t need regex if you are splitting by one character.
   * For example mystring.Split(,) makes “Please, sir” would be “Please” “ sir” with spaces
* if there are two characters you want to split it with, then you use regex.
  * `var regex = new System.text.RegularExpressions.Regex(“, “)` so it would be “Please” “sir” without spaces
