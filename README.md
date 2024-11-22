
<a align="left" href="https://github.com/nmfs-openscapes/2024-nmfs-champions"><img src="https://github.githubassets.com/images/modules/logos_page/GitHub-Mark.png" width="35px"/></a>

# Annual QA_QC procedures & GARFO permit hold overview 

Each year we conduct QA/QC procedures on a year's data in edealer in an attempt to make sure the reports are as complete and accurate as possible. We use any issues identified during this process as the basis for applying holds on the renewal of dealers' permits. Those holds can be released and the permit renewed once the appropriate dealer reports have been updated or missing dealer reports have been submitted. Below is an overview of the main steps. The more detailed explanation can be found in the "QA_QC process.md" file.


## Overall Steps in the QA/QC Process

**1) Gather previous year's vessel permit data**
- **Permits** Pull permits for Southeast Limited access and open access vessel permits, HMS open access permits, GARFO incidential squid trawl permits
- **Formatting** Format the different permit lists so that they can be combined into one file with issuance and expiration dates. indicate which permits require VTRs submission 


**2) Pull dealer reports that do not have VTRs and do not only contain smooth dogfish**
- **Missing VTRs** search for reports with no value in the "Trip ID" field in the final view or for records with only "R" in the "Trip ID" field


**3) Merging vessel permit data to dealer reports missing VTRs**
- **Merging files** Merge the file with the vessel permits to the dealer reports with missing VTRs by the supplier_vessel_ID value; Concatenate the fields: SAFIS DEALER_ID, SAFIS_DEALER_RPT_ID, DEALER_TICKET_NO, EDEALER_RPT_NUM, LANDING_SEQ; these will be the “UNIQUE ID” for a given record
- **Reviewing records** Review dealer reports that have a vessel on them with permits that require VTR submission by are missing VTRs
- **Identifying errors** Create an "Error" data field that indicates a VTR is need for the report. Sort all the reports and remove all the reoprts with no errors
- **Adding Contact Information** Merge information from above with the the Active List of Dealers that includes: Participant_ID, Acct Manager, State, Phone, Emails (concatnated together if more than one), County, and Permit Block Date; if contact information is missing, look for informatino on the Expired List of Dealers.
- **Creating word docs for emails** Send Rob the template language to create Word docs for each dealer in the spreadsheet. Have Rob run his Python code to create word docs that will be used as the basis for the emails to be sent to dealers
- **Google spreadsheet** Upload a google spreadsheet so that the team can track the reports. Add a columns called "Comments" and "Email sent?" at the beginning of the spreadsheet.

**4) Identifying Incomplete Records**
- **Look for prohibited species** These reports are identified and dealt with right away
- **Look for blacknose sharks landed in the GOM region** These reports are identified and dealt with right away
- **Look for shortfin mako sharks** These reports are identified and dealt with right away
- **Identifying errors** Create an "Error" data field that indicates the error assoicated with the record.  Add to "Error" field: "Please update report with a valid vessel"
- **Invalid vessels** Pull data from the final view and sort by “Supplier_Vessel_Id” and then see which Supplier_Vessel_Ids look odd or have “From Shore”
- **Look for missing price information** Sort data from the final view and identify records with price per pound $0.10 or less and do no have certain disposition codes. Add to "Error" field: "Please update reocrd with a price/lb"
- **Look for Reporting Quantities=$0/lb)	Sort data from the final view and identify records with REPORTED_QUANTITY = 0; Add to "Error" field: "Please update reported quantity"
- **Identify all STUCK records and associated errors** Identify why the record is stuck based on the error messages either at the trip or landing level. Add to "Error" field the reason for why the reocrd is stuck; Remove any records that administrator must adress and dealer cannot fix; put those in a separate tab. Remove all the reoprts with no errors and put on a separate tab.
- **Create a Unique ID** Concatenate the fields: SAFIS DEALER_ID, SAFIS_DEALER_RPT_ID, DEALER_TICKET_NO, EDEALER_RPT_NUM, LANDING_SEQ; these will be the “UNIQUE ID” for a given record
- **Adding Contact Information** Merge information from above with the the Active List of Dealers that includes: Participant_ID, Acct Manager, State, Phone, Emails (concatnated together if more than one), County, and Permit Block Date; if contact information is missing, look for informatino on the Expired List of Dealers.
- **Formatting** Format the spreadsheet according to: [https://docs.google.com/spreadsheets/d/1dD4lqZqdM_dQrF6YrJa4JaxZQfyh1e4WekMY07vRfIc/edit?usp=sharing](https://docs.google.com/spreadsheets/d/1dD4lqZqdM_dQrF6YrJa4JaxZQfyh1e4WekMY07vRfIc/edit?usp=sharing)
- **Creating word docs for emails** Send Rob the template language to create Word docs for each dealer in the spreadsheet. This template will include langauge on permit holds. Have Rob run his Python code to create word docs that will be used as the basis for the emails to be sent to dealers
- **Google spreadsheet** Upload a google spreadsheet so that the team can track the reports. Add a columns called "Comments", "Permit Hold" (have them all = Y), and "Email sent?" at the beginning of the spreadsheet.

**5) Check for Missing Reports**
- **Identifying missing reports** Run the compliance monitor for the years in question for all active dealers. Export "All details". Sort the spreadsheet by "Report Type" and then search for "Not Submitted". Remove all records except for ones with "Not Submitted".
- **Missing Weeks Field** Create a new field called "Missing Weeks" and concatenate the "Reporting_From" and "Reporting_To" data fields into the "Missing Weeks" field. Have the format be like "08/18/2024 to 08/24/2024"
- **Adding Contact Information** Merge information from above with the the Active List of Dealers that includes: Participant_ID, Acct Manager, State, Phone, Emails (concatnated together if more than one), County, and Permit Block Date; if contact information is missing, look for informatino on the Expired List of Dealers.
- **Formatting** Format the spreadsheet according to: [https://docs.google.com/spreadsheets/d/1ACGUpddFpjv8vzAyRGzBsi4UUSuYxqLtwgkbQ4-1wqs/edit?usp=sharing](https://docs.google.com/spreadsheets/d/13XxOSzYy9oigxHKTNjaw4HE5Z0BvSxiK075KLhZD2kY/edit?usp=sharing)
- **Creating word docs for emails** Send Rob the template language to create Word docs for each dealer in the spreadsheet. This template will include langauge on permit holds. Have Rob run his Python code to create word docs that will be used as the basis for the emails to be sent to dealers
- **Google spreadsheet** Upload a google spreadsheet so that the team can track the reports. Add a columns called "Comments", "Permit Hold" (have them all = Y), and "Email sent?" at the beginning of the spreadsheet.
  
## Applying GARFO Permit holds

If dealers have incomplete or missing reports, we communicate with the GARFO permit office that we would like to have a the renewal of that dealer's GARFO permit held up until the issues associated that dealer's reports have been addressed. The steps for applying these "permit holds" is outlined in the "QA_QC process.md" file.
- **Identify all GARFO permit holders** In each of the spreadsheets created under steps 4 & 5 above, identify the dealers who hold a GARFO permit. Indicate in a new "Issue" data field if the hold is for "Incomplete Reports" or "Missing Reports". Keep the Participant_ID, Dealer Name, GARFO_DNUM, Acct Mgr
- **Create a new list** For the isssuance year in question, merge the list of dealers with incomplete reoprts and missing reports into one spreadsheet. Format the list of dealers with incomplete and missing reports and add them to the google sheet for the team to track: [https://docs.google.com/spreadsheets/d/1j3tHnC15TjdkqyJfNE7ACX6vx4uoKeccjuscuBjLyuQ/edit?usp=sharing](https://docs.google.com/spreadsheets/d/1j3tHnC15TjdkqyJfNE7ACX6vx4uoKeccjuscuBjLyuQ/edit?usp=sharing)
- **Update GARFO_PERMIT_BLOCKS table** Have maintenance contractor add the dealers who would have a GARFO permit hold for a given year. Send them the necessary data for the following fields:
  Year, GARFO_NO, DEALER_NAME, CREATED_DATE, EXPIRATION_DATE, CREATED_BY, REMOVED_BY, IS_ACTIVE. Set all the IS_ACTIVE=Y.
- **Unlocking SAFIS records** For any Incomplete reports listed under step 4 above, sort the reports by the dealer state and SAFIS DEALER RPT ID. Look for all of the reports from Maine to Virginia. In a separate spreadsheet, take the Participant ID, Corporate (or Dealer) Name, SAFIS DEALER RPT ID, and GARFO_DNUM for all the records that belong to dealers residing in Maine to Virginia. Create a list of distinct reports by dealer and send that to David Ulmer (David.Ulmer@noaa.gov) and ask him to unlock the reports for a given reporting year. You will need to tell him when the records can be locked again.  
  
  

