Changelog
=========

in development
--------------

v0.6.1 - Under development
--------------------------

Docs: http://docks.stackstorm.com/latest

* Python runner and all the fabric based runners (``run-local``, ``run-local-script``,
  ``run-remote``, ``run-remote-script``) now expose ``timeout`` argument. With this argument
  user can specify action timeout. Previously, the action timeout was not user-configurable and
  a system-wide default value was used.
* The time when an action execution has finished is now recorded and availabla via the
  ``end_timestamp`` attribute on the ``ActionExecution`` model.
* Status code 400 (bad request) is now returned if user doesn't provide a body to API endpoints
  which require it. Previously 500 internal server error was returned (bug-fix).
* Refactor local runners so they are more robust, efficient and easier to debug. Previously, local
  actions were executed through SSH, now they are executed directly without the overhead of SSH.
* Fix local runner so it correctly executes a command under the provider system user if ``user``
  parameter is provided. (bug-fix)
* Fix a bug with a Trigger database object in some cases being created twice when registering a
  rule. (bug-fix)
* Fix a bug with child processes which run sensor code not being killed when stopping a sensor
  container service. (bug-fix)
* Fix a bug and allow user to use non-ascii (unicode) values in the parameter substitution values.
  (bug-fix)
* Allow polling sensors to retrieve current poll interval and change it using ``get_poll_interval``
  and ``set_poll_interval`` methods respectively. (new-feature)
* Add support for a ``standalone`` mode to the st2auth service. In the standalone mode,
  authentication is handled inside the st2auth service using the defined backend. (new feature)

v0.6.0 - December 8, 2014
-------------------------

Docs: http://docs.stackstorm.com/0.6.0/

* Separate virtualenv per pack. (Pythonic sensors and actions use them by default.)
* Install pip requirements from requiremets.txt in packs by default.
* Sensors are now run in their own process for isolation.
* Python Actions are now run in their own process for isolation.
* Add Sensor and PollingSensor base classes. (Sensors API change is non-backward compatible.)
* Separate out rules_engine into own process.
* YAML support for action, rules and chain meta.
* Add sensor meta support (JSON/YAML) to specify trigger types.
* Packs default path moves from /opt/stackstorm to /opt/stackstorm/packs/.
* Webhooks are not part of a sensor. They are now part of core API. (Authentication may
  be required.)
* API URLs are now versioned. All the existing paths have been prefixed with ``/v1``
  (e.g. ``/v1/actions``).
* Audit log messages are now saved in a structured format as JSON in
  ``st2actionrunner.{pid}.audit.log`` log file.
* Numerous bug fixes.


v0.5.1 - November 3rd, 2014
---------------------------

Docs: http://docs.stackstorm.com/0.5.1/

* Initial public release
