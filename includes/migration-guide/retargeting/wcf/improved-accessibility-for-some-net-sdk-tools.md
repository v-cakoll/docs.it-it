### <a name="improved-accessibility-for-some-net-sdk-tools"></a>Accessibilità migliorata per alcuni strumenti di .NET SDK

|   |   |
|---|---|
|Dettagli|In .NET Framework SDK 4.7.1, gli strumenti svcconfigedit.exe e svctraceviewer.exe sono stati migliorati risolvendo vari problemi relativi all'accessibilità. Molti erano problemi di lieve entità, come ad esempio un nome non definito o alcuni pattern dell'automazione interfaccia utente non implementati correttamente. È possibile che molti utenti non si siano accorti di questi valori non corretti. I clienti che usano tipi di assistive technology, ad esempio le utilità per la lettura dello schermo, troveranno invece questi strumenti SDK più accessibili. Queste correzioni modificano sicuramente alcuni comportamenti precedenti, ad esempio l'ordine dello stato attivo della tastiera. Per ottenere tutte le correzioni relative all'accessibilità in questi strumenti, è possibile applicare quanto segue al file app.config:<pre><code class="language-xml">&lt;runtime&gt;&#13;&#10;&lt;AppContextSwitchOverrides value=&quot;Switch.UseLegacyAccessibilityFeatures=false&quot;/&gt;&#13;&#10;&lt;/runtime&gt;&#13;&#10;</code></pre>|
|Ambito|Microsoft Edge|
|Versione|4.7.1|
|Tipo|Ridestinazione|

