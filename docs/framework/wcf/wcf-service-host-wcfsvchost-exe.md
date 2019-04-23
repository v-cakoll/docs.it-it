---
title: Host servizio WCF (WcfSvcHost.exe)
ms.date: 03/30/2017
ms.assetid: 8643a63d-a357-4c39-bd6c-cdfdf71e370e
ms.openlocfilehash: d9a086b3a6ae0ece3b1b45161402ce058e1fb447
ms.sourcegitcommit: 0be8a279af6d8a43e03141e349d3efd5d35f8767
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 04/18/2019
ms.locfileid: "59193018"
---
# <a name="wcf-service-host-wcfsvchostexe"></a>Host servizio WCF (WcfSvcHost.exe)
Host del servizio Windows Communication Foundation (WCF) (WcfSvcHost.exe) consente di avviare il debugger di Visual Studio (F5) per ospitare e testare un servizio che è stato implementato automaticamente. È quindi possibile testare il servizio mediante Client di prova WCF (WcfTestClient.exe) o un client specifico per individuare e correggere qualsiasi errore potenziale.  
  
## <a name="wcf-service-host"></a>Host servizio WCF  
 Host servizio WCF enumera i servizi in un progetto di servizio WCF, carica la configurazione del progetto e crea un'istanza di un host per ogni servizio che trova. Lo strumento è integrato in Visual Studio tramite il modello di servizio WCF e viene richiamato quando si avvia il debug del progetto.  
  
 Mediante Host servizio WCF, è possibile ospitare un servizio WCF (in un progetto di libreria di servizi WCF) senza scrivere codice aggiuntivo o eseguire il commit a un host specifico durante lo sviluppo.  
  
> [!NOTE]
>  Host servizio WCF non supporta parzialmente attendibile. Se si desidera utilizzare un servizio WCF in attendibilità parziale, non utilizzare il modello di progetto libreria di servizi WCF in Visual Studio per compilare il servizio. In alternativa, è possibile creare un nuovo sito Web in Visual Studio scegliendo il modello sito Web del servizio WCF, che possa ospitare il servizio in un server Web in cui è supportato il Trust parziale di WCF.  
  
## <a name="project-types-hosted-by-wcf-service-host"></a>Tipi di progetto ospitati da Host servizio WCF  
 Host servizio WCF può ospitare i seguenti tipi di progetto di libreria del servizio WCF: WCF Service Library, libreria di servizi flusso di lavoro sequenziale, libreria di servizio del flusso di lavoro macchina a stati e libreria di servizi di diffusione. Host servizio WCF può inoltre ospitare i servizi che possono essere aggiunti a un progetto libreria di servizio usando il **Aggiungi elemento** funzionalità. Questo include servizio WCF, servizio macchina a stati WF, servizio sequenziale WF, servizio macchina a stati WF XAML e servizio sequenziale WF XAML.  
  
 Tuttavia, è necessario notare che lo strumento non consentirà di configurare un host. Per questa attività, è necessario modificare manualmente il file App.config. Lo strumento non convalida nemmeno i file di configurazione definiti dall'utente.  
  
> [!CAUTION]
>  Non utilizzare Host del servizio WCF per ospitare i servizi in un ambiente di produzione, perché non è stato progettato per questo scopo.  Host servizio WCF non supporta l'affidabilità, sicurezza e i requisiti di gestibilità di un tale ambiente. Utilizzare invece IIS in quanto fornisce migliori funzionalità di affidabilità e monitoraggio ed è la soluzione preferita per i servizi di hosting. Una volta completato lo sviluppo dei servizi, è necessario eseguire la migrazione di servizi dall'Host del servizio WCF in IIS.  
  
## <a name="scenarios-for-using-wcf-service-host-inside-visual-studio"></a>Scenari per l'utilizzo di Host servizio WCF in Visual Studio  
 Nella tabella seguente elenca tutti i parametri in di **argomenti della riga di comando** finestra di dialogo, che può essere recuperata facendo clic con il progetto in **Esplora soluzioni** in Visual Studio, selezionando **Delle proprietà**, quindi selezionando il **eseguire il Debug** scheda e facendo clic su **Avvia progetto**. Questi parametri sono utili per la configurazione di Host servizio WCF.  
  
|Parametro|Significato|  
|---------------|-------------|  
|`/client`|Un parametro facoltativo che specifica il percorso di un file eseguibile da eseguire dopo l'hosting dei servizi. Client di prova WCF viene avviata dopo l'hosting.|  
|`/clientArg`|Consente di specificare una stringa come argomento che viene passato all'applicazione client personalizzata.|  
|`/?`|Visualizza il testo della Guida.|  
  
#### <a name="using-wcf-test-client"></a>Utilizzo di Client di test WCF  
 Dopo aver creato un nuovo progetto di servizio WCF e premere F5 per avviare il debugger, Host servizio WCF avvia tutti i servizi che trova nel progetto di hosting. Client di prova WCF viene aperto automaticamente e visualizza un elenco di endpoint di servizio definiti nel file di configurazione. Dalla finestra principale, è possibile testare i parametri e richiamare il servizio.  
  
 Per assicurarsi che il Client di prova WCF viene utilizzato, pulsante destro del mouse sul progetto in **Esplora soluzioni** in Visual Studio, selezionare **delle proprietà**, quindi selezionare il **Debug** scheda. Fare clic su **Avvia progetto** e assicurarsi che verrà visualizzato quanto segue nel **argomenti della riga di comando** nella finestra di dialogo.  
  
 `/client:WcfTestClient.exe`  
  
#### <a name="using-a-custom-client"></a>Utilizzo di un client personalizzato  
 Per usare un client personalizzato, pulsante destro del mouse sul progetto in **Esplora soluzioni** in Visual Studio, selezionare **delle proprietà**, quindi selezionare il **Debug** scheda. Fare clic su **Avvia progetto** e modificare il `/client` parametri nel **argomenti della riga di comando** finestra di dialogo in modo da puntare al client personalizzato, come indicato nell'esempio seguente.  
  
 `/client:"path/CustomClient.exe"`  
  
 Quando si preme F5 per avviare nuovamente il servizio, Host servizio WCF avvia automaticamente il client personalizzato quando si avvia il debugger.  
  
 È anche possibile utilizzare il parametro `/clientArg:` per specificare una stringa come argomento passato all'applicazione client personalizzata, come indicato nell'esempio seguente.  
  
 `/client:"path/CustomClient.exe" /clientArg:"arguments that are passed to Client"`  
  
 Ad esempio, se si utilizza il modello Libreria di servizi di diffusione, sarà possibile utilizzare gli argomenti della riga di comando seguenti:  
  
 `/client:iexplore.exe /clientArgs:http://localhost:8731/Design_Time_Addresses/Feed1/`  
  
#### <a name="specifying-no-client"></a>Specifica nessuno client  
 Per specificare che non verrà utilizzato alcun client dopo l'hosting dei servizi WCF, pulsante destro del mouse sul progetto in **Esplora soluzioni** in Visual Studio, selezionare **delle proprietà**, quindi selezionare il **Debug** scheda. Fare clic su **Avvia progetto** e lasciare il **argomenti della riga di comando** nella finestra di dialogo vuota.  
  
#### <a name="using-a-custom-host"></a>Utilizzo di un host personalizzato  
 Per utilizzare un host personalizzato, pulsante destro del mouse sul progetto in **Esplora soluzioni** in Visual Studio, selezionare **delle proprietà**, quindi selezionare il **Debug** scheda. Fare clic su **Avvia programma esterno** e immettere il percorso completo dell'host personalizzato. È anche possibile usare la **argomenti della riga di comando** finestra di dialogo per specificare gli argomenti da passare all'host.  
  
## <a name="wcf-service-host-user-interface"></a>Interfaccia utente dell'Host servizio WCF  
 Quando si richiama inizialmente Host servizio WCF (premendo F5 in Visual Studio), il **Host servizio WCF** finestra viene aperto automaticamente. Quando Host servizio WCF è in esecuzione, l'icona del programma viene visualizzato nell'area di notifica. Fare doppio clic sull'icona per aprire la **Host servizio WCF** finestra  
  
 Quando si verificano errori durante l'hosting del servizio, verrà aperta la finestra di dialogo Host servizio WCF per visualizzare informazioni rilevanti.  
  
 Il **Host servizio WCF** finestra principale contiene due menu:  
  
-   **File**: Contiene il **Close** e **uscita** comandi. Quando fa clic su **Close**, il **Host servizio WCF** chiude la finestra di dialogo, ma i servizi continuano a essere ospitati. Quando fa clic su **Exit**, Host servizio WCF viene anche arrestato. Questo arresta anche tutti i servizi in hosting.  
  
-   **Guida in linea**: Contiene il **sulle** comando che contiene informazioni sulla versione. Contiene anche il **aiutare** comando che è possibile aprire un file della Guida.  
  
 Principale **Host servizio WCF** finestra contiene due aree:  
  
-   La prima è quella **servizio**. Contiene un elenco che visualizza informazioni di base su tutti i servizi. Le informazioni includono:  
  
    -   **Servizio**: Elenca tutti i servizi.  
  
    -   **stato**: Elenca lo stato del servizio. I valori validi sono "Avviato", "Stopped" e "Error".  
  
    -   **Indirizzo dei metadati**: Consente di visualizzare l'indirizzo dei metadati dei servizi.  
  
-   La seconda area è **informazioni aggiuntive**. Visualizza una spiegazione dettagliata dello stato del servizio quando viene selezionata la riga del servizio specifica nel **servizio** area. Se lo stato è Errore, è possibile visualizzare il messaggio di errore completo sullo schermo.  
  
## <a name="stopping-wcf-service-host"></a>Interruzione dell'Host servizio WCF  
 È possibile arrestare Host servizio WCF in quattro modi seguenti:  
  
-   Arrestare la sessione di debug in Visual Studio.  
  
-   Selezionare **Exit** dalle **File** dal menu il **Host servizio WCF** finestra.  
  
-   Selezionare **Exit** dal menu di scelta rapida dell'icona sulla barra delle applicazioni Host dei servizi WCF nell'area di notifica del sistema.  
  
-   Se è in uso, uscire dal Client di prova WCF.  
  
## <a name="using-service-host-without-administrator-privilege"></a>Utilizzo di Host servizio senza privilegio di amministratore  
 Per abilitare gli utenti senza privilegi di amministratore per lo sviluppo di servizi WCF, viene creato un ACL (Access Control List) per lo spazio dei nomi "http://+:8731/Design_Time_Addresses" durante l'installazione di Visual Studio. L'ACL viene impostato su (UI) che include tutti gli utenti interattivi che hanno eseguito l'accesso al computer. Gli amministratori possono aggiungere o rimuovere utenti da questo ACL oppure aprire porte aggiuntive. Questo ACL consente agli utenti di utilizzare Host automatico del servizio WCF (wcfSvcHost.exe) senza concedere loro privilegi di amministratore.  
  
 È anche possibile modificare l'accesso utilizzando lo strumento netsh.exe in [!INCLUDE[wv](../../../includes/wv-md.md)] con l'account di amministratore con privilegi elevati. Di seguito è riportato un esempio dell'utilizzo di netsh.exe.  
  
```  
netsh http add urlacl url=http://+:8001/MyService user=<domain>\<user>  
```  
  
 Per altre informazioni su netsh.exe, vedere "[come usare lo strumento di Netsh.exe e opzioni della riga di comando](https://go.microsoft.com/fwlink/?LinkId=97877)".  
  
## <a name="see-also"></a>Vedere anche

- [Client di prova WCF (WcfTestClient.exe)](../../../docs/framework/wcf/wcf-test-client-wcftestclient-exe.md)
