---
title: incognito
slug: Mozilla/Add-ons/WebExtensions/manifest.json/incognito
tags:
  - Add-ons
  - WebExtensions
  - incognito
  - manifest.json
translation_of: Mozilla/Add-ons/WebExtensions/manifest.json/incognito
---
<div>{{AddonSidebar}}</div>

<table class="standard-table">
 <tbody>
  <tr>
   <th scope="row" style="width: 30%;">Type</th>
   <td>chaîne</td>
  </tr>
  <tr>
   <th scope="row">Obligatoire</th>
   <td>Non</td>
  </tr>
  <tr>
   <th scope="row">Exemple</th>
   <td>
    <pre class="brush: json">
"incognito": "spanning"</pre>

    <pre class="brush: json">
"incognito": "split"</pre>

    <pre class="brush: json">
"incognito": "not_allowed"</pre>
   </td>
  </tr>
 </tbody>
</table>

<p>Utilisez la clé <code>incognito</code> pour contrôler la façon dont l'extension fonctionne avec les fenêtres de navigation privées.</p>

<p>Il s'agit d'une chaîne qui peut prendre l'une des valeurs suivantes:</p>

<ul>
 <li>
  <p>"spanning" (la valeur par défaut) : affichera des événements à partir de fenêtres et d'onglets privés et non privés. Fenêtres et onglets obtiendront une propriété <code>incognito</code> dans la <code><a href="/fr/docs/Mozilla/Add-ons/WebExtensions/API/windows/Window">fenêtre</a></code> ou l'<code><a href="/fr/docs/Mozilla/Add-ons/WebExtensions/API/tabs/Tab">onglet </a></code>qui les représente. Cette propriété indique si l'objet est ou non privé :</p>

  <pre class="brush: js">browser.windows.getLastFocused().then((windowInfo) =&gt; {
  console.log(`Window is private: ${windowInfo.incognito}`);
});</pre>
 </li>
 <li>"split" : l'extension sera divisée entre des fenêtres privées et non privées. Il existe effectivement deux copies de l'extension en cours d'exécution : l'une ne voit que des fenêtres non privées, l'autre ne voit que des fenêtres privées. Chaque copie a un accès isolé aux APIs Web (par exemple, <code><a href="/fr/docs/Web/API/Storage/LocalStorage">localStorage</a></code> n'est pas partagé). Toutefois, l'API des WebExtension <code><a href="/fr/docs/Mozilla/Add-ons/WebExtensions/API/storage/local">storage.local</a></code> est partagé. (<strong>Note:</strong> ce paramètre n'est pas supporté par Firefox.)</li>
 <li>"not_allowed" : les onglets privés et les fenêtres sont invisibles pour l'extension.</li>
</ul>

<h2 id="Exemple">Exemple</h2>

<pre class="brush: json">"incognito": "spanning"
</pre>

<pre class="brush: json">"incognito": "split"
</pre>

<pre class="brush: json">"incognito": "not_allowed"
</pre>

<h2 id="Compatibilité_du_navigateur">Compatibilité du navigateur</h2>

<p>{{Compat("webextensions.manifest.incognito")}}</p>