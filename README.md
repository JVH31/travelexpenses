# TravelExpenses #

[Installation/Download](#installationdownload) | [Usage](#usage-examples) | [Know Issues/Todos](#known-issuestodos) | [Third Party Code](#third-party-code) | [Licence](#visualforce-tablegrid-license)

TableGrid is a free, open-source Force.com library, that provides users and developers a *highly customizable, native-looking, sortable, filterable, editable* Grid Visualforce component. 
This component can be used as an advanced, highly configurable (by developer and user) replacement of <apex:pageBlockTable>s and Standard Related Lists.

> ![Two instances of Visualforce TableGrid, one read-only and one editable version.](https://raw.github.com/Up2Go/TableGrid/master/resources/grid.png)
 
 
## Features: ##
- Native Salesforce.com Look And Feel
- Works as Standalone table grid or as an embedded replacement for Related List
- Works as replacement for Standard Lookup popups with <c:advancedLookup>
- Works for Standard and Custom SObjects
- Spreadsheet-like Cell-Editing
- Delete Muliple records
- Pagination with cutomizable page size
- Filter Builder UI to let users filter records
- Field Selection UI to let users customize columns 
- Each user`s customizations can be auto-saved in a "database-cookie"


## Installation/Download ##

**[Directly deploy to your Salesforce org](https://githubsfdeploy.herokuapp.com/app/githubdeploy/Up2Go/travelexpenses)**

or

1. Grab the source code: `git clone https://github.com/Up2Go/travelexpenses.git`
2. Deploy the Force.com metadata under the src folder to your destination org. You can deploy that using [Force.com Migration Tool](http://wiki.developerforce.com/index.php/Force.com_Migration_Tool) #or by using [Force.com IDE](http://wiki.developerforce.com/index.php/Force.com_IDE)


## Usage Examples ##
Please see `components/tableGrid.component` for a detailed description of all attributes. The following examples should give 
you enough information to get started.

### TableGrid in a standalone Visualforce page

> ![TableGrid in List mode with Customizations turned on](https://raw.github.com/Up2Go/TableGrid/master/resources/customizable.png)

This  snippet is taken from the sample page `pages/tableGridStandalone.page`.
 
        <apex:page showHeader="false" sidebar="false"> 
        	<apex:form >
        		...
			    <c:tableGrid type="Opportunity" 
		        			 title="Opportunities"
		                     fields="Name,StageName,Amount,CloseDate" 
		                     sortBy="Name" 
		                     image="/img/icon/hands24.png"
		                     sortDescending="true"
		                     mode="list"
		                     customizeFields="true"
		                     customizeFilter="true"
		                     pageSize="5" />   
		    	 ...
		   	</apex:form>
		</apex:page>
         

### TableGrid embedded into Standard Page Layouts

> ![Two TableGrid instanced replacing Standard Related Lists in a Standard Page Layout](https://raw.github.com/Up2Go/TableGrid/master/resources/tableGrid_embedded.png)

This  snippet is taken from the sample page `pages/tableGridRelatedList.page` and `pages/tableGridEmbedded.page`

		<apex:page standardController="Account"> 
		    <apex:form>
		        ...
		        
		        <!-- Advanced Related list -->
		        <c:tableGrid type="Contact" 
		                     fields="Id, Name, Email, Birthdate" 
		                     filter="AccountId = `{!Account.Id}`"
		                     title="Contacts" 
		                     gridPageId="readonly"
		                     pageSize="5"
		                     mode="list"/>
		             
		        <!-- Editable grid with customization turned on -->        
		        <c:tableGrid type="Opportunity" 
		                     fields="Name,StageName,Amount,CloseDate" 
		                     filter="AccountId = `{!Account.Id}`"
		                     sortBy="Name" 
		                     sortDescending="true"
		                     title="Opportunities" 
		                     gridPageId="editable"
		                     customizeFields="true"
		                     customizeFilter="true"
		                     pageSize="5"
		                     mode="edit"/>  
		                        
		    	 ...
		   	</apex:form>
		</apex:page>


### TableGrid as an Advanced Lookup Popup

> ![TableGrid as an Advanced Lookup Popup](https://raw.github.com/Up2Go/TableGrid/master/resources/advancedLookup.png)

This  snippet is taken from the sample page `pages/tableGridAdvancedLookup.page`.

	<apex:page standardController="Contact">    
	    <apex:form>
	    	...
		    <c:advancedLookup > 
		        <apex:inputField value="{!Contact.AccountId}" label="" />
		    </c:advancedLookup>
		    ...
		</apex:form>
	</apex:page>
    
 

## Known Issues/Todos ##

- tbd


## Third-party Code ##

- [Google Place Autocomplete](https://developers.google.com/places/documentation/autocomplete), returns place information based on text search terms and can be used to provide autocomplete functionality for text-based geographic searches.

- [jQuery](http://jquery.com), a fast, small, and feature-rich JavaScript library.

- [Bootstrap](http://getbootstrap.com/), the most popular HTML, CSS, and JS framework for developing responsive, mobile first projects on the web.

- [Bootstrap Switch](http://www.bootstrap-switch.org/), turns checkboxes and radio buttons in toggle switches.

- [Bootstrap datetimepicker](https://github.com/Eonasdan/bootstrap-datetimepicker), a nice datetimepicker widget.

- [Visualstrap](http://blogforce9dev-developer-edition.ap1.force.com/ProjectDetail?id=a0290000009MI61), a visualforce implementation of Bootstrap. VisualStrap is a set of components that work inside your visualforce page without affecting the standard layouts.



## Visualforce TableGrid License ##

Copyright (C) 2013 UP2GO International LLC, David Renz, Robert Méndez

Permission is hereby granted, free of charge, to any person obtaining a
copy of this software and associated documentation files (the
"Software"), to deal in the Software without restriction, including
without limitation the rights to use, copy, modify, merge, publish,
distribute, sublicense, and/or sell copies of the Software, and to
permit persons to whom the Software is furnished to do so, subject to
the following conditions:

The above copyright notice and this permission notice shall be included
in all copies or substantial portions of the Software.

THE SOFTWARE IS PROVIDED "AS IS", WITHOUT WARRANTY OF ANY KIND, EXPRESS
OR IMPLIED, INCLUDING BUT NOT LIMITED TO THE WARRANTIES OF
MERCHANTABILITY, FITNESS FOR A PARTICULAR PURPOSE AND
NONINFRINGEMENT. IN NO EVENT SHALL THE AUTHORS OR COPYRIGHT HOLDERS BE
LIABLE FOR ANY CLAIM, DAMAGES OR OTHER LIABILITY, WHETHER IN AN ACTION
OF CONTRACT, TORT OR OTHERWISE, ARISING FROM, OUT OF OR IN CONNECTION
WITH THE SOFTWARE OR THE USE OR OTHER DEALINGS IN THE SOFTWARE.
