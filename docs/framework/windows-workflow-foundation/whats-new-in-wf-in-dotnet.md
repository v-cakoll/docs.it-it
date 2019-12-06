---
title: Novità in Windows Workflow Foundation in .NET 4.5
ms.date: 03/30/2017
ms.assetid: 195c43a8-e0a8-43d9-aead-d65a9e6751ec
ms.openlocfilehash: 80919dd7a726cbac5fa13680e0c79292745a7bca
ms.sourcegitcommit: a4f9b754059f0210e29ae0578363a27b9ba84b64
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 12/05/2019
ms.locfileid: "74837584"
---
# <a name="whats-new-in-windows-workflow-foundation-in-net-45"></a>Novità in Windows Workflow Foundation in .NET 4.5

Windows Workflow Foundation (WF) in .NET Framework 4,5 introduce molte nuove funzionalità, ad esempio nuove attività, funzionalità di progettazione e modelli di sviluppo del flusso di lavoro. Molte, ma non tutte, delle nuove funzionalità del flusso di lavoro introdotte in .NET Framework 4,5 sono supportate nella finestra di progettazione del flusso di lavoro riallocata. Per ulteriori informazioni sulle nuove funzionalità supportate, vedere [supporto per le nuove funzionalità di Workflow Foundation 4,5 nella progettazione flussi di lavoro riallocata](wf-features-in-the-rehosted-workflow-designer.md). Per ulteriori informazioni sulla migrazione di applicazioni flusso di lavoro .NET 3,0 e .NET 3,5 per utilizzare la versione più recente, vedere la [Guida alla migrazione](migration-guidance.md). Questo argomento fornisce una panoramica delle nuove funzionalità del flusso di lavoro introdotte in .NET Framework 4,5.

> [!WARNING]
> Le nuove funzionalità di Windows Workflow Foundation introdotte in .NET Framework 4,5 non sono disponibili per i progetti destinati a versioni precedenti del Framework. Se un progetto che ha come destinazione .NET Framework 4,5 viene riassegnato a una versione precedente del Framework, possono verificarsi diversi problemi.
>
> - C#le espressioni verranno sostituite nella finestra di progettazione con il valore del messaggio **impostato in XAML**.
> - Si verificheranno molti errori di compilazione, incluso il seguente errore.
>
> **Il formato del file non è compatibile con il Framework di destinazione corrente. Per convertire il formato del file, salvare il file in modo esplicito. Questo messaggio di errore verrà tolto dopo il salvataggio del file e la riapertura della finestra di progettazione.**

## <a name="BKMK_Versioning"></a>Controllo delle versioni del flusso di lavoro

In .NET Framework 4,5 sono state introdotte diverse nuove funzionalità di controllo delle versioni basate sulla nuova classe <xref:System.Activities.WorkflowIdentity>. La classe <xref:System.Activities.WorkflowIdentity> fornisce agli autori dell'applicazione flusso di lavoro un meccanismo per eseguire il mapping di un'istanza del flusso di lavoro persistente con la relativa definizione.

- Gli sviluppatori che usano l'hosting di <xref:System.Activities.WorkflowApplication> possono usare la classe <xref:System.Activities.WorkflowIdentity> per consentire l'hosting side-by-side di più versioni di un flusso di lavoro. Le istanze del flusso di lavoro persistenti possono essere caricate usando la nuova classe <xref:System.Activities.WorkflowApplicationInstance>. Successivamente, <xref:System.Activities.WorkflowApplicationInstance.DefinitionIdentity%2A> può essere usato dall'host per fornire la versione corretta della definizione del flusso di lavoro durante la creazione di istanze di <xref:System.Activities.WorkflowApplication>. Per altre informazioni, vedere [uso di WorkflowIdentity e controllo delle versioni](using-workflowidentity-and-versioning.md) e [procedura: ospitare più versioni di un flusso di lavoro side-by-side](how-to-host-multiple-versions-of-a-workflow-side-by-side.md).

- L'oggetto <xref:System.ServiceModel.WorkflowServiceHost> è ora un host multiversione. Quando viene distribuita una nuova versione di un servizio del flusso di lavoro, vengono create nuove istanze usando il nuovo servizio, mentre le istanze esistenti vengono completate con la versione precedente. Per ulteriori informazioni, vedere [controllo delle versioni side-by-side in WorkflowServiceHost](../wcf/feature-details/side-by-side-versioning-in-workflowservicehost.md).

- Viene introdotto l'aggiornamento dinamico che fornisce un meccanismo per aggiornare la definizione di un'istanza del flusso di lavoro persistente. Per altre informazioni, vedere [aggiornamento dinamico](dynamic-update.md) e [procedura: aggiornare la definizione di un'istanza del flusso di lavoro in esecuzione](how-to-update-the-definition-of-a-running-workflow-instance.md).

- Viene fornito uno script di database SqlWorkflowInstanceStoreSchemaUpgrade. SQL per aggiornare i database di persistenza creati usando gli script di database .NET Framework 4. Questo script Aggiorna .NET Framework 4 database di persistenza per supportare le nuove funzionalità di controllo delle versioni introdotte in .NET Framework 4,5. Le istanze persistenti del flusso di lavoro nel database sono valori predefiniti specificati per il controllo delle versioni e possono partecipare all'esecuzione side-by-side e all'aggiornamento dinamico. Per ulteriori informazioni, vedere [aggiornamento .NET Framework 4 database di persistenza per supportare il controllo delle versioni del flusso di lavoro](using-workflowidentity-and-versioning.md#UpdatingWF4PersistenceDatabases).

## <a name="BKMK_NewActivities"></a>Attività

La libreria di attività predefinita contiene nuove attività e funzionalità per le attività esistenti.

### <a name="BKMK_NoPersistScope"></a>Ambito Norese

<xref:System.Activities.Statements.NoPersistScope> è una nuova attività contenitore che impedisce a un flusso di lavoro di essere reso persistente durante l'esecuzione delle attività figlio di NoPersistScope. Ciò si rivela utile in scenari in cui non è necessario che il flusso di lavoro sia reso persistente, ad esempio quando il flusso di lavoro usa risorse specifiche del computer come handle di file o durante le transazioni di database. In precedenza, per impedire la persistenza durante l'esecuzione di un'attività, era necessario un oggetto <xref:System.Activities.NativeActivity> personalizzato in cui veniva usato un oggetto <xref:System.Activities.NoPersistHandle>.

### <a name="BKMK_NewFlowchartCapabilities"></a>Nuove funzionalità del diagramma di flusso

I diagrammi di flusso vengono aggiornati per .NET Framework 4,5 e dispongono delle seguenti nuove funzionalità:

- La proprietà `DisplayName` di un'attività <xref:System.Activities.Statements.FlowSwitch%601> o <xref:System.Activities.Statements.FlowDecision> è modificabile. In questo modo, nell'ActivityDesigner verranno illustrate ulteriori informazioni sullo scopo dell'attività.

- I diagrammi di flusso dispongono di una nuova proprietà denominata <xref:System.Activities.Statements.Flowchart.ValidateUnconnectedNodes%2A>; l'impostazione predefinita per questa proprietà è `False`. Se questa proprietà viene impostata su `True`, i nodi dei diagrammi di flusso non connessi genereranno errori di convalida.

## <a name="support-for-partial-trust"></a>Supporto per l'attendibilità parziale

I flussi di lavoro in .NET Framework 4 richiedono un dominio applicazione completamente attendibile. In .NET Framework 4,5 i flussi di lavoro possono funzionare in un ambiente parzialmente attendibile. In un ambiente parzialmente attendibile, i componenti di terze parti possono essere usati senza concedere loro accesso completo alle risorse dell'host. Di seguito vengono riportati alcuni dei problemi che riguardano i flussi di lavoro in esecuzione con attendibilità parziale:

1. L'utilizzo dei componenti legacy (regole incluse) contenuti nell'attività di <xref:System.Activities.Statements.Interop> non è supportato con l'attendibilità parziale.

2. I flussi di lavoro in esecuzione con attendibilità parziale in <xref:System.ServiceModel.WorkflowServiceHost> non sono supportati.

3. Rendere persistenti le eccezioni in uno scenario parzialmente attendibile rappresenta una potenziale minaccia alla sicurezza. Per disabilitare la persistenza delle eccezioni, un'estensione di tipo <xref:System.Activities.ExceptionPersistenceExtension> deve essere aggiunta al progetto per rifiutare la memorizzazione delle eccezioni. Nell'esempio di codice riportato di seguito viene illustrato come implementare questo tipo.

    ```csharp
    public class ExceptionPersistenceExtension
    {
        public ExceptionPersistenceExtension()
        {
            this.PersistExceptions = false;
        }
        public bool PersistExceptions { get; set; }
    }
    ```

     Se le eccezioni non devono essere serializzate, assicurarsi che le eccezioni vengano usate all'interno di <xref:System.Activities.Statements.NoPersistScope>.

4. Gli autori di attività devono eseguire l'override <xref:System.Activities.Activity.CacheMetadata%2A> per evitare che il runtime del flusso di lavoro esegua automaticamente la reflection per questo tipo. Gli argomenti e le attività figlio devono essere non Null e <xref:System.Activities.ActivityMetadata.Bind%2A> deve essere chiamato in modo esplicito. Per altre informazioni sull'override di <xref:System.Activities.Activity.CacheMetadata%2A>, vedere [esposizione di dati con CacheMetadata](exposing-data-with-cachemetadata.md). Inoltre, è necessario creare in modo esplicito istanze di argomenti di un tipo `internal` o **privato** in <xref:System.Activities.Activity.CacheMetadata%2A> per evitare la creazione tramite reflection.

5. I tipi non utilizzeranno <xref:System.Runtime.Serialization.ISerializable> o <xref:System.SerializableAttribute> per la serializzazione; i tipi che devono essere serializzati devono supportare <xref:System.Runtime.Serialization.DataContractSerializer>.

6. Le espressioni che usano <xref:System.Activities.Expressions.LambdaValue%601> richiedono <xref:System.Security.Permissions.ReflectionPermissionAttribute.RestrictedMemberAccess%2A>e non funzioneranno con attendibilità parziale. I flussi di lavoro che usano <xref:System.Activities.Expressions.LambdaValue%601> sostituiscono le espressioni con le attività che derivano da <xref:System.Activities.CodeActivity%601>. .

7. Le espressioni non possono essere compilate usando <xref:System.Activities.XamlIntegration.TextExpressionCompiler> o il compilatore ospitato di Visual Basic in attendibilità parziale, ma le espressioni precedentemente compilate possono essere eseguite.

8. Un singolo assembly che utilizza la [trasparenza di livello 2](https://aka.ms/Level2Transparency) non può essere utilizzato in .NET Framework 4, [!INCLUDE[netfx_current_short](../../../includes/netfx-current-short-md.md)] con attendibilità totale e [!INCLUDE[netfx_current_short](../../../includes/netfx-current-short-md.md)] in attendibilità parziale.

## <a name="BKMK_NewDesignerCapabilites"></a>Nuove funzionalità di progettazione

### <a name="BKMK_DesignerSearch"></a>Ricerca nella finestra di progettazione

Per rendere più gestibili i flussi di lavoro di grandi dimensioni, è ora possibile effettuarvi ricerche in base a parole chiave. Questa funzionalità è disponibile solo in Visual Studio. Questa funzionalità non è disponibile in una finestra di progettazione ospitata nuovamente. Sono disponibili due tipi di ricerche:

- Ricerca veloce, avviata con **CTRL + F** o **modifica**, **trova e Sostituisci**, **ricerca veloce**.

- Cerca nei file, avviata con **CTRL + MAIUSC + F** o **modifica**, **trova e Sostituisci**, **Cerca nei file**.

Si noti che la sostituzione non è supportata.

#### <a name="BKMK_QuickFind"></a>Ricerca veloce

Le parole chiave ricercate nei flussi di lavoro corrisponderanno agli elementi delle finestre di progettazione seguenti:

- Proprietà degli oggetti <xref:System.Activities.Activity>, <xref:System.Activities.Statements.FlowNode>, <xref:System.Activities.Statements.State> e <xref:System.Activities.Statements.Transition>, nonché altri elementi di controllo del flusso personalizzati.

- Variabili

- Argomenti

- Espressioni

La ricerca veloce viene effettuata nell'albero <xref:System.Activities.Presentation.Model.ModelItem> della finestra di progettazione. Con la ricerca veloce non verranno individuati gli spazi dei nomi importati nella definizione del flusso di lavoro.

#### <a name="BKMK_FindInFiles"></a>Cerca nei file

Le parole chiave ricercate nei flussi di lavoro corrisponderanno al contenuto effettivo dei file del flusso di lavoro. I risultati della ricerca verranno mostrati nel riquadro di visualizzazione Risultati ricerca di Visual Studio. Facendo doppio clic sull'elemento del risultato verrà visualizzata l'attività contenente la corrispondenza nella finestra di progettazione del flusso di lavoro.

### <a name="BKMK_VariableDeleteContextMenu"></a>Voce di menu di scelta rapida Elimina in variabile e progettazione argomenti

In .NET Framework 4, le variabili e gli argomenti potevano essere eliminati solo nella finestra di progettazione tramite la tastiera. A partire da .NET Framework 4,5, le variabili e gli argomenti possono essere eliminati usando il menu di scelta rapida.

Nella schermata seguente è illustrato il menu di scelta rapida della finestra di progettazione delle variabili e degli argomenti.

![Menu di scelta rapida della finestra di progettazione argomenti e variabili](./media/whats-new-in-wf-in-dotnet/designer-context-menu.png)

### <a name="BKMK_AutoSurround"></a>Racchiudi automaticamente con sequenza

Poiché un flusso di lavoro o determinate attività contenitore (ad esempio <xref:System.Activities.Statements.NoPersistScope>) potevano contenere solo un'unica attività Body, l'aggiunta di una seconda attività richiedeva allo sviluppatore di eliminare la prima attività, di aggiungere un'attività <xref:System.Activities.Statements.Sequence> e, successivamente, di aggiungere entrambe le attività all'attività Sequence. A partire da .NET Framework 4,5, quando si aggiunge una seconda attività all'area di progettazione, viene creata automaticamente un'attività `Sequence` per eseguire il wrapping di entrambe le attività.

La schermata riportata di seguito mostra un'attività di `WriteLine` in `Body` di `NoPersistScope`.

![Attività WriteLine nel corpo di un'attività NoPersistScope.](./media/whats-new-in-wf-in-dotnet/auto-surround-write-line-activity.png)

La schermata riportata di seguito mostra l'attività automaticamente creata di `Sequence` in `Body` quando un secondo `WriteLine` viene rilasciato sotto il primo.

![Sequenza creata automaticamente nel corpo di un NoPersistScope.](./media/whats-new-in-wf-in-dotnet/auto-surround-sequence-activity.png)

### <a name="BKMK_PanMode"></a>Modalità panoramica

Per spostarsi più facilmente in un flusso di lavoro di grandi dimensioni nella finestra di progettazione è possibile abilitare la modalità dettaglio, consentendo allo sviluppatore di selezionare e trascinare la parte visibile del flusso di lavoro, anziché dover usare le barre di scorrimento. Il pulsante per attivare la modalità dettaglio si trova nell'angolo inferiore destro della finestra di progettazione.

Nella schermata seguente viene illustrato il pulsante della modalità dettaglio posizionato nell'angolo inferiore destro della finestra di progettazione del flusso di lavoro.

![Pulsante di panoramica evidenziato nella finestra di progettazione del flusso di lavoro.](./media/whats-new-in-wf-in-dotnet/pan-button-workflow-designer.png)

Per ottenere il dettaglio della finestra di progettazione del flusso di lavoro è anche possibile usare il pulsante centrale del mouse o la barra spaziatrice.

### <a name="BKMK_MultiSelect"></a>Selezione multifunzione

È possibile selezionare più attività alla volta trascinando un rettangolo attorno a esse (quando la modalità dettaglio non è abilitata) o tenendo premuto CTRL e facendo clic sulle attività desiderate una alla volta.

Le selezioni di più attività possono anche essere trascinate e rilasciate all'interno della finestra di progettazione, nonché usate con il menu di scelta rapida.

### <a name="BKMK_DocumentOutline"></a>visualizzazione Struttura di elementi del flusso di lavoro

Per consentire uno spostamento più semplice nei flussi di lavoro gerarchici, i componenti di un flusso di lavoro vengono visualizzati in una visualizzazione ad albero. La visualizzazione struttura viene visualizzata nella visualizzazione **struttura documento** . Per aprire questa visualizzazione, nel menu in alto selezionare **Visualizza**, **altre finestre**, **struttura documento**o premere CTRL W, U. Facendo clic su un nodo nella visualizzazione Struttura verrà visualizzata l'attività corrispondente nella finestra di progettazione del flusso di lavoro e la visualizzazione Struttura verrà aggiornata in modo da mostrare le attività selezionate nella finestra di progettazione.

Lo screenshot seguente del flusso di lavoro completato dall' [esercitazione Introduzione](getting-started-tutorial.md) illustra la visualizzazione struttura con un flusso di lavoro sequenziale.

![Screenshot della visualizzazione struttura con un flusso di lavoro sequenziale in Visual Studio.](./media/whats-new-in-wf-in-dotnet/outline-view-in-workflow-designer.jpg)

### <a name="BKMK_CSharpExpressions"></a>C# Espressioni di

Prima di .NET Framework 4,5, tutte le espressioni nei flussi di lavoro potevano essere scritte solo in Visual Basic. In .NET Framework 4,5, le espressioni Visual Basic vengono utilizzate solo per i progetti creati utilizzando Visual Basic. Nei progetti Visual C# viene ora usato C# per le espressioni. È ora disponibile un editor espressioni C# completamente funzionale con funzionalità quali l'evidenziazione della grammatica e Intellisense. I progetti di flussi di lavoro C# creati in versioni precedenti che utilizzavano espressioni di Visual Basic continueranno a funzionare.

Le espressioni C# vengono convalidate in fase di progettazione. Gli errori nelle espressioni C# verranno contrassegnati con una sottolineatura ondulata rossa.

Per ulteriori informazioni sulle C# espressioni, vedere [ C# espressioni](csharp-expressions.md).

### <a name="BKMK_Visibility"></a>Maggiore controllo della visibilità della barra della shell e degli elementi di intestazione

In una finestra di progettazione ospitata nuovamente, alcuni dei controlli dell'interfaccia utente standard possono non essere appropriati per un determinato flusso di lavoro e, pertanto, è possibile disattivarli. In .NET Framework 4 questa personalizzazione è supportata solo dalla barra della shell nella parte inferiore della finestra di progettazione. In .NET Framework 4,5, la visibilità degli elementi dell'intestazione della shell nella parte superiore della finestra di progettazione può essere regolata impostando <xref:System.Activities.Presentation.View.DesignerView.WorkflowShellHeaderItemsVisibility%2A> con il valore <xref:System.Activities.Presentation.View.ShellHeaderItemsVisibility> appropriato.

### <a name="BKMK_AutoConnect"></a>Connessione automatica e inserimento automatico nei flussi di lavoro del diagramma di flusso e della macchina a Stati

In .NET Framework 4, è necessario aggiungere manualmente le connessioni tra i nodi di un flusso di lavoro del diagramma di flusso. In .NET Framework 4,5, i nodi del diagramma di flusso e della macchina a Stati hanno punti di connessione automatica che diventano visibili quando un'attività viene trascinata dalla casella degli strumenti nell'area di progettazione. Rilasciando un'attività in uno di questi punti, viene automaticamente aggiunta insieme alla connessione necessaria.

Nella schermata seguente vengono illustrati i punti di associazione che diventano visibili quando un'attività viene trascinata dalla casella degli strumenti.

![Nodo di inizio diagramma di flusso che mostra i punti di connessione automatica](./media/whats-new-in-wf-in-dotnet/auto-connect-points-start-node.png)

Le attività possono anche essere trascinate nelle connessioni tra i nodi e gli stati del diagramma di flusso per inserire automaticamente un nodo tra altri due. Nella schermata seguente viene illustrata la linea di connessione evidenziata in cui è possibile trascinare e rilasciare le attività dalla casella degli strumenti.

![Handle di inserimento automatico per il trascinamento delle attività](./media/whats-new-in-wf-in-dotnet/auto-insert-connecting-line.png)

### <a name="BKMK_Annotations"></a>Annotazioni della finestra di progettazione

Per semplificare lo sviluppo di flussi di lavoro di grandi dimensioni, la finestra di progettazione supporta ora l'aggiunta di annotazioni per consentire di tenere traccia del processo di progettazione. Le annotazioni possono essere aggiunte ad attività, stati, nodi del diagramma di flusso, variabili e argomenti. Nella schermata seguente è illustrato il menu di scelta rapida usato per aggiungere annotazioni alla finestra di progettazione.

![Screenshot che mostra un menu per aggiungere annotazioni.](./media/whats-new-in-wf-in-dotnet/designer-annotations-context-menu.png)

### <a name="debugging-states"></a>Stati di debug

In .NET Framework 4 gli elementi non di attività non potevano supportare i punti di interruzione del debug poiché non erano unità di esecuzione. Questa versione fornisce un meccanismo per aggiungere punti di interruzione agli oggetti <xref:System.Activities.Statements.State>. Se un punto di interruzione è impostato su un oggetto <xref:System.Activities.Statements.State>, l'esecuzione verrà interrotta quando viene eseguita la transizione dello stato, prima della pianificazione delle attività o dei trigger di inserimento.

### <a name="BKMK_ActivityDelegates"></a>Definire e utilizzare oggetti ActivityDelegate nella finestra di progettazione

Le attività in .NET Framework 4 usavano <xref:System.Activities.ActivityDelegate> oggetti per esporre i punti di esecuzione in cui altre parti del flusso di lavoro possono interagire con l'esecuzione di un flusso di lavoro, ma l'uso di questi punti di esecuzione richiede in genere una quantità di codice corretta. In questa versione gli sviluppatori possono definire e usare delegati di attività tramite la finestra di progettazione del flusso di lavoro. Per ulteriori informazioni, vedere [procedura: definire e utilizzare delegati di attività nell'progettazione flussi di lavoro](/visualstudio/workflow-designer/how-to-define-and-consume-activity-delegates-in-the-workflow-designer).

### <a name="BKMK_BuildTimeValidation"></a>Convalida della fase di compilazione

In .NET Framework 4 gli errori di convalida del flusso di lavoro non sono stati conteggiati come errori di compilazione durante la compilazione di un progetto flusso di lavoro. In questo modo, la compilazione di un progetto di flusso di lavoro poteva essere completata correttamente anche in presenza di errori di convalida del flusso di lavoro. In .NET Framework 4,5, gli errori di convalida del flusso di lavoro provocano un errore di compilazione.

### <a name="BKMK_DesignTimeValidation"></a>Convalida in background in fase di progettazione

In .NET Framework 4 i flussi di lavoro sono stati convalidati come processo in primo piano, che potrebbe potenzialmente bloccare l'interfaccia utente durante i processi di convalida complessi o che richiedono molto tempo. La convalida del flusso di lavoro viene ora effettuata in un thread in background, pertanto l'interfaccia utente non viene bloccata.

### <a name="BKMK_ViewState"></a>Stato di visualizzazione che si trova in una posizione separata nei file XAML

In .NET Framework 4, le informazioni sullo stato di visualizzazione per un flusso di lavoro vengono archiviate nel file XAML in molte posizioni diverse. Questa condizione è poco pratica per gli sviluppatori che desiderano leggere direttamente i file XAML o scrivere codice per rimuovere le informazioni sullo stato di visualizzazione. In .NET Framework 4,5, le informazioni sullo stato di visualizzazione nel file XAML vengono serializzate come elemento separato nel file XAML. Gli sviluppatori possono individuare e modificare facilmente le informazioni sullo stato di visualizzazione di un'attività oppure rimuovere completamente lo stato di visualizzazione.

### <a name="BKMK_ExpressionExtensibility"></a>Estendibilità delle espressioni

In .NET Framework 4,5, viene fornito agli sviluppatori un modo per creare un'esperienza di creazione di espressioni ed espressioni che può essere inserita nella finestra di progettazione del flusso di lavoro.

### <a name="BKMK_BackwardCompatRehostedDesigner"></a>Consenso esplicito per le funzionalità del flusso di lavoro 4,5 nella finestra di progettazione ospitata nuovamente

Per mantenere la compatibilità con le versioni precedenti, alcune nuove funzionalità incluse in .NET Framework 4,5 non sono abilitate per impostazione predefinita nella finestra di progettazione ospitata nuovamente. In questo modo si garantisce che le applicazioni esistenti in cui viene usata la finestra di progettazione ospitata nuovamente non vengano interrotte in caso di aggiornamento alla versione più recente. Per abilitare le nuove funzionalità nella finestra di progettazione ospitata nuovamente, impostare la proprietà <xref:System.Activities.Presentation.DesignerConfigurationService.TargetFrameworkName%2A> su ".NET Framework 4.5" oppure impostare singoli membri dell'oggetto <xref:System.Activities.Presentation.DesignerConfigurationService> per abilitare singole funzionalità.

## <a name="BKMK_NewWFModels"></a>Nuovi modelli di sviluppo del flusso di lavoro

Oltre ai modelli di sviluppo dei flussi di lavoro del diagramma di flusso e sequenziale, in questa versione sono inclusi i flussi di lavoro macchina a stati e i servizi dei flussi di lavoro con priorità al contratto ("contract-first").

### <a name="BKMK_StateMachine"></a>Flussi di lavoro macchina a Stati

I flussi di lavoro della macchina a Stati sono stati introdotti come parte del .NET Framework 4, versione 4.0.1 in [Microsoft .NET Framework 4 Platform Update 1](https://blogs.msdn.microsoft.com/endpoint/2011/04/18/microsoft-net-framework-4-platform-update-1/). In questo aggiornamento sono incluse numerose nuove classi e attività che hanno consentito agli sviluppatori di creare i flussi di lavoro macchina a stati. Queste classi e attività sono state aggiornate per .NET Framework 4,5. Gli aggiornamenti includono:

1. Possibilità di impostare punti di interruzione negli stati

2. Possibilità di copiare e incollare transizioni nella finestra di progettazione del flusso di lavoro

3. Supporto della finestra di progettazione per la creazione di transizioni con trigger condivisi

4. Attività usate per creare i flussi di lavoro macchina a stati, incluse <xref:System.Activities.Statements.StateMachine>, <xref:System.Activities.Statements.State> e <xref:System.Activities.Statements.Transition>

Lo screenshot seguente illustra il flusso di lavoro della macchina a stati completato dal passaggio [Introduzione esercitazione](getting-started-tutorial.md) [procedura: creare un flusso di lavoro della macchina a stati](how-to-create-a-state-machine-workflow.md).

![Illustrazione che mostra il flusso di lavoro della macchina a stati completato.](./media/whats-new-in-wf-in-dotnet/complete-state-machine-workflow.jpg)

Per ulteriori informazioni sulla creazione di flussi di lavoro macchina a Stati, vedere [flussi di lavoro macchina a stati](state-machine-workflows.md).

### <a name="BKMK_ContractFirst"></a>Sviluppo di flussi di lavoro per primo contratto

Lo strumento di sviluppo del flusso di lavoro contratto-primo consente allo sviluppatore di progettare un contratto in Code First, quindi, con pochi clic in Visual Studio, generare automaticamente un modello di attività nella casella degli strumenti che rappresenta ciascuna operazione. Queste attività vengono quindi usate per creare un flusso di lavoro che implementa le operazioni definite dal contratto. La finestra di progettazione del flusso di lavoro convaliderà il servizio di quest'ultimo per garantire che queste operazioni vengano implementate e che la firma del flusso di lavoro corrisponda a quella del contratto. Lo sviluppatore può inoltre associare un servizio del flusso di lavoro a una raccolta di contratti implementati. Per ulteriori informazioni sullo sviluppo di servizi del flusso di lavoro Contract-First, vedere [procedura: creare un servizio flusso di lavoro che utilizza un contratto di servizio esistente](how-to-create-a-workflow-service-that-consumes-an-existing-service-contract.md).
