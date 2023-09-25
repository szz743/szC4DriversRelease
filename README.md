szWebControl. A simple http driver that can change a system variable value.
Accepts POST JSON requests.

Request sample 1:
{
	"command":"setSystemVariable", 
	"name":"TEST_VARIABLE_1", 
	"value":"some-value"
}

Request sample 2:
[
{
	"command":"setSystemVariable", 
	"name":"TEST_VARIABLE_1", 
	"value":"{parameterized value: {1}, {2}",
	"valueParams" : {
		"1":"param1",
		"2":"param2"
	}
},
{
	"command":"setSystemVariable", 
	"name":"TEST_VARIABLE_2", 
	"value":"CURRENT TIME: {time}"
},
{
	"command":"setSystemVariable", 
	"name":"TEST_VARIABLE_3", 
	"value":"{date} {time}"
}
]

Response sample 1:
{
	"result": true
}

Response sample 2:
{
	"result": false,
	"error": "Command 'setSystemVariable' failed: Unknown system variable 'TEST_VARIABLE_4'"
}

Response sample 3:
{
	"result": false,
	"error": "Command or array of commands is required"
}

Response sample 4:
{
	"result": false,
	"error": "Bad variable value"
}

OS version 3.3.0 is required at least
