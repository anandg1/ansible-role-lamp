<h1 class="code-line" data-line-start=0 data-line-end=1 ><a id="Ansible_role_for_building_a_LAMP_stack_in_Amazon_Linux2_0_and_CentOS7"></a>Ansible role for building a LAMP stack in Amazon Linux2 and CentOS7</h1>
<p class="has-line-data" data-line-start="2" data-line-end="3">This is a Ansible role to deploy a LAMP Stack on centos7/amazon-linux2 hosts.</p>
<ul>
<li class="has-line-data" data-line-start="4" data-line-end="6">Roles let you automatically load related vars, files, tasks, handlers, and other Ansible artifacts based on a known file structure. After you group your content in roles, you can easily reuse them and share them with other users.Each directory contains a main.yml file which contains relevant content.</li>
</ul>
<p class="has-line-data" data-line-start="6" data-line-end="7">This is the structure of role I have created for this project,</p>
<pre><code class="has-line-data" data-line-start="8" data-line-end="34" class="language-sh">├── defaults
│   └── main.yml
├── files
├── handlers
│   └── main.yml
├── meta
│   └── main.yml
├── README.md
├── tasks
│   ├── amazon.yml
│   ├── centos.yml
│   └── main.yml
├── templates
│   ├── httpd.conf.temp
│   └── virtualhost.conf.temp
├── tests
│   ├── inventory
│   └── test.yml
└── vars
    └── main.yml
</code></pre>
<h4 class="code-line" data-line-start=35 data-line-end=36 ><a id="STACK_35"></a>STACK</h4>
<ul>
<li class="has-line-data" data-line-start="36" data-line-end="37">Apache Webserver</li>
<li class="has-line-data" data-line-start="37" data-line-end="38">php7.4</li>
<li class="has-line-data" data-line-start="38" data-line-end="39">Mariadb-database-server</li>
</ul>
<h4 class="code-line" data-line-start=39 data-line-end=40 ><a id="Prerequisites_39"></a>Prerequisites</h4>
<p class="has-line-data" data-line-start="40" data-line-end="41">Latest ansible version installed.</p>
<h4 class="code-line" data-line-start=41 data-line-end=42 ><a id="Hosts_41"></a>Hosts</h4>
<ul>
<li class="has-line-data" data-line-start="42" data-line-end="43">Add hosts in an inventory file(say inventory.txt) under your working directory.</li>
</ul>
<h4 class="code-line" data-line-start=43 data-line-end=44 ><a id="Apache__Database_configuration_43"></a>Configuration</h4>
<ul>
<li class="has-line-data" data-line-start="44" data-line-end="45">Configuration of variables for both apache (port number,httpd_user,httpd_group) and mariadb (domain_name,mariadb_root_password,mariadb_database_name,mariadb_database_user_name,mariadb_database_user_password) are included in main.yml file the vars section, which can be modified as per the requirement.</li>
</ul>
<h4 class="code-line" data-line-start=45 data-line-end=46 ><a id="Setup_45"></a>Setup</h4>
<p class="has-line-data" data-line-start="46" data-line-end="47">To check if the playbook have any syntax error, run:</p>
<pre><code class="has-line-data" data-line-start="49" data-line-end="51" class="language-sh">ansible-playbook -i inventory_file your_custom.yml --syntax-check
</code></pre>
<p class="has-line-data" data-line-start="51" data-line-end="52">Inroder to execute, run</p>
<pre><code class="has-line-data" data-line-start="53" data-line-end="55" class="language-sh">ansible-playbook -i inventory_file your_custom.yml
</code></pre>
<p class="has-line-data" data-line-start="56" data-line-end="57">'your_custom.yml' can be any playbook with the role included in it </p>

