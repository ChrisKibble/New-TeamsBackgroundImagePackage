# New-TeamsBackgroundImagePackage

# How to Install
Coming soon...

# Purpose
Creates a new Teams Background image package in MSI and optionally in IntuneWin format. The resulting package(s) can be used with "New Teams" (e.g. "Teams 2.1") released in 2024, and will likely work on later versions as well.

# EXAMPLE
```powershell
New-TeamsBackgroundImagePackage -ImagePath "\\package_source\packages\Teams Backgrounds\Standard" -OutputFolder "\\sccm_content_share\private$\Teams Background Packages" -ProductName "Custom Teams Backgrounds" -ProductVendor "Biogen" -ProductVersion 2.0 -UpgradeGuid "12345678-9012-3456-7890-01234567890A" -ProductLink "https://www.winadmins.io/" -GenerateIntuneWin`
```

# Parameters

## ImagePath
The path that contains the images to include in the package. Only PNG, JPG, and JPEG files are included.
	
## Recurse
Optional Switch to determine if subfolders of ImagePath should be searched for image files to include.

## OutputFolder
The folder that the resulting package(s) should be exported to.
	
## ScratchSpace
Optional path to where the packaging should be done. Defaults to TEMP folder of user.
	
## GenerateIntuneWin
Determine if IntuneWin should be exported as well. Requires IntuneWinAppUtil.exe in the system PATH or in the folder the script is called from.

## DontCleanUp
When the processing is complete, leave the ScratchFolder alone (useful for troubleshooting).
	
## ProductName
The name of the product in the resulting MSI (e.g., "Standard Teams Backgrounds")
	
## ProductVendor
The name of the vendor in the resulting MSI (e.g., "Contoso Incorporated")
	
## ProductVersion
The version of the package (e.g. 1.0).
	
## ProductIcon
An optional icon to show in Add/Remove Programs along with the installation.
	
## ProductLink
An optional about/help link to include in the package to show in Add/Remove Programs.
	
## UpgradeGuid
A Unique Id to identify a string of MSIs thatc can upgrade or downgrade each other. Each package that should upgrade a previous package should use the same UpgradeGuid, else the packages will install side-by-side. This can be left blank the first time you create a new package.
	
## SkipUpgradeGuidWarning
If an UpgradeGuid isn't passed, don't warn the user that a new one will be generated.
	
## NoBanner
Hide the welcome and credits banner.
	
