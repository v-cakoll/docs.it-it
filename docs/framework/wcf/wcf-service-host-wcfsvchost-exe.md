---
title: Host servizio WCF (WcfSvcHost.exe)
ms.date: 03/30/2017
ms.assetid: 8643a63d-a357-4c39-bd6c-cdfdf71e370e
ms.openlocfilehash: e1e258015adc34edd4a109f3bc5a32b4bf6f0296
ms.sourcegitcommit: 15109844229ade1c6449f48f3834db1b26907824
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 05/07/2018
---
# <a name="wcf-service-host-wcfsvchostexe"></a>Host servizio WCF (WcfSvcHost.exe)
Host del servizio Windows Communication Foundation (WCF) (WcfSvcHost.exe) consente di avviare il debugger di Visual Studio (F5) per ospitare e testare un servizio che è stato implementato automaticamente. È quindi possibile testare il servizio mediante Client di prova WCF (WcfTestClient.exe) o un client specifico, per individuare e correggere qualsiasi errore potenziale.  
  
## <a name="wcf-service-host"></a>Host servizio WCF  
 Host servizio WCF enumera i servizi in un progetto di servizio WCF, carica la configurazione del progetto e crea un'istanza di un host per ogni servizio che trova. Lo strumento è integrato in Visual Studio tramite il modello di servizio WCF e viene richiamato quando si avvia il debug del progetto.  
  
 Mediante Host servizio WCF, è possibile ospitare un servizio WCF (in un progetto di libreria di servizi WCF) senza scrivere codice aggiuntivo o eseguire il commit di un host specifico durante lo sviluppo.  
  
> [!NOTE]
>  Host servizio WCF non supporta il Trust parziale. Se si desidera utilizzare un servizio WCF in attendibilità parziale, non utilizzare il modello di progetto libreria di servizi WCF in Visual Studio per compilare il servizio. Al contrario, creare un nuovo sito Web in Visual Studio scegliendo il modello sito Web del servizio WCF, che possa ospitare il servizio in un server Web in cui è supportato il Trust parziale di WCF.  
  
## <a name="project-types-hosted-by-wcf-service-host"></a>Tipi di progetto ospitati da Host servizio WCF  
 Host servizio WCF può ospitare i seguenti tipi di progetto di libreria del servizio WCF: libreria di servizi WCF, libreria di servizi flusso di lavoro sequenziale, libreria del servizio del flusso di lavoro macchina a stati e libreria di servizi di diffusione. Host servizio WCF può ospitare anche i servizi che possono essere aggiunti a un progetto libreria di servizi mediante il **Aggiungi elemento** funzionalità. Questo include servizio WCF, servizio macchina a stati WF, servizio sequenziale WF, servizio macchina a stati WF XAML e servizio sequenziale WF XAML.  
  
 Tuttavia, è necessario notare che lo strumento non consentirà di configurare un host. Per questa attività, è necessario modificare manualmente il file App.config. Lo strumento non convalida nemmeno i file di configurazione definiti dall'utente.  
  
> [!CAUTION]
>  Non è necessario utilizzare Host servizio WCF per ospitare i servizi in un ambiente di produzione, quanto non è stato codificato per questo scopo.  Host servizio WCF non supporta l'affidabilità, sicurezza e i requisiti di gestibilità di un tale ambiente. Utilizzare invece IIS in quanto fornisce migliori funzionalità di affidabilità e monitoraggio ed è la soluzione preferita per i servizi di hosting. Una volta completato lo sviluppo dei servizi, è necessario eseguire la migrazione di servizi dall'Host del servizio WCF in IIS.  
  
## <a name="scenarios-for-using-wcf-service-host-inside-visual-studio"></a>Scenari per l'utilizzo di Host servizio WCF in Visual Studio  
 Nella tabella seguente sono elencati tutti i parametri in di **argomenti della riga di comando** finestra di dialogo, disponibili facendo clic con il progetto in **Esplora soluzioni** in Visual Studio, selezionando **Le proprietà**, quindi selezionando la **eseguire il Debug** scheda e facendo clic su **Avvia progetto**. Questi parametri sono utili nella configurazione Host servizio WCF.  
  
|Parametro|Significato|  
|---------------|-------------|  
|`/client`|Un parametro facoltativo che specifica il percorso di un file eseguibile da eseguire dopo l'hosting dei servizi. Verrà avviato il Client di prova WCF dopo l'hosting.|  
|`/clientArg`|Consente di specificare una stringa come argomento che viene passato all'applicazione client personalizzata.|  
|`/?`|Visualizza il testo della Guida.|  
  
#### <a name="using-wcf-test-client"></a>Utilizzo di Client di test WCF  
 Dopo aver creato un nuovo progetto di servizio WCF e premere F5 per avviare il debugger, Host servizio WCF avvia l'hosting di tutti i servizi che trova nel progetto. Client di prova WCF apre automaticamente e visualizza un elenco di endpoint servizio definiti nel file di configurazione. Dalla finestra principale, è possibile testare i parametri e richiamare il servizio.  
  
 Per verificare che venga utilizzato Client di prova WCF, destro del mouse sul progetto in **Esplora soluzioni** in Visual Studio, selezionare **delle proprietà**, quindi selezionare il **Debug** scheda. Fare clic su **Avvia progetto** e assicurarsi che sia visualizzato quanto segue nel **argomenti della riga di comando** finestra di dialogo.  
  
 `/client:WcfTestClient.exe`  
  
#### <a name="using-a-custom-client"></a>Utilizzo di un client personalizzato  
 Per utilizzare un client personalizzato, fare doppio clic su progetto in **Esplora soluzioni** in Visual Studio, selezionare **delle proprietà**, quindi selezionare il **Debug** scheda. Fare clic su **Avvia progetto** e modificare il `/client` parametro il **argomenti della riga di comando** finestra di dialogo in modo da puntare al client personalizzato, come indicato nell'esempio seguente.  
  
 `/client:"path/CustomClient.exe"`  
  
 Quando si preme F5 per avviare nuovamente il servizio, Host servizio WCF avvia automaticamente il client personalizzato quando si avvia il debugger.  
  
 È anche possibile utilizzare il parametro `/clientArg:` per specificare una stringa come argomento passato all'applicazione client personalizzata, come indicato nell'esempio seguente.  
  
 `/client:"path/CustomClient.exe" /clientArg:"arguments that are passed to Client"`  
  
 Ad esempio, se si utilizza il modello Libreria di servizi di diffusione, sarà possibile utilizzare gli argomenti della riga di comando seguenti:  
  
 `/client:iexplore.exe /clientArgs:http://localhost:8731/Design_Time_Addresses/Feed1/`  
  
#### <a name="specifying-no-client"></a>Specifica nessuno client  
 Per specificare che verrà utilizzato alcun client dopo l'hosting dei servizi WCF, destro del mouse sul progetto in **Esplora soluzioni** in Visual Studio, selezionare **delle proprietà**, quindi selezionare il **Debug** scheda. Fare clic su **Avvia progetto** e lasciare il **argomenti della riga di comando** finestra di dialogo vuoto.  
  
#### <a name="using-a-custom-host"></a>Utilizzo di un host personalizzato  
 Per utilizzare un host personalizzato, fare doppio clic su progetto in **Esplora soluzioni** in Visual Studio, selezionare **delle proprietà**, quindi selezionare il **Debug** scheda. Fare clic su **Avvia programma esterno** e immettere il percorso completo per l'host personalizzato. È inoltre possibile utilizzare il **argomenti della riga di comando** la finestra di dialogo per specificare gli argomenti da passare all'host.  
  
## <a name="wcf-service-host-user-interface"></a>Interfaccia utente dell'Host servizio WCF  
 Quando si richiama inizialmente Host servizio WCF (premendo F5 in Visual Studio), il **Host servizio WCF** finestra verrà aperta automaticamente. Quando Host servizio WCF è in esecuzione, l'icona del programma viene visualizzato nell'area di notifica. Fare doppio clic sul pulsante per aprire la **Host servizio WCF** finestra  
  
 Quando si verificano errori durante l'hosting del servizio, verrà aperta la finestra Host servizio WCF per visualizzare informazioni rilevanti.  
  
 Il **Host servizio WCF** finestra principale contiene due menu:  
  
-   **File**: contiene il **Chiudi** e **Exit** comandi. Quando fa clic su **Chiudi**, **Host servizio WCF** chiude la finestra di dialogo, ma i servizi continuano a essere ospitati. Quando fa clic su **uscita**, chiuso anche Host servizio WCF. Questo arresta anche tutti i servizi in hosting.  
  
-   **Guida in linea**: contiene il **sulle** comando che contiene informazioni sulla versione. Contiene inoltre il **Guida** comando che è possibile aprire un file della Guida.  
  
 Il principale **Host servizio WCF** finestra contiene due aree:  
  
-   La prima area è **servizio**. Contiene un elenco che visualizza informazioni di base su tutti i servizi. Le informazioni includono:  
  
    -   **Servizio**: Elenca tutti i servizi.  
  
    -   **Stato**: elenca lo stato del servizio. I valori validi sono "Avviato", "Stopped" e "Error".  
  
    -   **Indirizzo dei metadati**: Visualizza l'indirizzo dei metadati dei servizi.  
  
-   La seconda area è **informazioni aggiuntive**. Visualizza una spiegazione dettagliata dello stato del servizio quando è selezionata la riga del servizio specifica nel **servizio** area. Se lo stato è Errore, è possibile visualizzare il messaggio di errore completo sullo schermo.  
  
## <a name="stopping-wcf-service-host"></a>Interruzione dell'Host servizio WCF  
 È possibile arrestare Host servizio WCF in quattro modi seguenti:  
  
-   Arrestare la sessione di debug in Visual Studio.  
  
-   Selezionare **uscita** dal **File** dal menu di **Host servizio WCF** finestra.  
  
-   Selezionare **uscita** dal menu di scelta rapida dell'icona della barra delle applicazioni Host servizio WCF nell'area di notifica del sistema.  
  
-   Se è in uso, uscire dal Client di prova WCF.  
  
## <a name="using-service-host-without-administrator-privilege"></a>Utilizzo di Host servizio senza privilegio di amministratore  
 Per consentire agli utenti senza privilegio di amministratore di sviluppare servizi WCF, viene creato un ACL (Access Control List) per lo spazio dei nomi "http://+:8731/Design_Time_Addresses" durante l'installazione di Visual Studio. L'ACL viene impostato su (UI) che include tutti gli utenti interattivi che hanno eseguito l'accesso al computer. Gli amministratori possono aggiungere o rimuovere utenti da questo ACL oppure aprire porte aggiuntive. Questo ACL consente agli utenti di utilizzare Host automatico del servizio WCF (wcfSvcHost.exe) senza concedere loro privilegi di amministratore.  
  
 È anche possibile modificare l'accesso utilizzando lo strumento netsh.exe in [!INCLUDE[wv](../../../includes/wv-md.md)] con l'account di amministratore con privilegi elevati. Di seguito è riportato un esempio dell'utilizzo di netsh.exe.  
  
```  
netsh http add urlacl url=http://+:8001/MyService user=<domain>\<user>  
```  
  
 Per ulteriori informazioni su netsh.exe, vedere "[sull'utilizzo dello strumento Netsh.exe e parametri della riga di comando](http://go.microsoft.com/fwlink/?LinkId=97877)".  
  
## <a name="see-also"></a>Vedere anche  
 [Client di prova WCF (WcfTestClient.exe)](../../../docs/framework/wcf/wcf-test-client-wcftestclient-exe.md)
