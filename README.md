# Artillery
Repo used in the "Lock &amp; Loaded - A brief introduction on Artillery" Testaholics Anonymous presentation

1. Node.js tool
Artillery.io is a Node.js tool with a basic СLI, which is a far simpler way to run performance tests.

2. Broad support of protocols, frameworks, and libraries
Out of the box, Artillery.io will support:
HTTP
Socket.IO
WebSocket
However, you can use Artillery.io to test any stack, thanks to the plugin interface.

3. YAML format
Artillery.io writes tests in YAML format which makes them readable and easy to understand. Artillery also supports a JSON format for testing.

4. Accessible scenarios
With Artillery's scenarios and phases, you can build more flexible tests and cover multiple use cases in parallel. Also, it takes you just a few steps and conditions to set up tests for complex user behaviours.

6. Detailed reports
After running tests, you can create a JSON report through the --output flag. Also, you can generate an HTML report out of JSON to save it as a file or export it to your browser.

7. Artillery Docs
Artillery provides numerous documents to browse for instructions and other useful info. This helps you get the performance testing software up and running much smoother than with other similar tools. Also, you can look up support from other developers on community forums.

## Initial Setup
In my setup I'm using Node v17.7.1 (node -v) and Artillery Core v2.0.01-12 (artillery -v) with cmd as my shell (on Windows 10)

`npm install -g artillery@latest`

## Running tests
Is as easy as writing a command line: `artillery quick --count 15 -n 30 https://www.google.com/search?q=%22Testaholics+Anonymous%22`

In real life, however, you will be using multiple urls, users, phases, etc..., which will be defined in YAML file. You will be running them using the command:

`artillery run -k /path_to/<test>.yml`

You can use the `-q` flag to run silently

## Debugging tests
In your terminal, run the following command prior to running your tests: `set/export DEBUG=http,http:capture,http:response` (set for Windows, export for Mac)

To turn off debugging, either start a new shell or execute `set/export DEBUG=`  (set for Windows, export for Mac)

## Reporting

### Generate a JSON report file while running the test

If you want to collect the performance metrics gathered by Artillery, you can do so by adding the output parameter (make sure the folder exist prior to running the test)

`artillery run -o report_folder/report_name.json -k /path_to/<test>.yml`

### Generating an HTML report

Upon the generation of the json report file, you can generate a graphical report from the json file and disaplay the report in your default browser.

`artillery report report_folder/report_name.json`

## References

https://www.artillery.io/docs/guides/guides/test-script-reference

https://www.artillery.io/docs/guides/guides/http-reference

https://github.com/artilleryio/artillery

