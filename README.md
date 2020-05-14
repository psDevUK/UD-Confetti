# UD-Confetti
Bringing some celebration to the world of Universal Dashboard with this confetti component

## Time to Party

Figured I now got quite a few components on the marketplace so how else better to celebrate than with some confetti. 

## What is it?

Animated confetti on your dashboard with numerous parameter options to allow you to control how the confetti is displayed.

![placeholder](https://raw.githubusercontent.com/psDevUK/UD-Confetti/master/UDConfetti.gif
"Demonstration of component")

## DEMO

```
Import-Module UniversalDashboard
Import-Module -Name UniversalDashboard.UDConfetti
Get-UDDashboard | Stop-UDDashboard
$init = New-UDEndpointInitialization -Module @('UniversalDashboard.UDConfetti')
$dashboard = New-UDDashboard -Title "New Component" -Content {
    New-UDRow -Columns {
        New-UDColumn -Size 4 -Content {
            New-UDHeading -Size 4 -Text "New-UDConfetti"
            New-UDButton -Text "LETS PARTY" -Icon robot -OnClick {
                Show-UDToast -Message "Clicked"
                Show-UDModal -Content {
                    New-UDConfetti -Run $true -Duration 7000 -PiecesNumber 400
                    New-UDHeading -Size 4 -Text "Well Done You"
                    New-UDHeading -Size 4 -Text "Clicked A Button"
                } -Width "50%" -Height "50%"
            }
        }
    }
} -EndpointInitialization $init
Start-UDDashboard -Dashboard $dashboard -Port 10005
```

## Parameters
 **PiecesNumber**  - integer value (default set)
 
 **Wind**              - decimal value (default set)
 
 **Gravity**           - decimal value (default set)
 
 **InitialVelocityX**  - integer value (default set)
 
 **InitialVelocityY**  - integer value (default set)
 
 **Colors**            - multi string value (default set)
 
 **Opacity**           - decimal (default set)
 
 **Recycle**           - boolean (default set)
 
 **Run**               - boolean (defaulted to false)
 
 **Duration**          - integer (default set)
