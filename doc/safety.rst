++++++++++++
Fusil safety
++++++++++++

Safe environment
================

To avoid computer crash, Fusil limits its own process but also child processes resources.

Limitation to Fusil process are set in Application.init():

 * Process priority: 19
 * Limit CPU usage: project.step_sleep (in second, default: 10 millisecond)
 * Limit memory: appplication.max_memory (in bytes, default: 100 MB)
 * Limit time: project.session_timeout (in second, default: disabled).
   See also 'time.txt' documentation.

Limitation of child process:

 * Process priority: 19
 * Limit memory: default limit of 100 MB
 * Limit time: default timeout of 10 seconds

Limitation of attached process:

 * Check used memory: default limit of 100 MB

Be nice with CPU
================

Project waits until system CPU load is below 30% before creating a new
session. It stops Fusil if system is not calm enough after 60 seconds.

