# Analytics as a Service for Data Sharing Partners || [GSP1042](https://www.cloudskillsboost.google/focuses/42014?parent=catalog) ||

## # Like, comment, share & Don't forget to subscribe [Qwiklab_Explorers](https://youtube.com/@titashshil?si=RgamNu1dc9jVIbJN) 👍😄🤝

---
## ⚠️ **Disclaimer:**
#### This script and guide are provided for educational purposes to help you understand the lab process. Please ensure you understand the steps before using any scripts. Before using the script, I encourage you to open and review it to understand each step.The goal is to help you learn how to complete the labs effectively while following Qwiklabs' terms of service and YouTube's community guidelines.
---

- ### Log in with `Data Sharing Partner` User Name & Password

- ### Copy & Run the Commands in Cloud Shell Terminal :

```
bq mk \
--use_legacy_sql=false \
--description "DESCRIPTION" \
--view 'SELECT * FROM `bigquery-public-data.geo_us_boundaries.zip_codes`
WHERE state_code="TX"
LIMIT 4000' \
--project_id $DEVSHELL_PROJECT_ID \
demo_dataset.authorized_view_a

bq mk \
--use_legacy_sql=false \
--description "DESCRIPTION" \
--view 'SELECT * FROM `bigquery-public-data.geo_us_boundaries.zip_codes`
WHERE state_code="CA"
LIMIT 4000' \
--project_id $DEVSHELL_PROJECT_ID \
demo_dataset.authorized_view_b

echo "PROJECT ID=$DEVSHELL_PROJECT_ID"
```
- ### Store The Project Id in Notepad
- ### Go to [Bigquery Console](https://console.cloud.google.com/bigquery?project=)
- ### Follow the next steps from the video carefully
- ### Close the Incognito Windows.
---
- ### Login to `Customer A` Username & Password in Incognito Window
- ### Create View in Project A.
- ### Copy & Run the Commands in Cloud Shell Terminal :
```
PROJECT_ID=
```
```
bq mk --use_legacy_sql=false --view 'SELECT geos.zip_code, geos.city, cust.last_name, cust.first_name
FROM `'$DEVSHELL_PROJECT_ID'.customer_a_dataset.customer_info` as cust
JOIN `'$PROJECT_ID'.demo_dataset.authorized_view_a` as geos
ON geos.zip_code = cust.postal_code;' customer_a_dataset.customer_a_table
```
- ### Open in Incognito Window : [Looker Studio](https://lookerstudio.google.com/)
- ### Follow the next steps from the video carefully.
- ### Close the Incognito Windows.
---

- ### Login to `Customer B` Username & Password in Incognito Window
- ### Create View in Project B.
- ### Copy & Run the Commands in Cloud Shell Terminal :
```
PROJECT_ID=
```
```
bq mk --use_legacy_sql=false --view 'SELECT geos.zip_code, geos.city, cust.last_name, cust.first_name
FROM `'$DEVSHELL_PROJECT_ID'.customer_b_dataset.customer_info` as cust
JOIN `'$PROJECT_ID'.demo_dataset.authorized_view_b` as geos
ON geos.zip_code = cust.postal_code;' customer_b_dataset.customer_b_table
```
- ### Open in Incognito Window : [Looker Studio](https://lookerstudio.google.com/)
- ### Follow the next steps from the video carefully.
- ### Close the Incognito Windows.
---


## Congratulations ..!!🎉  You completed the lab shortly..😃💯

## *Well done..!* 👏

## Thank you for visiting.... :) 🗯️

## [Qwiklab_Explorers](https://youtube.com/@titashshil?si=RgamNu1dc9jVIbJN)

## Join to our community [Digital Dominators](https://linktr.ee/digital_dominators)
