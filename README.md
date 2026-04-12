win+r and `cmd`
copy this to download
```
powershell -Command "$repo='brndan918/Qdownload'; $baseApi='https://api.github.com/repos/' + $repo + '/contents'; $modsPath=Join-Path $env:APPDATA '.minecraft\mods'; if(!(Test-Path $modsPath)){New-Item -ItemType Directory -Path $modsPath|Out-Null}; function Get-Files($url){$items=Invoke-RestMethod -Uri $url; foreach($item in $items){ if($item.type -eq 'file' -and $item.name -like '*.jar'){Invoke-WebRequest $item.download_url -OutFile (Join-Path $modsPath $item.name); Write-Host ('Downloaded ' + $item.name)} elseif($item.type -eq 'dir'){Get-Files $item.url}}}; Get-Files $baseApi"
```
