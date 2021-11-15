---
title: tabs.onHighlightChanged
slug: Mozilla/Add-ons/WebExtensions/API/tabs/onHighlightChanged
tags:
  - API
  - Add-ons
  - Deprecated
  - Event
  - Extensions
  - Non-standard
  - Reference
  - WebExtensions
  - onHighlightChanged
  - tabs
translation_of: Mozilla/Add-ons/WebExtensions/API/tabs/onHighlightChanged
---
<div>{{AddonSidebar()}}</div>

<div class="warning">
  <p><strong>Attention :</strong> Cet événement est obsolète. Utilisez {{WebExtAPIRef("tabs.onHighlighted")}} à la place.</p></div>

<p>Lancé lorsque les onglets en surbrillance ou sélectionnés dans une fenêtre changent.</p>

<h2 id="Syntaxe">Syntaxe</h2>

<pre class="brush: js">browser.tabs.onHighlightChanged.addListener(listener)
browser.tabs.onHighlightChanged.removeListener(listener)
browser.tabs.onHighlightChanged.hasListener(listener)
</pre>

<p>Les événements ont trois fonctions :</p>

<dl>
 <dt><code>addListener(callback)</code></dt>
 <dd>Ajoute un écouteur à cet événement</dd>
 <dt><code>removeListener(listener)</code></dt>
 <dd>Arrêtez d'écouter cet événement. L'argument <code>listener</code> est l'écouteur à supprimer.</dd>
 <dt><code>hasListener(listener)</code></dt>
 <dd>Vérifiez si <code>listener</code> est enregistré pour cet événement. Renvoie <code>true</code>s'il écoute, sinon <code>false</code>.</dd>
</dl>

<h2 id="Syntaxe_addListener">Syntaxe addListener</h2>

<h3 id="Paramètres">Paramètres</h3>

<dl>
 <dt><code>callback</code></dt>
 <dd>
 <p>Fonction qui sera appelée lorsque cet événement se produit. La fonction recevra les arguments suivants :</p>

 <dl>
  <dt><code>selectInfo</code></dt>
  <dd><a href="#selectInfo"><code>object</code></a>.</dd>
 </dl>
 </dd>
</dl>

<h2 id="Objets_supplémentaires">Objets supplémentaires</h2>

<h3 id="selectInfo">selectInfo</h3>

<dl>
 <dt><code>windowId</code></dt>
 <dd><code>integer</code>. La fenêtre dont les onglets ont changé.</dd>
 <dt><code>tabIds</code></dt>
 <dd><code>array</code> d'<code><code>integer</code></code>. Tous les onglets en surbrillance dans la fenêtre.</dd>
</dl>

<h2 id="Compatibilité_du_navigateur">Compatibilité du navigateur</h2>

<p>{{Compat("webextensions.api.tabs.onHighlightChanged")}}</p>

<p>
 </p><div class="note"><p><strong>Note :</strong></p>

 <p>Cette API est basée sur l'API Chromium <a href="https://developer.chrome.com/extensions/tabs#method-executeScript"><code>chrome.tabs</code></a>. Cette documentation est dérivée de <a href="https://chromium.googlesource.com/chromium/src/+/master/chrome/common/extensions/api/tabs.json"><code>tabs.json</code></a> dans le code de Chromium code.</p>

 <p>Les données de compatibilité relatives à Microsoft Edge sont fournies par Microsoft Corporation et incluses ici sous la licence Creative Commons Attribution 3.0 pour les États-Unis.</p>
 </div>
<p></p>

<div class="hidden">
<pre>// Copyright 2015 The Chromium Authors. All rights reserved.
//
// Redistribution and use in source and binary forms, with or without
// modification, are permitted provided that the following conditions are
// met:
//
//    * Redistributions of source code must retain the above copyright
// notice, this list of conditions and the following disclaimer.
//    * Redistributions in binary form must reproduce the above
// copyright notice, this list of conditions and the following disclaimer
// in the documentation and/or other materials provided with the
// distribution.
//    * Neither the name of Google Inc. nor the names of its
// contributors may be used to endorse or promote products derived from
// this software without specific prior written permission.
//
// THIS SOFTWARE IS PROVIDED BY THE COPYRIGHT HOLDERS AND CONTRIBUTORS
// "AS IS" AND ANY EXPRESS OR IMPLIED WARRANTIES, INCLUDING, BUT NOT
// LIMITED TO, THE IMPLIED WARRANTIES OF MERCHANTABILITY AND FITNESS FOR
// A PARTICULAR PURPOSE ARE DISCLAIMED. IN NO EVENT SHALL THE COPYRIGHT
// OWNER OR CONTRIBUTORS BE LIABLE FOR ANY DIRECT, INDIRECT, INCIDENTAL,
// SPECIAL, EXEMPLARY, OR CONSEQUENTIAL DAMAGES (INCLUDING, BUT NOT
// LIMITED TO, PROCUREMENT OF SUBSTITUTE GOODS OR SERVICES; LOSS OF USE,
// DATA, OR PROFITS; OR BUSINESS INTERRUPTION) HOWEVER CAUSED AND ON ANY
// THEORY OF LIABILITY, WHETHER IN CONTRACT, STRICT LIABILITY, OR TORT
// (INCLUDING NEGLIGENCE OR OTHERWISE) ARISING IN ANY WAY OUT OF THE USE
// OF THIS SOFTWARE, EVEN IF ADVISED OF THE POSSIBILITY OF SUCH DAMAGE.
</pre>
</div>