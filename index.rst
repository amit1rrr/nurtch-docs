.. NurtchDocs documentation master file, created by
   sphinx-quickstart on Sun May  6 15:14:02 2018.
   You can adapt this file completely to your liking, but it should at least
   contain the root `toctree` directive.

Welcome to Nurtch documentation!
======================================
|Nurtch| is an internal documentation platform based on executable |Jupyter Notebooks|. It's used by teams to write executable runbooks for quick incident response. Notebook supports markdown text, images, executable code, and output all within the single document served in a browser.

Nurtch is self hosted for complete control, security, and access to your infrastructure in VPC. All Notebooks are stored in S3 bucket you configure. |Sign up| to receive installation instructions.

While Nurtch is great for storing runbooks, it's also suitable to share any internal documentation within team. You can write design docs, onboarding guides, and even retrieve metrics, automate walk-up requests and such.

The documentation is split into two sections:

   * **Nurtch Platform**
       It concerns with the actual Jupyter UI that's used to write, edit and execute Notebooks. It provides ability to search documents, publish them to S3, store credentials as environment variables, and add team members to Nurtch.

   * **Rubix Library**
       Rubix is a Python library that simplifies common DevOps actions by leveraging infrastructure APIs. Simply put, we abstract the complexity of communicating with AWS/Kubernetes/<Your favourtute tool> APIs and presenting the result in Notebook.

       Here are some examples to make it more concrete:

       * ``plot_metrics`` method in Rubix fetches metrics data from cloudwatch and renders the graph in Notebook using Plotly
       * ``rollback_deployment`` communicates with ECS/ECR to provide task definitions that you can rollback to, performs rollback deployment to the version you choose, keeps you updated on the status of rollback deployment.



.. |Nurtch| raw:: html

   <a href="http://nurtch.com" target="_blank">Nurtch</a>

.. |Sign up| raw:: html

   <a href="http://nurtch.com" target="_blank">Sign up</a>

.. |Jupyter Notebooks| raw:: html

   <a href="http://jupyter.org/" target="_blank">Jupyter Notebooks</a>




.. toctree::
   :maxdepth: 2
   :caption: Table of Contents:

   nurtch-platform/index
   rubix-library/index






