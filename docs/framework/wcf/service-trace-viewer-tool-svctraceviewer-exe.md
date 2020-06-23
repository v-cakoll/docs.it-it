---
title: Strumento Visualizzatore di tracce dei servizi (SvcTraceViewer.exe)
description: Utilizzare Visualizzatore di tracce dei servizi per unire, visualizzare e filtrare i messaggi di traccia nel log in modo da poter diagnosticare, ripristinare e verificare i problemi del servizio WCF.
ms.date: 03/30/2017
ms.assetid: 9027efd3-df8d-47ed-8bcd-f53d55ed803c
ms.openlocfilehash: 0ad6094965291a965346522688a8334abbd4e6b3
ms.sourcegitcommit: 358a28048f36a8dca39a9fe6e6ac1f1913acadd5
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 06/23/2020
ms.locfileid: "85244569"
---
# <a name="service-trace-viewer-tool-svctraceviewerexe"></a>Strumento Visualizzatore di tracce dei servizi (SvcTraceViewer.exe)

Lo strumento Visualizzatore di tracce dei servizi Windows Communication Foundation (WCF) consente di analizzare le tracce diagnostiche generate da WCF. Il Visualizzatore di tracce dei servizi consente di unire, visualizzare e filtrare facilmente i messaggi di traccia nel log, in modo da poter diagnosticare, ripristinare e verificare i problemi del servizio WCF.

## <a name="configuring-tracing"></a>Configurazione delle funzionalità di traccia

Le tracce di diagnostica forniscono informazioni che mostrano quello si sta verificando in tutta l'operazione dell'applicazione. Come si intuisce dal nome, è possibile seguire le operazioni dall'origine alla destinazione e tramite punti intermedi.

È possibile configurare la traccia utilizzando il file di configurazione dell'applicazione, Web.config per le applicazioni ospitate sul Web o *appname*. config per le applicazioni indipendenti. Di seguito è riportato un esempio:

```xml
<system.diagnostics>
    <trace autoflush="true" />
    <sources>
            <source name="System.ServiceModel"
                    switchValue="Information, ActivityTracing"
                    propagateActivity="true">
            <listeners>
               <add name="sdt"
                   type="System.Diagnostics.XmlWriterTraceListener"
                   initializeData= "SdrConfigExample.e2e" />
            </listeners>
         </source>
    </sources>
</system.diagnostics>
```

In questo esempio vengono specificati il nome e il tipo del listener di traccia. Il listener viene denominato `sdt` e come tipo viene aggiunto il listener di traccia standard di .NET Framework, ovvero System.Diagnostics.XmlWriterTraceListener. L' `initializeData` attributo viene utilizzato per impostare il nome del file di log per il listener `SdrConfigExample.e2e` . Per il file di log è possibile sostituire un percorso completo con un semplice nome file.

In questo esempio viene creato un file nella directory radice denominato SdrConfigExample.e2e. Quando si utilizza il Visualizzatore di tracce per aprire il file come descritto nella sezione "apertura e visualizzazione di file di traccia WCF", è possibile visualizzare tutti i messaggi inviati.

Il livello di traccia viene controllato in base all'impostazione `switchValue`. Nella tabella seguente viene fornita una descrizione dei livelli di traccia disponibili.

|Livello di traccia|Descrizione|
|-----------------|-----------------|
|Critico|-Registra le voci del registro eventi e di errore, nonché le informazioni sulla correlazione delle tracce. Di seguito sono indicati alcuni esempi di quando è possibile utilizzare il livello Critico:<br />-L'AppDomain si è arrestato a causa di un'eccezione non gestita.<br />-Non è possibile avviare l'applicazione.<br />: Messaggio che ha causato l'errore originato dal processo MyApp.exe.|
|Errore|: Registra tutte le eccezioni. È possibile utilizzare il Livello di errore nei casi seguenti:<br />-Il codice si è arrestato in modo anomalo a causa di un'eccezione cast non valida.<br />-Un'eccezione "Impossibile creare l'endpoint" causa l'esito negativo dell'applicazione all'avvio.|
|Avviso|-Esiste una condizione che può causare un errore o un errore critico. È possibile utilizzare questo livello nei casi seguenti:<br />-L'applicazione riceve più richieste di quanto consentito dalle impostazioni di limitazione delle richieste.<br />-La coda di ricezione è al 98% della capacità configurata.|
|Informazioni|-I messaggi utili per il monitoraggio e la diagnosi dello stato del sistema, la misurazione delle prestazioni o la profilatura vengono generati. È possibile utilizzare queste informazioni durante la pianificazione delle capacità e la gestione delle prestazioni. È possibile utilizzare questo livello nei casi seguenti:<br />-Si è verificato un errore dopo che il messaggio ha raggiunto l'AppDomain ed è stato deserializzato.<br />-Si è verificato un errore durante la creazione del binding HTTP.|
|Dettagliato|-Traccia a livello di debug per il codice utente e la manutenzione. Impostare questo livello quando:<br />-Non si è certi del metodo chiamato nel codice quando si è verificato l'errore.<br />-È stato configurato un endpoint errato e non è stato possibile avviare il servizio perché la voce nell'archivio prenotazioni è bloccata.|
|ActivityTracing|Eventi di flusso tra attività di elaborazione e componenti.<br /><br /> Questo livello consente ad amministratori e sviluppatori di mettere in correlazione applicazioni nello stesso dominio applicazione.<br /><br /> -TRACES per i limiti dell'attività: Start/Stop.<br />: Tracce per i trasferimenti.|

 È possibile utilizzare l'istruzione `add` per specificare il nome e il tipo del listener di traccia che si desidera utilizzare. Nella configurazione dell'esempio il listener viene denominato `sdt` e come tipo viene aggiunto il listener di traccia standard di .NET Framework, ovvero `System.Diagnostics.XmlWriterTraceListener`. Utilizzare l'istruzione `initializeData` per impostare il nome del file di log del Listener. È inoltre possibile sostituire un percorso completo con un semplice nome file.

A partire da .NET Framework 4,8, i controlli ComboBox in alcuni temi a contrasto elevato vengono visualizzati nel colore corretto. È possibile disabilitare questa modifica rimuovendo l'impostazione seguente dal file *svcTraceViewer.exe.config* :

```xml
<AppContextSwitchOverrides value="Switch.UseLegacyAccessibilityFeatures=false;Switch.UseLegacyAccessibilityFeatures.2=false" />
```

## <a name="using-the-service-trace-viewer-tool"></a>Uso dello strumento Visualizzatore di tracce dei servizi

### <a name="opening-and-viewing-wcf-trace-files"></a>Apertura e visualizzazione di file di traccia WCF

Il Visualizzatore traccia servizio supporta tre tipi di file:

- File di traccia WCF (. svcLog)

- File di traccia eventi, con estensione etl

- File di traccia Crimson

 Mediante lo strumento Visualizzatore di tracce dei servizi è possibile aprire i file di traccia supportati, aggiungere e integrare file aggiuntivi e aprire e unire simultaneamente un gruppo di file di traccia.

##### <a name="to-open-a-trace-file"></a>Per aprire un file di traccia

1. Avviare il Visualizzatore di tracce dei servizi utilizzando una finestra di comando per passare al percorso di installazione di WCF (C:\Programmi\Microsoft SDKs\Windows\v6.0\Bin), quindi digitare `SvcTraceViewer.exe` .

> [!NOTE]
> Lo strumento Visualizzatore di tracce dei servizi può essere associato a due tipi di file: svclog e stvproj. Per eseguire e annullare la registrazione delle estensioni di file è possibile utilizzare due parametri nella riga di comando.
>
> /register: consente di registrare l'associazione delle estensioni di file "svclog" e "stvproj" a SvcTraceViewer.exe
>
> /unregister: consente di annullare la registrazione dell'associazione delle estensioni di file "svclog" e "stvproj" a SvcTraceViewer.exe

1. Quando viene avviato Visualizzatore di tracce del servizio, fare clic su **file** , quindi scegliere **Apri**. Passare al percorso in cui sono archiviati i file di traccia.

2. Fare doppio clic sul file di traccia che si desidera aprire.

    > [!NOTE]
    > Premere MAIUSC mentre si fa clic su più file di traccia per selezionarli e aprirli simultaneamente. Lo strumento Visualizzatore di tracce dei servizi consente di unire e visualizzare il contenuto di tutti i file in una visualizzazione unificata. È ad esempio possibile aprire i file di traccia sia del client sia del servizio. Ciò è utile quando nella configurazione sono state attivate le funzionalità di registrazione dei messaggi e di propagazione delle attività. In questo caso la visualizzazione unificata dei contenuti dei file consente infatti di analizzare lo scambio dei messaggi fra client e servizio. È inoltre possibile trascinare più file nel Visualizzatore oppure utilizzare la scheda **progetto** . Per ulteriori informazioni, vedere la sezione gestione del progetto.

3. Per aggiungere ulteriori file di traccia alla raccolta aperta, fare clic su **file** , quindi scegliere **Aggiungi**. Nella finestra visualizzata, spostarsi al percorso dei file di traccia e fare doppio clic sul file che si desidera aggiungere.

> [!CAUTION]
> Non è consigliabile caricare un file di log di traccia di dimensioni superiori a 200 MB. Se si tenta di caricare un file di dimensioni superiori, il processo di caricamento può richiedere molto tempo, a seconda delle risorse del computer. Lo strumento Visualizzatore di tracce dei servizi può non rispondere per molto tempo o può esaurire la memoria del computer. Per evitare che ciò avvenga, è consigliabile configurare la funzionalità di caricamento parziale. Per ulteriori informazioni su questa procedura, vedere la sezione "Caricamento di file di traccia di grandi dimensioni”.

#### <a name="event-tracing-and-crimson-tracing"></a>Formati di traccia eventi e di traccia Crimson

Il formato nativo del visualizzatore è il formato di traccia delle attività emesso da WCF. Le tracce generate in un altro formato devono essere convertite affinché il visualizzatore sia in grado di leggerle. Attualmente, oltre al formato di traccia delle attività, il visualizzatore supporta i formati di traccia eventi e di traccia Crimson.

Quando si apre un file che non contiene tracce di attività, il visualizzatore prova a convertirlo. Occorre quindi specificare il nome e il percorso del file in cui salvare i dati di traccia convertiti. Dopo aver eseguito la conversione dei dati, il visualizzatore mostra il contenuto del nuovo file.

> [!NOTE]
> Al termine della conversione, i dati di traccia convertiti vengono salvati nel disco rigido. Prima di avviare la conversione è pertanto necessario verificare che lo spazio disponibile sul disco sia sufficiente a contenere tali dati. In caso contrario, la conversione avrà esito negativo.

### <a name="managing-projects"></a>Gestione di progetti

Per visualizzare simultaneamente più file di traccia è possibile utilizzare la funzionalità di gestione di progetti del visualizzatore. Se ad esempio si dispone del file di traccia di un client e del file di traccia di un servizio, è possibile aggiungerli a un progetto. Ogni volta che si apre il progetto, tutti i relativi file di traccia verranno quindi caricati simultaneamente.

Esistono due modalità per gestire i progetti:

- Nel menu **file** è possibile aprire, salvare e chiudere i progetti.

- Nella scheda **progetto** è possibile aggiungere file a un progetto.

### <a name="viewing-wcf-traces"></a>Visualizzazione di tracce WCF

WCF emette tracce utilizzando il formato di traccia delle attività. Nel modello delle tracce delle attività, le singole tracce vengono raggruppate in attività in base al loro scopo. Il flusso di controllo logico viene trasferito tra le attività. Durante il periodo di attività di un'applicazione, ad esempio, iniziano e terminano molte attività di trasmissione di messaggi. Per ulteriori informazioni sulla visualizzazione di tracce e attività e sull'interfaccia utente del Visualizzatore di tracce dei servizi, vedere [utilizzo di Service Trace Viewer per la visualizzazione di tracce correlate e risoluzione dei problemi](./diagnostics/tracing/using-service-trace-viewer-for-viewing-correlated-traces-and-troubleshooting.md).

#### <a name="switching-to-different-views"></a>Passaggio a una visualizzazione specifica

Nel Visualizzatore di tracce dei servizi sono disponibili le visualizzazioni distinte seguenti, Vengono visualizzati come schede nel riquadro sinistro del visualizzatore ed è possibile accedervi anche dal menu **Visualizza** .

- Visualizzazione Attività

- Project View

- Visualizzazione Messaggio

- Visualizzazione grafico

##### <a name="activity-view"></a>Visualizzazione Attività

Una volta aperti i file di traccia, è possibile visualizzare le tracce raggruppate in attività e visualizzate nella visualizzazione **attività** nel riquadro a sinistra.

La visualizzazione **attività** consente di visualizzare i nomi delle attività, il numero di tracce nell'attività, la durata, l'ora di inizio e l'ora di fine.

Se si fa clic su una delle attività elencate, nel riquadro delle tracce a destra vengono visualizzate le tracce contenute in tale attività. È quindi possibile selezionare una traccia per visualizzarne i dettagli.

È possibile selezionare più attività premendo il tasto **CTRL** o **MAIUSC** e facendo clic sulle attività desiderate. Nel riquadro delle tracce vengono visualizzate tutte le tracce contenute nelle attività selezionate.

È possibile fare doppio clic su un'attività per visualizzarla nella visualizzazione **grafico** . In alternativa, è possibile selezionare un'attività e passare alla visualizzazione **grafico** .

> [!NOTE]
> L'attività "000000000000" è un'attività speciale che non può essere visualizzata nella visualizzazione grafico. Poiché a tale attività sono collegate tutte le altre attività, la visualizzazione di questa attività comporta una notevole riduzione delle prestazioni.

Per ordinare l'elenco delle attività è possibile fare clic sul titolo della colonna. Le attività che contengono tracce di avviso presentano uno sfondo giallo, mentre quelle che contengono tracce di errore presentano uno sfondo rosso.

Esistono tre tipi distinti di attività, ognuno di essi caratterizzato da un'icona visualizzata a sinistra di ogni attività. Per conoscere il significato delle icone, consultare la sezione relativa alla descrizione delle icone di traccia.

##### <a name="project-view"></a>Project View

Questa visualizzazione consente di gestire i file di traccia del progetto corrente. Per ulteriori dettagli, vedere la sezione relativa alla gestione dei progetti.

##### <a name="message-view"></a>Visualizzazione Messaggio

Questa visualizzazione consente di visualizzare tutte le tracce del log dei messaggi, tra cui Action, data/ora, process, attività e from/to, e di passare ai dettagli della traccia del log dei messaggi associata. È possibile raggruppare le tracce del log dei messaggi per limite di attività, processo/thread o inviare & ricevere per semplificare la navigazione del flusso di messaggi.

##### <a name="graph-view"></a>Visualizzazione grafico

Questa vista consente di visualizzare i dati di traccia per un'attività specifica in formato grafico. Questo tipo di visualizzazione consente di esaminare l'esecuzione sequenziale dei passaggi degli eventi e le interrelazioni tra più attività dovute allo spostamento di dati fra tali file.

Per passare alla visualizzazione **grafico** , selezionare un'attività nella visualizzazione **attività** , quindi fare clic sulla scheda **attività** o su una traccia del log dei messaggi nella visualizzazione **messaggio** . Se sono stati caricati più file di traccia e l'attività contiene tracce ricavate da più di un file, tutte le tracce attinenti sono visualizzate nella visualizzazione Grafico. Facendo doppio clic sulle attività e sulle tracce del log dei messaggi viene inoltre visualizzata la visualizzazione **grafico** .

Nella visualizzazione **grafico** ogni colonna verticale rappresenta un'attività e ogni blocco nella colonna rappresenta una traccia. Le attività sono raggruppate per processo (o thread). Le frecce piccole tra le attività rappresentano i trasferimenti. Le frecce grandi tra i processi rappresentano lo scambio di messaggi. L'attività attualmente selezionata è sempre visualizzata in giallo.

###### <a name="selecting-traces-in-the-graph"></a>Selezione di Tracce nel Grafico

1. Fare clic su un blocco del grafico.

2. Utilizzare i tasti SU e GIÙ per selezionare le tracce adiacenti.

3. Osservare le informazioni di traccia riportate nel riquadro delle tracce e nel Riquadro dettagli.

###### <a name="expanding-or-collapsing-activity-transfers"></a>Espansione o compressione dei trasferimenti delle attività

Quando l'attività attualmente selezionata trasferisce l'esecuzione a un'altra attività è possibile espandere i trasferimenti delle attività. Ciò consente di seguire i trasferimenti.

Per espandere o comprimere i trasferimenti delle attività,

1. Individuare la traccia di trasferimento con un segno "+" a sinistra dell'icona di trasferimento.

2. Fare clic su "+" oppure premere **CTRL** e "+" utilizzando la tastiera.

3. Nel grafico verrà visualizzata l'attività successiva.

4. A sinistra dell'icona di trasferimento viene visualizzato "-". Fare clic sul segno "-" o premere CTRL e "-" per comprimere il trasferimento dell'attività.

> [!NOTE]
> Quando esistono più trasferimenti verso una determinata attività e si espande uno di essi, il sistema visualizza le attività che portano alla nuova attività a partire dall'attività radice. Queste nuove attività sono visualizzate in forma compressa. Per esaminare i dettagli di queste attività è possibile espanderle verticalmente facendo clic sull'icona di espansione posta nell'intestazione del grafico.

###### <a name="expanding-or-collapsing-activities-vertically"></a>Espansione o compressione verticale delle attività

Al fine di nascondere i dettagli superflui, il visualizzatore consente di comprimere le attività riportate nel grafico delle attività. Quando un'attività è compressa, le tracce specifiche in essa contenute non vengono visualizzate. Vengono riportati soltanto i trasferimenti di traccia. Per visualizzare tutte le tracce di un'attività è possibile espandere verticalmente l'attività. A tale scopo, fare clic sul simbolo di espansione dell'attività posto nell'intestazione del grafico.

Per espandere o comprimere verticalmente le attività

1. Fare clic sull'icona "+" nell'intestazione dell'attività per espandere verticalmente l'attività.

2. Si noti che nel grafico vengono visualizzate tutte le tracce.

3. Fare clic sull'icona "-" nell'intestazione dell'attività per comprimere verticalmente l'attività.

4. Si noti che nell'attività sono riportati solo i trasferimenti, i log dei messaggi, le tracce di avviso e di eccezione di maggiore importanza.

###### <a name="options"></a>Opzioni

È possibile selezionare due opzioni dal menu **Opzioni** in visualizzazione grafico.

- Mostra tracce del limite delle attività. Tale opzione, se deselezionata, consente di escludere dal grafico le tracce di limite attività.

- Mostra tracce dettagliate che non appartengono a messaggi. Tale opzione, se deselezionata, consente di escludere dal grafico le tracce di livello dettagliato, tranne nel caso di tracce di messaggio. Nella maggior parte dei casi le tracce di livello dettagliato sono meno importanti ai fini dell'analisi. Questa opzione è utile quando non si desidera analizzare le tracce di livello dettagliato al fine di concentrarsi esclusivamente sulle tracce più importanti.

###### <a name="layout-mode"></a>Modalità di layout

Il visualizzatore presenta due modalità di layout: **processo** e **thread**. Questa impostazione definisce l'unità massima di organizzazione. La modalità di layout predefinita è **processo**, il che significa che le attività vengono raggruppate in base ai processi nel grafico.

###### <a name="execution-list"></a>Elenco di esecuzione

In questo elenco a discesa è possibile selezionare quale processo o thread visualizzare nel grafico. Se ad esempio sono stati aperti i file di traccia di un servizio e di due client (A e B), per visualizzare nel grafico solo il servizio e il client A è possibile deselezionare nell'elenco il client B.

#### <a name="viewing-trace-details"></a>Visualizzazione dei dettagli di una traccia

Per visualizzare i dettagli di una traccia, selezionarla nel riquadro delle tracce. I dettagli vengono riportati nel Riquadro dettagli.

##### <a name="trace-pane"></a>Riquadro delle tracce

Il riquadro nell'angolo superiore destro del Visualizzatore di tracce dei servici è il riquadro delle tracce. In questo riquadro sono elencate tutte le tracce contenute nell'attività selezionata, insieme alle relative informazioni aggiuntive, ad esempio livello di traccia, ID del thread e nome del processo.

È possibile copiare il codice XML non elaborato della traccia negli Appunti facendo clic con il pulsante destro del mouse su una traccia e selezionando **Copia traccia negli Appunti**.

##### <a name="detail-pane"></a>Riquadro dei dettagli

Il riquadro nell'angolo inferiore sinistro del Visualizzatore di tracce dei servizi è il Riquadro dettagli. Questo riquadro presenta tre schede che consentono di visualizzare i dettagli di una traccia.

La visualizzazione **formattata** consente di visualizzare le informazioni in modo più organizzato. Tutti gli elementi XML noti vengono elencati in tabelle e alberi, semplificando la lettura e la comprensione delle informazioni.

Nella visualizzazione **XML** viene visualizzato il codice XML corrispondente alla traccia selezionata. Tale visualizzazione supporta l'evidenziazione e l'utilizzo dei colori per la sintassi. Quando si usa **trova** per cercare stringhe, evidenzia i risultati della ricerca.

La visualizzazione **messaggio** Visualizza la parte del messaggio XML nelle tracce del log dei messaggi. Tale visualizzazione è visibile solo quando si seleziona una traccia di messaggio.

### <a name="filtering-wcf-traces"></a>Filtro delle tracce WCF

Per semplificare l'analisi dei file di traccia è possibile filtrarli nei modi seguenti:

- la barra degli strumenti di filtro consente di accedere ai filtri predefiniti e personalizzati. Può essere abilitato tramite il menu **Visualizza** .

- Il filtro predefinito del visualizzatore può essere utilizzato per filtrare in modo selettivo le parti delle tracce WCF. Per impostazione predefinita, tale filtro è impostato in modo da consentire il passaggio di tutte le tracce dell'infrastruttura. Le impostazioni di questo filtro sono definite nel sottomenu **Opzioni filtro** del menu **Visualizza** .

- I filtri XPath personalizzati consentono agli utenti di avere il controllo completo sull'applicazione dei filtri. Possono essere definiti nel menu **filtro personalizzato** sotto **visualizzazione** .

Vengono visualizzate solo le tracce che passano attraverso tutti i filtri attivi.

#### <a name="using-the-filter-toolbar"></a>Utilizzo della barra degli strumenti di filtro

La barra degli strumenti di filtro si trova nella parte superiore dello strumento. Se non è presente, è possibile attivarlo dal menu **Visualizza** . La barra è costituita da tre componenti:

- Cerca: **Cerca** definisce l'oggetto da cercare nell'operazione di filtro. Se, ad esempio, si desidera trovare tutte le tracce generate nel contesto del processo X, impostare questo campo su X e il campo **Cerca in** su "nome processo". Quando si sceglie un filtro basato su tempo, questo campo diventa un controllo di selezione Datetime.

- Cerca in: questo campo definisce il tipo di filtro da applicare.

- Livello: questa impostazione definisce il livello minimo di traccia consentito dal filtro. Ad esempio, se il livello è impostato su Errore e successivi, consente di visualizzare soltanto le tracce di livello Errore e Critico. I criteri di questo filtro vengono applicati insieme ai criteri specificati in Cerca e Cerca in.

Il pulsante **Filtra ora** avvia l'operazione di filtro. L'applicazione di alcuni filtri, specialmente quando riguarda set di dati di grandi dimensioni, richiede molto tempo. È possibile annullare l'operazione di filtro premendo il pulsante **Arresta** visualizzato sulla barra di stato nel menu **operazioni** .

Il pulsante **Cancella** consente di reimpostare i filtri predefiniti e personalizzati per consentire il passaggio di tutte le tracce.

#### <a name="filter-options"></a>Opzioni di filtro

Il visualizzatore è in grado di rimuovere automaticamente dalla visualizzazione determinate tracce di WCF. La rimozione può riguardare in modo selettivo le tracce generate da aree specifiche di WCF, ad esempio le tracce relative alle transazioni.

Le impostazioni di questo filtro sono definite nel sottomenu **Opzioni filtro** del menu **Visualizza** .

#### <a name="custom-filters"></a>Filtri personalizzati

Se si ha familiarità con il linguaggio Xpath (XML Path) è possibile utilizzarlo per creare filtri personalizzati finalizzati alla ricerca di dati di traccia correlati a qualsiasi elemento XML di interesse. I filtri sono accessibili tramite la barra degli strumenti di filtro.

I filtri personalizzati possono includere parametri. È inoltre possibile importare filtri personalizzati già esistenti.

##### <a name="creating-a-custom-filter"></a>Creazione di un filtro personalizzato

I filtri possono essere creati in due modi:

###### <a name="creating-a-custom-filter-using-the-template-wizard"></a>Creazione di un filtro personalizzato tramite la Creazione guidata modelli

È possibile fare clic su una traccia esistente e creare un filtro basato sulla struttura della traccia. Questo esempio illustra la creazione di un filtro personalizzato basato sull'ID del thread.

1. Nel riquadro di traccia che si trova nella parte superiore destra del visualizzatore, selezionare la traccia contenente l'elemento su cui si desidera basare il filtro.

2. Fare clic sul pulsante **Crea filtro personalizzato** che si trova nella parte superiore del riquadro traccia.

3. Nella finestra di dialogo visualizzata, immettere il nome del filtro. In questo esempio, immettere `Thread ID` . È inoltre possibile fornire una descrizione del filtro.

4. Nella visualizzazione albero a sinistra viene visualizzata la struttura del record di traccia selezionato nel passaggio 1. Passare all'elemento per il quale si desidera creare una condizione. In questo esempio, passare a ThreadID per trovarsi nel nodo XPath: /E2ETraceEvent/System/Execution/@ThreadID . Fare doppio clic sull'attributo ThreadID contenuto nella visualizzazione albero. Nella parte destra della finestra di dialogo viene creata un'espressione per l'attributo.

5. Modificare il campo del parametro per la condizione ThreadID da None a' {0} '. Questo passaggio fa in modo che il valore ThreadID venga configurato quando il filtro viene applicato. Per ulteriori informazioni, consultare la sezione relativa all'applicazione dei filtri. È possibile definire fino a quattro parametri. Le condizioni vengono combinate mediante l'operatore OR.

6. Fare clic su **OK** per creare il filtro.

> [!NOTE]
> I filtri creati tramite la Creazione guidata modelli possono essere modificati solo manualmente. Questa procedura guidata non può essere utilizzata su un filtro già esistente. Inoltre, se si utilizza la Creazione guidata modelli per creare un filtro Xpath, le condizioni di tale filtro vengono combinate tramite l'operatore OR. Di conseguenza, se si desidera impostare un operatore AND, l'espressione del filtro deve essere modificata manualmente.

###### <a name="creating-a-custom-filter-manually"></a>Creazione manuale di un filtro personalizzato

Il menu Filtri Personalizzati consente di immettere filtri XPath manualmente.

1. Scegliere la voce di menu **filtri personalizzati** dal menu Visualizza.

2. Nella finestra di dialogo visualizzata fare clic su **nuovo.**

3. Specificare almeno il nome e un'espressione Xpath del filtro.

4. Fare clic su **OK**.

###### <a name="applying-a-custom-filter"></a>Applicazione di un filtro personalizzato

Una volta creato un filtro personalizzato, tale filtro è accessibile tramite la barra degli strumenti di filtro. Selezionare il filtro che si desidera applicare nel campo **Cerca in** della barra degli strumenti del filtro. Per utilizzare l'esempio precedente, selezionare "ID thread".

1. Specificare il valore che si sta cercando nel campo **trova** . In questo esempio, immettere l'ID del thread da individuare.

2. Fare clic su **Filtra ora**e osservare il risultato dell'operazione.

Se il filtro usa più parametri, immetterli usando ";" come separatore nel campo **trova** . Ad esempio, nella stringa seguente sono definiti 3 parametri: "1;findValue;text". Il Visualizzatore applica ' 1' al {0} parametro del filtro. ' findValue ' è text ' vengono applicati {1} rispettivamente a e {2} .

###### <a name="sharing-custom-filters"></a>Condivisione di filtri personalizzati

I filtri personalizzati possono essere condivisi tra sessioni diverse e utenti diversi. È possibile esportare i filtri in un file di definizione e quindi importare questo file in un altro percorso.

 Per importare un filtro personalizzato:

1. Scegliere **filtri personalizzati**dal menu **Visualizza** .

2. Nella finestra di dialogo visualizzata fare clic sul pulsante **Importa** .

3. Passare al file di filtro personalizzato (con estensione stvcf), fare clic sul file e quindi fare clic sul pulsante **Apri** .

Per esportare un filtro personalizzato:

1. Scegliere **filtri personalizzati**dal menu Visualizza.

2. Nella finestra di dialogo visualizzata, selezionare il filtro che si desidera esportare.

3. Fare clic sul pulsante **Esporta**.

4. Specificare il nome e il percorso del file di definizione del filtro personalizzato (con estensione stvcf), quindi fare clic sul pulsante **Salva** .

> [!NOTE]
> Questi filtri personalizzati possono essere importati ed esportati solo tramite lo strumento Visualizzatore di tracce dei servizi e non possono essere letti con altri strumenti.

### <a name="finding-data"></a>Ricerca dei dati

Il visualizzatore offre le modalità seguenti per la ricerca dei dati:

- La barra degli strumenti Trova consente di accedere rapidamente alle opzioni di ricerca più comuni.

- La finestra di dialogo Trova offre ulteriori opzioni di ricerca. È accessibile dal menu **modifica** o dalla chiave breve CTRL + F.

La barra degli strumenti Trova si trova nella parte superiore del visualizzatore. Se non è presente, è possibile attivarlo dal menu **Visualizza** . La barra è costituita da due componenti:

- Trova: consente di immettere una parola chiave di ricerca.

- Cerca in: consente di definire l'ambito di ricerca. È possibile scegliere se eseguire la ricerca in tutte le attività o soltanto nell'attività corrente.

Nella finestra di dialogo Trova sono disponibili altre due opzioni:

- Trova destinazione:

  - L'opzione "dati di log non elaborati" Cerca nella parola chiave tutti i dati non elaborati.

  - Le opzioni "testo XML" e "attributo XML" cercano solo elementi XML.

  - L'opzione "messaggio registrato" Cerca la parola chiave solo nei messaggi.

- Ignora attività radice: la ricerca ignora le tracce nell'attività "000000000000". Ciò consente di migliorare le prestazioni nei file di traccia di grandi dimensioni quando l'attività radice presenta migliaia di tracce, per lo più relative a trasferimenti.

### <a name="navigating-traces"></a>Esplorazione delle tracce

Poiché le tracce vengono registrate in sequenza durante la fase di esecuzione dell'applicazione, l'esplorazione delle tracce può agevolarne il debug. Il Visualizzatore di tracce dei servizi offre varie opzioni di esplorazione delle tracce.

#### <a name="step-forward-or-backward"></a>Passo avanti o Passo indietro

Se si considera ogni traccia come una riga di codice nel programma, la fase di avanzamento è molto simile a quella dell'ambiente di sviluppo integrato (IDE) di Visual Studio. A differenza di tale funzione, tuttavia, è inoltre possibile passare alla traccia precedente. Queste opzioni consentono di passare alla traccia successiva o precedente dell'attività.

- Passaggio successivo: utilizzare il menu **attività** oppure premere "F10". È inoltre possibile utilizzare il tasto freccia "giù" nel riquadro traccia.

- Passaggio precedente: usare il menu **attività** oppure premere "F9". Nel riquadro traccia è inoltre possibile utilizzare il tasto di direzione "up".

> [!NOTE]
> In questo modo è possibile passare a un'attività che si verifica in un processo diverso o anche in un computer diverso, perché i messaggi WCF possono includere ID attività che si estendono su più computer.

#### <a name="follow-transfer"></a>Trasferimento successivo

Le tracce di trasferimento sono tracce speciali del file di traccia che descrivono il trasferimento dell'esecuzione da un'attività a un'altra. Ad esempio, "Activity A" può essere trasferito a "Activity B". In tal caso, è presente una traccia di trasferimento nell'"attività A" con il nome "to: Activity" e l'icona di trasferimento. Questa traccia di trasferimento è un collegamento tra le due tracce. In "Activity B", potrebbe essere presente anche una traccia di trasferimento alla fine dell'attività per il trasferimento di nuovo a "Activity A". Questo funzionamento è simile alle chiamate di funzione dei programmi: A chiama B e quindi B restituisce il risultato.

"Follow Transfer" è simile a "Esegui istruzione" in un debugger. consente di seguire il trasferimento dell'esecuzione da A a B, senza influire sulle altre tracce.

Esistono due modalità per eseguire questo tipo di esplorazione: tramite mouse o mediante tastiera.

- Tramite mouse: fare doppio clic sulla traccia di trasferimento nel riquadro delle tracce.

- Per tastiera: selezionare una traccia di trasferimento e usare "Segui trasferimento" nel menu **attività** oppure premere "F11".

> [!NOTE]
> In molti casi, quando l'attività A trasferisce l'esecuzione all'attività B, l'attività A attende che l'attività B restituisca l'esecuzione. Di conseguenza, durante la registrazione di traccia dell'attività B, per l'attività A non viene eseguita alcuna registrazione di traccia. Tuttavia, è anche possibile che l'attività A non attenda l'attività B. In questo caso la registrazione di traccia dell'attività A continua normalmente. Un'altra possibilità è che l'attività B non restituisca l'esecuzione all'attività A. Ciò rappresenta una differenza rispetto alle chiamate di funzione. I trasferimenti fra le attività risultano più comprensibili se esaminati nella visualizzazione Grafico.

#### <a name="jump-to-next-or-previous-transfer"></a>Vai al trasferimento successivo o Vai al trasferimento precedente

Durante l'analisi dell'attività corrente o delle attività selezionate, quando vengono selezionate più attività, può essere utile individuare rapidamente le attività a cui viene trasferita l'esecuzione. "Vai al trasferimento successivo" consente di individuare la traccia di trasferimento successiva nell'attività. Una volta individuata la traccia di trasferimento, è possibile usare "Segui trasferimento" per eseguire un'istruzione nell'attività successiva.

- Vai al trasferimento successivo: usare il menu **attività** oppure premere "CTRL + F10".

- Vai al trasferimento precedente: usare il menu **attività** o premere "CTRL + F9".

#### <a name="navigate-in-graph-view"></a>Esplorazione tramite la visualizzazione Grafico

Anche se la navigazione nel riquadro attività e nel riquadro delle tracce è simile al debug, l'utilizzo della visualizzazione **grafico** offre un'esperienza molto migliore nell'esplorazione. Per ulteriori informazioni, vedere la sezione "visualizzazione Graph".

### <a name="loading-large-trace-files"></a>Caricamento dei file di traccia di grandi dimensioni

I file di traccia possono essere di dimensioni notevoli. Ad esempio, se si attiva la traccia sul livello "verbose", il file di traccia risultante per l'esecuzione di alcuni minuti può essere facilmente costituito da centinaia di megabyte o addirittura più grandi, a seconda della velocità di rete e del modello di comunicazione.

L'apertura di un file di traccia di grandi dimensioni nello strumento Visualizzatore di tracce dei servizi può comportare una riduzione delle prestazioni. È possibile che il caricamento risulti lento e che il tempo di risposta dopo il caricamento sia elevato. La velocità effettiva varia da caso a caso e dipende della configurazione hardware del sistema in uso. Nella maggior parte dei PC, il caricamento di un file di traccia più grande di 200 MB comporta una notevole riduzione delle prestazioni. Se il file di traccia presenta dimensioni superiori a 1 GB, è possibile che lo strumento utilizzi tutta la memoria disponibile o che risulti bloccato per un periodo di tempo molto lungo.

Per evitare il caricamento lento e il tempo di risposta durante l'analisi di file di traccia di grandi dimensioni, il Visualizzatore di tracce dei servizi fornisce una funzionalità denominata "caricamento parziale", che carica solo una piccola parte della traccia alla volta. Si supponga ad esempio di disporre di un file di oltre 1 GB relativo a una traccia in esecuzione sul server da diversi giorni. In questo caso, qualora si verifichino errori, non è necessario aprire l'intero file di traccia. È invece possibile caricare soltanto le tracce relative all'intervallo di tempo in cui si ritiene che si siano verificati gli errori. Poiché l'ambito è ridotto, lo strumento Visualizzatore di tracce dei servizi può caricare il file più velocemente. L'identificazione degli errori può quindi essere svolta a partire da un set minore di dati.

#### <a name="enabling-partial-loading"></a>Abilitazione della funzionalità di caricamento parziale

La funzionalità di caricamento parziale non richiede l'abilitazione manuale. Se si tenta di caricare un set di file di traccia le cui dimensioni complessive sono maggiori di 40 MB, nello strumento Visualizzatore di tracce dei servizi viene aperta automaticamente una finestra di dialogo in cui è possibile selezionare la parte che si desidera caricare.

> [!NOTE]
> Poiché è possibile che le tracce non siano distribuite uniformemente nell'intervallo di tempo, l'ampiezza del periodo di tempo che si specifica nella barra degli strumenti della funzionalità di caricamento parziale potrebbe non essere proporzionale alle dimensioni di caricamento visualizzate. Le dimensioni di caricamento effettive possono essere minori rispetto alla stima visualizzata nella finestra di dialogo della funzionalità di caricamento parziale.

#### <a name="adjusting-partial-loading"></a>Impostazione dell'intervallo di tempo per il caricamento parziale

Dopo aver caricato parte del file di traccia, per modificare l'intervallo di tempo relativo al set di dati caricato è possibile regolare la barra degli strumenti della funzionalità di caricamento parziale che si trova nella parte superiore del visualizzatore.

1. Utilizzare il mouse per spostare la barra degli strumenti oppure immettere l'ora di inizio e di fine.

2. Fare clic sul pulsante **modifica** .

## <a name="understanding-trace-icons"></a>Descrizione delle icone di traccia

Di seguito è riportato un elenco di icone utilizzate dallo strumento Visualizzatore di tracce dei servizi nella visualizzazione **attività** , nella visualizzazione **grafico** e nel riquadro **traccia** per rappresentare elementi diversi.

> [!NOTE]
> Alcune tracce non categorizzate, ad esempio "un messaggio chiuso", non hanno un'icona.

### <a name="activity-tracing-traces"></a>Tracce di attività

|Icona|Descrizione|
|----------|-----------------|
|![Traccia degli avvisi](./media/7457c4ed-8383-4ac7-bada-bcb27409da58.gif "7457c4ed-8383-4ac7-bada-bcb27409da58")|Traccia di avviso: traccia generata al livello di avviso|
|![Traccia di errore](./media/7d908807-4967-4f6d-9226-d52125db69ca.gif "7d908807-4967-4f6d-9226-d52125db69ca")|Traccia di errore: traccia generata al livello di errore.|
|![Traccia di inizio dell'attività:](./media/8a728f91-5f80-4a95-afe8-0b6acd6e0317.gif "8a728f91-5f80-4a95-afe8-0b6acd6e0317")|Traccia di inizio dell’attività: traccia che indica l’inizio di un’attività, contenente il nome dell’attività. I progettisti dell’applicazione e gli sviluppatori devono definire una traccia d’inizio dell’attività per ogni ID attività per processo o thread.<br /><br /> Se l'ID attività viene propagato attraverso origini di traccia per la correlazione tra tracce, è possibile vedere più inizi per lo stesso ID attività (uno per ogni origine di traccia). La traccia di inizio viene emessa se è abilitata la funzione ActivityTracing per l'origine di traccia.|
|![Traccia di arresto dell'attività](./media/a0493e95-653e-4af8-84a4-4d09a400bc31.gif "a0493e95-653e-4af8-84a4-4d09a400bc31")|Traccia di interruzione dell’attività: traccia che indica l’interruzione di un’attività, . contenente il nome dell’attività. I progettisti dell’applicazione e gli sviluppatori devono definire una traccia d’interruzione dell’attività per ogni ID attività per origine di traccia. Nessuna traccia derivante da una determinata origine di traccia viene visualizzata dopo che venga generata un’interruzione dell’attività da parte dell’origine di traccia, a meno che la granularità del tempo di traccia non sia sufficientemente piccola. In questo caso, durante la visualizzazione, può verificarsi un’esecuzione interleave di due tracce della stessa durata, comprendenti un’interruzione. Se l'ID attività viene propagato attraverso origini di traccia per la correlazione tra tracce, è possibile vedere più Interruzioni per lo stesso ID attività (una per ogni origine di traccia). La traccia di interruzione viene emessa se è abilitata la funzione ActivityTracing per l'origine di traccia.|
|![Traccia di sospensione dell'attività](./media/6f7f4191-df2b-4592-8998-8379769e2d32.gif "6f7f4191-df2b-4592-8998-8379769e2d32")|Traccia di sospensione dell’attività: traccia che indica il tempo di sospensione di un’attività. Nessuna traccia è generata in un'attività sospesa finché l'attività non riprende. Un'attività sospesa indica che non si sta verificando nessuna elaborazione in quell'attività nell'ambito dell'origine della traccia. Le tracce di Sospensione/Ripresa sono utili per il profiling. La traccia di sospensione viene emessa se è abilitata la funzione ActivityTracing per l'origine di traccia.|
|![Traccia di ripresa dell'attività](./media/1060d9d2-c9c8-4e0a-9988-cdc2f7030f17.gif "1060d9d2-c9c8-4E0A-9988-cdc2f7030f17")|Traccia di ripresa dell'attività: traccia che indica il momento di ripresa di un’attività dopo la sospensione. Le tracce possono essere generate nuovamente in quell'attività. Le tracce di Sospensione/Ripresa sono utili per il profiling. La traccia di ripresa viene emessa se è abilitata la funzione ActivityTracing per l'origine di traccia.|
|![Trasferimento](./media/b2d9850e-f362-4ae5-bb8d-9f6f3ca036a5.gif "b2d9850e-f362-4ae5-bb8d-9f6f3ca036a5")|Trasferimento: traccia generata quando il flusso di controllo logico viene trasferito da un’attività all’altra. L'attività originaria del trasferimento può continuare ad eseguire le operazioni in parallelo con l'attività che riceve il trasferimento. La traccia di trasferimento viene emessa se è abilitata la funzione ActivityTracing per l'origine di traccia.|
|![Trasferimento da](./media/1df215cb-b344-4f36-a20d-195999bda741.gif "1df215cb-b344-4f36-a20d-195999bda741")|Trasferimento da: traccia che definisce il trasferimento da un’altra attività all’attività corrente.|
|![Trasferimento a](./media/74255b6e-7c47-46ef-8e53-870c76b04c3f.gif "74255b6e-7c47-46ef-8e53-870c76b04c3f")|Trasferimento a: traccia che definisce il trasferimento di un flusso di controllo logico dall’attività corrente a un’altra attività.|

### <a name="wcf-traces"></a>Tracce WCF

|Icona|Descrizione|
|----------|-----------------|
|![Traccia del log del messaggio](./media/7c66e994-2476-4260-a0db-98948b9af197.gif "7c66e994-2476-4260-a0db-98948b9af197")|Traccia del log dei messaggi: traccia generata quando un messaggio WCF viene registrato dalla funzionalità di registrazione dei messaggi, quando l' `System.ServiceModel.MessageLogging` origine di traccia è abilitata. Facendo clic su questa traccia verrà visualizzato il messaggio. Ci sono quattro punti di registrazione configurabili per un messaggio: ServiceLevelSendRequest, TransportSend, TransportReceive e ServiceLevelReceiveRequest che possono essere specificati anche dall'attributo `messageSource` nella traccia del log dei messaggi.|
|![Traccia messaggio ricevuto](./media/de4f586c-c5dd-41ec-b1c3-ac56b4dfa35c.gif "de4f586c-c5dd-41ec-b1c3-ac56b4dfa35c")|Traccia messaggio ricevuto: traccia generata quando viene ricevuto un messaggio WCF, se l' `System.ServiceModel` origine di traccia è abilitata a livello di informazioni o dettagliato. Questa traccia è essenziale per la visualizzazione della freccia di correlazione dei messaggi nella visualizzazione del **grafico** delle attività.|
|![Traccia messaggio inviato](./media/558943c4-17cf-4c12-9405-677e995ac387.gif "558943c4-17cf-4c12-9405-677e995ac387")|Trace inviato al messaggio: traccia generata quando viene inviato un messaggio WCF se l' `System.ServiceModel` origine di traccia è abilitata a livello di informazioni o dettagliato. Questa traccia è essenziale per la visualizzazione della freccia di correlazione dei messaggi nella visualizzazione del **grafico** delle attività.|

### <a name="activities"></a>attività

|Icona|Descrizione|
|----------|-----------------|
|![Attività](./media/wcfc-defaultactivityc.gif "wcfc_defaultActivityc")|Attività: indica che l'attività corrente è un'attività generica.|
|![Attività radice](./media/5dc8e0eb-1c32-4076-8c66-594935beaee9.gif "5dc8e0eb-1c32-4076-8c66-594935beaee9")|Attività radice: indica l'attività radice di un processo.|

### <a name="wcf-activities"></a>Attività WCF

|Icona|Descrizione|
|----------|-----------------|
|![Attività dell'ambiente](./media/29fa00ac-cf78-46e5-822d-56222fff61d1.gif "29fa00ac-cf78-46e5-822d-56222fff61d1")|Attività ambiente: attività che crea, apre o chiude un host o un client WCF. Gli errori che si sono verificati durante queste fasi verranno visualizzati in questa attività.|
|![Attività di ascolto](./media/d7b135f6-ec7d-45d7-9913-037ab30e4c26.gif "d7b135f6-ec7d-45d7-9913-037ab30e4c26")|Attività Listen: attività che si registra tracce riferita a un listener. In questa attività, si possono visualizzare informazioni e richieste di connessione del listener.|
|![Attività di ricezione byte](./media/2f628580-b80f-45a7-925b-616c96426c0e.gif "2f628580-b80f-45a7-925b-616c96426c0e")|Attività ricezione byte: attività che raduna tutte le tracce relative alla ricezione di byte in ingresso su una connessione tra due endpoint. Questa attività è essenziale nelle correlazioni con le attività del trasporto che propagano l'ID attività, ad esempio http.sys. Errori di connessione, quali interruzioni, verranno visualizzati in questa attività.|
|![Attività Elaborazione messaggio](./media/wcfc-executionactivityiconc.GIF "wcfc_ExecutionActivityIconc")|Attività elabora messaggio: attività che raggruppa le tracce correlate alla creazione di un messaggio WCF. Gli errori causati da envelope errata o da messaggi in formato non valido verranno visualizzati nell'attività. In questa attività, è possibile controllare le intestazioni del messaggio per vedere se un ID attività è stato propagato dal chiamante. In questo caso, quando si passa all’attività di tipo ProcessAction (icona successiva), si può inoltre assegnare a tale attività l'ID attività propagato per la correlazione tra tracce di chiamante e chiamato.|
|![Traccia del log del messaggio](./media/7c66e994-2476-4260-a0db-98948b9af197.gif "7c66e994-2476-4260-a0db-98948b9af197")|Attività elabora azione: un'attività che raggruppa tutte le tracce correlate a una richiesta WCF tra due endpoint. Se `propagateActivity` è impostato su `true` su entrambi gli endpoint della configurazione, tutte le tracce da entrambi gli endpoint vengono incorporate in un'unica attività per correlazione diretta. Tale attività conterrà errori a causa dell’elaborazione nel trasporto o della sicurezza, che si estendono al limite del codice utente e viceversa (se esiste una risposta).|
|![Attività Elaborazione messaggio](./media/wcfc-executionactivityiconc.GIF "wcfc_ExecutionActivityIconc")|Attività Esecuzione del codice utente: attività che raduna le tracce del codice utente per l'elaborazione di una richiesta.|

## <a name="troubleshooting"></a>Risoluzione dei problemi

Se non si dispone delle autorizzazioni necessarie per scrivere nel registro di sistema, viene ricevuto il messaggio di errore seguente: "il Visualizzatore di tracce dei servizi Microsoft non è stato registrato nel sistema" quando si utilizza il `svctraceviewer /register` comando "" per registrare lo strumento. In questo caso è necessario accedere utilizzando un account che abbia accesso in scrittura al Registro di sistema.

Lo strumento Visualizzatore di tracce dei servizi scrive inoltre alcune impostazioni (ad esempio, filtri personalizzati e opzioni di filtro) nel file SvcTraceViewer.exe.settings nella cartella dell'assembly. Se non si dispone dell’autorizzazione in lettura per il file, è comunque possibile avviare lo strumento, ma non è possibile caricare le impostazioni.

Se, aprendo il file con estensione etl, viene visualizzato il messaggio di errore "Si è verificato un errore sconosciuto durante l'elaborazione di una o più tracce" vuole dire che il formato del file con estensione etl non è valido.

Se si apre un registro di traccia creato utilizzando un sistema operativo attivato per la lingua araba, è possibile che il filtro dell'ora non funzioni. Ad esempio, l'anno 2005 corrisponde all’anno 1427 del calendario arabo. L'intervallo di tempo supportato dal filtro dello strumento Visualizzatore di tracce dei servizi, tuttavia, non supporta una data antecedente al 1752. Questo può determinare l'impossibilità di selezionare una data corretta nel filtro. Per risolvere il problema, è possibile creare un filtro personalizzato (**visualizzazione/filtri personalizzati**) utilizzando un'espressione XPath per includere un intervallo di tempo specifico.

## <a name="see-also"></a>Vedere anche

- [Uso del visualizzatore di tracce dei servizi per la visualizzazione di tracce correlate e la risoluzione dei problemi](./diagnostics/tracing/using-service-trace-viewer-for-viewing-correlated-traces-and-troubleshooting.md)
- [Configurazione delle funzionalità di traccia](./diagnostics/tracing/configuring-tracing.md)
- [Traccia end-to-end](./diagnostics/tracing/end-to-end-tracing.md)
