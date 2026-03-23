## relation_capture

This project performs LLM-driven annotation to partition the Flickr30k dataset. It is based on the NaaN software platform.

### Installation

1. Install NaanIDE [using npm](https://www.npmjs.com/package/@naanlang/naanide).
2. Create a credentials JSON file to access the LLM API (see below)
3. Verify the pathname location for the flickr30k folder at the top of source/main.nlg
4. Build and Run the software
5. In the REPL console that starts, use `hello()` to verify access to the LLM and `convert(firstLine, lastLine)` to generate relational annotations for the specified line number range. There is also a `test()` function to execute for a single line as a smoke test.

The annotated CSV file will be emitted as `augmented_aws.csv` or `augmented_yc.csv` depending on the LLM chosen.

### Prompt

The prompt document, which includes specific processing for the CSV file formats, is one of the following:

* label_gigachat.txt
* label_openai.txt

These can be freely modified, after which you should build and run again, and then use the `convert()` function.

### Credentials

Exact credentials depend on the LLM being used. Two options are:

OpenAI `openai_creds.json`:

	{
		{
	    "login": {
	        "relayHost": "your.proxy.host",
	        "relayHostKey": "proxy.authentication.token",
	        "apiKey": "openai.api.key",
	        "description": "optional.description"
	    }
	}

GigaChat `gigachat_creds.json`:

	{
	    "login": {
	        "authType": "Basic",
	        "authKey": "gigachat.api.key",
	        "scope": "GIGACHAT_API_B2B or scope.from.gigachat",
	        "description": "optional.description"
	    }
	}
