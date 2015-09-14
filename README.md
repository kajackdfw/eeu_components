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
 7. A submit button that will disable itself if valid flags are false
 8. All component groups will have the same HTML tags
 9. Each component group will only use one style library ( Bootstrap or Paper Element or Foundation ), not 2 .
 10. Do not duplicate any HTML5 tags or their functionality ( wrappers or an alias may be considered )
  
## Groups / Component Files
 1. eeu_html_bootstrap.html ( generic html with Bootstrap css )
 2. eeu_blade_bootstrap.html ( Laravel Compatible )
 3. eeu_html_paper.html 
 
## Project Status
 New, Google samples working, eeu-input-dec-fifrac working
 
## Web Components ( html tags ) working in eeu_html_bootstrap.html
 1. eeu-display-dec-fifrac ( display feet inches and fraction for a decimal value )
 2. eeu-input-dec-fifrac ( decimal input field value with feet inches and fraction label )
 
## Web Components being considered for eeu_html_bootstrap ( html tags )
 1. eeu-input-fifrac-dec ( fifrac in , with field value set to decimal equivalent ) 
 2. eeu-input-rest-validated ( backend validated input field )
 3. eeu-input-combo 
 4. eeu-input-unix-date ( submits unix format to app, and displays selected format to user )
 5. eeu-submit-if-fields-valid ( eliminate need for custom jquery scripts to disable submit button )
 
## Planned Features

 1. Support Input types like fifrac ( Feet Inches and Fractions )
 2. User Input Feedback / Front end validation messages
 3. Ajax support for validation via backend/rest service, or get serialized validation info from server
 4. Some simple input types with data transformers , such as eeu-input-unix-date
 5. a Blade/Laravel compatible set of components to reduce need for data transformations between the UI and the database
 
## Fixme / Todos
 
 1. Create a sample Blade/Bootstrap EEU web components file for Laravel developers.
 2. Decide witch component to build next.
 3. Remove any inline styles used in prototype web components.
 4. Installation instructions in individual web component files like the Laravel set. 
 
## Updates
 9/13/2015 | Had an excellent proof of concept test in my Laravel site with Polymer
 9/10/2015 | New outline of planned components on index.html page
 9/1/2015 | Removed the Iron Element dependency from eeu_html_bootstrap.html ( rule #9 violation )