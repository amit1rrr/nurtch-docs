.. include:: ../../globals.rst

Elastic Container Service (ECS)
=======================================

.. function:: rollback_deployment(service, **kwargs)

   Quickly rollback an ECS service to any prior version. This method first communicates with ECS to retrieve rollback candidates (prior task definitions that you can rollback to). Performs a rollback deployment to a version that you select. Shows deployment progress.

   :param service: The name of your ECS service.
   :type service: ``str``
   :param \**kwargs: These are optional. See below.

   :Keyword Arguments (Optional):
      * *cluster* (``str``)
         Name of the ECS cluster to which the service belongs. If the cluster name is not given, ECS uses *default cluster*. We highly recommend putting your services inside clusters and not using *default cluster* unless you are just experimenting.

      * *aws_access_key_id* (``str``)
         AWS access key of an IAM user to call ECS APIs. Defaults to environment variable ``AWS_ACCESS_KEY_ID``. Can be overwritten per method by supplying this keyword argument.

      * *aws_secret_access_key* (``str``)
         AWS secret access key of an IAM user to call ECS APIs. Defaults to environment variable ``AWS_SECRET_ACCESS_KEY``. Can be overwritten per method by supplying this keyword argument.

      * *aws_region* (``str``)
         AWS region where the service resides. Defaults to environment variable ``AWS_REGION``. Can be overwritten per method by supplying this keyword argument.

   :Examples:

   .. code-block:: python

      from rubix.aws.ecs import rollback_deployment

      rollback_deployment(service='xyz-api', cluster='prod-cluster')

   :Sample Usage and Output:
      .. image:: ../../images/ecs_rollback.png
         :scale: 30%
         :align: center


.. _get_latest_deployment_status_ecs:

.. function:: get_latest_deployment_status(service, **kwargs)

   Retrieve metadata of last deployment on your ECS service. Metadata includes deployment time, desired/pending/running counts, task definition etc.

   :param service: The name of your ECS service.
   :type service: ``str``
   :param \**kwargs: These are optional. See below.
   :returns: dict -- See response section below.

   :Keyword Arguments (Optional):
      * *cluster* (``str``)
         Name of the ECS cluster to which the service belongs. If the cluster name is not given, ECS uses *default cluster*.

      * *aws_access_key_id* (``str``)
         AWS access key of an IAM user to call ECS APIs. Defaults to environment variable ``AWS_ACCESS_KEY_ID``. Can be overwritten per method by supplying this keyword argument.

      * *aws_secret_access_key* (``str``)
         AWS secret access key of an IAM user to call ECS APIs. Defaults to environment variable ``AWS_SECRET_ACCESS_KEY``. Can be overwritten per method by supplying this keyword argument.

      * *aws_region* (``str``)
         AWS region where the service resides. Defaults to environment variable ``AWS_REGION``. Can be overwritten per method by supplying this keyword argument.

   :Response:
      * *id* (``str``)
         The ID of the deployment.
      * *taskDefinition* (``str``)
         The most recent task definition that was specified for the service to use.
      * *desiredCount* (``int``)
         The most recent desired count of tasks that was specified for the service to deploy or maintain.
      * *pendingCount* (``int``)
         The number of tasks in the deployment that are in the PENDING status.
      * *runningCount* (``int``)
         The number of tasks in the deployment that are in the RUNNING status.
      * *createdAt* (``datetime.datetime``)
         The Unix time stamp for when the deployment was created.
      * *updatedAt* (``datetime.datetime``)
         The Unix time stamp for when the service was last updated.
   :Examples:

   .. code-block:: python

      from rubix.aws.ecs import get_latest_deployment_status

      get_latest_deployment_status(service='hello-world-service', cluster='prod-cluster')

   :Sample Usage and Output:
      .. image:: ../../images/latest_deployment_status.png
         :scale: 35%
         :align: center