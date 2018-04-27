### <a name="wpf-textboxtext-can-be-out-of-sync-with-databinding"></a>TextBox.Text di WPF può non essere sincronizzata con il data binding

|   |   |
|---|---|
|Dettagli|In alcuni casi, la proprietà <xref:System.Windows.Controls.TextBox.Text> riflette un valore precedente del valore della proprietà associata a dati se viene modificata durante un'operazione di scrittura di associazione dati.|
|Suggerimento|Non dovrebbe avere alcun impatto negativo. Tuttavia, è possibile ripristinare il comportamento precedente impostando la proprietà <xref:System.Windows.FrameworkCompatibilityPreferences.KeepTextBoxDisplaySynchronizedWithTextProperty> su <code>false</code>.|
|Ambito|Microsoft Edge|
|Versione|4.5|
|Tipo|Ridestinazione|
|API interessate|<ul><li><xref:System.Windows.Controls.TextBox.Text?displayProperty=nameWithType></li></ul>|

