# Veracode Community Policy Examples

A collection of example application security "policies as code" that can be added to your Veracode organization account using the process below.

## Adding a policy to your Veracode organization

To add one of these policies to your organization in Veracode, use the Veracode Policy API. This example uses httpie with the Veracode API Signing tool.

### Before you start

1. You must use a user with the Policy Manager role.
1. [Generate your API credentials](https://help.veracode.com/go/c_api_credentials3) and store them in a [Veracode credentials file](https://help.veracode.com/go/c_configure_api_cred_file) (or use [environment variables](https://help.veracode.com/go/t_store_creds_linux_env)).
1. Install the Veracode Python Authentication Library.
1. Install [HTTPie](https://help.veracode.com/go/c_httpie_tool). (You can use other API tools, but HTTPie is used for the command line examples below.)

### Add a policy

1. Download the policy JSON file to your local system (e.g. `example.json`).
2. Execute the following command at the command line:

`http --auth-type=veracode_hmac POST "https://api.veracode.com/appsec/v1/policies" < example.json`

## Example policies

* [FISMA](examples/fisma.json) - NVD cross-section mappings of CWEs.  DIACAP/FEDRAMP based off of the same requirements.
* [HIPAA](examples/hipaa.json) - Example policy to act as a guide for those attempting to comply with HIPAA + Omnibus/HITECH/HITRUST.
* [OWASP API Security Top 10 2019](examples/owaspapi2019.json) - Policy based on the CWE mappings in the (preview version of the) OWASP API Security Top 10 list for 2019. (Note: *In some cases, child or parent CWEs of the ones mentioned in the standard have been used depending on how Veracode categorizes the vulnerabilities.*)
* [Veracode Verified](https://veracode.com/verified) Policies
  * [Verified Standard](examples/verified/verified-standard.json) - initial level of Veracode Verified
  * [Verified Team](examples/verified/verified-team.json) - second level of Veracode Verified
  * [Verified Continuous](examples/verified/verified-continuous.json) - highest level of Veracode Verified
