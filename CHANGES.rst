0.8 (2019-03-10)
----------------

- Make RQ proc counting more efficient and correct (#49)
- CeleryProc close open channels (#51)

0.7 (2018-12-10)
----------------

- Make ProcSerializer inherit from object (#47)

0.6 (2018-10-10)
----------------

- Use concurrent futures to reduce blocking IO (#37)
- Add a test suite (#41)
- Fix RabbitMQ connection `TimeoutError` (#42).
  Acquire and dispose broker connection per request

0.5 (2017-01-20)
----------------

- Add ``simple_queues`` feature to Celery Proc, to enable optionally
  skipping one inspect call. (#23)
- Make the default quantity 0 by the recommendation of the HireFire team.

0.4 (2016-06-04)
----------------

- Consider all Celery tasks including the ones in the active, reserved and
  scheduled queues. This fixes a long standing issue where tasks in those
  queues could have been dropped if HireFire were to scale down the workers.
  Many thanks to Ryan Hiebert for working on this.

- Removed django-pq backend since the library is unmaintained.

0.3 (2015-05-05)
----------------

- Added Flask blueprint.
- Fixed Celery queue length measurement for AMQP backends.

0.2.2 (2014-11-27)
------------------

- Fixed a regression in 0.2.1 fix. Thanks to Ryan West.

0.2.1 (2014-05-27)
------------------

- Fix the RQ_ Proc implementation to take the number of task into account
  that are currently being processed by the workers to prevent accidental
  shutdown mid-processing. Thanks to Jason Lantz for the report and
  initial patch.

0.2 (2014-04-20)
----------------

- Got rid of d2to1 dependency.
- Added django-pq backend.
- Ported to Python 3.
- Added Tornado contrib handlers.

0.1 (2013-02-17)
----------------

- Initial release with backends:

  * Celery_
  * HotQueue_
  * Huey_
  * Queues_
  * RQ_

.. _Heroku: http://www.heroku.com/
.. _Celery: http://celeryproject.com/
.. _HotQueue: http://richardhenry.github.com/hotqueue/
.. _Huey: https://huey.readthedocs.io/
.. _Queues: http://queues.googlecode.com/
.. _RQ: http://python-rq.org/
