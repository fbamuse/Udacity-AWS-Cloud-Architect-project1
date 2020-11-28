

In this project you will create highly available solutions to common use cases. You will build a Multi-AvailabilityZone, Multi-Region database and show how to use it in multiple geographically separate AWS regions. You will also build a website hosting solution that is versioned so that any data destruction and accidents can be quickly and easily undone.
#
# Part 1  Data Durability And Recovery

## two AWS regions. An active region and a standby region.

![](primary_vpc.png)
![](secondary_vpc.png)

## Highly durable RDS Database
primaryDB
![](primaryDB_config.png)
secondaryDB
![](secondaryDB_config.png)
primary subnet
![](primaryDB_subnetgroup.png)
secondary subnet
![](secondaryDB_subnetgroup.png)
subnets
![](primaryVPC_subnets.png)
![](secondaryVPC_subnets.png)

routing table
![](primary_subnet_routing.png)
![](secondary_subnet_routing.png)

## Availability Estimate

## Demonstrate normal usage


![](log_primary.png)


## Monitor database
![](monitoring_connections.png)
![](monitoring_replication.png)


## Failover And Recovery

![](log_rr_before_promotion-2.png)
![](rr_before_promotion.png)
![](log_rr_after_promotion.png)


![](rr_after_promotion.png)
![](rr_after_promotion-2.png)


#
# Part 2 Website Resiliency
Build a resilient static web hosting solution in AWS. Create a versioned S3 bucket and configure it as a static website.

![](s3_original.png)
You will now “accidentally” change the contents of the website such that it is no longer serving the correct content
![](s3_season.png)
You will now need to “recover” the website by rolling the content back to a previous version.
![](s3_season_revert.png)
You will now “accidentally” delete contents from the S3 bucket
![](s3_deletion.png)
You will now need to “recover” the objec
![](s3_delete_marker.png)
![](s3_delete_revert.png)