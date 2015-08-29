# eeu_components
## Polymer Web Components for forms in MVC Views 

The purpose for this project is to provide a uniform set of web components for English Engineering Unit type form fields such as feet
 inches and fractions and eliminate the duplication of validation code on front and backend, by utilizing a rest 
 service call in some components to validate a web component field as the user types in a value. Each component group file 
 is intended for one type of template, such as html or Blade, and one style library such as Bootstrap , or Iron Elements.
 
## Groups / Component Files
 1. eeu_html_bootstrap.html ( generic html with Bootstrap css )
 2. eeu_blade_bootstrap.html ( Laravel Compatible )
 3. eeu_html_iron.html ( may be changed to Paper Elements )
 
## Project Status
 New, Google samples working, eeu-input-dec-fifrac working
 
## Web Components ( html tags )
 1. eeu-input-dec-fifrac ( decimal input field value with feet inches and fraction label )
 2. eeu-input-fifrac-dec ( fifrac in , with field value set to decimal equivalent ) 
 3. eeu-input-rest-validated ( backend validated input field )
 4. eeu-submit-if-fields-valid
 5. eeu-input-combo
 
## Planned Features

1. Support Input types like fifrac ( Feet Inches and Fractions )
2. User Input Feedback
3. Input Validation
4. Ajax support for backend/rest service validation, or get serialized validation info from server
 
