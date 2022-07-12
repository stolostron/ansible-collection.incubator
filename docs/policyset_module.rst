.. Document meta

:orphan:

.. Anchors

.. _ansible_collections.stolostron.incubator.policyset_module:

.. Anchors: short name for ansible.builtin

.. Anchors: aliases



.. Title

stolostron.incubator.policyset -- Create/Update/Delete PolicySet, Policies, PlacementRule, and PlacementBinding
+++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++

.. Collection note

.. note::
    This plugin is part of the `stolostron.incubator collection <https://galaxy.ansible.com/stolostron/incubator>`_ (version 0.0.1).

    To install it use: :code:`ansible-galaxy collection install stolostron.incubator`.

    To use it in a playbook, specify: :code:`stolostron.incubator.policyset`.

.. version_added


.. contents::
   :local:
   :depth: 1

.. Deprecated


Synopsis
--------

.. Description

- Generate Open Cluster Management policies from existing Kubernetes manifests in your manifest directory. A policySet, placementRule, and placementBinding will be created. All policies will be group into the policySet.
- Any add/update/delete files in manifest directory, polcies will be added/updated/deleted
- Any update to the cluster_selectors, placementRule will be updated


.. Aliases


.. Requirements


.. Options

Parameters
----------

.. raw:: html

    <table  border=0 cellpadding=0 class="documentation-table">
        <tr>
            <th colspan="1">Parameter</th>
            <th>Choices/<font color="blue">Defaults</font></th>
                        <th width="100%">Comments</th>
        </tr>
                    <tr>
                                                                <td colspan="1">
                    <div class="ansibleOptionAnchor" id="parameter-cluster_selectors"></div>
                    <b>cluster_selectors</b>
                    <a class="ansibleOptionLink" href="#parameter-cluster_selectors" title="Permalink to this option"></a>
                    <div style="font-size: small">
                        <span style="color: purple">list</span>
                         / <span style="color: purple">elements=string</span>                         / <span style="color: red">required</span>                    </div>
                                                        </td>
                                <td>
                                                                                                                                                            </td>
                                                                <td>
                                            <div>Expressions to match your desired managed clusters. A placementRule will be created with this cluster selectors expressions.</div>
                                                        </td>
            </tr>
                                <tr>
                                                                <td colspan="1">
                    <div class="ansibleOptionAnchor" id="parameter-description"></div>
                    <b>description</b>
                    <a class="ansibleOptionLink" href="#parameter-description" title="Permalink to this option"></a>
                    <div style="font-size: small">
                        <span style="color: purple">string</span>
                                                                    </div>
                                                        </td>
                                <td>
                                                                                                                                                            </td>
                                                                <td>
                                            <div>The description of the policySet</div>
                                                        </td>
            </tr>
                                <tr>
                                                                <td colspan="1">
                    <div class="ansibleOptionAnchor" id="parameter-github_repository_branch"></div>
                    <b>github_repository_branch</b>
                    <a class="ansibleOptionLink" href="#parameter-github_repository_branch" title="Permalink to this option"></a>
                    <div style="font-size: small">
                        <span style="color: purple">string</span>
                                                                    </div>
                                                        </td>
                                <td>
                                                                                                                                                            </td>
                                                                <td>
                                            <div>The branch of repository on GitHub.</div>
                                                        </td>
            </tr>
                                <tr>
                                                                <td colspan="1">
                    <div class="ansibleOptionAnchor" id="parameter-github_repository_url"></div>
                    <b>github_repository_url</b>
                    <a class="ansibleOptionLink" href="#parameter-github_repository_url" title="Permalink to this option"></a>
                    <div style="font-size: small">
                        <span style="color: purple">string</span>
                                                                    </div>
                                                        </td>
                                <td>
                                                                                                                                                            </td>
                                                                <td>
                                            <div>The URL of repository on GitHub where manifest yaml files are stored.</div>
                                                        </td>
            </tr>
                                <tr>
                                                                <td colspan="1">
                    <div class="ansibleOptionAnchor" id="parameter-github_token"></div>
                    <b>github_token</b>
                    <a class="ansibleOptionLink" href="#parameter-github_token" title="Permalink to this option"></a>
                    <div style="font-size: small">
                        <span style="color: purple">string</span>
                                                                    </div>
                                                        </td>
                                <td>
                                                                                                                                                            </td>
                                                                <td>
                                            <div>The access token of private repository on GitHub.</div>
                                            <div>This is not required for public repository on GitHub.</div>
                                                        </td>
            </tr>
                                <tr>
                                                                <td colspan="1">
                    <div class="ansibleOptionAnchor" id="parameter-hub_kubeconfig"></div>
                    <b>hub_kubeconfig</b>
                    <a class="ansibleOptionLink" href="#parameter-hub_kubeconfig" title="Permalink to this option"></a>
                    <div style="font-size: small">
                        <span style="color: purple">path</span>
                                                 / <span style="color: red">required</span>                    </div>
                                                        </td>
                                <td>
                                                                                                                                                            </td>
                                                                <td>
                                            <div>Path to the Hub cluster kubeconfig. Can also be specified via K8S_AUTH_KUBECONFIG environment variable.</div>
                                                        </td>
            </tr>
                                <tr>
                                                                <td colspan="1">
                    <div class="ansibleOptionAnchor" id="parameter-manifest_dir"></div>
                    <b>manifest_dir</b>
                    <a class="ansibleOptionLink" href="#parameter-manifest_dir" title="Permalink to this option"></a>
                    <div style="font-size: small">
                        <span style="color: purple">path</span>
                                                 / <span style="color: red">required</span>                    </div>
                                                        </td>
                                <td>
                                                                                                                                                            </td>
                                                                <td>
                                            <div>Path to the manifest directory must contain &#x27;enforce&#x27; and &#x27;inform&#x27; sub-directory, The &#x27;enforce&#x27; and &#x27;inform&#x27; sub-directory both must contain &#x27;musthave&#x27;, &#x27;mustnothave&#x27;, and &#x27;mustonlyhave&#x27; sub-directory. The &#x27;musthave&#x27;, &#x27;mustnothave&#x27;, and &#x27;mustonlyhave&#x27; sub-directory could contain manifest yaml files or other sub-directory that contains manifest yaml files. manifest_dir path will be the policySet name.</div>
                                            <div>The path specified should either be the absolute or relative to the location of the playbook.</div>
                                            <div>In order to avoid potential resource name collision, the name is prefix with policySet name and suffix with the yaml filename.</div>
                                                        </td>
            </tr>
                                <tr>
                                                                <td colspan="1">
                    <div class="ansibleOptionAnchor" id="parameter-max_policy_worker_threads"></div>
                    <b>max_policy_worker_threads</b>
                    <a class="ansibleOptionLink" href="#parameter-max_policy_worker_threads" title="Permalink to this option"></a>
                    <div style="font-size: small">
                        <span style="color: purple">integer</span>
                                                                    </div>
                                                        </td>
                                <td>
                                                                                                                                                                    <b>Default:</b><br/><div style="color: blue">5</div>
                                    </td>
                                                                <td>
                                            <div>The maximum number of policy worker threads to do multi-thread processing</div>
                                                        </td>
            </tr>
                                <tr>
                                                                <td colspan="1">
                    <div class="ansibleOptionAnchor" id="parameter-namespace"></div>
                    <b>namespace</b>
                    <a class="ansibleOptionLink" href="#parameter-namespace" title="Permalink to this option"></a>
                    <div style="font-size: small">
                        <span style="color: purple">string</span>
                                                 / <span style="color: red">required</span>                    </div>
                                                        </td>
                                <td>
                                                                                                                                                            </td>
                                                                <td>
                                            <div>The name of the namespace.  All resources will be created in this namespace.</div>
                                                        </td>
            </tr>
                                <tr>
                                                                <td colspan="1">
                    <div class="ansibleOptionAnchor" id="parameter-state"></div>
                    <b>state</b>
                    <a class="ansibleOptionLink" href="#parameter-state" title="Permalink to this option"></a>
                    <div style="font-size: small">
                        <span style="color: purple">string</span>
                                                                    </div>
                                                        </td>
                                <td>
                                                                                                                            <ul style="margin: 0; padding: 0"><b>Choices:</b>
                                                                                                                                                                <li>absent</li>
                                                                                                                                                                                                <li><div style="color: blue"><b>present</b>&nbsp;&larr;</div></li>
                                                                                    </ul>
                                                                            </td>
                                                                <td>
                                            <div>Determines if policySet, policies, placementRule, and placementBinding should be created, or deleted. When set to <code>present</code>, a policySet, policies, placementRule, and placementBinding will be created. If set to <code>absent</code>, an existing policySet, policies, placementRule, and placementBinding will be deleted.</div>
                                                        </td>
            </tr>
                        </table>
    <br/>

.. Notes


.. Seealso


.. Examples

Examples
--------

.. code-block:: yaml+jinja

    
    - name: "Creating a PolicySet"
      stolostron.incubator.pollicyset:
        hub_kubeconfig: /path/to/hub/kubeconfig
        namespace: default
        manifest_dir: /path/to/manifest_dir
        cluster_selectors:
          - vendor=OpenShift
          - name!=local-cluster




.. Facts


.. Return values

Return Values
-------------
Common return values are documented :ref:`here <common_return_values>`, the following are the fields unique to this module:

.. raw:: html

    <table border=0 cellpadding=0 class="documentation-table">
        <tr>
            <th colspan="1">Key</th>
            <th>Returned</th>
            <th width="100%">Description</th>
        </tr>
                    <tr>
                                <td colspan="1">
                    <div class="ansibleOptionAnchor" id="return-err"></div>
                    <b>err</b>
                    <a class="ansibleOptionLink" href="#return-err" title="Permalink to this return value"></a>
                    <div style="font-size: small">
                      <span style="color: purple">string</span>
                                          </div>
                                    </td>
                <td>when there&#x27;s an error</td>
                <td>
                                            <div>Error message</div>
                                        <br/>
                                    </td>
            </tr>
                                <tr>
                                <td colspan="1">
                    <div class="ansibleOptionAnchor" id="return-result"></div>
                    <b>result</b>
                    <a class="ansibleOptionLink" href="#return-result" title="Permalink to this return value"></a>
                    <div style="font-size: small">
                      <span style="color: purple">string</span>
                                          </div>
                                    </td>
                <td>success</td>
                <td>
                                            <div>message describing the policySet, policies, placementRule, and placementBinding successfully done.</div>
                                        <br/>
                                    </td>
            </tr>
                        </table>
    <br/><br/>

..  Status (Presently only deprecated)


.. Authors

Authors
~~~~~~~

- Hao Liu (@TheRealHaoLiu)
- Hanqiu Zhang (@hanqiuzh)
- Nathan Weatherly (@nathanweatherly)
- Tsu Phin Hee (@tphee)



.. Parsing errors

