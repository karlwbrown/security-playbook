# Brakeman 
Brakeman is a source code security analysis tool **for Rails projects**. 

One great aspect of brakeman is that, not only does it scan your code and alert you to potential security bugs, but it also provides extensive documentation to help you understand the dangers of each vulnerability. 

### Installation
`$ gem install brakeman`

### Usage
`$ brakeman my-project/`  
##### Useful Options
-A, --run-all-checks (Run all default and optional checks)  

-q, --quiet (Suppresses informational output)

--skip-files

-d, --debug

-k, --checks (List all available vulnerability checks)

-f, --format 

-o, --output 

--confidence-level (Set minimal confidence level to be reported (1 - 3). This option can be used to reduce noise and/or potential false positives.)

You can specify the Rails version with -4,5 etc (though please make sure your version of Rails is secure. You can check known vulnerabilities [here][rails_cve].)  

[rails_cve]:https://www.cvedetails.com/vulnerability-list/vendor_id-12043/product_id-22568/Rubyonrails-Ruby-On-Rails.html

##### A "Heavier" Run:
`$ brakeman my-project/ -A -f html -o brakeman-report-DATE.html`  
This is probably best suited for manual testing, I would not recommend this kind of scan in your pipeline, but it's good to run after significant changes have been made to the code.

##### "Light" Run:
`$ brakeman my-project/ --faster -confidence-level 2 -f html -o brakeman-report-DATE.html`
While you might not want to specifiy a file to write output to in your pipeline, a scan like this could be a good option. Just make sure failures (and possibly passing checks) are adequately logged in your console for debugging. You can silence repetitive false positives in the config file or in the command itself.  

Checkout further documentation on Brakeman options [here][brakeman_link].

[brakeman_link]:http://brakemanscanner.org/docs/options/


