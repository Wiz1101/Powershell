# Powershell

Powershell is the Windows Scripting Language and shell environment built using the .NET framework.

This also allows Powershell to execute .NET functions directly from its shell. Most Powershell commands, called cmdlets, are written in .NET. 
Unlike other scripting languages and shell environments, the output of these cmdlets are objects - making Powershell somewhat object-oriented.

This also means that running cmdlets allows you to perform actions on the output object (which makes it convenient to pass output from one cmdlet to another). The normal format of a cmdlet is represented using Verb-Noun; for example, the cmdlet to list commands is called `Get-Command`
Common verbs to use include:

    Get
    Start
    Stop 
    Read
    Write
    New
    Out

To get the complete list of approved verbs, visit this link. This would return output like the following: 

https://learn.microsoft.com/en-us/powershell/scripting/developer/cmdlet/approved-verbs-for-windows-powershell-commands?view=powershell-7.4&viewFallbackFrom=powershell-7

## Using Get-Help

`Get-Help` displays information about a cmdlet. To get help with a particular command, run the following:

`Get-Help` `Command-Name`

You can also understand how exactly to use the command by passing in the `-examples` flag. 
![Screenshot 2024-04-10 at 20 36 15](https://github.com/Wiz1101/Powershell/assets/77725643/0d98c738-886e-4aae-987f-611156806d94)



## Using Get-Command

`Get-Command` gets all the cmdlets installed on the current Computer. The great thing about this cmdlet is that it allows for pattern matching like the following

`Get-Command Verb-*` or `Get-Command *-Noun`

Running `Get-Command New-*` to view all the cmdlets for the verb new displays the following: 


![Screenshot 2024-04-10 at 20 35 21](https://github.com/Wiz1101/Powershell/assets/77725643/87ac7f3c-df67-4c7a-8bb4-188b53f868d6)

## Object Manipulation

The Pipeline(|) is used to pass output from one cmdlet to another. A major difference compared to other shells is that Powershell passes an object to the next cmdlet instead of passing text or string to the command after the pipe. Like every object in object-oriented frameworks, an object will contain methods and properties.

You can think of methods as functions that can be applied to output from the cmdlet, and you can think of properties as variables in the output from a cmdlet. To view these details, pass the output of a cmdlet to the `Get-Member` cmdlet:

`Verb-Noun | Get-Member` 

An example of running this to view the members for Get-Command is:


`Get-Command | Get-Member -MemberType Method`

![Screenshot 2024-04-10 at 20 33 44](https://github.com/Wiz1101/Powershell/assets/77725643/18cdd846-4652-4c32-9d40-710ce0d4d5bf)

## Creating Objects From Previous cmdlets

One way of manipulating objects is pulling out the properties from the output of a cmdlet and creating a new object. This is done using the `Select-Object` cmdlet. 

Here's an example of listing the directories and just selecting the mode and the name:

![Screenshot 2024-04-10 at 20 41 02](https://github.com/Wiz1101/Powershell/assets/77725643/3435a1d7-33d0-45f2-a98f-7d0042def631)

## Filtering Objects









