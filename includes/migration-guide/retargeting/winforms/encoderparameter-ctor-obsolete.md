### <a name="encoderparameter-ctor-is-obsolete"></a>Il costruttore EncoderParameter è obsoleto

|   |   |
|---|---|
|Dettagli|Il costruttore <xref:System.Drawing.Imaging.EncoderParameter.%23ctor(System.Drawing.Imaging.Encoder,System.Int32,System.Int32,System.Int32,System.Int32)> è ora obsoleto e l'eventuale uso causerà avvisi di compilazione.|
|Suggerimento|Anche se il costruttore <xref:System.Drawing.Imaging.EncoderParameter.%23ctor(System.Drawing.Imaging.Encoder,System.Int32,System.Int32,System.Int32,System.Int32)> continuerà a funzionare, è necessario usare il costruttore seguente per evitare l'avviso di compilazione obsoleto durante la ricompilazione del codice con gli strumenti di .NET 4.5: <xref:System.Drawing.Imaging.EncoderParameter.%23ctor(System.Drawing.Imaging.Encoder,System.Int32,System.Drawing.Imaging.EncoderParameterValueType,System.IntPtr)>.|
|Ambito|Secondario|
|Versione|4.5|
|Tipo|Ridestinazione|
|API interessate|<ul><li><xref:System.Drawing.Imaging.EncoderParameter.%23ctor(System.Drawing.Imaging.Encoder,System.Int32,System.Int32,System.Int32,System.Int32)?displayProperty=nameWithType></li></ul>|

