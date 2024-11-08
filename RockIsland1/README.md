# Issues

- Postal codes are randomly selected in select\_postcodes.py, which currently
  writes to a csv file.
  But Anylogic takes Excel file as input.
  Would need third party library to write to Excel file from Python.
  Currently, the csv file is manually converted to .xlsx format, so that
  AnyLogic can import it to a population agent.
  That is not sustainable for an automatic software pipeline that changes
  the randomly selected list of postcodes on demand, as it needs to be changed
  outside AnyLogic.

  Unclear if it is possible to randomly select a list from the database table
  of 800+ postcodes, inside AnyLogic, and then populate the agent using the
  selected list.
  Currently, this is all done through GUI, and it's unclear how to change
  the agent setup programmatically. Perhaps you can through these
  [functions](https://anylogic.help/anylogic/gis/agents-placement.html#agent-location-api).

- For AnyLogic Database to automatically refresh when the postcodes input
  .xlsx file is changed, make sure in
  Database > orkney\_postcodes\_randomly\_selected, check "Update data on
  the model startup".

- Once the postcode csv has been converted to a .xlsx, the AnyLogic model
  needs to be manually pointed to the .xlsx file. This is done through the
  database properties (this should only need to be done once).

# Sources

[1] List of postcodes in Orkney
https://www.doogal.co.uk/AdministrativeAreas?district=S12000023

