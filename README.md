
<a align="left" href="https://github.com/nmfs-openscapes/2024-nmfs-champions"><img src="https://github.githubassets.com/images/modules/logos_page/GitHub-Mark.png" width="35px"/></a>

# Annual QA_QC procedures overview 

Each year we conduct QA/QC procedures on a year's data in edealer in an attempt to make sure the reports are as complete and accurate as possible.


## Overall Steps in the Process

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
- **Google spreadsheet** Upload a google spreadsheet so that the team can track the reports. Add a columns called "Email sent?" and "Comments" at the beginning of the spreadsheet.

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
- **Creating word docs for emails** Send Rob the template language to create Word docs for each dealer in the spreadsheet. This template will include langauge on permit holds. Have Rob run his Python code to create word docs that will be used as the basis for the emails to be sent to dealers
- - **Google spreadsheet** Upload a google spreadsheet so that the team can track the reports. Add a columns called "Email sent?" and "Comments" at the beginning of the spreadsheet.

**5) Check for Missing Reports**
- **Identifying missing reports** Run the compliance monitor for the years in question for all active dealers
- **
- **Adding Contact Information** Merge information from above with the the Active List of Dealers that includes: Participant_ID, Acct Manager, State, Phone, Emails (concatnated together if more than one), County, and Permit Block Date; if contact information is missing, look for informatino on the Expired List of Dealers.
- **Creating word docs for emails** Send Rob the template language to create Word docs for each dealer in the spreadsheet. This template will include langauge on permit holds. Have Rob run his Python code to create word docs that will be used as the basis for the emails to be sent to dealers
  
## Applying Permit holds

Coworking sessions are where get our own work done at the same time
together. Sometimes, this means quiet work with check-ins to break up
focused work and get feedback, and sometimes this involves asking
questions and screensharing to learn and problem solve. We will make
breakout rooms in Zoom so people working on related themes can meet and
learn from each other.

Participants across all three Fall 2024 NMFS Openscapes Champions
Cohorts are welcome and encouraged to join a Coworking session in the
weeks between Cohort Calls.

**Coworking Date-Times:**   
Tuesdays and Thursdays 12:00 -1:00 pm PT every second
week: Oct 15, 17, 29\*, 31, Nov 12, 14, 26, 28.   
\*Tuesday Oct 29 will be 11:00 - 12:00 PT.

## Participating teams and individuals

Some brief information about participants. Please add any edits directly
(we’ll learn how in our GitHub Clinic!)

1. **PIFSC Socioeconomics**: My name is Crystal Dombrow and I analyze socioeconomic cost-earnings survey data from small boat fisheries in the Pacific Islands region.
2. **Alaska HCD**: Our team works on EFH in AK. We are interested in learning best practices for data workflow and report writing. You can see more here: [Alaska Essential Fish Habitat](https://www.fisheries.noaa.gov/alaska/habitat-conservation/essential-fish-habitat-efh-alaska). Names: Skylar Bayer, Mallarie Yeager, Molly Zaleski, Mason Smith.

## Our Team

Julie Lowndes (@jules32), Openscapes   
Stefanie Butland (@stefaniebutland), Openscapes  
Eli Holmes (@eeholmes), NMFS Open Science  
Jon Peake (@jonpeake), NMFS Open Science   
NMFS Openscapes Mentors

## More about Openscapes and the Champions program:

- [**NMFS Openscapes Champions
  Cohorts**](https://nmfs-openscapes.github.io/champions.html)
- [**Our path to better science in less time using open data science
  tools**](https://www.nature.com/articles/s41559-017-0160) (Lowndes et
  al. 2017) - This describes a marine science team’s transition to open
  collaborative teamwork. It was the original inspiration for creating
  the Champions Program and heavily influences the Core Lessons. We’ll
  ask that everyone participating reads it before our first Cohort Call.
- [**Supercharge your research: a ten-week plan for open data science**](https://openscapes.github.io/supercharge-research/) (Lowndes et
  al. 2019) - This was co-authored with the inaugural Champions Cohort,
  capturing the most valuable take-aways for marine and environmental
  science early career faculty.
- [**Shifting institutional culture to develop climate solutions with
  Open Science**](https://onlinelibrary.wiley.com/doi/10.1002/ece3.11341) (Lowndes
  et al. 2019) - This was co-authored by Openscapes mentors across
  organizations – including NASA Earthdata, NOAA Fisheries, EPA,
  California Water Boards, Pathways to Open Science, Fred Hutch Cancer
  Center.
