### <a name="nullreferenceexception-in-exception-handling-code-from-imagesourceconverterconvertfrom"></a>NullReferenceException nel codice di gestione delle eccezioni da ImageSourceConverter.ConvertFrom

|   |   |
|---|---|
|Dettagli|Un errore del codice di gestione delle eccezioni per <xref:System.Windows.Media.ImageSourceConverter.ConvertFrom(System.ComponentModel.ITypeDescriptorContext,System.Globalization.CultureInfo,System.Object)> ha causato la generazione di un oggetto <xref:System.NullReferenceException?displayProperty=name> non corretto anziché dell'eccezione prevista (<xref:System.IO.DirectoryNotFoundException?displayProperty=name> o <xref:System.IO.FileNotFoundException?displayProperty=name>). Questa modifica corregge tale errore e quindi il metodo ora genera l'eccezione appropriata. Per impostazione predefinita, tutte le applicazioni con destinazione .NET Framework 4.6.2 e versioni precedenti continueranno a generare <xref:System.NullReferenceException?displayProperty=name> per garantire la compatibilità, gli sviluppatori che usano .NET Framework 4.7 e versioni successive come destinazione devono visualizzare le eccezioni corrette.|
|Suggerimento|Gli sviluppatori che preferiscono tornare al recupero di <xref:System.NullReferenceException?displayProperty=name> quando usano .NET Framework 4.7 o versione successiva come destinazione possono aggiungere o unire il codice seguente al file App.config della propria applicazione:<pre><code class="language-xml">&lt;configuration&gt;&#13;&#10;&lt;runtime&gt;&#13;&#10;&lt;AppContextSwitchOverrides value=&quot;Switch.System.Windows.Media.ImageSourceConverter.OverrideExceptionWithNullReferenceException=true&quot;/&gt;&#13;&#10;&lt;/runtime&gt;&#13;&#10;&lt;/configuration&gt;&#13;&#10;</code></pre>|
|Ambito|Microsoft Edge|
|Versione|4.7|
|Tipo|Ridestinazione|
|API interessate|<ul><li><xref:System.Windows.Media.ImageSourceConverter.ConvertFrom(System.ComponentModel.ITypeDescriptorContext,System.Globalization.CultureInfo,System.Object)?displayProperty=nameWithType></li></ul>|

