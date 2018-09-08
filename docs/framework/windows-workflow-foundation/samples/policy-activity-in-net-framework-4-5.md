---
title: Attività Policy in .NET Framework 4.5
ms.date: 03/30/2017
ms.assetid: 8e375e0c-d7c1-4d69-88ab-36d52db0aa7e
ms.openlocfilehash: 9d8983f2f1d3f75beffeacfff4b673f6c23c4204
ms.sourcegitcommit: c7f3e2e9d6ead6cc3acd0d66b10a251d0c66e59d
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 09/08/2018
ms.locfileid: "44208705"
---
# <a name="policy-activity-in-net-framework-45"></a>Attività Policy in .NET Framework 4.5
L'attività Policy4 consente a Windows Workflow Foundation in [!INCLUDE[netfx35_long](../../../../includes/netfx35-long-md.md)] (WF 3.5) <xref:System.Workflow.Activities.Rules.RuleSet> oggetti utilizzabili in Windows Workflow Foundation in [!INCLUDE[netfx_current_long](../../../../includes/netfx-current-long-md.md)] (WF 4.5) direttamente tramite il motore di regole che è disponibile in WF 3.5. Usando questa attività, è possibile creare ed eseguire un oggetto <xref:System.Workflow.Activities.Rules.RuleSet> di WF 3.5. Per altre informazioni sul motore regole di WF 3.5 incluso come parte di Windows Workflow Foundation, vedere Introduzione al motore di regole di Windows Workflow Foundation. Per altre informazioni sulla migrazione delle regole a WF in [!INCLUDE[netfx_current_long](../../../../includes/netfx-current-long-md.md)], leggere [materiale sussidiario di migrazione](../../../../docs/framework/windows-workflow-foundation/migration-guidance.md).  
  
> [!IMPORTANT]
>  È possibile che gli esempi siano già installati nel computer. Verificare la directory seguente (impostazione predefinita) prima di continuare.  
>   
>  `<InstallDrive>:\WF_WCF_Samples`  
>   
>  Se questa directory non esiste, andare al [Windows Communication Foundation (WCF) e gli esempi di Windows Workflow Foundation (WF) per .NET Framework 4](https://go.microsoft.com/fwlink/?LinkId=150780) per scaricare tutti i Windows Communication Foundation (WCF) e [!INCLUDE[wf1](../../../../includes/wf1-md.md)] esempi. Questo esempio si trova nella directory seguente.  
>   
>  `<InstallDrive>:\WF_WCF_Samples\WF\Scenario\ActivityLibrary\Rules-Policy4`  
  
## <a name="projects-in-this-sample"></a>Progetti di questo esempio  
  
|Nome progetto|Descrizione|File principali|  
|------------------|-----------------|----------------|  
|Policy4|Contiene l'attività Policy4 e la relativa finestra di progettazione di [!INCLUDE[wf1](../../../../includes/wf1-md.md)].|**Policy4.cs**: definizione dell'attività Policy4.<br /><br /> **Policydesigner. XAML**: finestra di progettazione personalizzata per l'attività Policy4. Usa l'editor delle regole ([classe RuleSetDialog](https://go.microsoft.com/fwlink/?LinkId=150378)) da [!INCLUDE[wf1](../../../../includes/wf1-md.md)] motore regole di business.|  
|ImperativeCodeClientSample|Applicazione client di esempio che configura ed esegue un flusso di lavoro tramite un'applicazione Policy4 e il codice C# imperativo (non viene usata alcuna finestra di progettazione di [!INCLUDE[wf1](../../../../includes/wf1-md.md)]).|**ApplyDiscount**: File con [!INCLUDE[wf1](../../../../includes/wf1-md.md)] definizioni delle regole.<br /><br /> **Order.cs**: tipo che rappresenta un ordine del cliente. Le regole vengono applicate agli oggetti di questo tipo.<br /><br /> **Program.cs**: configura ed esegue un flusso di lavoro che dispone di un'attività Policy4 per applicare le regole definite in ApplyDiscount alle istanze di oggetti Order.<br /><br /> **App. config**: file di configurazione con il percorso del file di regole.|  
|DesignerClientSample|Applicazione client di esempio che configura ed esegue un flusso di lavoro tramite un'applicazione Policy4 nella finestra di progettazione di [!INCLUDE[wf1](../../../../includes/wf1-md.md)].|**Sequence1.XAML**: flusso di lavoro sequenza che usa un'attività Policy4 per eseguire valutazioni delle regole.<br /><br /> `Program.cs`: esegue un'istanza del flusso di lavoro definito in Sequence1.xaml.|  
  
## <a name="the-policy4-activity"></a>Attività Policy4  
 L'attività Policy4 è una classe che deriva dall'oggetto <xref:System.Activities.NativeActivity%601> che consente ai flussi di lavoro di eseguire oggetti RuleSet di [!INCLUDE[wf1](../../../../includes/wf1-md.md)]. L'esempio di codice seguente è una definizione semplificata del modello a oggetti pubblico dell'attività.  
  
```csharp  
public class Policy4Activity<TResult>: NativeActivity<TResult>  
{  
    public RuleSet RuleSet  
  
    [IsRequired]  
    public InArgument Input  
  
    public OutArgument<ValidationErrorCollection> ValidationErrors  
}  
```  
  
|Proprietà|Descrizione|  
|--------------|-----------------|  
|RuleSet|WF [classe RuleSet](https://go.microsoft.com/fwlink/?LinkId=150379) per .NET Framework 3.5 da valutare quando viene eseguita l'attività.|  
|TargetObject|Oggetto rispetto al quale le regole nel [classe RuleSet](https://go.microsoft.com/fwlink/?LinkId=150379) vengono valutati.|  
|ValidationError|L'elenco di errori di convalida restituiti dal [!INCLUDE[wf1](../../../../includes/wf1-md.md)] motore regole di business per .NET Framework 3.5 quando si convalida la [classe RuleSet](https://go.microsoft.com/fwlink/?LinkId=150379) rispetto all'oggetto di destinazione prima dell'esecuzione.|  
  
## <a name="policy4-activity-designer"></a>ActivityDesigner di Policy4  
 La finestra di progettazione di Policy4 aggiunge la funzionalità che consente di configurare un'attività Policy4 senza dover scrivere codice. Dopo aver compilato la soluzione, è disponibile nella casella degli strumenti nella sezione **Activities**.  
  
 La finestra di progettazione di WF consente di configurare un oggetto di destinazione e un oggetto RuleSet. Quando la **modifica RuleSet** viene fatto clic sul pulsante, WF [classe RuleSetDialog](https://go.microsoft.com/fwlink/?LinkId=150378) per [!INCLUDE[netfx35_short](../../../../includes/netfx35-short-md.md)] viene visualizzato. Questa finestra di dialogo è l'editor delle regole di [!INCLUDE[netfx35_short](../../../../includes/netfx35-short-md.md)] rieseguito nell'host. Usare l'editor per creare e modificare le regole eseguite dall'attività Policy4.  
  
## <a name="using-this-sample"></a>Utilizzo dell'esempio  
 Per eseguire questo esempio non è necessaria alcuna configurazione particolare. È sufficiente aprire la soluzione in Visual Studio e premere F5 per eseguire l'applicazione.  
  
 In questo esempio sono contenute due applicazioni client: ImperativeCodeClientSample e DesignerClientSample. Nel client ImperativeCodeClientSample viene illustrato come configurare ed eseguire l'attività Policy40 tramite il codice imperativo C#. In DesignerClientSample viene illustrato come configurare ed eseguire l'attività Policy4 tramite la finestra di progettazione.  
  
#### <a name="to-run-the-imperativecodeclientsample-client-application"></a>Per eseguire l'applicazione client ImperativeCodeClientSample  
  
1.  In [!INCLUDE[vs_current_long](../../../../includes/vs-current-long-md.md)] aprire il file della soluzione Policy4Sample.sln.  
  
2.  Nella **Esplora soluzioni**, fare doppio clic il **ImperativeCodeClientSample** del progetto e quindi selezionare **imposta come progetto di avvio**.  
  
3.  Per eseguire il progetto, premere CTRL+F5.  
  
#### <a name="to-run-the-imperativecodeclientsample-client-application"></a>Per eseguire l'applicazione client ImperativeCodeClientSample  
  
1.  In [!INCLUDE[vs_current_long](../../../../includes/vs-current-long-md.md)] aprire il file della soluzione Policy4Sample.sln.  
  
2.  Nelle **Esplora soluzioni**, fare doppio clic il **DesignerClientSample** progetto.  
  
    -   Selezionare **imposta come progetto di avvio**.  
  
3.  Per compilare il progetto, premere CTRL+MAIUSC+B.  
  
4.  Per eseguire il progetto, premere CTRL+F5.