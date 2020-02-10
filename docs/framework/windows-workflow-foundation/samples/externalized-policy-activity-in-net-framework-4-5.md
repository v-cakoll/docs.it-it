---
title: Attività ExternalizedPolicy in .NET Framework 4.5
ms.date: 03/30/2017
ms.assetid: 92fd6f92-23a1-4adf-b96a-2754ea93ad3e
ms.openlocfilehash: 8fd08c9c29f7a268170aaa101a9bdb85250157dc
ms.sourcegitcommit: 011314e0c8eb4cf4a11d92078f58176c8c3efd2d
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 02/09/2020
ms.locfileid: "77094631"
---
# <a name="externalized-policy-activity-in-net-framework-45"></a>Attività ExternalizedPolicy in .NET Framework 4.5

Questo esempio illustra il modo in cui l'attività ExternalizedPolicy4 consente l'esecuzione diretta di .NET Framework 3,5 Windows Workflow Foundation (WF 3,5) <xref:System.Workflow.Activities.Rules.RuleSet> oggetti in [!INCLUDE[netfx_current_long](../../../../includes/netfx-current-long-md.md)] Windows Workflow Foundation (WF 4,5) usando il motore regole fornito in WF 3,5. Usando questa attività, è possibile aprire ed eseguire un oggetto <xref:System.Workflow.Activities.Rules.RuleSet> esistente di WF 3.5. Per ulteriori informazioni sul motore regole di WF 3,5 incluso come parte di Windows Workflow Foundation, vedere [Introduzione al motore regole di Windows Workflow Foundation](https://docs.microsoft.com/previous-versions/dotnet/articles/aa480193(v=msdn.10)). Per ulteriori informazioni sulla migrazione delle regole per [!INCLUDE[wf1](../../../../includes/wf1-md.md)] in [!INCLUDE[netfx_current_short](../../../../includes/netfx-current-short-md.md)], vedere la [Guida alla migrazione](../migration-guidance.md).

## <a name="projects-in-this-sample"></a>Progetti di questo esempio

|Nome del progetto|Descrizione|File principali|
|-|-|-|
|ExternalizedPolicy4|Contiene l'attività ExternalizedPolicy4 e la relativa finestra di progettazione di WF 4.5.|**ExternalizedPolicy4.cs**: definizione dell'attività.<br /><br /> **ExternalizedPolicy4Designer. XAML**: finestra di progettazione personalizzata per l'attività ExternalizedPolicy4. Usa l'editor delle regole (<xref:System.Workflow.Activities.Rules.Design.RuleSetDialog>) dal motore per le regole di WF 3.5.|
|ImperativeCodeClientSample|Applicazione client di esempio che configura ed esegue un flusso di lavoro tramite un'applicazione ExternalizedPolicy4 e il codice C# imperativo (non viene usata alcuna finestra di progettazione).|**ApplyDiscount. Rules**: file con definizioni della regola di [!INCLUDE[wf1](../../../../includes/wf1-md.md)].<br /><br /> **Order.cs**: tipo che rappresenta un ordine del cliente. Le regole vengono applicate agli oggetti di questo tipo.<br /><br /> **Program.cs**: configura ed esegue un flusso di lavoro che dispone di un'attività Policy4 per applicare le regole definite in ApplyDiscount. Rules alle istanze degli oggetti Order.<br /><br /> App.config: file di configurazione con il percorso del file delle regole.|
|DesignerClientSample|Applicazione client di esempio che configura ed esegue un flusso di lavoro tramite un'applicazione ExternalPolicy4 nella finestra di progettazione di [!INCLUDE[wf1](../../../../includes/wf1-md.md)].|**Sequence1. XAML**: flusso di lavoro sequenziale che usa un'attività Policy4 per eseguire valutazioni delle regole.<br /><br /> **Program.cs**: esegue un'istanza del flusso di lavoro definito in Sequence1. XAML.|

## <a name="the-externalizedpolicy4-activity"></a>Attività ExternalizedPolicy4

L'attività ExternalizedPolicy4 è un oggetto <xref:System.Activities.NativeActivity> che consente l'esecuzione degli oggetti <xref:System.Workflow.Activities.Rules.RuleSet> di WF 3.5 all'interno dei flussi di lavoro di WF 4.5. L'esempio seguente è una definizione semplificata del modello a oggetti pubblico dell'attività.

```csharp
public class ExternalizedPolicy4Activity<TResult>: CodeActivity
{
    public string RulesFilePath

    public string RuleSetName

    [RequiredArgument]
    public InArgument<T> TargetObject

    [RequiredArgument]
    public OutArgument<T> ResultObject

    public OutArgument<ValidationErrorCollection> ValidationErrors
}
```

|Proprietà|Descrizione|
|-|-|
|RuleSetFilePath|Percorso del file <xref:System.Workflow.Activities.Rules.RuleSet> di .NET Framework 3.5 da valutare quando viene eseguita l'attività.|
|RuleSetName|Nome dell'oggetto <xref:System.Workflow.Activities.Rules.RuleSet> da usare all'interno del file con estensione rules.|
|TargetObject|Oggetto nel quale gli oggetti <xref:System.Workflow.Activities.Rules.Rule> vengono valutati rispetto all'oggetto <xref:System.Workflow.Activities.Rules.RuleSet>.|
|ResultObject|Oggetto risultante dopo aver applicato le regole (ad esempio le regole vengono applicate rispetto all'argomento di input e il risultato viene archiviato nell'argomento Result).|
|ValidationError|Elenco di errori di convalida restituiti dal motore per le regole di WF 3.5 quando si convalida l'oggetto <xref:System.Workflow.Activities.Rules.RuleSet> rispetto all'oggetto di destinazione prima dell'esecuzione.|

## <a name="externalizedpolicy4-activity-designer"></a>ActivityDesigner di ExternalizedPolicy4

La finestra di progettazione ExternalizedPolicy4 consente di configurare un'attività per usare un oggetto RuleSet esistente senza scrivere codice. È sufficiente impostare il percorso in cui si trova il file con estensione rules e specificare il nome dell'oggetto <xref:System.Workflow.Activities.Rules.RuleSet> che si desidera usare. Consente inoltre di modificare l'oggetto <xref:System.Workflow.Activities.Rules.RuleSet>. Dopo aver compilato la soluzione, è disponibile nella casella degli strumenti nella sezione Microsoft.Samples.Activities.Rules. La finestra di progettazione consente di selezionare un file con estensione rules e un oggetto <xref:System.Workflow.Activities.Rules.RuleSet>. Quando si fa clic sul pulsante **Modifica RuleSet** , viene visualizzato il <xref:System.Workflow.Activities.Rules.Design.RuleSetDialog> WF 3,5. Questa finestra di dialogo è l'editor delle regole di WF 3.5 rieseguito nell'host e viene usata per visualizzare e modificare le regole eseguite dall'attività ExternalizedPolicy4.

## <a name="policy4-and-externalpolicy4"></a>Policy4 e ExternalPolicy4

L'attività criterio consente di creare ed eseguire un set di regole .NET Framework 3,5 in un flusso di lavoro di WF 4,5. L'oggetto <xref:System.Workflow.Activities.Rules.RuleSet> è serializzato inline nella definizione XML dell'attività Policy4. Nell'esempio ExternalizedPolicy4 viene illustrato come usare un oggetto <xref:System.Workflow.Activities.Rules.RuleSet> esterno esistente (contenuto in un file con estensione rules).

## <a name="use-this-sample"></a>Usare questo esempio

Per eseguire questo esempio non è necessaria alcuna configurazione particolare. Aprire la soluzione in Visual Studio, quindi premere **F5** per eseguire l'applicazione.

In questo esempio sono contenute due applicazioni client: ImperativeCodeClientSample e DesignerClientSample. Nel client ImperativeCodeClientSample viene illustrato come configurare ed eseguire l'attività ExternalizedPolicy4 tramite il codice imperativo C#. In DesignerClientSample viene illustrato come configurare ed eseguire l'attività ExternalizedPolicy4 tramite la finestra di progettazione.

### <a name="run-the-imperativecodeclientsample-application"></a>Eseguire l'applicazione ImperativeCodeClientSample

1. Con Visual Studio aprire il file della soluzione *Policy4sample. sln* .

2. In **Esplora soluzioni**fare clic con il pulsante destro del mouse sul progetto **ImperativeCodeClientSample** , quindi scegliere **Imposta come progetto di avvio**.

3. Per eseguire il progetto, premere **Ctrl**+**F5**.

### <a name="run-the-designerclientsample-application"></a>Eseguire l'applicazione DesignerClientSample

1. Con Visual Studio aprire il file della soluzione *Policy4sample. sln* .

2. In **Esplora soluzioni**fare clic con il pulsante destro del mouse sul progetto **DesignerClientSample** , quindi scegliere **Imposta come progetto di avvio**.

3. Premere **Ctrl**+**MAIUSC**+**B** per compilare il progetto.

4. Premere **Ctrl**+**F5** per eseguire il progetto.

> [!IMPORTANT]
> È possibile che gli esempi siano già installati nel computer. Verificare la directory seguente (impostazione predefinita) prima di continuare.
>
> `<InstallDrive>:\WF_WCF_Samples`
>
> Se questa directory non esiste, passare a [Windows Communication Foundation (WCF) ed esempi di Windows Workflow Foundation (WF) per .NET Framework 4](https://www.microsoft.com/download/details.aspx?id=21459) per scaricare tutti i Windows Communication Foundation (WCF) e [!INCLUDE[wf1](../../../../includes/wf1-md.md)] esempi.
>
> Questo esempio si trova nella directory seguente.
>
> `<InstallDrive>:\WF_WCF_Samples\WF\Scenario\ActivityLibrary\Rules-ExternalizedPolicy4`
