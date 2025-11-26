# Configure alerts through Grafana Dashboard

## Import new dashboards

- Import Grafana Dashboards from [Grafana Labs](https://grafana.com/grafana/dashboards)
- Open dashboard page > Copy ID

- Grafana > Dashboards > New > Import

## Create Contact points
Grafana > Alerting > Contact points

## Create email alerts

- Upload **grafana.ini** file to project directory

>Verify the ```[smtp]``` Email server settings in the **grafana.ini** file.
>
>Must be set to ```enabled``` to allow Grafana to send email. Default is ```false```.
##
