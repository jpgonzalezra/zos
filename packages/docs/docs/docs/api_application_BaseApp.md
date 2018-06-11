---
id: application_BaseApp
title: BaseApp
---

<div class="contract-doc"><div class="contract"><h2 class="contract-header"><span class="contract-kind">contract</span> BaseApp</h2><p class="base-contracts"><span>is</span> <a href="_Ownable.html">Ownable</a></p><p class="description">Abstract base contract for upgradeable applications. It handles the creation and upgrading of proxies.</p><div class="source">Source: <a href="https://github.com/zeppelinos/zos-lib/blob/v1.0.0/contracts/application/BaseApp.sol" target="_blank">application/BaseApp.sol</a></div></div><div class="index"><h2>Index</h2><ul><li><a href="application_BaseApp.html#BaseApp">BaseApp</a></li><li><a href="application_BaseApp.html#create">create</a></li><li><a href="application_BaseApp.html#createAndCall">createAndCall</a></li><li><a href="application_BaseApp.html#getImplementation">getImplementation</a></li><li><a href="application_BaseApp.html#getProvider">getProvider</a></li><li><a href="application_BaseApp.html#getProxyAdmin">getProxyAdmin</a></li><li><a href="application_BaseApp.html#getProxyImplementation">getProxyImplementation</a></li><li><a href="application_BaseApp.html#upgrade">upgrade</a></li><li><a href="application_BaseApp.html#upgradeAndCall">upgradeAndCall</a></li></ul></div><div class="reference"><h2>Reference</h2><div class="functions"><h3>Functions</h3><ul><li><div class="item function"><span id="BaseApp" class="anchor-marker"></span><h4 class="name">BaseApp</h4><div class="body"><code class="signature">function <strong>BaseApp</strong><span>(UpgradeabilityProxyFactory _factory) </span><span>public </span></code><hr/><div class="description"><p>Constructor function.</p></div><dl><dt><span class="label-parameters">Parameters:</span></dt><dd><div><code>_factory</code> - Proxy factory</div></dd></dl></div></div></li><li><div class="item function"><span id="create" class="anchor-marker"></span><h4 class="name">create</h4><div class="body"><code class="signature">function <strong>create</strong><span>(string contractName) </span><span>public </span><span>returns  (AdminUpgradeabilityProxy) </span></code><hr/><div class="description"><p>Creates a new proxy for the given contract.</p></div><dl><dt><span class="label-parameters">Parameters:</span></dt><dd><div><code>contractName</code> - Name of the contract.</div></dd><dt><span class="label-return">Returns:</span></dt><dd>Address of the new proxy.</dd></dl></div></div></li><li><div class="item function"><span id="createAndCall" class="anchor-marker"></span><h4 class="name">createAndCall</h4><div class="body"><code class="signature">function <strong>createAndCall</strong><span>(string contractName, bytes data) </span><span>public </span><span>payable </span><span>returns  (AdminUpgradeabilityProxy) </span></code><hr/><div class="description"><p>Creates a new proxy for the given contract and forwards a function call to it. This is useful to initialize the proxied contract.</p></div><dl><dt><span class="label-parameters">Parameters:</span></dt><dd><div><code>contractName</code> - Name of the contract.</div><div><code>data</code> - Data to send as msg.data in the low level call. It should include the signature and the parameters of the function to be called, as described in https://solidity.readthedocs.io/en/develop/abi-spec.html#function-selector-and-argument-encoding.</div></dd><dt><span class="label-return">Returns:</span></dt><dd>Address of the new proxy.</dd></dl></div></div></li><li><div class="item function"><span id="getImplementation" class="anchor-marker"></span><h4 class="name">getImplementation</h4><div class="body"><code class="signature">function <strong>getImplementation</strong><span>(string contractName) </span><span>public </span><span>view </span><span>returns  (address) </span></code><hr/><div class="description"><p>Returns the implementation address for a given contract name, provided by the `ImplementationProvider`.</p></div><dl><dt><span class="label-parameters">Parameters:</span></dt><dd><div><code>contractName</code> - Name of the contract.</div></dd><dt><span class="label-return">Returns:</span></dt><dd>Address where the contract is implemented.</dd></dl></div></div></li><li><div class="item function"><span id="getProvider" class="anchor-marker"></span><h4 class="name">getProvider</h4><div class="body"><code class="signature"><span>abstract </span>function <strong>getProvider</strong><span>() </span><span>internal </span><span>view </span><span>returns  (ImplementationProvider) </span></code><hr/><div class="description"><p>Abstract function to return the implementation provider.</p></div><dl><dt><span class="label-return">Returns:</span></dt><dd>The implementation provider.</dd></dl></div></div></li><li><div class="item function"><span id="getProxyAdmin" class="anchor-marker"></span><h4 class="name">getProxyAdmin</h4><div class="body"><code class="signature">function <strong>getProxyAdmin</strong><span>(AdminUpgradeabilityProxy proxy) </span><span>public </span><span>view </span><span>returns  (address) </span></code><hr/><div class="description"><p>Returns the admin of a proxy. Only the admin can query it.</p></div><dl><dt><span class="label-parameters">Parameters:</span></dt><dd><div><code>proxy</code> - AdminUpgradeabilityProxy</div></dd><dt><span class="label-return">Returns:</span></dt><dd>The address of the current admin of the proxy.</dd></dl></div></div></li><li><div class="item function"><span id="getProxyImplementation" class="anchor-marker"></span><h4 class="name">getProxyImplementation</h4><div class="body"><code class="signature">function <strong>getProxyImplementation</strong><span>(AdminUpgradeabilityProxy proxy) </span><span>public </span><span>view </span><span>returns  (address) </span></code><hr/><div class="description"><p>Returns the current implementation of a proxy. This is needed because only the proxy admin can query it.</p></div><dl><dt><span class="label-parameters">Parameters:</span></dt><dd><div><code>proxy</code> - AdminUpgradeabilityProxy</div></dd><dt><span class="label-return">Returns:</span></dt><dd>The address of the current implementation of the proxy.</dd></dl></div></div></li><li><div class="item function"><span id="upgrade" class="anchor-marker"></span><h4 class="name">upgrade</h4><div class="body"><code class="signature">function <strong>upgrade</strong><span>(AdminUpgradeabilityProxy proxy, string contractName) </span><span>public </span></code><hr/><div class="description"><p>Upgrades a proxy to the newest implementation of a contract.</p></div><dl><dt><span class="label-modifiers">Modifiers:</span></dt><dd><a href="_Ownable.html#onlyOwner">onlyOwner </a></dd><dt><span class="label-parameters">Parameters:</span></dt><dd><div><code>proxy</code> - Proxy to be upgraded.</div><div><code>contractName</code> - Name of the contract.</div></dd></dl></div></div></li><li><div class="item function"><span id="upgradeAndCall" class="anchor-marker"></span><h4 class="name">upgradeAndCall</h4><div class="body"><code class="signature">function <strong>upgradeAndCall</strong><span>(AdminUpgradeabilityProxy proxy, string contractName, bytes data) </span><span>public </span><span>payable </span></code><hr/><div class="description"><p>Upgrades a proxy to the newest implementation of a contract and forwards a function call to it. This is useful to initialize the proxied contract.</p></div><dl><dt><span class="label-modifiers">Modifiers:</span></dt><dd><a href="_Ownable.html#onlyOwner">onlyOwner </a></dd><dt><span class="label-parameters">Parameters:</span></dt><dd><div><code>proxy</code> - Proxy to be upgraded.</div><div><code>contractName</code> - Name of the contract.</div><div><code>data</code> - Data to send as msg.data in the low level call. It should include the signature and the parameters of the function to be called, as described in https://solidity.readthedocs.io/en/develop/abi-spec.html#function-selector-and-argument-encoding.</div></dd></dl></div></div></li></ul></div></div></div>