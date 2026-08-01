Context:
Act as a Senior Developer create strictly HTML page for user story extract and review agent from jira with customized UI not embedding/Without Langflow CDN. On selecting the user story the should be able to generate test case for the user story

Instructions:
1) Strictly DO NOT use the below langflow CDN for chat 
<script src="https://cdn.jsdelivr.net/gh/langflow-ai/langflow-embedded-chat@main/dist/build/static/js/bundle.min.js"></script>
2) Mandatorily page should be Custom page calling both the Langflow API 
3) Page should have the Option for clear and Copy
4) Generated Testcases should be exported in the Excel with below Format
TC ID|Description|steps|Expected result| Actual result
5) UI should have a Description about the Testcase Generator
6) Toggle for Dark and Light Theme
7) UI should have jira connection section with just a connect button and on connect should pull all the user stories
8) User stories pulled from jira should be selectable with as check box and have a button to " view user story " and " generate test cases.
9) Welcome message should be "Happy to help you in Testcase generation choose a user story"
10) Error message should be in red
11) click on "view user story" should show user story availabel details.clcik on "generate test cases" should generate Test cases for the chosen user story in the check box.
12) Placeholder for the test case section window should be --"Am Aishubot Here Type your user stories"
13) use the below APIs --API Baseurl,flowid,API key and model should be configurable in the script file no hardcoing in the HTML

HTTP Method: 
POST Endpoint for user story review agent:
http://localhost:7860/api/v1/run/15435741-d48a-4056-8579-a43a7a84e6e4?stream=false
Base URL: http://localhost:7860/api/v1/run
Flow ID:15435741-d48a-4056-8579-a43a7a84e6e4
API Key:sk-Bt3nslUkq-oXbOuPpCtkNEquPegTbV9hhDyePKrJYQ4


Request Body:
{
		           "output_type": "chat",
		           "input_type": "text",
		           "input_value": " user story from jira",
		           "tweaks": {
		             "GroqModel-XTvSW": {
		               "model_name": "qwen/qwen3.6-27b"
		             }
		           }
		         }



HTTP Method: 
POST Endpoint for Test case generator Day 9:
http://localhost:7860/api/v1/run/b6629b62-453e-4dae-b13c-2fbe80d28d8b?stream=false
Base URL: http://localhost:7860/api/v1/run
Flow ID:b6629b62-453e-4dae-b13c-2fbe80d28d8b
API Key:sk-Bt3nslUkq-oXbOuPpCtkNEquPegTbV9hhDyePKrJYQ4

{
		           "output_type": "chat",
		           "input_type": "chat",
		           "input_value": "Generate test cases for user story",
		           "tweaks": {
		             "GroqModel-XTvSW": {
		               "model_name": "qwen/qwen3.6-27b",
		               "temperature": 0.1
		             }
				   }
				   
				   }
