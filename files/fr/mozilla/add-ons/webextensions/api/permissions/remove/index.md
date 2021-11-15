---
title: permissions.remove()
slug: Mozilla/Add-ons/WebExtensions/API/permissions/remove
tags:
  - API
  - Add-ons
  - Method
  - Permissions
  - Reference
  - WebExtensions
  - remove
translation_of: Mozilla/Add-ons/WebExtensions/API/permissions/remove
---
<div>{{AddonSidebar()}}</div>

<p>Demander d'abandonner les permissions listées dans l'objet {{WebExtAPIRef("permissions.Permissions")}}.</p>

<p>L'argument <code>Permissions</code> peut contenir soit une propriété  <code>origins</code> ,qui est un tableau de <a href="/fr/Add-ons/WebExtensions/manifest.json/permissions#Host_permissions">permissions d'hôte</a> , ou une propriété <code>permissions</code>, qui est un tableau de <a href="/fr/Add-ons/WebExtensions/manifest.json/permissions#API_permissions">permissions d'API</a>, ou les deux. Les permissions  doivent provenir de l'ensemble des permissions définies dans la clé <code><a href="/fr/docs/Mozilla/Add-ons/WebExtensions/manifest.json/optional_permissions">optional_permissions</a></code> du manifest.json.</p>

<p>Il s'agit d'une fonction asynchrone qui renvoie une <code><a href="/fr/docs/Web/JavaScript/Reference/Global_Objects/Promise">Promesse</a></code>.</p>

<h2 id="Syntaxe">Syntaxe</h2>

<pre class="brush: js">var removing = browser.permissions.remove(
  permissions                // Permissions object
)
</pre>

<h3 id="Paramètres">Paramètres</h3>

<dl>
 <dt><code>permissions</code></dt>
 <dd>Un objet {{WebExtAPIRef("permissions.Permissions")}}.</dd>
</dl>

<h3 id="Valeur_retournée">Valeur retournée</h3>

<p>Une <code><a href="/fr/docs/Web/JavaScript/Reference/Global_Objects/Promise">Promesse</a></code> qui sera remplie avec <code>true</code> si les permissions répertoriées dans l'argument <code>permissions</code> ont été supprimées, ou <code>false</code> dans le cas contraire.</p>

<h2 id="Browser_compatibility">Browser compatibility</h2>

<p>{{Compat("webextensions.api.permissions.remove")}}</p>

<h2 id="Exemples">Exemples</h2>

<p>Ce code ajoute un gestionnaire de clic qui supprime une permission donnée.</p>

<pre class="brush: js">const permissionToRemove = {
  permissions: ["history"]
}

function remove() {
  console.log("removing");
  browser.permissions.remove(permissionToRemove).then(result =&gt; {
    console.log(result);
  });
}

document.querySelector("#remove").addEventListener("click", remove);</pre>

<p>{{WebExtExamples}}</p>

<div class="note"><p><strong>Note :</strong></p>

<p>Cette API est basée sur l'API Chromium <a href="https://developer.chrome.com/extensions/permissions"><code>chrome.permissions</code></a>.</p>

<p>Les données de compatibilité relatives à Microsoft Edge sont fournies par Microsoft Corporation et incluses ici sous la licence Creative Commons Attribution 3.0 pour les États-Unis.</p>
</div>