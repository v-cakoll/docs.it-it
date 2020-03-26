---
title: Processo di assunzione
ms.date: 03/30/2017
ms.assetid: d5fcacbb-c884-4b37-a5d6-02b1b8eec7b4
ms.openlocfilehash: ade72422d29d170e9c80f602f151ce765a1a00f7
ms.sourcegitcommit: e48a54ebe62e874500a7043f6ee0b77a744d55b4
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 03/26/2020
ms.locfileid: "80291691"
---
# <a name="hiring-process"></a>Processo di assunzione
In questo esempio viene illustrato come implementare un processo aziendale tramite attività di messaggistica e due flussi di lavoro ospitati come servizi flusso di lavoro e appartenenti all'infrastruttura IT di una società fittizia denominata Contoso, Inc.  
  
 Il processo del flusso di lavoro `HiringRequest`, implementato come un oggetto <xref:System.Activities.Statements.Flowchart>, chiede l'autorizzazione a diversi responsabili nell'organizzazione. Per raggiungere questo obiettivo, il flusso di lavoro utilizza altri servizi esistenti nell'organizzazione (nel nostro caso, un servizio di posta in arrivo e un servizio dati dell'organizzazione implementato come servizi Windows Communication Foundation (WCF) semplici).  
  
 Il flusso di lavoro `ResumeRequest`, implementato come un oggetto <xref:System.Activities.Statements.Sequence>, pubblica un elenco di offerte di lavoro nel sito Web esterno delle carriere di Contoso e gestisce l'acquisizione dei curriculum. Tale elenco è disponibile nel sito Web esterno per un periodo fisso di tempo, ovvero fino alla scadenza di un timeout, o fino a quando un dipendente di Contoso non decide di rimuoverlo.  
  
 In questo esempio vengono illustrate le funzionalità [!INCLUDE[netfx_current_long](../../../../includes/netfx-current-long-md.md)] seguenti:  
  
- Flussi di lavoro <xref:System.Activities.Statements.Flowchart> e <xref:System.Activities.Statements.Sequence> per modellare processi aziendali  
  
- Servizi flusso di lavoro  
  
- Attività di messaggistica  
  
- Correlazione basata sul contenuto  
  
- Attività personalizzate (dichiarative e basate sul codice)  
  
- Persistenza di SQL Server fornita dal sistema  
  
- Oggetto <xref:System.Activities.Persistence.PersistenceParticipant> personalizzato  
  
- Rilevamento personalizzato  
  
- Rilevamento ETW (Event Tracking for Windows)  
  
- Composizione di attività  
  
- Attività <xref:System.Activities.Statements.Parallel>  
  
- Attività <xref:System.Activities.Statements.CancellationScope>  
  
- Timer durevoli (attività <xref:System.Activities.Statements.Delay>)  
  
- Transazioni  
  
- Uso di più di un flusso di lavoro nella stessa soluzione  
  
> [!IMPORTANT]
> È possibile che gli esempi siano già installati nel computer. Verificare la directory seguente (impostazione predefinita) prima di continuare.  
>
> `<InstallDrive>:\WF_WCF_Samples`  
>
> Se questa directory non esiste, passare a [Windows Communication Foundation (WCF) e Windows Workflow Foundation (WF) Esempi per .NET Framework 4](https://www.microsoft.com/download/details.aspx?id=21459) per scaricare tutti gli esempi e [!INCLUDE[wf1](../../../../includes/wf1-md.md)] Windows Communication Foundation (WCF). Questo esempio si trova nella directory seguente.  
>
> `<InstallDrive>:\WF_WCF_Samples\WF\Application\HiringProcess`  
  
## <a name="description-of-the-process"></a>Descrizione del processo  
 Contoso, Inc. desidera avere stretto controllo sul personale presente in ciascun reparto. Di conseguenza, tutte le volte che un dipendente desidera avviare un nuovo processo di assunzione deve passare attraverso un'approvazione del processo di richiesta di assunzione prima che la selezione possa effettivamente avere luogo. Tale processo è denominato richiesta del processo di assunzione (definito nel progetto HiringRequestService) ed è costituito dai passaggi seguenti.  
  
1. Un dipendente (il richiedente) avvia la richiesta del processo di assunzione.  
  
2. Il responsabile del richiedente deve approvare la richiesta:  
  
    1. Il responsabile può rifiutare la richiesta.  
  
    2. Il responsabile può restituire la richiesta al richiedente per ottenere informazioni aggiuntive.  
  
        1. Il richiedente rivede la richiesta e la invia nuovamente al responsabile.  
  
    3. Il responsabile può approvare la richiesta.  
  
3. Dopo l'approvazione del responsabile del richiedente, il proprietario del reparto deve approvare la richiesta:  
  
    1. Il responsabile del reparto può rifiutare la richiesta.  
  
    2. Il responsabile del reparto può approvare la richiesta.  
  
4. Dopo che il responsabile del reparto ha concesso l'approvazione, è necessaria l'approvazione di 2 responsabili delle risorse umane o del CEO.  
  
    1. Il processo può passare allo stato accettato o rifiutato.  
  
    2. Se il processo viene accettato, verrà avviata una nuova istanza del flusso di lavoro `ResumeRequest` (`ResumeRequest` è collegato a HiringRequest.csproj tramite un riferimento al servizio.)  
  
 Dopo che i responsabili hanno approvato l'assunzione di un nuovo dipendente, il reparto risorse umane deve individuare il candidato adatto. Questo processo viene eseguito dal secondo flusso di lavoro (`ResumeRequest`, definito in ResumeRequestService.csproj). Tale flusso di lavoro definisce il processo per l'invio di un elenco di offerte di lavoro con un'opportunità di carriera al sito Web esterno delle carriere di Contoso, riceve i curriculum dei candidati ed esamina lo stato dell'elenco. Le posizioni sono disponibili per un periodo fisso di tempo, ovvero fino a una scadenza predeterminata, o fino a quando un dipendente di Contoso non decide di rimuoverle. Il flusso di lavoro `ResumeRequest` è costituito dai passaggi seguenti.  
  
1. Un dipendente di Contoso inserisce le informazioni sulla posizione e una durata del timeout. Dopo che il dipendente ha inserito tali informazioni, la posizione viene pubblicata nel sito Web delle carriere.  
  
2. Dopo la pubblicazione delle informazioni, le parti interessate possono inviare il curriculum che viene archiviato in un record collegato all'apertura della pratica.  
  
3. I candidati possono inviare il proprio curriculum fino alla scadenza del timeout o fino a quando un appartenente al reparto risorse umane di Contoso non decide in modo esplicito di rimuovere l'elenco arrestando il processo.  
  
## <a name="projects-in-the-sample"></a>Progetti presenti nell'esempio  
 Nella tabella seguente vengono illustrati i progetti presenti nella soluzione di esempio.  
  
|Project|Descrizione|  
|-------------|-----------------|  
|ContosoHR|Contiene contratti dati, oggetti business e classi di repository.|  
|HiringRequestService|Contiene la definizione del flusso di lavoro relativo al processo di richiesta di assunzione.<br /><br /> Il progetto viene implementato come un'applicazione console che ospita in modalità self-hosting il flusso di lavoro (file con estensione xaml) come un servizio.|  
|ResumeRequestService|Servizio flusso di lavoro che raccoglie i curriculum dei candidati fino alla scadenza di un timeout o fino a quando qualcuno non decide che il processo deve essere arrestato.<br /><br /> Il progetto viene implementato come un servizio flusso di lavoro dichiarativo (file con estensione xamlx).|  
|OrgService|Servizio che espone informazioni organizzative (dipendenti, posizioni, tipi di posizioni e reparti). Questo servizio può essere paragonato al modulo di organizzazione dell'azienda di una pianificazione ERP (Enterprise Resource Plan).<br /><br /> Questo progetto viene implementato come un'applicazione console che espone un servizio Windows Communication Foundation (WCF).|  
|InboxService|Casella di posta in arrivo che contiene attività in base alle quali i dipendenti intraprendono un'azione.<br /><br /> Il progetto viene implementato come un'applicazione console che espone un servizio WCF.|  
|InternalClient|Applicazione Web per l'interazione con il processo. Gli utenti possono avviare e visualizzare i propri flussi di lavoro HiringProcess nonché parteciparvi. Grazie a questa applicazione, possono inoltre avviare e monitorare i processi ResumeRequest.<br /><br /> Questo sito viene implementato in modo che sia interno alla rete Intranet di Contoso, mentre il progetto viene implementato come un sito Web ASP.NET.|  
|CareersWebSite|Sito Web esterno che espone le posizioni aperte in Contoso. Qualsiasi candidato potenziale può spostarsi in questo sito e inviare un curriculum.|  
  
## <a name="feature-summary"></a>Riepilogo delle funzionalità  
 Nella tabella seguente vengono descritte le modalità di utilizzo di ogni funzionalità nell'esempio.  
  
|Funzionalità|Descrizione|Project|  
|-------------|-----------------|-------------|  
|Diagramma di flusso|Il processo aziendale viene rappresentato come un diagramma di flusso la cui descrizione rappresenta il processo in modo analogo a quello in cui un'azienda l'avrebbe riportato su una lavagna.|HiringRequestService|  
|Servizi flusso di lavoro|Il diagramma di flusso con la definizione del processo è ospitato in un servizio (in questo esempio il servizio è ospitato in un'applicazione console).|HiringRequestService|  
|Attività di messaggistica|Il diagramma di flusso usa le attività di messaggistica per gli scopi seguenti:<br /><br /> - Per ottenere informazioni dall'utente (per ricevere le decisioni e le informazioni correlate in ogni fase di approvazione).<br />- Per interagire con altri servizi esistenti (InboxService e OrgDataService, utilizzati tramite riferimenti al servizio).|HiringRequestService|  
|Correlazione basata sul contenuto|I messaggi di approvazione sono correlati alla proprietà ID della richiesta di assunzione:<br /><br /> - Quando viene avviato un processo, l'handle di correlazione viene inizializzato con l'ID della richiesta.<br />- I messaggi di approvazione in arrivo sono correlati al loro ID (il primo parametro di ogni messaggio di approvazione è l'ID della richiesta).|HiringRequestService / ResumeRequestService|  
|Attività personalizzate (dichiarative e basate sul codice)|Nell'esempio sono presenti diverse attività personalizzate:<br /><br /> -   `SaveActionTracking`: questa attività genera <xref:System.Activities.Tracking.TrackingRecord> un'operazione personalizzata (utilizzando <xref:System.Activities.NativeActivityContext.Track%2A>). L'attività è stata creata usando codice imperativo che estende <xref:System.Activities.NativeActivity>.<br />-   `GetEmployeesByPositionTypes`: questa attività riceve un elenco di ID di tipo di posizione e restituisce un elenco di persone che hanno tale posizione in Contoso. L'attività è stata creata in modo dichiarativo (usando la finestra di progettazione delle attività).<br />-   `SaveHiringRequestInfo`: questa attività salva le `HiringRequest` informazioni `HiringRequestRepository.Save`di un (using ). L'attività è stata creata usando codice imperativo che estende <xref:System.Activities.CodeActivity>.|HiringRequestService|  
|Persistenza di SQL Server fornita dal sistema|L'istanza di <xref:System.ServiceModel.Activities.WorkflowServiceHost> che ospita la definizione del processo del diagramma di flusso è configurata per usare la persistenza di SQL Server fornita dal sistema.|HiringRequestService / ResumeRequestService|  
|Rilevamento personalizzato|Nell'esempio è incluso un partecipante del rilevamento personalizzato che salva la cronologia di un processo `HiringRequestProcess` (quest'ultimo registra l'azione eseguita nonché l'autore e il momento dell'esecuzione). Il codice sorgente si trova nella cartella Tracking di HiringRequestService.|HiringRequestService|  
|Rilevamento ETW|Il rilevamento ETW fornito dal sistema viene configurato nel file App.config nel servizio HiringRequestService.|HiringRequestService|  
|Composizione di attività|La definizione del processo usa la composizione libera di <xref:System.Activities.Activity>. Il diagramma di flusso contiene diverse attività Sequence e Parallel che a loro volta ne contengono altre e così via.|HiringRequestService|  
|Attività parallele|-   <xref:System.Activities.Statements.ParallelForEach%601>viene utilizzato per registrarsi nella Posta in arrivo del CEO e dei responsabili delle risorse umane in parallelo (in attesa del passaggio di approvazione di due responsabili delle risorse umane).<br />-   <xref:System.Activities.Statements.Parallel>viene utilizzato per eseguire alcune attività di pulizia nei passaggi Completato e Rifiutato|HiringRequestService|  
|Annullamento del modello|Nel diagramma di flusso viene usato <xref:System.Activities.Statements.CancellationScope> per applicare l'annullamento (in questo caso eseguendo attività di pulizia).|HiringRequestService|  
|Partecipante di persistenza personalizzato|`HiringRequestPersistenceParticipant` salva i dati da una variabile del flusso di lavoro in una tabella archiviata nel database delle risorse umane di Contoso.|HiringRequestService|  
|Servizi flusso di lavoro|`ResumeRequestService` viene implementato usando servizi flusso di lavoro. La definizione del flusso di lavoro e le informazioni sul servizio sono contenute in ResumeRequestService.xamlx.Workflow definition and service information are contained in ResumeRequestService.xamlx. Il servizio è configurato per usare la persistenza e il rilevamento.|ResumeRequestService|  
|Timer durevoli|In `ResumeRequestService` vengono usati timer durevoli per definire la durata di un elenco di offerte di lavoro (quando un timeout scade, le offerte vengono chiuse).|ResumeRequestService|  
|Transazioni|<xref:System.Activities.Statements.TransactionScope> viene usato per garantire la coerenza dei dati durante l'esecuzione di diverse attività (quando viene ricevuto un nuovo curriculum).|ResumeRequestService|  
|Transazioni|Il partecipante di persistenza (`HiringRequestPersistenceParticipant`) e il partecipante del rilevamento personalizzati (`HistoryFileTrackingParticipant`) usano la stessa transazione.|HiringRequestService|  
|Utilizzo [!INCLUDE[wf1](../../../../includes/wf1-md.md)] in ASP.NET applicazioni.|I flussi di lavoro sono accessibili da due applicazioni ASP.NET.|InternalClient / CareersWebSite|  
  
## <a name="data-storage"></a>Archiviazione dati  
 I dati vengono archiviati in un database di SQL Server denominato `ContosoHR` (lo script per la creazione di questo database si trova nella cartella `DbSetup`), mentre le istanze di flusso di lavoro vengono archiviate in un database di SQL Server denominato `InstanceStore` (gli script per la creazione per l'archivio di istanze sono parte della distribuzione di [!INCLUDE[netfx_current_short](../../../../includes/netfx-current-short-md.md)]).  
  
 Entrambi i database vengono creati eseguendo lo script Setup.cmd da un prompt dei comandi per sviluppatori per Visual Studio.  
  
## <a name="running-the-sample"></a>Esecuzione dell'esempio  
  
#### <a name="to-create-the-databases"></a>Per creare i database  
  
1. Aprire un prompt dei comandi per sviluppatori per Visual Studio.Open a Developer Command Prompt for Visual Studio.  
  
2. Passare alla cartella dell'esempio.  
  
3. Eseguire Setup.cmd.  
  
4. Verificare che i due database `ContosoHR` e `InstanceStore` siano creati in SQL Express.  
  
#### <a name="to-set-up-the-solution-for-execution"></a>Per configurare la soluzione per l'esecuzione  
  
1. Eseguire Visual Studio come amministratore. Aprire HiringRequest.sln.  
  
2. Fare clic con il pulsante destro del mouse sulla soluzione in **Esplora soluzioni** e scegliere **Proprietà**.  
  
3. Selezionare l'opzione Progetti di **avvio multipli** e impostare **CareersWebSite**, **InternalClient**, **HiringRequestService**e **ResumeRequestService** su **Start**. Lasciare **ContosoHR**, **InboxService**e **OrgService** come Nessuno.  
  
4. Premere CTRL+MAIUSC+B per compilare la soluzione, quindi verificare che la compilazione sia stata eseguita in modo corretto.  
  
#### <a name="to-run-the-solution"></a>Per eseguire la soluzione  
  
1. Dopo che la soluzione è stata compilata, premere CTRL+F5 per eseguirla senza debug. Verificare che tutti i servizi siano stati avviati.  
  
2. Fare clic con il pulsante destro del mouse su **InternalClient** nella soluzione, quindi **scegliere Visualizza nel browser**. Verrà visualizzata la pagina predefinita per `InternalClient`. Verificare che i servizi siano in esecuzione, quindi fare clic sul collegamento.  
  
3. Viene visualizzato il modulo **HiringRequest.** È possibile seguire lo scenario descritto in questo punto.  
  
4. Una volta che `HiringRequest` è completo, è possibile avviare `ResumeRequest`. È possibile seguire lo scenario descritto in questo punto.  
  
5. Quando `ResumeRequest` viene pubblicato, sarà disponibile nel sito Web pubblico (sito Web delle carriere di Contoso). Per visualizzare l'elenco delle offerte di lavoro e candidarsi per la posizione, spostarsi su tale sito.  
  
6. Fare clic con il pulsante destro del mouse su **CareersWebSite** nella soluzione e scegliere **Visualizza nel browser**.  
  
7. Tornare alla `InternalClient` finestra di dialogo facendo clic con il pulsante destro del mouse su **InternalClient** nella soluzione e scegliendo **Visualizza nel browser**.  
  
8. Passare alla sezione **JobPostings** facendo clic sul collegamento **Job Postings** nel menu in arrivo. È possibile seguire lo scenario descritto in questo punto.  
  
## <a name="scenarios"></a>Scenari  
  
### <a name="hiring-request"></a>Richiesta di assunzione  
  
1. Michael Alexander (programmatore) desidera richiedere una nuova posizione per assumere un esperto in testing (SDET) nel reparto tecnico con almeno tre anni di esperienza nel linguaggio di programmazione C#.  
  
2. Dopo la creazione, la richiesta viene visualizzata nella posta in arrivo di Michael (fare clic su **Aggiorna** se non viene visualizzata la richiesta) in attesa dell'approvazione di Peter Brehm, che è il manager di Michael.  
  
3. Peter vuole agire su richiesta di Michael. poiché ritiene che la posizione richieda 5 anni di esperienza nel linguaggio C# anziché 3 e pertanto invia i propri commenti per la revisione.  
  
4. Michael vede un messaggio nella sua casella di posta dal suo manager e vuole agire. Michael vede la storia della richiesta di posizione e concorda con Peter. Michael modifica pertanto la descrizione per richiedere 5 anni di esperienza nel linguaggio C# e accetta la modifica.  
  
5. Peter agisce su richiesta modificata di Michael e la accetta. A questo punto la richiesta deve essere approvata dal direttore del reparto tecnico, Tsvi Reiter.  
  
6. Tsvi Reiter desidera accelerare la richiesta, pertanto inserisce un commento per indicare che la richiesta è urgente e l'accetta.  
  
7. La richiesta deve ora essere approvata da due responsabili delle risorse umane o dal CEO. Quest'ultimo, Brian Richard Goldstein, vede la richiesta urgente di Tsvi e interviene accettandola, precedendo l'approvazione dei due responsabili delle risorse umane.  
  
8. La richiesta viene rimossa dalla posta in arrivo di Michael e il processo di assunzione di un SDET è ora iniziato.  
  
### <a name="start-resume-request"></a>Avviare la richiesta di curriculum  
  
1. A questo punto, la posizione di lavoro è in attesa di essere pubblicata in un sito Web esterno in cui gli utenti possono fare domanda (è possibile visualizzarla facendo clic sul collegamento **Registrazioni processi).** Attualmente, la posizione lavorativa deve essere completata da un addetto delle risorse umane responsabile della finalizzazione e della pubblicazione della posizione.  
  
2. HR desidera modificare questa posizione lavorativa (facendo clic sul collegamento **Modifica)** impostando un timeout di 60 minuti (nella vita reale, potrebbero essere giorni o settimane). Il timeout consente che la posizione lavorativa venga eliminata dal sito Web esterno dopo il tempo specificato.  
  
3. Dopo aver salvato la posizione lavorativa modificata, questa viene visualizzata nella scheda **Ricezione curriculum** (aggiornare la pagina Web per visualizzare la nuova posizione lavorativa).  
  
### <a name="collecting-resumes"></a>Raccolta di curriculum  
  
1. La posizione lavorativa dovrebbe essere visualizzata sul sito Web esterno. Una persona interessata può pertanto candidarsi per la posizione e inviare il proprio curriculum.  
  
2. Se si torna al servizio Job Postings List, è possibile "visualizzare i curriculum" che sono stati raccolti finora.  
  
3. Il reparto risorse umane può decidere di interrompere la raccolta, ad esempio se il candidato appropriato è stato identificato.  
  
## <a name="troubleshooting"></a>Risoluzione dei problemi  
  
1. Assicurarsi di eseguire Visual Studio con privilegi di amministratore.  
  
2. Se non è possibile compilare la soluzione, verificare l'elemento seguente:  
  
    - Il riferimento `ContosoHR` a non `InternalClient` è `CareersWebSite` presente nei progetti o .  
  
3. Se non è possibile eseguire la soluzione, verificare gli elementi seguenti:  
  
    1. Tutti i servizi sono in esecuzione.  
  
    2. I riferimenti al servizio sono aggiornati.  
  
        1. Aprire la cartella App_WebReferences.  
  
        2. Fare clic con il pulsante destro del mouse su **Contoso** e **scegliere Aggiorna riferimenti Web/servizi**.  
  
        3. Ricompilare la soluzione premendo CTRL -MAIUSC-B in Visual Studio.  
  
## <a name="uninstalling"></a>Disinstallazione  
  
1. Eliminare l'archivio dell'istanza di SQL Server eseguendo Cleanup.bat, disponibile nella cartella DbSetup.  
  
2. Eliminare il codice sorgente dal disco rigido.
