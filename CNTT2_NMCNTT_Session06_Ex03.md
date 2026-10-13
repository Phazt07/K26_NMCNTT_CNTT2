1\. Sơ đồ luồng dữ liệu (stdout → | → stdin)   
Get-Content access.log (stdout)  →  \[ | \]  →  Select-String "TIMEOUT" (stdin)  →  \[ | \]  →  Measure-Object \-Line (stdin)  
2\. Câu lệnh PowerShell hoàn chỉnh   
Get-Content access.log | Select-String "TIMEOUT" | Measure-Object \-Line | Select-Object \-ExpandProperty Lines