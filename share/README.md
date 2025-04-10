# Common file sharing repository 
Contains scripts and templates for common integration projects

## Alloy install
Script `install-alloy-fm.ps1` install alloy on Windows in Fleet Management mode. 

To use the script open Windows CMD as Administrator and run the following command:
```
cd "%TEMP%" && powershell -c Invoke-WebRequest "https://raw.githubusercontent.com/cesramires/grafana-integrations/refs/heads/main/share/install-alloy-fm.ps1" -OutFile "install-windows.ps1" -Proxy <YOUR HTTPS PROXY> && powershell -executionpolicy Bypass -File ".\install-alloy-fm.ps1" -GCLOUD_RW_API_KEY <YOUR GCLOUD API KEY> -GCLOUD_HOSTED_METRICS_ID <YOUR METRICS USER ID> -GCLOUD_HOSTED_METRICS_URL <YOUR PROMETHEUS URL> -GCLOUD_HOSTED_LOGS_ID <LOKI USER ID> -GCLOUD_HOSTED_LOGS_URL <LOKI PUSH URL> -GCLOUD_FM_URL <YOUR FM HOST> -GCLOUD_FM_POLL_FREQUENCY "60s" -GCLOUD_FM_HOSTED_ID <YOU FM ID> -REMOTE_CONFIG <CONFIG-FM URI> -ATTR <YOUR REMOTE AGENT TAGS> -PROXY <YOUR PROXY URL>
```


The `-REMOTE_CONFIG` param defaults to Grafana's default configuration template.


The `-PROXY` param is optional. Use only if you need a http proxy to downlod files or send out agent metrics/logs. Case your http proxy requires authentication use `<http|https>://<username>:<password>@<proxy uri>`.
