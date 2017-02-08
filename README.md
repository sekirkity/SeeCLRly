# SeeCLRly
Fileless SQL Server CLR-based Custom Stored Procedure Command Execution

For more info about the techinque, please visit [sekirkity.com](http://sekirkity.com/seeclrly-fileless-sql-server-clr-based-custom-stored-procedure-command-execution/)

This techinque will allow for the execution of commands on a comprompised Microsoft SQL Server in a novel, fileless manner. The PowerShell module consists of two cmdlets:

1. New-CLRProcedure - This cmdlet enables CLR stored procedures on the SQL Server, reconfigures it, loads the Dot Net assembly into memory, then creates a stored procedure from the loaded assembly.
2. Invoke-CmdExec - This cmdlet passes a specified command to the previously created stored procedure, where it is then executed.

First, import the module:

`import-module SeeClearly.ps1`

Next, use the New-CLRProcedure cmdlet to create a custom stored procedure on the target SQL Server:

`Add-CLRProcedure -Server MSSQL`

Finally, use the Invoke-CmdExec cmdlet to execute commands on the target server:

`Invoke-CmdExec -Server MSSQL -Command "mkdir c:\temp"`

## Roadmap

* Create another cmdlet to remove the custom stored procedure from the SQL Server
* Allow for the name of the assembly and the stored procedure to be changed via paramaters.
