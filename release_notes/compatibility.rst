.. _compatibility:

*******************************************
|morphver| Compatibility & Breaking Changes
*******************************************

When installing and upgrading to |morpheus| |morphver|, refer to the following to ensure compatibility.

Breaking Changes
================

- 4.2.1: Appliance: OS: Ubuntu 14.04 has reached its end of life (EOL) and is no longer supported as a Morpheus Appliance Host Operating System. Any |morpheus| Appliance running on 14.04 must be upgraded to 16.04, 18.04 or 20.04 BEFORE upgrading to 4.2.1+. Upgrades on 14.04 will not succeed
- 4.2.1: Clouds: VirtualBox, VirtuSteam, and MetaCloud Cloud Types are no longer supported or available
- 4.2.1: Puppet: |morpheus| integration now supports version 6+. Puppet versions prior to 6 are no longer supported
- 4.2.1: Tasks: Python: Virtual environment are now used for Python Tasks. **Note:** ``virtualenv`` is required on all Appliance App nodes: ``pip install virtualenv``

|morpheus| Application OS
=========================

.. important:: Existing Appliances on 14.04 must upgrade to 16.04 or 18.04 PRIOR to upgrading to v4.2.1+.

.. list-table:: **Supported Appliance Operating Systems**
   :widths: auto
   :header-rows: 1

   * - OS
     - Version(s)
     - Notes
   * - Amazon Linux
     - 2
     -
   * - CentOS
     - 7.x, 8.x
     -
   * - Debian
     - 9, 10
     - FreeRDP 2.0 is not compatible with Debian 9. Guacd will remain at 1.0.0 for Appliances running on 9.
   * - RHEL
     - 7.x, 8.x
     -
   * - SUSE SLES
     - 12, 15
     -
   * - Ubuntu
     - 16.04, 18.04
     - 14.04 is no longer supported for Appliance OS. Existing Appliances on 14.04 must upgrade to 16.04 or 18.04 PRIOR to upgrading to v4.2.1+. Note: 14.04 is still supported by the |morpheus| Agent.

Services
========

|morphver| Service Version Changes
----------------------------------

No service version changes between v4.2.1 and v4.2.2

|morphver| Service Version Compatibility
----------------------------------------

When externalizing MySQL, Elasticsearch and/or RabbitMQ services, the following versions are compatible with version |morpheus| |morphver|

+---------------------------------------+-----------------------+-------------------------------------+
| **Service**                           | **Compatible Branch** | **Morpheus Installer Version**      |
+---------------------------------------+-----------------------+-------------------------------------+
| MySQL                                 | 5.7                   | 5.7.29                              |
+---------------------------------------+-----------------------+-------------------------------------+
| Percona                               | 5.7, WSREP 31         | n/a                                 |
+---------------------------------------+-----------------------+-------------------------------------+
| Elasticsearch                         | 7.x                   | 7.6.2                               |
+---------------------------------------+-----------------------+-------------------------------------+
| RabbitMQ                              | 3.5-3.8               | 3.8.3                               |
+---------------------------------------+-----------------------+-------------------------------------+

.. important:: Elasticsearch 7.x is required for |morphver|. Refer to :ref:`upgrading` section for more information.

Security
========

.. important:: Please be aware of the default security enhancements added to v4.1.2+ and assess potential impacts to your environment, including agent installation and frontend load balancers.

- 4.1.2: Appliance: Starting in v4.1.2, the default |morpheus| Nginx config removes support for incoming ``TLS v1.0 and v1.1`` connections. Please update source config to be compatible. If necessary, |morpheus| can be configured to support older TLS versions via :ref:`morpheus.rb` config.
- 4.2.1: Security: Web Security response headers set for enhanced security

..
  CVEs Addressed
  --------------

  - CVE-2017-18640
  - CVE-2019-12418

Integrations
============

.. note:: Current iterations of Amazon AWS, Microsoft Azure, Google Cloud Platform, Digital Ocean, HPE OneView, OpenTelekom Cloud, IBM Bluemix, Softlayer and UpCloud are all supported.

.. important:: VirtualBox, VirtuSteam, and MetaCloud Cloud Types are no longer supported.

.. include:: compatibility_table.rst

.. note:: Non-listed versions may be compatible but are not verified.
