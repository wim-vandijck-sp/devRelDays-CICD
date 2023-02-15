README for Log4j 2.17.1 Update for IdentityIQ

Security Fix Deliverable:
 
  identityiq-<versions>-IIQCB-4610.zip


General Information:

  As part of SailPoint's ongoing commitment to the security of our solutions, 
  our Engineering team is releasing a security fix to address a critical 
  vulnerability in current releases of IdentityIQ.
 
  For IdentityIQ version 8.0 and later, this security fix provides version 
  2.17.1 of the Apache Log4j library to provide remediation for Denial of 
  Service (DoS) and Remote Code Execution (RCE) vulnerabilities documented 
  in CVE-2021-44228, CVE-2021-44832, CVE-2021-45046, and CVE-2021-45105.

  This security fix supersedes all previously communicated mitigation 
  procedures for Log4j vulnerabilities involving the addition of a JVM 
  system property and is agnostic of the presence of those changes.  This 
  security fix also supersedes the Log4j security fix released on December 
  17 referenced as IIQCB-4601.

  The fix for this vulnerability has general applicability and should be 
  applied to all instances of IdentityIQ and the IdentityIQ Cloud Gateway.

  The fix for this vulnerability includes product code changes packaged in 
  e-fix format and requires deploying the changes to, and restart of, all 
  application server instances in the IdentityIQ installation.   
 
  Updating your environment should include a combination of patches and/or 
  security fixes that includes fixes for all known vulnerabilities. The 
  IdentityIQ Security Vulnerabilities page on Compass can be used to 
  determine which security fixes are required for each supported IdentityIQ 
  version.
 
  As with all software vulnerabilities, we recommend that you apply this
  security fix or a patch containing resolution to this issue as soon as
  reasonably possible.

  CVSS: 7.5
 

Installation Instructions:
 
  1. Download the security fix file for the version of IdentityIQ in
     use. The security fix is compatible with all patch levels of the
     indicated version unless otherwise specified.
 
  2. Extract the security fix into the root of each IdentityIQ instance in the
     IdentityIQ installation.
 
     Alternatively, use site processes and procedures for introducing
     security fixes into the deployable build process and for deploying
     IdentityIQ to application server instances.

     If the IdentityIQ Cloud Gateway is used, extract the security fix into
     the root of the CloudGateway application in the webapps/CloudGateway
     directory of the Tomcat instance hosting the Cloud Gateway.

     NOTE: This patch replaces the older version of the Log4j library with
     empty jar files using the same name. This is the equivalent of removing
     the library through the overlay mechanism used to install e-fixes.
     These empty jar files can be manually removed to prevent security
     tools from indicating existence of vulnerable versions of the library.
 
  3. Restart all application server instances in the IdentityIQ installation.

 
Installation Verification:
 
  Steps to verify:

    1. Login to IdentityIQ as a user with the System Administrator capability

    2. Navigate to the Debug page (/debug/debug.jsf)

    3. Navigate to the wrench icon -> About

    4. Verify that the EFIX appears under the Product Information

  For information on verifying the specific Log4j version please see: 
    https://community.sailpoint.com/t5/IdentityIQ-Wiki/IdentityIQ-log4j-Version-Verification/ta-p/207194

  For more detailed instructions on how to verify the installation of this
  security fix, contact SailPoint Customer Support.


Security Fix Contents:
 
  This e-fix package includes a list of the security fix contents in a manifest
  file named:

     WEB-INF/efixes/identityiq-<versions>-IIQCB-4610.txt
     
