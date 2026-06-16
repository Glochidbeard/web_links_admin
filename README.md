# Website links
A complete list of websites/application links for administrative level tasks. 

## Order check app
https://orderchecks-production.up.railway.app/ 

This website prompts the user for an inventory and an order. Then, it runs a check against what we have, what we need, and what needs to be propagated. Results are exportable in a .txt format for the whole order check, a customer facing summary, and just the highest priority action items. Route optimization has been implemented which groups plants of interest as well, so the user doesn't need to walk in inefficient paths. This works best when you have 10 or less stops, but algorithms are actively being researched that optimize this path for more than 10 stops. To use the app, you're going to need two files, with a third strongly recommended. 

Order csv: Obtained by going to Plantiful > Sales > Line items. Then, go to the order check view, and in the search bar, type in the order number of the order you're trying to check. For example; 28176. Then, wait for the view to load, and export the csv when you're done. Importantly, you'll have to rename the order csv to 28176_order.csv. The code reads the numbers associated with the order when it's doing some of the behind the scences work!

Inventory csv: Obtained by going to Plantiful > Production, and then using the Timesaver view. Then, just export this and wait! No need to name it anything special 

Catalog csv (Optional but highly recommended): Obtained by going to Plantiful > Catalog, then clicking on the order check view. This brings in information about the availability of certain line items across the nursery, so it's then up to the user on how they disperse the existing inventory. If for example we have a deficit of a given product overall but we have an existing amount of product that could satisfy one order, it will flag this in the 'Caution' status. 

With these files in hand, you can then navigate to the website and upload them where necessary. You also have the ability to upload multiple orders at once. When you click on the Order CSV box in the app, hold down 'Ctrl' and then click as many Orders CSVs as you like! When ready, click 'Generate report'. 

Meanings of Statuses
1. Ready : We have enough existing available inventory that's in the correct size and meets the quantity demand of the order. Additionally, the total remaining inventory quantity (taking into account all orders placed on that item) is positive. 
2. Caution : We have enough existing available inventory that's in the correct size and meets the quantity demand of the order. However, the total remaining inventory quantity (taking into account all orders placed on that item) is negative.
3. Short : We have a sufficient quantity of material in the nursery, but it's not in the right size.
4. Propagate : We do not have enough plant material in the nursery at an equal or smaller size than the requested variant. That is, we just need to propagate or buy more!

You then have the option to generate a few reports.
1. The full report is extremely comprehensive, giving a summary table and then information on all plants throughout the nursery which could possibly be used for the given order. 

2. The Short/propagate report will essentially give you the full report but filtered for those plants which have a short/propagate status. This is the "action report", which also gives suggested actions that one can take in order to fulfill the order. 

3. The customer facing report exports ONLY the summary table from the full report and replaces some of the status names with more outward friendly nomenclature. For each of the following equivalencies, the internal status is the first in the group and the customer facing status is the second: (Ready, Ready), (Short, In production), (Propagate, Currently propagating), and (Caution, Available). 

Note that some customers ask for a liner size of some plant, and while we may not have exactly the liner size they're looking for, we may have another liner size that's satisfactory for them. In this case, we internally flag this with a "Liner ready" status, but on the customer facing report, it shows up as "Ready". 

## Inventory auto-formatter
https://web-production-cd05a.up.railway.app/

This tool allows the user to convert formats for a few different pieces of data. The most obvious one is the inventory, but there's a capability to format invoices too. 
1. The website catalog formats the Plantiful inventory in a way that's readily usable by the Squarespace website (https://nativewest.squarespace.com/config/). The user must replace un-translated common names from botanical names if they don't all come through, although there's a back-end way to add things to the translation at a later time. Within the very near future we will also be able to do the same with the Little Barn inventory. 
2. The striven inventory tool allows the user to get a correctly formatted striven upload for regular communication between the sites that we use the most. It first requires the user to upload the catalog from Plantiful > Catalog in the 'Plantiful qty to Striven' view (https://app.plantiful.ai/organizations/native-west-nursery/catalog/availability?viewId=e9fc8bf0-43c8-439e-a95e-2de02f079bd1). Then, you'll need to get the Striven inventory by navigating to this site (https://nwn.striven.com/next/reports#/custom-reports/57880/viewer) and then exporting from here. Now you have the files necessary to upload to the tool! Upon doing so, you'll be prompted to upload any un-seen items into the Striven inventory seperately here (https://nwn.striven.com/Order/Items/ItemsImport.aspx?nav=1). Striven won't take "Inventory adjustments" on non-existing inventory which is why the user needs to do this. Upon uploading non-existing items, 500 cell long files fitting the expected format of the import will be available to the user to upload here (https://nwn.striven.com/Accounting/InventoryAdjustments/InventoryAdjustment.aspx?nav=1). If all goes well, you're done! If all is not well, let me know and we can sort it out.
3. The invoicing component allows the user to take shipping and line item information from the sales tab in Plantiful and upload it to Striven in the form of invoices. The user should first  decide on a date range that will be used throughout the invoice production. Make sure these are held consistent across all files pulled. Navigate to Plantiful > Sales > Shipments, then pick the 'Invoice Plantiful to Striven' view. Make sure to edit the filters to match the date range that you're interested in before exporting! Then, go to Plantiful > Sales > Line items and use the 'Invoice to Striven' view. Here, again, edit the date ranges to align with the time frame you're interested in, then export! Now you have the essentials and can head over to the website. Upon successfully running the tool, the user will be given some information about the run. It'll first tell you, if any, what cities are listed in the export but aren't recognized for tax purposes by Striven. You then have two options. Either edit the city name to be something recognized manually, or let me know and I can add some code behind the scenes that automatically converts some of these cities to other recognized ones for Tax code equivalency purposes (i.e., La Jolla = San Diego). When these are resolved, you can then scroll down and see the names of shipments which had no listed shipping city. Whenever this occurs, we assume that the shipping city is San Diego for tax purposes, since it usually means that they're picking up the plants at the nursery - formally in San Diego. Finally, the uploadable CSVs should be formatted correctly for importability into Striven. Navigate here (https://nwn.striven.com/Utilities/InvoicesImport.aspx?nav=1) and import away! 


## Plursery - The nursery planner
https://nurseryplanner-production.up.railway.app/

This app allows for one to create Polygons for roads, structures, and features to efficiently plan space in the nursery. It starts you off in Yuma for some reason but you'll have to scroll to the nursery (or potential new site?!) of interest. You can then design how everything should look in a self explanatory way. To save the maps you have to export them - and then next time you want to work on it, you'll have to import them back in. 







