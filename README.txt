Jmeter Functional Tests

Running Jmeter

    	COMMAND LINE MODE:
    	Make the tests run in command line mode using the -n flag.

	USAGE WITH REQUIRED FIELDS:
	$jmeter -Jusername=<common_api_username> -Jpassword=<common_api_password> 
         -t <jmeter_file>

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


