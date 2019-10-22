# calibre-recipes

A set of custom recipes for automatic news fetching in [Calibre](https://calibre-ebook.com)

# Debugging
* Do a test run: 
```
ebook-convert PocketRSS.recipe .epub --dont-download-recipe --test --password <password> --username <username> -vvv
```
* Enable browser debugging:
```
import sys, logging
def enable_logging(br):
    logger = logging.getLogger("mechanize")
    logger.addHandler(logging.StreamHandler(sys.stdout))
    logger.setLevel(logging.DEBUG)
    br.set_debug_http(True)
    br.set_debug_responses(True)
    br.set_debug_redirects(True)
```
* Start the Python debugger at a specific line:
```
import pdb; pdb.set_trace()
```

# Warnings
* Due to limitations enforced by `getpocket.com`, PocketRSS will eventually tigger the following error if run too frequently: `Too many login attempts were made. Try again in 24 hours or reset your password.` The exact limits are not yet known, but were encountered during testing.
