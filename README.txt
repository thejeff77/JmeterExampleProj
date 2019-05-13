# Jmeter Example Project

* Good starter example project for command-line specification of stacks, including setting a default if unset.
* Easily scripted to be a parameterized jenkins job via command line specification of run configurations.
* Authentication strategy assumes Auth:Basic with known username/password. Change the "Authorization Manager" to specify Kerberos, or add an OAuth flow to obtain a token.
* Includes examples for REGEX parsing of return data and using the parsed values in subsequent requests.
* Includes examples of JSON Path Extraction.
* Includes colored output printing for each result for easier parsing of results via command line only execution.

### Where to get started: 

1. Configure jmeter for command line launch by adding Jmeter's /bin bath to your PATH in either Windows or Linux. Linux is done via .profile or .bashrc typically.
2. Launch the project for the first time with: ">jmeter -t API_Test.jmx" (or ">jmeter.bat -t API_Test.jmx" on Linux)
3. Open "Test Variables" and familiarize yourself with the __P format. In the following Value: "${__P(stack,dev.example.com)}", the "__P(stack" says to accept a command line parameter named "-Jstack=<value>" and if it isn't set, use "dev.example.com".
4. Replace "dev.example.com" in the Value mentioned in step 3 with your default test environment (the one to use as default if left unspecified).
5. Run test with example input specified below. View the "Debug Sampler" to see how all variables are set. View the "Results Tree" for detailed HTTP results.

### Running Example Project in Jmeter

	COMMAND LINE MODE:
	Make the tests run in command line mode using the -n flag.

	USAGE WITH REQUIRED FIELDS:
	$jmeter -Jusername=<common_api_username> -Jpassword=<common_api_password> 
         -t API_Test.jmx

	EXAMPLE:
	$jmeter -Jusername=user123 -Jpassword=pw123
         -t API_Test.jmx

	OPTIONAL PARAMETERS AND THEIR DEFAULTS
	-Jstack=<www.example.com|dev.example.com|etc...>
		DEFAULT: www.example.com

	-Jcommon.api_svc_protocol=<http|https>
		DEFAULT: https

	-Jcommon.api_svc_port=<443|any-othervalid-port>
		DEFAULT: 443

	PROXY:
	Specify a proxy host and port by adding "-H <proxy_host> -P 8080"
	Note: there is no "=" equals sign for these.
