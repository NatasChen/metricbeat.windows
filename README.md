### To install the merticbeat for windows server use 01 or 02 ###
01. PS C:\Program Files\Metricbeat> .\install-service-metricbeat.ps1
02. PowerShell.exe -ExecutionPolicy UnRestricted -File .\install-service-metricbeat.ps1


### 針對特定欄位進行在Kibana JSON Input 運算 ###
#網路流量轉換為KBytes
{ "script" : "doc['windows.perfmon.Bytes.Received.sec'].value / 1024" }

#磁碟使用空間取"遞增"表示
{ "script" : "100-(doc['windows.perfmon.Free.Disk.Space.pct'].value)" }
