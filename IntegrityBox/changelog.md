> Release Date: 20/08/2025
> Version: v16
> Source: Github
> Author: 𝗠𝗘𝗢𝗪𝗻𝗮 💅 

- Fixed unexpected delay in action button(script) expectation.

- Now default target packages will be updated based on TEE status too, instead of forcing leaf certificate hack mode for devices with non broken TEE

- Disable intro in WebUI by default & added option to re-enable it in WebUI menu.

- Improved Keybox updater.

- Optimised installation script.

- Added more configuration flags

- Fixed Lsposed logs spoofing failure 

- Replaced simple "echo" outputs with structured logging mechanism for better traceability.
  
- Added a consistent logging format including timestamp for each log entry to improve readability and debugging.
  
- Implemented log file capturing using "tee -a" to ensure both console visibility and file persistence of logs.
  
- Ensured that all network retry attempts are logged with clear retry counters for transparency.
  
- Improved reliability of network connectivity checks by introducing a maximum retry limit with controlled loop execution.
  
- Enhanced error handling by introducing explicit exit codes upon failure conditions for better integration with other scripts.
  
- Suppressed unnecessary command outputs to keep logs clean and focused only on meaningful information.
  
- Introduced graceful exit after maximum retry attempts to avoid indefinite loops in case of no internet connectivity.
  
- Standardized indentation, spacing, and code structure for improved readability and maintainability.
  
- Consolidated redundant command sequences to simplify the flow and reduce script overhead.
  
- Improved user feedback by ensuring retry attempts and failure messages are displayed consistently.
  
- Added robust handling of slow or unstable network scenarios to minimize false negatives.
  
- Ensured compatibility with BusyBox environment by using portable shell syntax.
  
- Improved overall script maintainability by reducing noise and making error handling self-explanatory.
  
- Strengthened integration readiness by introducing reliable log capturing that can be parsed or shared easily.
  
- Ensured that no sensitive data or unnecessary verbose output is written into the log files.
  
- Refined exit behavior to prevent accidental continuation of dependent operations in case of failure.
  
- Improved script resilience under low-resource or high-latency conditions.
  
- General code cleanup to maintain long-term stability.

- Custom fonts will be added in next update (got no time to find fonts).

- Logs will be zipped automatically, if you face any issue, just send me the log zip file
