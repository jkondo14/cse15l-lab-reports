# Lab 3 Report - Jake Kondo
---
## Part 1 - Bugs
---
### Fail-Inducing Input
```
  @Test
  public void testReversed() {
    int[] input1 = {8,9};
    assertArrayEquals(new int[]{9,8}, ArrayExamples.reversed(input1));
  }
```
### Input that does not induce a failure
```
  @Test
  public void testReversed() {
    int[] input1 = {};
    assertArrayEquals(new int[]{}, ArrayExamples.reversed(input1));
  }
```
### Symptoms of Fail-Inducing Input
```
  @Test
  public void testReversed() {
    int[] input1 = {};
    assertArrayEquals(new int[]{}, ArrayExamples.reversed(input1));
  }

    @Test
  public void testReversed2() {
    int[] input1 = {8};
    assertArrayEquals(new int[]{8}, ArrayExamples.reversed(input1));
  }
```
<img width="979" alt="Screenshot 2023-11-05 at 8 50 39 PM" src="https://github.com/jkondo14/cse15l-lab-reports/assets/146896972/35a553f6-b3d4-4d9c-8ac1-cdb98be92b74">

### Bug Fix Before and After

**Before**
```
  static int[] reversed(int[] arr) {
    int[] newArray = new int[arr.length];
    for(int i = 0; i < arr.length; i += 1) {
      arr[i] = newArray[arr.length - i - 1];
    }
    return arr;
  }
```
**After**
```
  static int[] reversed(int[] arr) {
    int[] newArray = new int[arr.length];
    for(int i = 0; i < arr.length; i += 1) {
      newArray[i] = arr[arr.length - i - 1];
    }
    return newArray;
  }
```
<img width="402" alt="Screenshot 2023-11-05 at 8 56 27 PM" src="https://github.com/jkondo14/cse15l-lab-reports/assets/146896972/c90a469e-dd92-47cd-b0f3-5bd0064c2b1d">
<br />
The original code changed each index of the original array with elements from newArray, which does not contain any element since it is a new Array, thus the code did not copy into the right array or copy it in reverse order into either array.
<br />
<br />
The new code copies the elements from the original array into newArray in reverse orders and returns newArray unlike the original code, where it returned the original array.

## Part 2 - Researching Commands
### Find Command
For sourcing, I used the man find command in the terminal to find which primaries to use for the find command.
**find -empty**
```
tamonkondo@Tamons-MacBook-Air technical % find biomed -empty
biomed/s.txt
```
The find command with the empty primary finds an empty file within the directory and in the code above, I added an empty txt file to biomed. After that, I used the find biomed -empty command to see if the biomed directory had any empty files, which the command could find. The find -empty command is useful to ensure there are no empty files or which empty files are on hand to write in. 
```
tamonkondo@Tamons-MacBook-Air technical % find biomed -empty
biomed/s.txt
tamonkondo@Tamons-MacBook-Air technical %
```
The find command with the empty primary finds an empty file within the directory and in the code above, since the plos directory did not have any empty files, the terminal returned nothing. The find -empty command is useful to ensure there are no empty files or which empty files are on hand to write in. 
<br />
<br />
**find -delete**
```
tamonkondo@Tamons-MacBook-Air technical % find biomed/s.txt -delete
tamonkondo@Tamons-MacBook-Air technical %
```
The find -delete command takes a file path as an argument and deletes the file in the file path like how the command deleted s.txt from the biomed directory. This is useful when we need to get rid of a file when we know the name and do not want to look for it, especially in bigger files where there can be tens of thousands of files.
```
tamonkondo@Tamons-MacBook-Air technical % find biomed/a.txt -delete    
find: biomed/a.txt: No such file or directory
tamonkondo@Tamons-MacBook-Air technical % find biomed/rr196.txt -delete
tamonkondo@Tamons-MacBook-Air technical % 
```
The find -delete command takes a file path as an argument and deletes the file in the file path like how the command deleted rr196.txt from the biomed directory. However, this command does not work if the file does not exist within the directory such as a.txt. This is useful when we need to get rid of a file when we know the name and do not want to look for it, especially in bigger files where there can be tens of thousands of files.
<br />
<br />
**find -type**
```
tamonkondo@Tamons-MacBook-Air technical % find biomed/rr191.txt  -type f
biomed/rr191.txt
tamonkondo@Tamons-MacBook-Air technical % 
```
The find -type command finds a certain type of file depending on what the argument is after the type command. The code above shows that using -type with f shows the regular files within biomed/rr191.txt, which is the rr191.txt file within the biomed directory. The -type command for find is especially useful when looking for a certain type of file within a directory or a folder since there can be a lot of files and this command can be used to filter it.
```
tamonkondo@Tamons-MacBook-Air technical % find 911report -type f
911report/chapter-13.4.txt
911report/chapter-13.5.txt
911report/chapter-13.1.txt
911report/chapter-13.2.txt
911report/chapter-13.3.txt
911report/chapter-3.txt
911report/chapter-2.txt
911report/chapter-1.txt
911report/chapter-5.txt
911report/chapter-6.txt
911report/chapter-7.txt
911report/chapter-9.txt
911report/chapter-8.txt
911report/preface.txt
911report/chapter-12.txt
911report/chapter-10.txt
911report/chapter-11.txt
tamonkondo@Tamons-MacBook-Air technical %
```
The find -type command finds a certain type of file depending on what the argument is after the type command. The code above shows that using -type with f shows the regular files within the 911report directory, which is the handful of files within the 911report directory. The -type command for find is especially useful when looking for a certain type of file within a directory or a folder since there can be a lot of files and this command can be used to filter it.
<br />
<br />
**find -print**
```
tamonkondo@Tamons-MacBook-Air technical % find 911report -print
911report
911report/chapter-13.4.txt
911report/chapter-13.5.txt
911report/chapter-13.1.txt
911report/chapter-13.2.txt
911report/chapter-13.3.txt
911report/chapter-3.txt
911report/chapter-2.txt
911report/chapter-1.txt
911report/chapter-5.txt
911report/chapter-6.txt
911report/chapter-7.txt
911report/chapter-9.txt
911report/chapter-8.txt
911report/preface.txt
911report/chapter-12.txt
911report/chapter-10.txt
911report/chapter-11.txt
tamonkondo@Tamons-MacBook-Air technical %
```
The find -print command prints out all the files within that directory and the directories within the directory, including the directory specified in the command. The code above shows the directories and files of the 911report directory. The find -print command is useful when wanting to see what directories or files or contained in a specific directory without having to actually go click around and look for it. 
```
tamonkondo@Tamons-MacBook-Air technical % find government -print
government
government/About_LSC
government/About_LSC/LegalServCorp_v_VelazquezSyllabus.txt
government/About_LSC/Progress_report.txt
government/About_LSC/Strategic_report.txt
government/About_LSC/Comments_on_semiannual.txt
government/About_LSC/Special_report_to_congress.txt
government/About_LSC/CONFIG_STANDARDS.txt
government/About_LSC/commission_report.txt
government/About_LSC/LegalServCorp_v_VelazquezDissent.txt
government/About_LSC/ONTARIO_LEGAL_AID_SERIES.txt
government/About_LSC/LegalServCorp_v_VelazquezOpinion.txt
government/About_LSC/diversity_priorities.txt
government/About_LSC/reporting_system.txt
government/About_LSC/State_Planning_Report.txt
government/About_LSC/Protocol_Regarding_Access.txt
government/About_LSC/ODonnell_et_al_v_LSCdecision.txt
government/About_LSC/conference_highlights.txt
government/About_LSC/State_Planning_Special_Report.txt
government/Env_Prot_Agen
government/Env_Prot_Agen/multi102902.txt
government/Env_Prot_Agen/section-by-section_summary.txt
government/Env_Prot_Agen/jeffordslieberm.txt
government/Env_Prot_Agen/final.txt
government/Env_Prot_Agen/ctf7-10.txt
government/Env_Prot_Agen/ctf1-6.txt
government/Env_Prot_Agen/ro_clear_skies_book.txt
government/Env_Prot_Agen/ctm4-10.txt
government/Env_Prot_Agen/1-3_meth_901.txt
government/Env_Prot_Agen/atx1-6.txt
government/Env_Prot_Agen/tech_sectiong.txt
government/Env_Prot_Agen/bill.txt
government/Env_Prot_Agen/nov1.txt
government/Env_Prot_Agen/tech_adden.txt
government/Alcohol_Problems
government/Alcohol_Problems/Session2-PDF.txt
government/Alcohol_Problems/Session3-PDF.txt
government/Alcohol_Problems/DraftRecom-PDF.txt
government/Alcohol_Problems/Session4-PDF.txt
government/Gen_Account_Office
government/Gen_Account_Office/d0269g.txt
government/Gen_Account_Office/Testimony_cg00010t.txt
government/Gen_Account_Office/og97032.txt
government/Gen_Account_Office/og99036.txt
government/Gen_Account_Office/GovernmentAuditingStandards_yb2002ed.txt
government/Gen_Account_Office/Sept27-2002_d02966.txt
government/Gen_Account_Office/d01376g.txt
government/Gen_Account_Office/Statements_Feb28-1997_volume.txt
government/Gen_Account_Office/og97019.txt
government/Gen_Account_Office/pe1019.txt
government/Gen_Account_Office/Testimony_Jul15-2002_d02940t.txt
government/Gen_Account_Office/gg96118.txt
government/Gen_Account_Office/og97020.txt
government/Gen_Account_Office/ffm.txt
government/Gen_Account_Office/og97023.txt
government/Gen_Account_Office/July11-2001_gg00172r.txt
government/Gen_Account_Office/d01121g.txt
government/Gen_Account_Office/og96011.txt
government/Gen_Account_Office/d03419sp.txt
government/Gen_Account_Office/Letter_Walkeraug17let.txt
government/Gen_Account_Office/og97051.txt
government/Gen_Account_Office/og97045.txt
government/Gen_Account_Office/Testimony_d01609t.txt
government/Gen_Account_Office/og97050.txt
government/Gen_Account_Office/og96038.txt
government/Gen_Account_Office/og98029.txt
government/Gen_Account_Office/Sept14-2002_d011070.txt
government/Gen_Account_Office/d03273g.txt
government/Gen_Account_Office/Oct15-1999_gg00026t.txt
government/Gen_Account_Office/og96012.txt
government/Gen_Account_Office/og97046.txt
government/Gen_Account_Office/og97052.txt
government/Gen_Account_Office/d03232sp.txt
government/Gen_Account_Office/og97043.txt
government/Gen_Account_Office/June30-2000_gg00135r.txt
government/Gen_Account_Office/d01591sp.txt
government/Gen_Account_Office/Oct15-2001_d0224.txt
government/Gen_Account_Office/og96028.txt
government/Gen_Account_Office/og96014.txt
government/Gen_Account_Office/og97041.txt
government/Gen_Account_Office/og96015.txt
government/Gen_Account_Office/d01145g.txt
government/Gen_Account_Office/InternalControl_ai00021p.txt
government/Gen_Account_Office/og96031.txt
government/Gen_Account_Office/d01186g.txt
government/Gen_Account_Office/og96033.txt
government/Gen_Account_Office/og96027.txt
government/Gen_Account_Office/og98022.txt
government/Gen_Account_Office/og96026.txt
government/Gen_Account_Office/og96032.txt
government/Gen_Account_Office/im814.txt
government/Gen_Account_Office/og96036.txt
government/Gen_Account_Office/og96022.txt
government/Gen_Account_Office/og96023.txt
government/Gen_Account_Office/og96037.txt
government/Gen_Account_Office/og98032.txt
government/Gen_Account_Office/og98026.txt
government/Gen_Account_Office/og98030.txt
government/Gen_Account_Office/og98024.txt
government/Gen_Account_Office/og96009.txt
government/Gen_Account_Office/og96021.txt
government/Gen_Account_Office/og98018.txt
government/Gen_Account_Office/ai00134.txt
government/Gen_Account_Office/og96034.txt
government/Gen_Account_Office/og98019.txt
government/Gen_Account_Office/og96020.txt
government/Gen_Account_Office/Testimony_Jul17-2002_d02957t.txt
government/Gen_Account_Office/og96047.txt
government/Gen_Account_Office/ai9868.txt
government/Gen_Account_Office/og98041.txt
government/Gen_Account_Office/og97038.txt
government/Gen_Account_Office/Paper_Walker11-2002_acpro122.txt
government/Gen_Account_Office/og97011.txt
government/Gen_Account_Office/og97039.txt
government/Gen_Account_Office/May1998_ai98068.txt
government/Gen_Account_Office/og98040.txt
government/Gen_Account_Office/og96045.txt
government/Gen_Account_Office/og98044.txt
government/Gen_Account_Office/og96041.txt
government/Gen_Account_Office/d02701.txt
government/Gen_Account_Office/og97001.txt
government/Gen_Account_Office/og97028.txt
government/Gen_Account_Office/ai2132.txt
government/Gen_Account_Office/Letter_WalkerJan30-2001.txt
government/Gen_Account_Office/og96040.txt
government/Gen_Account_Office/og98045.txt
government/Gen_Account_Office/og96042.txt
government/Gen_Account_Office/og97002.txt
government/Gen_Account_Office/og97003.txt
government/Gen_Account_Office/og96043.txt
government/Gen_Account_Office/og98046.txt
government/Post_Rate_Comm
government/Post_Rate_Comm/Gleiman_EMASpeech.txt
government/Post_Rate_Comm/Mitchell_spyros-first-class.txt
government/Post_Rate_Comm/Cohenetal_CreamSkimming.txt
government/Post_Rate_Comm/Cohenetal_DeliveryCost.txt
government/Post_Rate_Comm/Mitchell_RMVancouver.txt
government/Post_Rate_Comm/Gleiman_gca2000.txt
government/Post_Rate_Comm/Cohenetal_Cost_Function.txt
government/Post_Rate_Comm/Redacted_Study.txt
government/Post_Rate_Comm/Mitchell_6-17-Mit.txt
government/Post_Rate_Comm/Cohenetal_comparison.txt
government/Post_Rate_Comm/Cohenetal_Scale.txt
government/Post_Rate_Comm/Cohenetal_RuralDelivery.txt
government/Post_Rate_Comm/ReportToCongress2002WEB.txt
government/Post_Rate_Comm/WolakSpeech_usps.txt
government/Media
government/Media/Federal_agency.txt
government/Media/water_fees.txt
government/Media/Helping_Out.txt
government/Media/balance_scales_of_justice.txt
government/Media/BusinessWire2.txt
government/Media/Legal-aid_chief.txt
government/Media/Unusual_Woodburn.txt
government/Media/Funding_cuts_force.txt
government/Media/Good_guys_reward.txt
government/Media/Anthem_Payout.txt
government/Media/Donald_Hilliker.txt
government/Media/Free_legal_service.txt
government/Media/Owning_a_Piece.txt
government/Media/Targeting_Domestic_Violence.txt
government/Media/highlight_Senior_Day.txt
government/Media/State_funding.txt
government/Media/Few_who_need.txt
government/Media/City_Council_Budget.txt
government/Media/Legal_system_fails_poor.txt
government/Media/Supporting_Legal_Center.txt
government/Media/Lindsays_legacy.txt
government/Media/New_funding_sources.txt
government/Media/Barnes_new_job.txt
government/Media/Providing_Legal_Aid.txt
government/Media/Nonprofit_Buys.txt
government/Media/Legal_Aid_in_Clay_County.txt
government/Media/Domestic_Violence_Ruling.txt
government/Media/Abuse_penalties.txt
government/Media/Law_Award_from_College.txt
government/Media/Law_Schools.txt
government/Media/Raising_the_Bar.txt
government/Media/Justice_for_all.txt
government/Media/agency_expands.txt
government/Media/Helping_Hands.txt
government/Media/Legal_hotline.txt
government/Media/not_accessible_to_disabled.txt
government/Media/Campaign_Pays.txt
government/Media/New_Online_Resources.txt
government/Media/Annual_Fee.txt
government/Media/Oregon_Poor.txt
government/Media/Barnes_pro_bono.txt
government/Media/Poor_Lacking_Legal_Aid.txt
government/Media/Paralegal_Honored.txt
government/Media/Workers_aid_center.txt
government/Media/Philly_Lawyers.txt
government/Media/Too_Crucial_to_Take_Cut.txt
government/Media/Pro_Bono_Services.txt
government/Media/Rumble_in_the_Bronx.txt
government/Media/FortWorthStarTelegram.txt
government/Media/predatory_loans.txt
government/Media/Survey.txt
government/Media/AP_LawSchoolDebts.txt
government/Media/Working_for_Free.txt
government/Media/Eviction_law.txt
government/Media/Law-school_grads.txt
government/Media/FY_04_Budget_Outlook.txt
government/Media/help_rent-to-own_tenants.txt
government/Media/Texas_Lawyer.txt
government/Media/Disaster_center.txt
government/Media/Kiosks_for_court_forms.txt
government/Media/Higher_Registration_Fees.txt
government/Media/Fire_Victims_Sue.txt
government/Media/Funds_Shortage.txt
government/Media/Terrorist_Attack.txt
government/Media/Butler_Co_attorneys.txt
government/Media/BergenCountyRecord.txt
government/Media/families_saved.txt
government/Media/Court_Keeps_Judge_From.txt
government/Media/Volunteers_Step_Up.txt
government/Media/Coup_Reshapes_Legal_Aid.txt
government/Media/IOLTA_INTEREST_RATE.txt
government/Media/Ginny_Kilgore.txt
government/Media/Legal_Aid_looks_to_legislators.txt
government/Media/Poverty_Lawyers.txt
government/Media/Wingates_winds.txt
government/Media/Avoids_Budget_Cut.txt
government/Media/grants_fail_to_come.txt
government/Media/Lockyer_Warns.txt
government/Media/It_Pays_to_Know.txt
government/Media/Self-Help_Website.txt
government/Media/Rental_rules.txt
government/Media/Using_Tech_Tools.txt
government/Media/Assuring_Underprivileged.txt
government/Media/Boone_legal_service.txt
government/Media/Firm_to_the_Poor_Needs_Help.txt
government/Media/Making_a_case.txt
government/Media/Barnes_Volunteers.txt
government/Media/Commercial_Appeal.txt
government/Media/Justice_requests.txt
government/Media/Free_Legal_Assistance.txt
government/Media/Local_Attorneys.txt
government/Media/Texas_Supreme_Court.txt
government/Media/Civil_Matters.txt
government/Media/Low-income_children.txt
government/Media/man_on_national_team.txt
government/Media/BusinessWire.txt
government/Media/Funding_May_Limit.txt
government/Media/The_Columbian.txt
government/Media/Higher_court.txt
government/Media/Service_Agency.txt
government/Media/Marylands_Legal_Aid.txt
government/Media/Bias_on_the_Job.txt
government/Media/Attorney_gives_his_time.txt
government/Media/Library_Lawyers.txt
government/Media/Crains_New_York_Business.txt
government/Media/Hard_to_Get.txt
government/Media/The_State_of_Pro_Bono.txt
government/Media/residents_sue_city.txt
government/Media/Legal_Aid_Society.txt
government/Media/GreensburgDailyNews.txt
government/Media/Major_Changes.txt
government/Media/Program_Lodges.txt
government/Media/Wilmington_lawyer.txt
government/Media/All_May_Have_Justice.txt
government/Media/Domestic_violence_aid.txt
government/Media/Advocate_for_Poor.txt
government/Media/fight_domestic_abuse.txt
government/Media/CommercialAppealMemphis2.txt
government/Media/Weak_economy.txt
government/Media/Lawyer_Web_Survey.txt
government/Media/Valley_Needing_Legal_Services.txt
government/Media/Barr_sharpening_ax.txt
government/Media/Legal_Aid_attorney.txt
government/Media/The_Bend_Bulletin.txt
government/Media/Legal_services_for_poor.txt
government/Media/Farm_workers.txt
government/Media/Entities_Merge.txt
government/Media/less_legal_aid.txt
government/Media/Understanding.txt
government/Media/Do-it-yourself_divorce.txt
government/Media/Politician_Practices.txt
government/Media/defend_yourself.txt
government/Media/Towson_Attorney.txt
government/Media/Pro-bono_road_show.txt
government/Media/A_Perk_of_Age.txt
government/Media/A_helping_hand.txt
government/Media/pro_bono_efforts.txt
government/Media/5_Legal_Groups.txt
government/Media/Greedy_Generous.txt
government/Media/Retirement_Has_Its_Appeal.txt
government/Media/RoanokeTimes.txt
government/Media/NJ_Legal_Services.txt
government/Media/Bridging_legal_aid_gap.txt
government/Media/Legal_Aid_campaign.txt
government/Media/Aid_Gets_7_Million.txt
tamonkondo@Tamons-MacBook-Air technical % 
```
The find -print command prints out all the files within that directory and the directories within the directory, including the directory specified in the command. The code above shows the directories and files of the government directory. The find -print command is useful when wanting to see what directories or files or contained in a specific directory without having to actually go click around and look for it. 
