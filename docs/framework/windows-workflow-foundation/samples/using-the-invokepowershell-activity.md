---
title: "Utilizzo dell'attività InvokePowerShell"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 956251a0-31ca-4183-bf76-d277c08585df
caps.latest.revision: "10"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.openlocfilehash: b3ef8b539e490911e5454fe87db483508cc8a5d8
ms.sourcegitcommit: ce279f2d7fe2220e6ea0a25a8a7a5370ddf8d9f0
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 12/02/2017
---
# <a name="using-the-invokepowershell-activity"></a>Utilizzo dell'attività InvokePowerShell
Nell'esempio InvokePowerShell viene illustrato come richiamare i comandi di Windows PowerShell usando l'attività `InvokePowerShell`.  
  
## <a name="demonstrates"></a>Dimostrazione  
  
-   Semplice innovazione dei comandi di Windows PowerShell.  
  
-   Recupero di valori dalla pipeline di output di Windows PowerShell e relativa archiviazione nelle variabili del flusso di lavoro.  
  
-   Passaggio di dati in Windows PowerShell come pipeline di input per un comando di esecuzione.  
  
> [!IMPORTANT]
>  È possibile che gli esempi siano già installati nel computer. Verificare la directory seguente (impostazione predefinita) prima di continuare.  
>   
>  `<InstallDrive>:\WF_WCF_Samples`  
>   
>  Se questa directory non esiste, andare alla sezione relativa agli [esempi di Windows Communication Foundation (WCF) e Windows Workflow Foundation (WF) per .NET Framework 4](http://go.microsoft.com/fwlink/?LinkId=150780) per scaricare tutti gli esempi di [!INCLUDE[indigo1](../../../../includes/indigo1-md.md)] e [!INCLUDE[wf1](../../../../includes/wf1-md.md)] . Questo esempio si trova nella directory seguente.  
>   
>  `<InstallDrive>:\WF_WCF_Samples\WF\Scenario\ActivityLibrary\PowerShell`  
  
## <a name="discussion"></a>Discussione  
 In questo esempio sono contenuti i tre progetti seguenti.  
  
|Nome progetto|Descrizione|File principali|  
|------------------|-----------------|----------------|  
|CodedClient|Applicazione client di esempio che usa l'attività PowerShell.|-   **Program.cs**: a livello di codice crea un flusso di lavoro basato su sequenze che chiama l'attività InvokePowerShell.|  
|DesignerClient|Set di attività personalizzate che contengono l'attività personalizzata `InvokePowerShell` e altre varie attività personalizzate, nonché un flusso di lavoro che le usa.|<ul><li>Attività:<br /><br /> <ul><li>**Printcollection**: attività di supporto che stampa tutti gli elementi in una raccolta nella console.</li><li>**ReadLine**: attività di supporto per la lettura dell'input dalla console.</li></ul></li><li>File system:<br /><br /> <ul><li>**Copy. XAML**: un'attività che copia un file.</li><li>**CreateFile. XAML**: un'attività che crea un file.</li><li>**DeleteFile. XAML**: un'attività che elimina un file.</li><li>**MakeDir. XAML**: un'attività che crea una directory.</li><li>**Move. XAML**: un'attività che consente di spostare un file.</li><li>**ReadFile. XAML**: un'attività che legge un file e restituisce il relativo contenuto.</li><li>**TestPath. XAML**: attività che verifica l'esistenza di un percorso.</li></ul></li><li>Processo:<br /><br /> <ul><li>**GetProcess. XAML**: un'attività che ottiene un elenco dei processi in esecuzione.</li><li>**Stopprocess. XAML**: un'attività che interrompe un processo specifico.</li></ul></li><li>**Program.cs**: chiama il flusso di lavoro Sequence1.</li><li>**Sequence1**: un flusso di lavoro basato su sequenze.</li></ul>|  
|PowerShell|Attività `InvokePowerShell` e finestre di progettazione associate.|File di attività<br /><br /> -   **Executepowershell**: logica di esecuzione principale dell'attività.<br />-   **Invokepowershell. cs**: wrapper della logica di esecuzione principale che contiene una versione generica (valore restituito) e una versione non generica (valore non restituito). Si tratta dell'interfaccia pubblica per l'attività.<br />-   **Nopersistzone**: questa attività impedisce la persistenza delle attività figlio. Questa classe viene usata all'interno dell'implementazione dell'attività `InvokePowerShell` per evitare che l'attività venga resa persistente a metà esecuzione.<br /><br /> File delle finestre di progettazione:<br /><br /> 1.  **ArgumentDictionaryEditor.cs**: finestra di dialogo di Windows che consente all'utente di modificare gli argomenti del `InvokePowerShell` attività.<br />2.  **Genericinvokepowershelldesigner. XAML** e **GenericInvokePowerShellDesigner.xaml.cs**: definisce l'aspetto del tipo generico `InvokePowerShell` attività [!INCLUDE[wfd2](../../../../includes/wfd2-md.md)].<br />3.  **Invokepowershelldesigner. XAML** e **invokepowershelldesigner. cs**: definisce l'aspetto del tipo non generico- `InvokePowerShell` attività [!INCLUDE[wfd2](../../../../includes/wfd2-md.md)].|  
  
 I progetti client vengono discussi per primi, poiché è più semplice capire la funzionalità interna dell'attività PowerShell una volta capito il relativo uso.  
  
## <a name="using-this-sample"></a>Utilizzo dell'esempio  
 Nelle sezioni seguenti viene descritto come usare i tre progetti dell'esempio.  
  
### <a name="using-the-coded-client-project"></a>Utilizzo del progetto CodedClient  
 Il client di esempio crea a livello di codice un'attività Sequence che contiene esempi di diversi metodi di utilizzo dell'attività `InvokePowerShell`. La prima chiamata avvia il Blocco note.  
  
```  
new InvokePowerShell()  
{  
    CommandText = "notepad"  
},  
```  
  
 La seconda chiamata ottiene un elenco dei processi in esecuzione nel computer locale.  
  
```  
new InvokePowerShell<Process>()  
{  
    CommandText = "Get-Process",  
    Output = processes1,  
},  
```  
  
 `Output` è la variabile usata per archiviare l'output del comando.  
  
 La chiamata successiva mostra come eseguire un passaggio della post-elaborazione in ogni singolo output della chiamata di PowerShell. `InitializationAction` viene impostato sulla funzione che restituisce una rappresentazione in forma di stringa per ogni processo. La raccolta di queste stringhe viene restituita nella variabile `Output` dall'attività `InvokePowerShell<string>`.  
  
 Le chiamate `InvokePowerShell` successive dimostrano il passaggio di dati nell'attività e la restituzione di output ed errori.  
  
### <a name="using-the-designer-client-project"></a>Utilizzo del progetto DesignerClient  
 Il progetto DesignerClient è costituito da un set di attività personalizzate, di cui gran parte è stata compilata con l'attività `InvokePowerShell`. La maggior parte delle attività chiama la versione non generica dell'attività `InvokePowerShell` e non prevede un valore restituito. Le altre attività usano la versione generica dell'attività `InvokePowerShell` e l'argomento `InitializationAction` per elaborare i risultati in un secondo momento.  
  
## <a name="using-the-powershell-project"></a>Utilizzo del progetto PowerShell  
 L'azione principale dell'attività si verifica nella classe `ExecutePowerShell`. Poiché l'esecuzione dei comandi di PowerShell non deve bloccare il thread del flusso di lavoro principale, l'attività viene creata in modo da essere un'attività asincrona ereditando dalla classe <xref:System.Activities.AsyncCodeActivity>.  
  
 Il metodo <xref:System.Activities.AsyncCodeActivity.BeginExecute%2A> viene chiamato dall'esecuzione del flusso di lavoro per iniziare l'esecuzione dell'attività. Inizia chiamando le API di PowerShell per creare una pipeline di PowerShell.  
  
```  
runspace = RunspaceFactory.CreateRunspace();  
runspace.Open();  
pipeline = runspace.CreatePipeline();  
```  
  
 Successivamente crea un comando di PowerShell e lo popola con parametri e variabili.  
  
```  
Command cmd = new Command(this.CommandText, this.IsScript);   
// loop over parameters and run: cmd.Parameters.Add(...)  
// loop over variables and run: runspace.SessionStateProxy.SetVariable(...)  
pipeline.Commands.Add(cmd);  
```  
  
 A questo punto, gli input inoltrati tramite pipe vengono inviati anche alla pipeline. Infine, la pipeline viene sottoposta a wrapping in un oggetto `PipelineInvokerAsyncResult` e restituita. L'oggetto `PipelineInvokerAsyncResult` registra un listener e richiama la pipeline.  
  
```  
pipeline.InvokeAsync();  
```  
  
 Al termine dell'esecuzione, gli output e gli errori vengono archiviati all'interno dello stesso oggetto `PipelineInvokerAsyncResult` e il controllo viene restituito all'esecuzione del flusso di lavoro chiamando il metodo di callback passato originariamente al metodo <xref:System.Activities.AsyncCodeActivity.BeginExecute%2A>.  
  
 Alla fine dell'esecuzione del metodo, l'esecuzione del flusso di lavoro chiama il metodo <xref:System.Activities.AsyncCodeActivity.EndExecute%2A> dell'attività.  
  
 La classe `InvokePowerShell` esegue il wrapping della classe `ExecutePowerShellCommand` e crea due versioni dell'attività: una generica e una non generica. La versione non generica restituisce direttamente l'output dell'esecuzione di PowerShell, mentre la versione generica trasforma i singoli risultati nel tipo generico.  
  
 La versione generica dell'attività viene implementata come un flusso di lavoro sequenziale che chiama l'oggetto `ExecutePowerShellCommand` ed elabora i risultati in un secondo momento. Per ogni elemento nella raccolta di risultati, la fase di post-elaborazione chiama l'oggetto `InitializationAction` se impostato. In caso contrario, esegue un semplice cast.  
  
```  
new ForEach<PSObject>  
{  
    Values = psObjects,  
    Body = new ActivityAction<PSObject>  
    {  
        Argument = psObject,  
        Handler = new Sequence  
        {  
            Activities =  
            {  
                new If  
                {  
                    Condition = // Is InitializationAction set?  
                    Then = new InvokeFunc<PSObject, TResult>  
                    {  
                        Argument = psObject,  
                        Result = outputObject,  
                        Func = this.InitializationAction  
                    },  
                    Else = new Assign<TResult>  
                    {  
                        To = outputObject,  
                        Value = new InArgument<TResult>(ctx => (TResult) psObject.Get(ctx).BaseObject),  
                    }  
                },  
                new AddToCollection<TResult>  
                {  
                    Collection = outputObjects,  
                    Item = outputObject  
                },  
            }  
        }  
    }  
},  
```  
  
 Per ognuna delle due attività `InvokePowerShell` (generica e non generica), è stata creata una finestra di progettazione. InvokePowerShellDesigner.xaml e il file con estensione cs associato definiscono l'aspetto in [!INCLUDE[wfd2](../../../../includes/wfd2-md.md)] per la versione non generica dell'attività `InvokePowerShell`. In InvokePowerShellDesigner.xaml, viene usato un oggetto <xref:System.Windows.Controls.DockPanel> per rappresentare l'interfaccia grafica.  
  
```  
<DockPanel x:Uid="DockPanel_1" LastChildFill="True">  
        <TextBlock x:Uid="TextBlock_1" Text="CommandText" />  
        <TextBox x:Uid="TextBox_1" Text="{Binding Path=ModelItem.CommandText, Mode=TwoWay}"  
                 TextWrapping="WrapWithOverflow"  AcceptsReturn="True" MinLines="4" MaxLines="4"  
                 Background="{x:Null}" Margin="3" />  
    </DockPanel>  
```  
  
 Si noti che la proprietà `Text` della casella di testo è un'associazione bidirezionale che assicura che il valore della proprietà `CommandText` dell'attività sia equivalente al valore inserito nella finestra di progettazione.  
  
 GenericInvokePowerShellDesigner.xaml e il file con estensione cs associato definiscono l'interfaccia grafica per l'attività `InvokePowerShell` generica. La finestra di progettazione è leggermente più complessa perché consente agli utenti di impostare un oggetto `InitializationAction`. L'elemento principale è l'uso dell'oggetto <xref:System.Activities.Presentation.WorkflowItemPresenter> per consentire il trascinamento delle attività figlio nell'area di progettazione di `InvokePowerShell`.  
  
```  
<sap:WorkflowItemPresenter x:Uid="sap:WorkflowItemPresenter_1" Margin="0,10,0,10"  
    HintText="Drop Activities Here"  
    AllowedItemType="{x:Type sa:Activity}"  
    Item="{Binding Path=ModelItem.InitializationAction.Handler, Mode=TwoWay}"  
    Grid.Row="1" Grid.Column="1" />  
```  
  
 La personalizzazione della finestra di progettazione non termina con i file con estensione xaml che definiscono l'aspetto dell'attività nell'area di disegno della progettazione. Anche le finestre di dialogo usate per visualizzare i parametri dell'attività possono essere personalizzate. Questi parametri e le variabili PowerShell influiscono sul comportamento dei comandi di PowerShell. L'attività li espone come <!--zz <xref:System.Collections.Generic.Dictionary%601>--> `System.Collections.Generic.Dictionary` tipi. ArgumentDictionaryEditor.cs, PropertyEditorResources.xaml e PropertyEditorResources.cs definiscono la finestra di dialogo che consente di modificare questi tipi.  
  
## <a name="to-set-up-build-and-run-the-sample"></a>Per impostare, compilare ed eseguire l'esempio  
 È necessario installare Windows PowerShell per eseguire questo esempio. Windows PowerShell può essere installato da questo percorso: [Windows PowerShell](http://go.microsoft.com/fwlink/?LinkId=150383).  
  
#### <a name="to-run-the-coded-client"></a>Per eseguire il progetto CodedClient  
  
1.  Aprire PowerShell.sln tramite [!INCLUDE[vs2010](../../../../includes/vs2010-md.md)].  
  
2.  Fare clic con il pulsante destro del mouse sulla soluzione e compilarla.  
  
3.  Fare doppio clic su di **CodedClient** del progetto e selezionare **imposta come progetto di avvio**.  
  
4.  Premere CTRL+F5 per eseguire l'applicazione.  
  
#### <a name="to-run-the-designer-client"></a>Per eseguire il progetto DesignerClient  
  
1.  Aprire PowerShell.sln tramite [!INCLUDE[vs2010](../../../../includes/vs2010-md.md)].  
  
2.  Fare clic con il pulsante destro del mouse sulla soluzione e compilarla.  
  
3.  Fare doppio clic su di **DesignerClient** del progetto e selezionare **imposta come progetto di avvio**.  
  
4.  Premere CTRL+F5 per eseguire l'applicazione.  
  
## <a name="known-issues"></a>Problemi noti  
  
1.  Se si fa riferimento all'assembly o al progetto di attività `InvokePowerShell` da un altro progetto si verifica un errore di compilazione, pertanto potrebbe essere necessario aggiungere manualmente l'elemento `<SpecificVersion>True</SpecificVersion>` al file con estensione csproj del nuovo progetto sotto la riga che fa riferimento a `InvokePowerShell`.  
  
2.  Se non è installato Windows PowerShell, il seguente messaggio di errore viene visualizzato in Visual Studio non appena si aggiunge un `InvokePowerShell` attività su un flusso di lavoro:`Workflow Designer encountered problems with your document. Could not load file or assembly ‘System.Management.Automation’ ... or one of its dependencies. The system cannot find the file specified.`  
  
3.  In Windows PowerShell 2.0, la chiamata a livello di codice di `$input.MoveNext()` non viene eseguita correttamente e gli script che usano `$input.MoveNext()` generano errori e risultati imprevisti. Per risolvere questo problema, usare il verbo PowerShell `foreach` anziché chiamare `MoveNext()` quando si scorre una matrice.  
  
> [!IMPORTANT]
>  È possibile che gli esempi siano già installati nel computer. Verificare la directory seguente (impostazione predefinita) prima di continuare.  
>   
>  `<InstallDrive>:\WF_WCF_Samples`  
>   
>  Se questa directory non esiste, andare alla sezione relativa agli [esempi di Windows Communication Foundation (WCF) e Windows Workflow Foundation (WF) per .NET Framework 4](http://go.microsoft.com/fwlink/?LinkId=150780) per scaricare tutti gli esempi di [!INCLUDE[indigo1](../../../../includes/indigo1-md.md)] e [!INCLUDE[wf1](../../../../includes/wf1-md.md)] . Questo esempio si trova nella directory seguente.  
>   
>  `<InstallDrive>:\WF_WCF_Samples\WF\Scenario\ActivityLibrary\PowerShell`