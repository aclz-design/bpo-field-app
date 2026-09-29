# BPO Field Inspection

Version 3 adds direct loading of the route CSV exported by the Excel planner and repairs inspection CSV downloads.

## Daily use

1. In the Windows planner, mark assignments with X, set Route Order and click **Export iPad Route**.
2. Open this app on the iPad. Tap **Load Route CSV** and choose `BPO_iPad_Route.csv` using Files/Dropbox.
3. Tap a property to inspect it. Changes save in this browser on this device. **Restore Saved Route** reloads the last route.
4. Tap **Save Inspection File**. Use the share sheet to save the CSV in Dropbox's Inspections folder. If sharing is unavailable, the app downloads it; move that file to Inspections.
5. In the planner, click **Import Inspection Results** and save the workbook. This stores results in the planner. It does not yet transfer them into a MASTER workbook.

The **Or paste route lines** option remains available. Loading a new route never clears saved inspection records. Prop ID identifies each assignment; different apartments and even identical addresses remain separate when their IDs differ.

## File formats

Route CSVs require `Route Order`, `Prop ID`, `Property Address`, `City`, `State` and `Zip` headers. The optional `App Route Line` column is ignored. Column order may vary. Stops are sorted numerically. Invalid or duplicate IDs/orders are rejected before the saved route changes.

Inspection CSVs preserve the planner's existing 32-column format and use a `_Inspection.csv` filename. Quoted commas, quotation marks, Unicode and multiline comments are supported. Commercial properties can be marked **Commercial / Other**; additional commercial details belong in Assignment-specific comments. A specialized commercial checklist is not included.

## Storage and updates

Routes use `bpoRoute` and inspections use `inspection:<Prop ID>` in browser local storage, as in earlier versions. No inspection data is uploaded to GitHub. Use the existing site address and browser when updating. Clearing website data, changing browser/device or opening another site address does not carry saved inspections along.

Keep completed CSVs in Dropbox as the return copy for the planner. This app has no service worker or guaranteed offline launch; open it while connected before going into the field.
