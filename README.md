Ansible Role for Fisheye
========================

[![Build Status](https://travis-ci.org/pantarei/ansible-role-fisheye.svg?branch=master)](https://travis-ci.org/pantarei/ansible-role-fisheye)
[![GitHub tag](https://img.shields.io/github/tag/pantarei/ansible-role-fisheye.svg)](https://github.com/pantarei/ansible-role-fisheye)
[![GitHub license](https://img.shields.io/github/license/pantarei/ansible-role-fisheye.svg)](https://github.com/pantarei/ansible-role-fisheye/blob/master/LICENSE)
[![Ansible Role](https://img.shields.io/ansible/role/5988.svg)](https://galaxy.ansible.com/detail#/role/5988)

Ansible Role for Atlassian Fisheye Installation.

Requirements
------------

This role require Ansible 1.9 or higher.

This role was designed for Ubuntu Server 14.04 LTS.

Role Variables
--------------

<table>
<colgroup>
<col width="20%" />
<col width="20%" />
<col width="20%" />
<col width="20%" />
<col width="20%" />
</colgroup>
<thead>
<tr class="header">
<th align="left">parameter</th>
<th align="left">required</th>
<th align="left">default</th>
<th align="left">choices</th>
<th align="left">comments</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td align="left">fisheye_archive</td>
<td align="left">yes</td>
<td align="left">/tmp/fisheye-3.10.1.zip</td>
<td align="left"></td>
<td align="left">Download archive filename for cache during (re)install.</td>
</tr>
<tr class="even">
<td align="left">fisheye_catalina</td>
<td align="left">yes</td>
<td align="left">/usr/share/fisheye</td>
<td align="left"></td>
<td align="left">Location for the Fisheye installation directory.</td>
</tr>
<tr class="odd">
<td align="left">fisheye_connector_port</td>
<td align="left">yes</td>
<td align="left">8095</td>
<td align="left"></td>
<td align="left">Fisheye Apache Tomcat connector port.</td>
</tr>
<tr class="even">
<td align="left">fisheye_home</td>
<td align="left">yes</td>
<td align="left">/var/lib/fisheye</td>
<td align="left"></td>
<td align="left">Location for the Fisheye home directory.</td>
</tr>
<tr class="odd">
<td align="left">fisheye_jvm_maximum_memory</td>
<td align="left">yes</td>
<td align="left">1024m</td>
<td align="left"></td>
<td align="left">Fisheye JVM maximum memory usage.</td>
</tr>
<tr class="even">
<td align="left">fisheye_jvm_minimum_memory</td>
<td align="left">yes</td>
<td align="left">512m</td>
<td align="left"></td>
<td align="left">Fisheye JVM minimum memory usage.</td>
</tr>
<tr class="odd">
<td align="left">fisheye_jvm_support_recommended_args</td>
<td align="left">no</td>
<td align="left">-Datlassian.plugins.enable.wait=300</td>
<td align="left"></td>
<td align="left">Atlassian Support recommended JVM arguments.</td>
</tr>
<tr class="even">
<td align="left">fisheye_pass</td>
<td align="left">yes</td>
<td align="left">Pi0oode7</td>
<td align="left"></td>
<td align="left">Password for Fisheye system user.</td>
</tr>
<tr class="odd">
<td align="left">fisheye_proxy_name</td>
<td align="left">no</td>
<td align="left"><code>null</code></td>
<td align="left"></td>
<td align="left">Pass value as <code>proxyName</code> to <a href="https://github.com/pantarei/ansible-role-fisheye/blob/master/templates/usr/share/fisheye/conf/server.xml.j2">template</a>.</td>
</tr>
<tr class="even">
<td align="left">fisheye_scheme</td>
<td align="left">no</td>
<td align="left"><code>null</code></td>
<td align="left"><ul>
<li><code>null</code></li>
<li>http</li>
<li>https</li>
</ul></td>
<td align="left">Install Fisheye in standalone mode if <code>null</code>, or integrating with Apache using HTTP if <code>http</code>, or integrating with Apache using HTTPS if <code>https</code>.</td>
</tr>
<tr class="odd">
<td align="left">fisheye_server_port</td>
<td align="left">yes</td>
<td align="left">8020</td>
<td align="left"></td>
<td align="left">Fisheye Apache Tomcat server port.</td>
</tr>
<tr class="even">
<td align="left">fisheye_sha256</td>
<td align="left">yes</td>
<td align="left">884728bbfd31d99a1e23001fb19cf529d0b46add2fa23ea8c6ae69f934e2a8a2</td>
<td align="left"></td>
<td align="left">Download archive sha256 checksum for cache during (re)install.</td>
</tr>
<tr class="odd">
<td align="left">fisheye_upgrade</td>
<td align="left">no</td>
<td align="left"><code>false</code></td>
<td align="left"><ul>
<li><code>true</code></li>
<li><code>false</code></li>
</ul></td>
<td align="left">If <code>true</code>, trigger upgrade by stop existing Fisheye service, purge existing Fisheye installation direcoty before normal tasks.</td>
</tr>
<tr class="even">
<td align="left">fisheye_url</td>
<td align="left">yes</td>
<td align="left">https://downloads.atlassian.com/software/fisheye/downloads/fisheye-3.10.1.zip</td>
<td align="left"></td>
<td align="left">URL for download archive.</td>
</tr>
<tr class="odd">
<td align="left">fisheye_user</td>
<td align="left">yes</td>
<td align="left">fisheye</td>
<td align="left"></td>
<td align="left">Username for Fisheye system user.</td>
</tr>
</tbody>
</table>

Dependencies
------------

-   [hswong3i.java](https://galaxy.ansible.com/detail#/role/5971)

Example Playbook
----------------

    - hosts: servers
      roles:
        - { role: hswong3i.java }
        - { role: hswong3i.fisheye, fisheye_user: 'fisheye', fisheye_pass: 'Pi0oode7', fisheye_upgrade: 'false' }

License
-------

-   Code released under [MIT](https://github.com/hswong3i/ansible-role-fisheye/blob/master/LICENSE)
-   Docs released under [CC BY 4.0](http://creativecommons.org/licenses/by/4.0/)

Author Information
------------------

-   Wong Hoi Sing Edison
    -   <https://twitter.com/hswong3i>
    -   <https://github.com/hswong3i>

