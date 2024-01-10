# AD-Module
This repo contains the legitimate and signed DLL from Microsoft for the Active Directory PowerShell module. By loading the assembly into memory, we can import the module directly into PowerShell.

This can bypass A/V and EDR to give operators access to the AD module without installing RSAT.

```pwsh
$ad = [System.Reflection.Assembly]::Load([byte[]]([IO.File]::ReadAllBytes("Microsoft.ActiveDirectory.Management.dll")));
Import-Module -Assembly $ad
```