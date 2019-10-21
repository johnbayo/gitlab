# gitlab
gitlab deployment in kubernetes<br/>
<br/>
Requirements<br/>
Kubernetes cluster<br/>
Kubectl installed and configured on control machine<br/>
<br/>
### usage
<br/>
<pre>
kubectl apply -f ./
</pre>
<br/>
# enabling active directory
<br/>
<pre>
gitlab_rails['ldap_enabled'] = true
gitlab_rails['ldap_servers'] = {
'main' => {
  'label' => 'ACTIVE DIRECTORY TEST',
  'host' =>  'test.activedirectory.com',
  'port' => 636,
  'uid' => 'sAMAccountName',
  'encryption' => 'simple_tls',
  'verify_certificates' => false,
  'bind_dn' => 'CN=ad-test,OU=Project,DC=example,DC=ng',
  'password' => 'AWsd12nT',
  'active_directory' => true,
  'base' => 'OU=User,DC=example,DC=ng',
  'group_base' => 'OU=User,DC=example,DC=ng',
  'user_filter' => 'memberOf=CN=grp-example,OU=Organisation,OU=User,DC=example,DC=ng',
  'lowercase_usernames' => 'true'
   }
  }
</pre>

