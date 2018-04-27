### <a name="workflowdesignerload-doesnt-remove-symbol-property"></a>WorkflowDesigner.Load non rimuove la proprietà del simbolo

|   |   |
|---|---|
|Dettagli|Se si usa .NET Framework 4.5 come destinazione in Progettazione flussi di lavoro e si carica un flusso di lavoro 3.5 riallocato con il metodo <xref:System.Activities.Presentation.WorkflowDesigner.Load>, viene generata un'eccezione <xref:System.Xaml.XamlDuplicateMemberException?displayProperty=name> durante il salvataggio del flusso di lavoro.|
|Suggerimento|Questo bug si manifesta solo quando si seleziona .NET Framework 4.5 come destinazione in Progettazione flussi di lavoro, quindi è possibile evitarlo impostando <code>WorkflowDesigner.Context.Services.GetService&lt;DesignerConfigurationService&gt;().TargetFrameworkName</code> su .NET Framework 4.0. In alternativa il problema può essere evitato usando il metodo <xref:System.Activities.Presentation.WorkflowDesigner.Load(System.String)> per caricare il flusso di lavoro, invece di <xref:System.Activities.Presentation.WorkflowDesigner.Load>.|
|Ambito|Principale|
|Versione|4.5|
|Tipo|Ridestinazione|
|API interessate|<ul><li><xref:System.Activities.Presentation.WorkflowDesigner.Load?displayProperty=nameWithType></li></ul>|

