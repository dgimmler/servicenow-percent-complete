# ServiceNow: Percent Complete Formatter
## UI Formatter to display percentage bar on ServiceNow forms

### Intro:
![Screenshot](https://github.com/dgimmler/servicenow-percent-complete/blob/master/Percentage%20Bars%20Screenshot.png?raw=true)

ServiceNow offers a really cool percentage bar display for fields of type "Percent Complete" in the list view. However, it's always really bothered me that nothing is available on the forms themselves - you just get another field on the form.

It's been a general project of mine to provide better visuals and UI elements for the native ServiceNow form view - while the data forms are great, UI elements can add a lot to the end-user experience.

This update set includes the following:
- UI Macro for formatter
- Example formatter for Incident
- Configuration table to configure the formatter for any and as many fields as you want for any and as many tables as you want. 

### Installation:
1. Download the update set file (update_set_percent_formatter.xml)
2. In your target ServiceNow instance, select "Import Update Set from XML" under "System Update Sets -> Retrieved Update Sets". Selected the downloaded XML.
3. Preview and commit the update set.

### Configuration:

#### Adding formatter to form:
1. Under System UI -> Formatters, create a new formatter with the following properties:
- Name: "Percent Complete"
- Formatter: " percent_complete.xml
- Table: <target table>
- Active: true
- Type: Formatter
  
2. In the form layout or form designer, add the formatter to the form. The formatter works best set as the entire width of the form (not in a column)

#### Configuring formatter
1. Navigate to System UI -> Percent Complete
2. For each percent complete field you want displayed on the form, create a record on the table. 
3. Select the target table name and the percent complete type field the percentage should be based on.
4. Enter an order value. If multiple fields are configured for the same table, a percentage bar will be displayed for each field in ascending order.
5. Select a color. The color must be a valid css color (hex value, rgb or rgba value.. if it works as a css color value, it should work here). The field defaults to the same shade of blue used in the process flow formatter.
6. Toggle the active checkbox to acitvate or deactivate the percentage bar.
