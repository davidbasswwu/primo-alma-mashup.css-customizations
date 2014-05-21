primo-alma-openurl-mashup.css-customizations
============================================

Primo openurl CSS customizations

David Bass
WWU Libraries
21 May 2014

Here are the steps I took to change the CSS on a page like http://tinyurl.com/openurl-example

1.	I modified the existing CSS and created new classes by using Chrome's "inspect element" style editor.  If you’re not familiar with how to use that tool, you should be able to find a tutorial on YouTube by searching for “chrome inspect element css tutorial”, or you can use our css file to help you get started.

2.	Once I had the CSS I wanted, I added it to a custom CSS file and stored it on our webserver:
> http://library.wwu.edu/info/alma/css/viewit_customizations.css 

3.	Then I logged-in to Alma, and went to General Configuration > Configuration Menu > Branding/Logo > Digital Delivery > Add Skin, and downloaded the provided "Default Zip file".  Unzip that file, and then replace the contents of mashup.css with your custom CSS, or with the following line of code (which points to the CSS file on your web server):
> @import url("//your.website.edu/info/alma/css/viewit_customizations.css?year-month-day"); 

The advantage of hosting the file on your webserver with @import is that you can quickly and easily make changes to the CSS without having to download, unzip, modify, zip, and upload your changes into Alma again.  The name of my new skin in Alma is "viewit_customizations".  

4.	Zip the files and upload them into Alma.

5.	Login to the Primo Back Office (PBO), go to Advanced Configuration > All Mapping Tables> Delivery > Templates, and append "&req.skin=viewit_customizations" to the end of the following mapping tables:  
 * Almaviewit
 * Almaviewit_remote
 * almaviewit_services

Please note: ***3rd party cookies must be enabled in your browser for these CSS customizations to work***.  If you have 3rd party cookies disabled (as they are by default in Safari), you will see the default CSS.  
