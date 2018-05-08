.. include:: globals.rst

Welcome to Nurtch documentation!
======================================
|Nurtch| is an internal documentation platform based on |Jupyter Notebooks|. It's used by teams to write executable runbooks for quick incident response. Notebook supports markdown text, images, executable code, and output all within the single document served in a browser.

Nurtch is self hosted for complete control, security, and access to your infrastructure in VPC. All Notebooks are stored in S3 bucket you configure. |Sign up| to receive installation instructions.

While Nurtch is great for storing runbooks, it's also suitable to share any internal documentation within team. You can write onboarding guides, retrieve metrics, automate walk-up requests and such.
This documentation is split into two sections:

   * **Nurtch Platform**
       We talk about the actual Jupyter UI that's used to write, edit and execute Notebooks. We provide ability to search documents, publish them to S3, store credentials, add team members to Nurtch etc. We also talk about some useful features that are built into Jupyter Notebooks.

   * **Rubix Library**
       Rubix :sup:`™` is a Python library that simplifies common DevOps actions by leveraging infrastructure APIs. Simply put, we abstract the complexity of communicating with AWS/Kubernetes/<Your favourtute tool> APIs.

       Here are some examples of Rubix methods:

       * ``plot_metrics`` method fetches metrics data from cloudwatch and renders the graph in Notebook.
       * ``rollback_deployment`` quickly rollbacks an ECS service to any prior version. First it communicates with ECS to retrieve rollback candidates. Performs a rollback deployment to a version that you select & shows deployment progress.

.. toctree::
   :maxdepth: 2
   :caption: Table of Contents:

   nurtch-platform/index
   rubix-library/index
