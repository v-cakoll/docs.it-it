---
title: Host servizio WCF (WcfSvcHost.exe)
ms.date: 03/30/2017
ms.assetid: 8643a63d-a357-4c39-bd6c-cdfdf71e370e
ms.openlocfilehash: c000ad3ba53f103cb1a24a9a7fbc71049ba707c7
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 05/04/2018
---
# <a name="wcf-service-host-wcfsvchostexe"></a>Host servizio WCF (WcfSvcHost.exe)
Host del servizio Windows Communication Foundation (WCF) (WcfSvcHost.exe) consente di avviare il debugger di Visual Studio (F5) per ospitare e testare un servizio che è stato implementato automaticamente. È quindi possibile testare il servizio mediante Client di test [!INCLUDE[indigo2](../../../includes/indigo2-md.md)] (WcfTestClient.exe) o un client specifico per trovare e correggere qualsiasi errore potenziale.  
  
## <a name="wcf-service-host"></a>Host servizio WCF  
 Host servizio [!INCLUDE[indigo2](../../../includes/indigo2-md.md)] enumera i servizi in un progetto di servizio [!INCLUDE[indigo2](../../../includes/indigo2-md.md)], carica la configurazione del progetto e crea un'istanza di un host per ciascun servizio che trova. Lo strumento è integrato in Visual Studio tramite il [!INCLUDE[indigo2](../../../includes/indigo2-md.md)] modello di servizio e viene richiamato quando si avvia il debug del progetto.  
  
 Mediante Host servizio [!INCLUDE[indigo2](../../../includes/indigo2-md.md)], è possibile ospitare un servizio [!INCLUDE[indigo2](../../../includes/indigo2-md.md)] (in un progetto della libreria di servizi [!INCLUDE[indigo2](../../../includes/indigo2-md.md)]) senza scrivere codice aggiuntivo o eseguire il commit di un host specifico durante lo sviluppo.  
  
> [!NOTE]
>  L'host del servizio [!INCLUDE[indigo2](../../../includes/indigo2-md.md)] non supporta il trust parziale. Se si desidera utilizzare un [!INCLUDE[indigo2](../../../includes/indigo2-md.md)] servizio in attendibilità parziale, non utilizzare il [!INCLUDE[indigo2](../../../includes/indigo2-md.md)] modello progetto libreria di servizi in Visual Studio per compilare il servizio. Al contrario, creare un nuovo sito Web in Visual Studio, scegliere il [!INCLUDE[indigo2](../../../includes/indigo2-md.md)] modello di sito Web del servizio, che possa ospitare il servizio in un server Web in cui [!INCLUDE[indigo2](../../../includes/indigo2-md.md)] è supportato il Trust parziale.  
  
## <a name="project-types-hosted-by-wcf-service-host"></a>Tipi di progetto ospitati da Host servizio WCF  
 Host servizio [!INCLUDE[indigo2](../../../includes/indigo2-md.md)] può fungere da host per i seguenti tipi di progetto di libreria di servizi [!INCLUDE[indigo2](../../../includes/indigo2-md.md)]: Libreria di servizi [!INCLUDE[indigo2](../../../includes/indigo2-md.md)], Libreria di servizi flusso di lavoro sequenziale, Libreria di servizi flusso di lavoro macchina a stati e Libreria d servizi con pubblicazione via RSS. [!INCLUDE[indigo2](../../../includes/indigo2-md.md)] Host del servizio può ospitare anche i servizi che possono essere aggiunti a un progetto libreria di servizi mediante il **Aggiungi elemento** funzionalità. Questo include Servizio [!INCLUDE[indigo2](../../../includes/indigo2-md.md)], Servizio macchina a stati WF, Servizio sequenziale WF, Servizio macchina a stati WF XAML Servizio sequenziale WF XAML.  
  
 Tuttavia, è necessario notare che lo strumento non consentirà di configurare un host. Per questa attività, è necessario modificare manualmente il file App.config. Lo strumento non convalida nemmeno i file di configurazione definiti dall'utente.  
  
> [!CAUTION]
>  Host servizio [!INCLUDE[indigo2](../../../includes/indigo2-md.md)] non deve essere utilizzato per l'hosting di servizi in un ambiente di produzione in quanto non è stato codificato per questo scopo.  Servizio host [!INCLUDE[indigo2](../../../includes/indigo2-md.md)] non supporta i requisiti di affidabilità, sicurezza e gestibilità di un tale ambiente. Utilizzare invece IIS in quanto fornisce migliori funzionalità di affidabilità e monitoraggio ed è la soluzione preferita per i servizi di hosting. Dopo avere completato lo sviluppo dei servizi, è necessario eseguirne la migrazione dal Servizio host [!INCLUDE[indigo2](../../../includes/indigo2-md.md)] a IIS.  
  
## <a name="scenarios-for-using-wcf-service-host-inside-visual-studio"></a>Scenari per l'utilizzo di Host servizio WCF in Visual Studio  
 Nella tabella seguente sono elencati tutti i parametri in di **argomenti della riga di comando** finestra di dialogo, disponibili facendo clic con il progetto in **Esplora soluzioni** in Visual Studio, selezionando **Le proprietà**, quindi selezionando la **eseguire il Debug** scheda e facendo clic su **Avvia progetto**. Questi parametri sono utili nella configurazione di Host servizio[!INCLUDE[indigo2](../../../includes/indigo2-md.md)].  
  
|Parametro|Significato|  
|---------------|-------------|  
|`/client`|Un parametro facoltativo che specifica il percorso di un file eseguibile da eseguire dopo l'hosting dei servizi. Dopo l'hosting viene avviato il Client test [!INCLUDE[indigo2](../../../includes/indigo2-md.md)].|  
|`/clientArg`|Consente di specificare una stringa come argomento che viene passato all'applicazione client personalizzata.|  
|`/?`|Visualizza il testo della Guida.|  
  
#### <a name="using-wcf-test-client"></a>Utilizzo di Client di test WCF  
 Dopo avere creato un nuovo progetto di servizio [!INCLUDE[indigo2](../../../includes/indigo2-md.md)] e avere premuto F5 per avviare il debugger, Servizio Host [!INCLUDE[indigo2](../../../includes/indigo2-md.md)] avvia l'hosting di tutti i servizi che trova nel progetto. Client di test [!INCLUDE[indigo2](../../../includes/indigo2-md.md)] viene aperto automaticamente e visualizza un elenco degli endpoint di servizio definiti nel file di configurazione. Dalla finestra principale, è possibile testare i parametri e richiamare il servizio.  
  
 Per assicurarsi che [!INCLUDE[indigo2](../../../includes/indigo2-md.md)] Client di Test viene usato pulsante destro del mouse sul progetto in **Esplora soluzioni** in Visual Studio, selezionare **delle proprietà**, quindi selezionare il **Debug**scheda. Fare clic su **Avvia progetto** e assicurarsi che sia visualizzato quanto segue nel **argomenti della riga di comando** finestra di dialogo.  
  
 `/client:WcfTestClient.exe`  
  
#### <a name="using-a-custom-client"></a>Utilizzo di un client personalizzato  
 Per utilizzare un client personalizzato, fare doppio clic su progetto in **Esplora soluzioni** in Visual Studio, selezionare **delle proprietà**, quindi selezionare il **Debug** scheda. Fare clic su **Avvia progetto** e modificare il `/client` parametro il **argomenti della riga di comando** finestra di dialogo in modo da puntare al client personalizzato, come indicato nell'esempio seguente.  
  
 `/client:"path/CustomClient.exe"`  
  
 Quando si preme F5 per avviare nuovamente il servizio, Host servizio [!INCLUDE[indigo2](../../../includes/indigo2-md.md)] avvia automaticamente il client personalizzato quando si avvia il debugger.  
  
 È anche possibile utilizzare il parametro `/clientArg:` per specificare una stringa come argomento passato all'applicazione client personalizzata, come indicato nell'esempio seguente.  
  
 `/client:"path/CustomClient.exe" /clientArg:"arguments that are passed to Client"`  
  
 Ad esempio, se si utilizza il modello Libreria di servizi di diffusione, sarà possibile utilizzare gli argomenti della riga di comando seguenti:  
  
 `/client:iexplore.exe /clientArgs:http://localhost:8731/Design_Time_Addresses/Feed1/`  
  
#### <a name="specifying-no-client"></a>Specifica nessuno client  
 Per specificare che non verrà utilizzato alcun client dopo [!INCLUDE[indigo2](../../../includes/indigo2-md.md)] hosting del servizio pulsante destro del mouse sul progetto in **Esplora soluzioni** in Visual Studio, selezionare **delle proprietà**, quindi selezionare il  **Eseguire il debug** scheda. Fare clic su **Avvia progetto** e lasciare il **argomenti della riga di comando** finestra di dialogo vuoto.  
  
#### <a name="using-a-custom-host"></a>Utilizzo di un host personalizzato  
 Per utilizzare un host personalizzato, fare doppio clic su progetto in **Esplora soluzioni** in Visual Studio, selezionare **delle proprietà**, quindi selezionare il **Debug** scheda. Fare clic su **Avvia programma esterno** e immettere il percorso completo per l'host personalizzato. È inoltre possibile utilizzare il **argomenti della riga di comando** la finestra di dialogo per specificare gli argomenti da passare all'host.  
  
## <a name="wcf-service-host-user-interface"></a>Interfaccia utente dell'Host servizio WCF  
 Quando si richiama inizialmente [!INCLUDE[indigo2](../../../includes/indigo2-md.md)] Host del servizio (premendo F5 in Visual Studio), il **Host servizio WCF** finestra verrà aperta automaticamente. Quando Host servizio [!INCLUDE[indigo2](../../../includes/indigo2-md.md)] è in esecuzione, nell'area della notifica viene visualizzata l'icona del programma. Fare doppio clic sul pulsante per aprire la **Host servizio WCF** finestra  
  
 Quando si verificano gli errori durante l'hosting del servizio, verrà aperta la finestra Host servizio [!INCLUDE[indigo2](../../../includes/indigo2-md.md)] per visualizzare informazioni rilevanti.  
  
 Il **Host servizio WCF** finestra principale contiene due menu:  
  
-   **File**: contiene il **Chiudi** e **Exit** comandi. Quando fa clic su **Chiudi**, **Host servizio WCF** chiude la finestra di dialogo, ma i servizi continuano a essere ospitati. Quando fa clic su **uscita**, [!INCLUDE[indigo2](../../../includes/indigo2-md.md)] chiuso anche Host servizio. Questo arresta anche tutti i servizi in hosting.  
  
-   **Guida in linea**: contiene il **sulle** comando che contiene informazioni sulla versione. Contiene inoltre il **Guida** comando che è possibile aprire un file della Guida.  
  
 Il principale **Host servizio WCF** finestra contiene due aree:  
  
-   La prima area è **servizio**. Contiene un elenco che visualizza informazioni di base su tutti i servizi. Le informazioni includono:  
  
    -   **Servizio**: Elenca tutti i servizi.  
  
    -   **Stato**: elenca lo stato del servizio. I valori validi sono "Avviato", "Stopped" e "Error".  
  
    -   **Indirizzo dei metadati**: Visualizza l'indirizzo dei metadati dei servizi.  
  
-   La seconda area è **informazioni aggiuntive**. Visualizza una spiegazione dettagliata dello stato del servizio quando è selezionata la riga del servizio specifica nel **servizio** area. Se lo stato è Errore, è possibile visualizzare il messaggio di errore completo sullo schermo.  
  
## <a name="stopping-wcf-service-host"></a>Interruzione dell'Host servizio WCF  
 È possibile arrestare Host servizio [!INCLUDE[indigo2](../../../includes/indigo2-md.md)] nei quattro modi seguenti:  
  
-   Arrestare la sessione di debug in Visual Studio.  
  
-   Selezionare **uscita** dal **File** dal menu di **Host servizio WCF** finestra.  
  
-   Selezionare **uscita** dal menu di scelta rapida di [!INCLUDE[indigo2](../../../includes/indigo2-md.md)] icona Host del servizio nell'area di notifica di sistema.  
  
-   Uscire da Client di test [!INCLUDE[indigo2](../../../includes/indigo2-md.md)] se è utilizzato.  
  
## <a name="using-service-host-without-administrator-privilege"></a>Utilizzo di Host servizio senza privilegio di amministratore  
 Per consentire agli utenti senza privilegio di amministratore di sviluppare [!INCLUDE[indigo2](../../../includes/indigo2-md.md)] services, viene creato un ACL (Access Control List) per lo spazio dei nomi "http://+:8731/Design_Time_Addresses" durante l'installazione di Visual Studio. L'ACL viene impostato su (UI) che include tutti gli utenti interattivi che hanno eseguito l'accesso al computer. Gli amministratori possono aggiungere o rimuovere utenti da questo ACL oppure aprire porte aggiuntive. Questo ACL consente agli utenti di utilizzare Host automatico servizio [!INCLUDE[indigo2](../../../includes/indigo2-md.md)] (wcfSvcHost.exe) senza disporre dei privilegi di amministratore.  
  
 È anche possibile modificare l'accesso utilizzando lo strumento netsh.exe in [!INCLUDE[wv](../../../includes/wv-md.md)] con l'account di amministratore con privilegi elevati. Di seguito è riportato un esempio dell'utilizzo di netsh.exe.  
  
```  
netsh http add urlacl url=http://+:8001/MyService user=<domain>\<user>  
```  
  
 Per ulteriori informazioni su netsh.exe, vedere "[sull'utilizzo dello strumento Netsh.exe e parametri della riga di comando](http://go.microsoft.com/fwlink/?LinkId=97877)".  
  
## <a name="see-also"></a>Vedere anche  
 [Client di prova WCF (WcfTestClient.exe)](../../../docs/framework/wcf/wcf-test-client-wcftestclient-exe.md)
