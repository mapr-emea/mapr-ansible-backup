- Create config for native secure
- Add precheck for disks
- Add OpenTSDB / Grafana
- Add elastic search, kibana
- RStudio for Redhat, Centos, Suse
- Execute spark Hadoop fs creation only once
- Add storm
- Add hue
- Add latest patches

http://maprdocs.mapr.com/home/AdvancedInstallation/InstallMonitoring.html

/opt/mapr/server/configure.sh -C ip-10-0-0-10.eu-west-1.compute.internal,ip-10-0-0-8.eu-west-1.compute.internal,ip-10-0-0-9.eu-west-1.compute.internal -Z ip-10-0-0-10.eu-west-1.compute.internal,ip-10-0-0-8.eu-west-1.compute.internal,ip-10-0-0-9.eu-west-1.compute.internal  -N my.cluster.com -RM framework2.marathon.mesos  -HS jobhistory.framework2.mesos -MF framework2  -MCL framework2

/opt/mapr/server/configure.sh -N ip-10-0-0-166.eu-west-1.compute.internal -Z ip-10-0-0-166.eu-west-1.compute.internal -C ip-10-0-0-166.eu-west-1.compute.internal -u mapr -g mapr -secure -RM ip-10-0-0-166.eu-west-1.compute.internal -HS ip-10-0-0-166.eu-west-1.compute.internal

https://www.rstudio.com/products/rstudio/download-commercial/


