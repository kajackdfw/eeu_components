# eeu_components

## My Gripes about MVC Apps

How many times have you built data models with validation rules on the backend, and later had to put in some unfamiliar js 
library to do almost the same validation on the front end, to avoid making the user having to hit the submit button to see the validation messages. Or 
have you gone to the trouble of creating a backend service so you could submit the entire form every time the user changes one
field, so you could display the backend validation messages before the user hits the submit button? 

## Polymer Web Components for forms in MVC Application Views 

The purpose for this project is to provide a uniform set of web components for English Engineering Unit type form fields such as feet
 inches and fractions, and eliminate the duplication of validation code on front and backend, by utilizing a rest 
 service call in some components to validate a web component field as the user types in a value. Each component group file 
 is intended for one type of template, such as html or Blade, and only one style library such as Bootstrap , or Iron Elements per 
 group. I also hope to reduce the need for data transformers in the base application between the view and the database layer, such 
 as when a users desired date format is different from the Unix datetime format. Other front-end data transformations will be 
 considered.
 
## Design Rules / Requirements
 1. Only one validation rule for each field, with no duplication, or room for differences between back and front
 2. Minimal to no JQuery scripts in the page ( some required for bootstrap components of course, but not Paper Elements )
 3. No dependencies on framework classes like Laravel/Html Helper or ZF/Form Builder etc, only template compatibility
 4. Simple to use custom HTML tags
 5. If ajax is required in a field, it will be self contained in the web component, and the url can be passed to it from
  the parent application's view template.
 6. EEU fields will have a valid flag compatible with a Polymer event listener
 7. A submit button that will disable itself if other web component valid flags are false
 8. All component groups will have the same HTML tags
 9. Each component group will only use one style library ( Bootstrap or Paper Element or Foundation ), not 2 .
 10. Do not duplicate any HTML5 tags or their functionality ( wrappers or an alias may be considered )
  
## Groups / Component Files
 1. larapoly.html ( Laravel compatible with Bootstrap css )
 2. eeu_html_paper.html 
 
## Project Status
 Putting this on hold until late October, while completing LaraPoly for alpha release.
 
## Web Components ( html tags ) working in larapoly.html
 1. larapoly-display-dec-fifrac ( display feet inches and fraction for a decimal value )
 2. larapoly-input-dec-fifrac ( decimal input field value with feet inches and fraction label )
 3. larapoly-string and larapoly-string-inline
 4. larapoly-alert
 5. larapoly-double-select
 
## Web Components being considered for eeu_html_bootstrap ( html tags )
 1. *-input-fifrac-dec ( fifrac in , with field value set to decimal equivalent ) 
 2. *-input-rest-validated ( backend validated input field )
 3. *-input-combo 
 4. *-input-date ( submits unix format to app, and displays selected format to user )
 5. *-submit-if-fields-valid ( eliminate need for custom jquery scripts to disable submit button )
 
## Planned Features

 1. Support Input types like fifrac ( Feet Inches and Fractions )
 2. User Input Feedback / Front end validation messages
 3. Ajax support for validation via backend/rest service, or get serialized validation info from server
 4. Some simple input types with data transformers , such as *-input-date
 5. Request for special fields like IP numbers will be considered if request sent to kajackdfw@yahoo.com .
 
## Fixme / Todos
 
 0. Remove invalid date choices when min or max is set.
 0. Clean up responsive form style support ( inline vs non-inline style )
 0. Make alerts fade away after 90 seconds, or drop this component
 
## Updates

 0. 10/22/2015 | Combine larapoly-dec-to-frac-ro code into a single larapoly-dec-to-frac with a ro=true param. (749 lines)
 0. 10/21/2015 | combined string and string-inline together (831 lines)
 0. 10/20/2015 | Made min, max, and any other validation params, a Laravel style rule string like min:4|max:12 etc. (795 lines)
 0. 10/09/2015 | Option selected for double-select when the id value is initially provided. (617 Lines)
 0. 10/08/2015 | Created a demo page for web component issue 182
 9. 10/07/2015 | Made larapoly-double-select 100% dynamic. ( 580 lines in larapoly.html ) 
 8. 10/06/2015 | Removed all inline style code. 
 7. 10/04/2015 | New larapoly-double-select web component 
 6. 9/27/2015 | new Laravel dedicated fork at https://github.com/larapoly/larapoly 
 5. 9/20/2015 | eeu_blade_bootstrap.html will be forked to a new Laravel only repo. 
 4. 9/18/2015 | Enhanced error messages for *-string. *-string-inline needs more error red css. 
 3. 9/13/2015 | Had an excellent proof of concept test in my Laravel site with Polymer 
 2. 9/10/2015 | New outline of planned components on index.html page 
 1. 9/01/2015 | Removed the Iron Element dependency from eeu_html_bootstrap.html ( rule #9 violation ) 