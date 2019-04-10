---
title: Attività ExternalizedPolicy in .NET Framework 4.5
ms.date: 03/30/2017
ms.assetid: 92fd6f92-23a1-4adf-b96a-2754ea93ad3e
ms.openlocfilehash: 622b0f14281d5b068700d9e4fe03485aa1a60fcb
ms.sourcegitcommit: 558d78d2a68acd4c95ef23231c8b4e4c7bac3902
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 04/09/2019
ms.locfileid: "59338280"
---
# <a name="externalized-policy-activity-in-net-framework-45"></a>Attività ExternalizedPolicy in .NET Framework 4.5

Questo esempio viene illustrato come l'attività ExternalizedPolicy4 consenta l'esecuzione esistente [!INCLUDE[netfx35_long](../../../../includes/netfx35-long-md.md)] Windows Workflow Foundation (WF 3.5) <xref:System.Workflow.Activities.Rules.RuleSet> gli oggetti in [!INCLUDE[netfx_current_long](../../../../includes/netfx-current-long-md.md)] Windows Workflow Foundation (WF 4.5) direttamente tramite il motore regole che viene fornito in WF 3.5. Usando questa attività, è possibile aprire ed eseguire un oggetto <xref:System.Workflow.Activities.Rules.RuleSet> esistente di WF 3.5. Per altre informazioni sul motore regole di WF 3.5 incluso come parte di Windows Workflow Foundation, leggere [Introduzione al motore di regole di Windows Workflow Foundation](https://go.microsoft.com/fwlink/?LinkId=166079). Per altre informazioni sulla migrazione delle regole per [!INCLUDE[wf1](../../../../includes/wf1-md.md)] nel [!INCLUDE[netfx_current_short](../../../../includes/netfx-current-short-md.md)], leggere le istruzioni di migrazione [materiale sussidiario di migrazione](../migration-guidance.md).

## <a name="projects-in-this-sample"></a>Progetti di questo esempio

|Nome progetto|Descrizione|File principali|
|-|-|-|
|ExternalizedPolicy4|Contiene l'attività ExternalizedPolicy4 e la relativa finestra di progettazione di WF 4.5.|**ExternalizedPolicy4.cs**: definizione di attività.<br /><br /> **ExternalizedPolicy4Designer.xaml**: Finestra di progettazione personalizzata per l'attività ExternalizedPolicy4. Usa l'editor delle regole (<xref:System.Workflow.Activities.Rules.Design.RuleSetDialog>) dal motore per le regole di WF 3.5.|
|ImperativeCodeClientSample|Applicazione client di esempio che configura ed esegue un flusso di lavoro tramite un'applicazione ExternalizedPolicy4 e il codice C# imperativo (non viene usata alcuna finestra di progettazione).|**ApplyDiscount.rules**: File con [!INCLUDE[wf1](../../../../includes/wf1-md.md)] definizioni delle regole.<br /><br /> **Order.cs**: Tipo che rappresenta un ordine del cliente. Le regole vengono applicate agli oggetti di questo tipo.<br /><br /> **Program.cs**: Configura ed esegue un flusso di lavoro che dispone di un'attività Policy4 per applicare le regole definite in ApplyDiscount alle istanze di oggetti Order.<br /><br /> App.config: File di configurazione con il percorso del file di regole.|
|DesignerClientSample|Applicazione client di esempio che configura ed esegue un flusso di lavoro tramite un'applicazione ExternalPolicy4 nella finestra di progettazione di [!INCLUDE[wf1](../../../../includes/wf1-md.md)].|**Sequence1.XAML**: Flusso di lavoro sequenza che usa un'attività Policy4 per eseguire valutazioni delle regole.<br /><br /> **Program.cs**: Esegue un'istanza del flusso di lavoro definito in Sequence1.xaml.|

## <a name="the-externalizedpolicy4-activity"></a>Attività ExternalizedPolicy4

L'attività ExternalizedPolicy4 è un oggetto <xref:System.Activities.NativeActivity> che consente l'esecuzione degli oggetti <xref:System.Workflow.Activities.Rules.RuleSet> di WF 3.5 all'interno dei flussi di lavoro di WF 4.5. L'esempio seguente è una definizione semplificata del modello a oggetti pubblico dell'attività.

```
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

La finestra di progettazione ExternalizedPolicy4 consente di configurare un'attività per usare un oggetto RuleSet esistente senza scrivere codice. È sufficiente impostare il percorso in cui si trova il file con estensione rules e specificare il nome dell'oggetto <xref:System.Workflow.Activities.Rules.RuleSet> che si desidera usare. Consente inoltre di modificare l'oggetto <xref:System.Workflow.Activities.Rules.RuleSet>. Dopo aver compilato la soluzione, è disponibile nella casella degli strumenti nella sezione Microsoft.Samples.Activities.Rules. La finestra di progettazione consente di selezionare un file con estensione rules e un oggetto <xref:System.Workflow.Activities.Rules.RuleSet>. Quando la **modifica RuleSet** viene fatto clic sul pulsante, di WF 3.5 <xref:System.Workflow.Activities.Rules.Design.RuleSetDialog> viene visualizzato. Questa finestra di dialogo è l'editor delle regole di WF 3.5 rieseguito nell'host e viene usata per visualizzare e modificare le regole eseguite dall'attività ExternalizedPolicy4.

## <a name="policy4-and-externalpolicy4"></a>Policy4 e ExternalPolicy4

L'attività relativa ai criteri consente di creare ed eseguire un set di regole di .NET Framework 3.5 in un flusso di lavoro di WF 4.5. L'oggetto <xref:System.Workflow.Activities.Rules.RuleSet> è serializzato inline nella definizione XML dell'attività Policy4. Nell'esempio ExternalizedPolicy4 viene illustrato come usare un oggetto <xref:System.Workflow.Activities.Rules.RuleSet> esterno esistente (contenuto in un file con estensione rules).

## <a name="use-this-sample"></a>Usare questo esempio

Per eseguire questo esempio non è necessaria alcuna configurazione particolare. Aprire la soluzione in Visual Studio e quindi premere **F5** per eseguire l'applicazione.

In questo esempio contiene due applicazioni client: ImperativeCodeClientSample e DesignerClientSample. Nel client ImperativeCodeClientSample viene illustrato come configurare ed eseguire l'attività ExternalizedPolicy4 tramite il codice imperativo C#. In DesignerClientSample viene illustrato come configurare ed eseguire l'attività ExternalizedPolicy4 tramite la finestra di progettazione.

### <a name="run-the-imperativecodeclientsample-application"></a>Eseguire l'applicazione ImperativeCodeClientSample

1. Se si utilizza Visual Studio, aprire il *Policy4sample.sln* file della soluzione.

2. Nella **Esplora soluzioni**, fare doppio clic il **ImperativeCodeClientSample** del progetto e quindi selezionare **imposta come progetto di avvio**.

3. Per eseguire il progetto, premere **Ctrl**+**F5**.

### <a name="run-the-designerclientsample-application"></a>Eseguire l'applicazione DesignerClientSample

1. Se si utilizza Visual Studio, aprire il *Policy4sample.sln* file della soluzione.

2. Nella **Esplora soluzioni**, fare doppio clic il **DesignerClientSample** del progetto e quindi selezionare **imposta come progetto di avvio**.

3. Premere **Ctrl**+**MAIUSC**+**B** per compilare il progetto.

4. Premere **Ctrl**+**F5** per eseguire il progetto.

> [!IMPORTANT]
> È possibile che gli esempi siano già installati nel computer. Verificare la directory seguente (impostazione predefinita) prima di continuare.
>
> `<InstallDrive>:\WF_WCF_Samples`
>
> Se questa directory non esiste, andare al [Windows Communication Foundation (WCF) e gli esempi di Windows Workflow Foundation (WF) per .NET Framework 4](https://go.microsoft.com/fwlink/?LinkId=150780) per scaricare tutti i Windows Communication Foundation (WCF) e [!INCLUDE[wf1](../../../../includes/wf1-md.md)] esempi.
>
> Questo esempio si trova nella directory seguente.
>
> `<InstallDrive>:\WF_WCF_Samples\WF\Scenario\ActivityLibrary\Rules-ExternalizedPolicy4`
