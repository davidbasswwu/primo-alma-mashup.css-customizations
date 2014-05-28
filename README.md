Primo openurl / Alma mashup.css customizations
---

Here are the steps I took to change the CSS on our openurl pages (example: http://tinyurl.com/openurl-example) which are powered by ExLibris Alma/Primo:

1.	I modified the existing CSS and created new classes by using Chrome's "inspect element" style editor.

2.	Once I had the CSS I wanted, I added it to a custom CSS file and stored it on our webserver:
> http://library.wwu.edu/info/alma/css/viewit_customizations.css 

3.	Then I logged-in to Alma, and went to General Configuration > Configuration Menu > Branding/Logo > Digital Delivery > Add Skin, and downloaded the provided "Default Zip file".  Unzip that file, and then replace the contents of mashup.css with your custom CSS, or with the following line of code (which points to the CSS file on your web server):
> @import url("//your.website.edu/info/alma/css/viewit_customizations.css?year-month-day"); 

  The advantage of hosting the file on your webserver with @import is that you can quickly and easily make changes to the CSS without having to download, unzip, modify, zip, and upload your changes into Alma again.  The name of my new skin in Alma is "viewit_customizations".  

4.	Zip the files and upload them into Alma.

5.	Login to the Primo Back Office (PBO), go to Advanced Configuration > All Mapping Tables> Delivery > Templates, and append "&req.skin=viewit_customizations" to the end of the following mapping table values:  
 * Almaviewit
 * Almaviewit_remote
 * almaviewit_services

Please note: 
 * ***3rd party cookies and data must be enabled in your browser for these CSS customizations to work***.  If you have 3rd party cookies or data disabled (as they are by default in Safari), you will see the default CSS.  Here is a video showing the difference when 3rd party data/cookies are enabled and disabled:  http://screencast.com/t/SNlUugJrJ  
 * the "Public notes" text is not inside of an LI (screenshot: http://bit.ly/1c1pjp6), which makes it difficult to write CSS  for the uResolver ViewIt iFrame.  I reported this to ExLibris in February 2014, but there is no estimated date for a fix yet.  We are currently on Primo 4.6.
 * we also have customized CSS in http://library.wwu.edu/info/alma/css/wwu_skin_no_barcode.css
