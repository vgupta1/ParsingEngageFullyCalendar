# ParsingEngageFullyCalendar
This year (2023) the INFORMS Annual Meeting is using the Engagefully App.  Unfortunately, the app's calendar features leave a lot to be desired.

This little repository has some bare-bones (not rigorously tested) python code that allows one to export events from Engagefully to a csv and then use GoogleCalendar to upload that csv.  I threw this together for myself and welcome pull requests.  

# How do I use this?
 - Use the Engagefully app and add the sessions you want to your calendar.  I did this on mobile.
 - Export the calendar using the share functionality of your phone.  On iPhone, this generated a .txt file. A sample .txt file of output is available in the repo as `raw_my_informs_talks.txt'
 - Run the code in the above notebook.  It should create a output.csv file that has parsed the data into a suitable format.  A sample output.csv file is in the repo.
 - Follow these instructions [these instructions](https://support.google.com/calendar/answer/37095?hl=en) to create a  new calendar in google calendar.  You can do this in MST (for Phoenix, AZ).
 - Follow [these instructions](https://support.google.com/calendar/answer/37118?hl=en&co=GENIE.Platform%3DDesktop) to import events to your new calendar.  Be sure to add them to the calendar you just created.
 - Enjoy.  If anything goes screwy in the input process, you can just delete the calendar and try again.


## Known Issues (Happy for pull requests!)
 - Currently this only works for technical sessions.  The parsing code fails (in an untested way) for panels since EngageFully formats these differently in the export.  
 - Google Calendar .csv import has some [trouble with time zones](https://support.google.com/calendar/thread/16256597/family-calendar-csv-import-time-zone?hl=en#:~:text=CSV%20calendar%20import%20doesn't,the%20tz%20is%20GMT...)  Consequently, if you specify the time-zone on your calendar as MST (as you should for Phoenix) but your local timezone is not MST at the moment, it will import the calendar events at the wrong time.  (I'm in LA, so this doesn't matter for me.)  Two practical options:  One, someone could write the code to adjust the times of the .csv file appropriately. Two, wait till you arrive in Phoenix to do the import. :) 
