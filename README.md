Ansible role to install and manage uWSGI
===========================

* Upstart service script
* Install and manage [uwsgi](https://uwsgi-docs.readthedocs.io/en/latest/)
* Support single uWSGI process and also emperor mode with vassals


Installation methods
--------------------
* Binary packages from the github repository (role name: ansible.uwsgi)
* Ansible Galaxy: ansible-galaxy install lciolecki.uwsgi (role name: lciolecki.uwsgi) 
 
Recommended way installation is ansible galaxy.

Usage
-----

```yaml
---
- hosts: all

  roles:
    - lciolecki.uwsgi

  vars:
  ....
```


Variables
---------

```yaml
---

uwsgi_version: '2.0.13.1'

uwsgi_configs:
  master: true
  processes: 12
  vacuum: true
  lazy-apps: true
  die-on-term: true
  enable-threads: true
  max-worker-lifetime: 600
  chmod-socket: 666
  chdir: "/project_path"
  virtualenv: "/project_path/virtualenv"
  hook-post-fork: "chdir:/project_path"
  wsgi-file: "/project_path/wsgi.py"
  socket: "/project_path/socket-file.sock"
  pidfile: "/project_path/pid-file.pid"
  touch-chain-reload: "/project_path/uwsgi-reload-file"
  logto: "/project_path/uwsgi.log"
  logdate: true

```


License
-------
The MIT License (MIT)

Permission is hereby granted, free of charge, to any person obtaining a copy
of this software and associated documentation files (the "Software"), to deal
in the Software without restriction, including without limitation the rights
to use, copy, modify, merge, publish, distribute, sublicense, and/or sell
copies of the Software, and to permit persons to whom the Software is
furnished to do so, subject to the following conditions:

The above copyright notice and this permission notice shall be included in
all copies or substantial portions of the Software.

THE SOFTWARE IS PROVIDED "AS IS", WITHOUT WARRANTY OF ANY KIND, EXPRESS OR
IMPLIED, INCLUDING BUT NOT LIMITED TO THE WARRANTIES OF MERCHANTABILITY,
FITNESS FOR A PARTICULAR PURPOSE AND NONINFRINGEMENT. IN NO EVENT SHALL THE
AUTHORS OR COPYRIGHT HOLDERS BE LIABLE FOR ANY CLAIM, DAMAGES OR OTHER
LIABILITY, WHETHER IN AN ACTION OF CONTRACT, TORT OR OTHERWISE, ARISING FROM,
OUT OF OR IN CONNECTION WITH THE SOFTWARE OR THE USE OR OTHER DEALINGS IN
THE SOFTWARE.
